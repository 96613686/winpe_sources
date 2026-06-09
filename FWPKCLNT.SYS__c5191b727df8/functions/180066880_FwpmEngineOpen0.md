# FwpmEngineOpen0

- ea: `0x180066880`
- end: `0x1800668f4`
- name: `FwpmEngineOpen0`
- size: `116`
- prototype: `NTSTATUS __stdcall(const wchar_t *serverName, UINT32 authnService, SEC_WINNT_AUTH_IDENTITY_W *authIdentity, const FWPM_SESSION0 *session, HANDLE *engineHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800050cc`
- `0x180008f10`
- `0x180066880`
- `0x1800668fc`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180066894`
- `ntoskrnl!KeGetCurrentIrql` at `0x180066894`

## string_xrefs

- `0x1800668de`: `FwpmEngineOpen0`

## pseudocode

```c

```
