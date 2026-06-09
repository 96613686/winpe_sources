# WSManHttpListenerRequest::ProcessAuthorization(char const *,ushort,WSManHttpListenerConnection *)

- ea: `0x180058e84`
- end: `0x180059365`
- name: `?ProcessAuthorization@WSManHttpListenerRequest@@AEAAXPEBDGPEAVWSManHttpListenerConnection@@@Z`
- size: `1249`
- prototype: `void(WSManHttpListenerRequest *__hidden this, const char *, unsigned __int16, struct WSManHttpListenerConnection *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180054c30`

## callees

- `0x180005d10`
- `0x1800224f0`
- `0x180058e84`
- `0x18005936c`
- `0x180059ec0`
- `0x18005b250`
- `0x18008d16c`
- `0x18008e040`
- `0x180112380`
- `0x18011a6d4`
- `0x18016e190`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18005902b`
- `msvcrt!_strnicmp` at `0x180059070`
- `msvcrt!_strnicmp` at `0x1800590d1`
- `msvcrt!_strnicmp` at `0x18005919d`
- `msvcrt!_strnicmp` at `0x180059266`
- `msvcrt!_strnicmp` at `0x18005902b`
- `msvcrt!_strnicmp` at `0x180059070`
- `msvcrt!_strnicmp` at `0x1800590d1`
- `msvcrt!_strnicmp` at `0x18005919d`
- `msvcrt!_strnicmp` at `0x180059266`

## string_xrefs

- `0x180058fa8`: `Failed to retrieve server configuration settings`
- `0x180058f68`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c

```
