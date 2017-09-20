FROM telegraf:1.4-alpine

COPY . /

RUN apk add --no-cache --update --virtual .build-deps curl && \
    apk add --no-cache --update jq \
    # This will come back once the kuberentes plugin is release in November
    && curl -fsSL -o /usr/bin/envtpl https://github.com/arschles/envtpl/releases/download/0.2.3/envtpl_linux_amd64 \
  	&& chmod +x /usr/bin/envtpl \
    && curl -fsSL -o /usr/bin/jq https://github.com/stedolan/jq/releases/download/jq-1.5/jq-linux64 \
    && chmod +x /usr/bin/jq

CMD ["/start-telegraf"]
