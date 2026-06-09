# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount(void)

- ea: `0x1800057e0`
- end: `0x1800057e3`
- name: `?GetObjectCount@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@EEBAKXZ`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800017bc`

## pseudocode

```c
__int64 Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount()
{
  return 0;
}

```

## disassembly

```asm
0x1800057e0  xor     eax, eax
0x1800057e2  retn
```
