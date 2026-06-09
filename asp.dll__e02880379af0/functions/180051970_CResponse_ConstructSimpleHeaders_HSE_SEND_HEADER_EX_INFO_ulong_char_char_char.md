# CResponse::ConstructSimpleHeaders(_HSE_SEND_HEADER_EX_INFO *,ulong,char *,char *,char *)

- ea: `0x180051970`
- end: `0x180051b4b`
- name: `?ConstructSimpleHeaders@CResponse@@SAJPEAU_HSE_SEND_HEADER_EX_INFO@@KPEAD11@Z`
- size: `475`
- prototype: `static int(struct _HSE_SEND_HEADER_EX_INFO *, unsigned int, char *, char *, char *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180052ab0`
- `0x180052cb0`
- `0x18005316c`

## callees

- `0x18001894c`
- `0x180023dd0`
- `0x180051970`
- `0x180061c2c`

## import_xrefs

- `msvcrt!_ltoa` at `0x180051a0b`
- `msvcrt!_ltoa` at `0x180051a0b`
- `KERNEL32!HeapAlloc` at `0x180051a4c`
- `KERNEL32!HeapAlloc` at `0x180051a4c`

## string_xrefs

- `0x180051ab0`: `Cache-control: private\n`

## pseudocode

```c

```
