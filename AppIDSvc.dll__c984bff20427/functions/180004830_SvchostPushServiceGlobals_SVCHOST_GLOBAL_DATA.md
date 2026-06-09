# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180004830`
- end: `0x180004838`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `8`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  AiSvcpSvchostSharedGlobals = a1;
}

```

## disassembly

```asm
0x180004830  mov     cs:?AiSvcpSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * AiSvcpSvchostSharedGlobals
0x180004837  retn
```
