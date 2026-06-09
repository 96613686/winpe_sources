# GetFeatureStateEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort const *,tagINSTALLSTATE *)

- ea: `0x1800e2658`
- end: `0x1800e298c`
- name: `?GetFeatureStateEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@0PEAW4tagINSTALLSTATE@@@Z`
- size: `820`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, enum tagMSIINSTALLCONTEXT, const unsigned __int16 *, enum tagINSTALLSTATE *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800e2530`
- `0x18019f780`

## callees

- `0x180014848`
- `0x180017a84`
- `0x180020d40`
- `0x1800250d4`
- `0x180025a18`
- `0x18004b560`
- `0x18005a4f0`
- `0x180064a78`
- `0x18008eac8`
- `0x1800e2658`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800e27f2`
- `KERNEL32!GlobalFree` at `0x1800e280b`
- `KERNEL32!GlobalFree` at `0x1800e2827`
- `KERNEL32!GlobalFree` at `0x1800e2847`
- `KERNEL32!GlobalFree` at `0x1800e285e`
- `KERNEL32!GlobalFree` at `0x1800e287a`
- `KERNEL32!GlobalFree` at `0x1800e27f2`
- `KERNEL32!GlobalFree` at `0x1800e280b`
- `KERNEL32!GlobalFree` at `0x1800e2827`
- `KERNEL32!GlobalFree` at `0x1800e2847`
- `KERNEL32!GlobalFree` at `0x1800e285e`
- `KERNEL32!GlobalFree` at `0x1800e287a`
- `USER32!CharUpperW` at `0x1800e270d`
- `USER32!CharUpperW` at `0x1800e270d`

## string_xrefs

- `0x1800e27b4`: `Failed to get the current user SID with error code=%d`

## pseudocode

```c

```
