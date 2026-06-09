# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount(void)

- ea: `0x180005520`
- end: `0x180005523`
- name: `?GetObjectCount@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@EEBAKXZ`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800018e8`

## pseudocode

```c
__int64 Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount()
{
  return 0;
}

```

## disassembly

```asm
0x180005520  xor     eax, eax
0x180005522  retn
```
