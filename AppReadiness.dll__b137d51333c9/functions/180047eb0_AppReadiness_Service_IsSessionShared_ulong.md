# AppReadiness::Service::IsSessionShared(ulong)

- ea: `0x180047eb0`
- end: `0x180047f2e`
- name: `?IsSessionShared@Service@AppReadiness@@SA_NK@Z`
- size: `126`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180035f14`

## callees

- `0x180027a4c`
- `0x18003ecb4`
- `0x180047eb0`

## import_xrefs

- `ntdll!RtlGetSessionProperties` at `0x180047ed5`
- `ntdll!RtlGetSessionProperties` at `0x180047ed5`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180047eb8`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180047eb8`

## string_xrefs

- `0x180047ee2`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180047ef6`: `AppReadiness::Service::IsSessionShared`

## pseudocode

```c

```
