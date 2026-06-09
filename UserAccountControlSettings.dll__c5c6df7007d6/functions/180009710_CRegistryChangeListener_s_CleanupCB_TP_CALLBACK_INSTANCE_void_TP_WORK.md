# CRegistryChangeListener::s_CleanupCB(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180009710`
- end: `0x180009718`
- name: `?s_CleanupCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `8`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PTP_WAIT *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800093b4`

## pseudocode

```c
void __fastcall CRegistryChangeListener::s_CleanupCB(PTP_CALLBACK_INSTANCE Instance, PTP_WAIT *Context, PTP_WORK Work)
{
  CRegistryChangeListener::_CleanupCB(Context);
}

```

## disassembly

```asm
0x180009710  mov     rcx, rdx; this
0x180009713  jmp     ?_CleanupCB@CRegistryChangeListener@@AEAAXXZ; CRegistryChangeListener::_CleanupCB(void)
```
