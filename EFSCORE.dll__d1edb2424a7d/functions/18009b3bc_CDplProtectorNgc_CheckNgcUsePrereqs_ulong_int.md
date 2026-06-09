# CDplProtectorNgc::CheckNgcUsePrereqs(ulong *,int *)

- ea: `0x18009b3bc`
- end: `0x18009b5a0`
- name: `?CheckNgcUsePrereqs@CDplProtectorNgc@@KAJPEAKPEAH@Z`
- size: `484`
- prototype: `__int64 __fastcall(unsigned int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ad00`

## callees

- `0x180063698`
- `0x18009b3bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b437`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b4a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b544`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b437`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b4a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009b544`
- `ntdll!RtlIsMultiSessionSku` at `0x18009b3f3`
- `ntdll!RtlIsMultiSessionSku` at `0x18009b4fd`
- `ntdll!RtlIsMultiSessionSku` at `0x18009b3f3`
- `ntdll!RtlIsMultiSessionSku` at `0x18009b4fd`

## string_xrefs

- `0x18009b427`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c

```
