# Patched micronaut-http-client 4.10.28

`micronaut-http-client-4.10.28` with the WebSocket proxy fix
(micronaut-projects/micronaut-core#14446, PR #14447): the WebSocket client now adds the
configured HTTP/SOCKS proxy handler, so `micronaut.http.client.proxy-*` applies to the
agent's WebSocket connection.

Built from the `v4.10.28` tag plus one line in `ConnectionManager.connectForWebsocket`:

    configureProxy(ch.pipeline(), requestKey.isSecure(), requestKey.getHost(), requestKey.getPort());

Temporary: remove this directory and the `exclusiveContent` block in `build.gradle` once a
Micronaut release includes the fix.
