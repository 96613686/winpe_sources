# KerbCreateUnicodeStringFromBlob(uchar *,ulong,_UNICODE_STRING *,uchar)

- ea: `0x1800757e0`
- end: `0x18007593b`
- name: `?KerbCreateUnicodeStringFromBlob@@YAJPEAEKPEAU_UNICODE_STRING@@E@Z`
- size: `347`
- prototype: `int(unsigned __int8 *, unsigned int, struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180053070`
- `0x1800534a0`
- `0x180075984`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x180003980`
- `0x18005a060`
- `0x1800757e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800758a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800758ed`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800758a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800758ed`
- `ntdll!RtlInitUnicodeString` at `0x18007590a`
- `ntdll!RtlInitUnicodeString` at `0x18007590a`

## pseudocode

```c

```
