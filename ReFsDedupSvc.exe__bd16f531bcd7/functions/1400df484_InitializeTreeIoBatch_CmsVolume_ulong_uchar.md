# InitializeTreeIoBatch(CmsVolume *,ulong,uchar)

- ea: `0x1400df484`
- end: `0x1400df623`
- name: `?InitializeTreeIoBatch@@YAPEAU_SmsIoBatch@@PEAVCmsVolume@@KE@Z`
- size: `415`
- prototype: `struct _SmsIoBatch *__fastcall(struct CmsVolume *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400e31b4`

## callees

- `0x140004f44`
- `0x1400057f8`
- `0x140085a3c`
- `0x1400df484`
- `0x1400e1368`
- `0x1400f360c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400df4d6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400df4d6`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400df513`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400df513`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400df521`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400df521`

## pseudocode

```c

```
