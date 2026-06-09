# SE_GetProcAddressForCaller

- ea: `0x1800112c0`
- end: `0x1800116b6`
- name: `SE_GetProcAddressForCaller`
- size: `1014`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000f114`
- `0x180010fb0`
- `0x1800112c0`
- `0x180011a80`
- `0x18001df70`
- `0x18001f65c`
- `0x180021fe0`
- `0x180035638`
- `0x18005921d`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800114a2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800114a2`
- `ntdll!RtlEnterCriticalSection` at `0x18001135c`
- `ntdll!RtlEnterCriticalSection` at `0x18001135c`
- `ntdll!RtlCaptureStackBackTrace` at `0x180011393`
- `ntdll!RtlCaptureStackBackTrace` at `0x180011393`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011524`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011524`
- `ntdll!RtlReleaseSRWLockShared` at `0x180011551`
- `ntdll!RtlReleaseSRWLockShared` at `0x180011551`

## string_xrefs

- `0x1800113a0`: `Exception capturing backtrace`
- `0x180011610`: `Ignoring hooks for intra-module call from Dll: 0x%p`

## pseudocode

```c

```
