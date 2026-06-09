# FveShouldDeferForMdmPolicySync(long (*)(_WNF_STATE_NAME const *,_WNF_TYPE_ID const *,void const *,ulong *,void *,ulong *),long (*)(_UNICODE_STRING *,ulong *,void *,ulong,ulong *),bool *,unsigned __int64 *)

- ea: `0x18006e0f8`
- end: `0x18006e527`
- name: `?FveShouldDeferForMdmPolicySync@@YAJP6AJPEBU_WNF_STATE_NAME@@PEBU_WNF_TYPE_ID@@PEBXPEAKPEAX3@ZP6AJPEAU_UNICODE_STRING@@34K3@ZPEA_NPEA_K@Z`
- size: `1071`
- prototype: `__int64 __fastcall(int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *), int (*)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *), bool *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18006c39c`

## callees

- `0x180001fe8`
- `0x180003608`
- `0x180009f30`
- `0x180009f60`
- `0x180025ed4`
- `0x18002f28c`
- `0x18006e0f8`
- `0x18006fa60`
- `0x18007e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006e1a6`
- `ntdll!RtlInitUnicodeString` at `0x18006e1a6`

## string_xrefs

- `0x18006e19b`: `WorkstationService-DomainJoinEnabled`

## pseudocode

```c

```
