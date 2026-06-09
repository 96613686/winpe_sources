# CIEAdminBrokerClassFactory::AddRef(void)

- ea: `0x402c20`
- end: `0x402c34`
- name: `?AddRef@CIEAdminBrokerClassFactory@@UAGKXZ`
- size: `20`
- prototype: `unsigned int __stdcall(CIEAdminBrokerClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned int __stdcall CIEAdminBrokerClassFactory::AddRef(CIEAdminBrokerClassFactory *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 1);
  return *((_DWORD *)this + 1);
}

```

## disassembly

```asm
0x402c20  mov     edi, edi
0x402c22  push    ebp
0x402c23  mov     ebp, esp
0x402c25  mov     eax, [ebp+this]
0x402c28  add     eax, 4
0x402c2b  lock inc dword ptr [eax]
0x402c2e  mov     eax, [eax]
0x402c30  pop     ebp
0x402c31  retn    4
```
