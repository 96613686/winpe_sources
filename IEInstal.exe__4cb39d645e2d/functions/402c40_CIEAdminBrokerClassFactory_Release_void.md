# CIEAdminBrokerClassFactory::Release(void)

- ea: `0x402c40`
- end: `0x402c79`
- name: `?Release@CIEAdminBrokerClassFactory@@UAGKXZ`
- size: `57`
- prototype: `int __stdcall(CIEAdminBrokerClassFactory *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x402712`
- `0x402c40`
- `0x409525`

## pseudocode

```c
int __stdcall CIEAdminBrokerClassFactory::Release(CIEAdminBrokerClassFactory *this)
{
  int v1; // edi

  v1 = *((_DWORD *)this + 1) - 1;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) )
  {
    v1 = 0;
    if ( this )
    {
      *(_DWORD *)this = &CIEAdminBrokerClassFactory::`vftable';
      ObjectDestroyed();
      operator delete(this);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x402c40  mov     edi, edi
0x402c42  push    ebp
0x402c43  mov     ebp, esp
0x402c45  push    esi
0x402c46  mov     esi, [ebp+lpMem]
0x402c49  or      eax, 0FFFFFFFFh
0x402c4c  push    edi
0x402c4d  lea     ecx, [esi+4]
0x402c50  mov     edi, [ecx]
0x402c52  dec     edi
0x402c53  lock xadd [ecx], eax
0x402c57  jnz     short loc_402C71
0x402c59  xor     edi, edi
0x402c5b  test    esi, esi
0x402c5d  jz      short loc_402C71
0x402c5f  mov     dword ptr [esi], offset ??_7CIEAdminBrokerClassFactory@@6B@; const CIEAdminBrokerClassFactory::`vftable'
0x402c65  call    ?ObjectDestroyed@@YGXXZ; ObjectDestroyed(void)
0x402c6a  push    esi; lpMem
0x402c6b  call    ??3@YAXPAX@Z; operator delete(void *)
0x402c70  pop     ecx
0x402c71  mov     eax, edi
0x402c73  pop     edi
0x402c74  pop     esi
0x402c75  pop     ebp
0x402c76  retn    4
```
