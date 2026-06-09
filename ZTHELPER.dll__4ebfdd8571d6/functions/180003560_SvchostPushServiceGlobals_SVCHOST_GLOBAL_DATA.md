# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180003560`
- end: `0x180003568`
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
  g_pSvchostData = a1;
}

```

## disassembly

```asm
0x180003560  mov     cs:?g_pSvchostData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * g_pSvchostData
0x180003567  retn
```
