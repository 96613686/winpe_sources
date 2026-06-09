# CIEAdminBrokerClassFactory::LockServer(int)

- ea: `0x402c80`
- end: `0x402c9d`
- name: `?LockServer@CIEAdminBrokerClassFactory@@UAGJH@Z`
- size: `29`
- prototype: `int __stdcall(CIEAdminBrokerClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x402c80`
- `0x4091c5`
- `0x4091ed`

## pseudocode

```c
int __stdcall CIEAdminBrokerClassFactory::LockServer(CIEAdminBrokerClassFactory *this, int a2)
{
  if ( a2 == 1 )
    IncrementLockCount();
  else
    DecrementLockCount();
  return 0;
}

```

## disassembly

```asm
0x402c80  mov     edi, edi
0x402c82  push    ebp
0x402c83  mov     ebp, esp
0x402c85  cmp     [ebp+arg_4], 1
0x402c89  jnz     short loc_402C92
0x402c8b  call    ?IncrementLockCount@@YGJXZ; IncrementLockCount(void)
0x402c90  jmp     short loc_402C97
0x402c92  call    ?DecrementLockCount@@YGJXZ; DecrementLockCount(void)
0x402c97  xor     eax, eax
0x402c99  pop     ebp
0x402c9a  retn    8
```
