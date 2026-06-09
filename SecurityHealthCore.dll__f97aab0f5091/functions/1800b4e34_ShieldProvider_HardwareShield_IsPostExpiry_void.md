# ShieldProvider::HardwareShield::IsPostExpiry(void)

- ea: `0x1800b4e34`
- end: `0x1800b4ede`
- name: `?IsPostExpiry@HardwareShield@ShieldProvider@@CAHXZ`
- size: `170`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b1558`

## callees

- `0x180004710`
- `0x1800b4e34`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800b4e5a`
- `KERNEL32!GetSystemTime` at `0x1800b4e5a`
- `KERNEL32!SystemTimeToFileTime` at `0x1800b4e8e`
- `KERNEL32!SystemTimeToFileTime` at `0x1800b4e9e`
- `KERNEL32!SystemTimeToFileTime` at `0x1800b4e8e`
- `KERNEL32!SystemTimeToFileTime` at `0x1800b4e9e`
- `KERNEL32!CompareFileTime` at `0x1800b4eb4`
- `KERNEL32!CompareFileTime` at `0x1800b4eb4`

## pseudocode

```c

```
