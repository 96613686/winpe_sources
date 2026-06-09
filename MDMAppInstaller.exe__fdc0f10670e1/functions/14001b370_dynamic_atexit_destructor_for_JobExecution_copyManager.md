# _dynamic_atexit_destructor_for__JobExecution::copyManager__

- ea: `0x14001b370`
- end: `0x14001b37c`
- name: `_dynamic_atexit_destructor_for__JobExecution::copyManager__`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000904c`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__JobExecution::copyManager__()
{
  return ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>((__int64 *)&JobExecution::copyManager);
}

```

## disassembly

```asm
0x14001b370  lea     rcx, ?copyManager@JobExecution@@0V?$CComPtr@UIBackgroundCopyManager@@@ATL@@A; ATL::CComPtr<IBackgroundCopyManager> JobExecution::copyManager
0x14001b377  jmp     ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
```
