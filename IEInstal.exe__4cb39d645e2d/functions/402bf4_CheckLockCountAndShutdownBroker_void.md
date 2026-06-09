# CheckLockCountAndShutdownBroker(void)

- ea: `0x402bf4`
- end: `0x402c12`
- name: `?CheckLockCountAndShutdownBroker@@YGJXZ`
- size: `30`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4091c5`

## callees

- `0x402bbc`

## pseudocode

```c
int __stdcall CheckLockCountAndShutdownBroker()
{
  _InterlockedIncrement(&g_LockCount);
  if ( _InterlockedExchangeAdd(&g_LockCount, 0xFFFFFFFF) )
    return 1;
  else
    return RevokeClassFactory();
}

```

## disassembly

```asm
0x402bf4  mov     edi, edi
0x402bf6  lock inc ?g_LockCount@@3JA; long g_LockCount
0x402bfd  or      eax, 0FFFFFFFFh
0x402c00  lock xadd ?g_LockCount@@3JA, eax; long g_LockCount
0x402c08  jz      ?RevokeClassFactory@@YGJXZ; RevokeClassFactory(void)
0x402c0e  xor     eax, eax
0x402c10  inc     eax
0x402c11  retn
```
