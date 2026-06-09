# CIEAdminBrokerClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x402cb0`
- end: `0x402d14`
- name: `?QueryInterface@CIEAdminBrokerClassFactory@@UAGJABU_GUID@@PAPAX@Z`
- size: `100`
- prototype: `int __stdcall(CIEAdminBrokerClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x402cb0`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CIEAdminBrokerClassFactory::QueryInterface(
        CIEAdminBrokerClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  int v3; // edi
  int v4; // ecx
  int v5; // ecx

  v3 = 0;
  v4 = 0;
  while ( *(&a2->Data1 + v4) == *(&IID_IUnknown.Data1 + v4) )
  {
    if ( ++v4 == 4 )
    {
LABEL_8:
      *a3 = this;
      (*(void (__thiscall **)(_DWORD, CIEAdminBrokerClassFactory *))(*(_DWORD *)this + 4))(
        *(_DWORD *)(*(_DWORD *)this + 4),
        this);
      return v3;
    }
  }
  v5 = 0;
  while ( *(&a2->Data1 + v5) == *(&IID_IClassFactory.Data1 + v5) )
  {
    if ( ++v5 == 4 )
      goto LABEL_8;
  }
  *a3 = 0;
  return -2147467262;
}

```

## disassembly

```asm
0x402cb0  mov     edi, edi
0x402cb2  push    ebp
0x402cb3  mov     ebp, esp
0x402cb5  mov     edx, [ebp+arg_4]
0x402cb8  push    esi
0x402cb9  push    edi
0x402cba  xor     edi, edi
0x402cbc  mov     esi, offset _IID_IUnknown
0x402cc1  xor     ecx, ecx
0x402cc3  mov     eax, [edx+ecx*4]
0x402cc6  cmp     eax, [esi+ecx*4]
0x402cc9  jnz     short loc_402CD3
0x402ccb  inc     ecx
0x402ccc  cmp     ecx, 4
0x402ccf  jnz     short loc_402CC3
0x402cd1  jmp     short loc_402CE8
0x402cd3  mov     esi, offset _IID_IClassFactory
0x402cd8  xor     ecx, ecx
0x402cda  mov     eax, [edx+ecx*4]
0x402cdd  cmp     eax, [esi+ecx*4]
0x402ce0  jnz     short loc_402D02
0x402ce2  inc     ecx
0x402ce3  cmp     ecx, 4
0x402ce6  jnz     short loc_402CDA
0x402ce8  mov     ecx, [ebp+this]
0x402ceb  mov     eax, [ebp+arg_8]
0x402cee  push    ecx
0x402cef  mov     [eax], ecx
0x402cf1  mov     eax, [ecx]
0x402cf3  mov     esi, [eax+4]
0x402cf6  mov     ecx, esi
0x402cf8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x402cfe  call    esi
0x402d00  jmp     short loc_402D0C
0x402d02  mov     eax, [ebp+arg_8]
0x402d05  mov     [eax], edi
0x402d07  mov     edi, 80004002h
0x402d0c  mov     eax, edi
0x402d0e  pop     edi
0x402d0f  pop     esi
0x402d10  pop     ebp
0x402d11  retn    0Ch
```
