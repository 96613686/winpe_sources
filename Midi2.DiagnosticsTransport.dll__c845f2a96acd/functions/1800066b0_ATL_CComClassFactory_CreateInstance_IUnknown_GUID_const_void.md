# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800066b0`
- end: `0x180006712`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800066b0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800066b0  sub     rsp, 28h
0x1800066b4  mov     r11, rcx
0x1800066b7  mov     rax, r8
0x1800066ba  xor     ecx, ecx
0x1800066bc  mov     r10, rdx
0x1800066bf  mov     r8d, 80004003h
0x1800066c5  test    r9, r9
0x1800066c8  jz      short loc_18000670A
0x1800066ca  mov     [r9], rcx
0x1800066cd  test    rdx, rdx
0x1800066d0  jz      short loc_1800066F5
0x1800066d2  cmp     [rax], ecx
0x1800066d4  jnz     short loc_1800066ED
0x1800066d6  cmp     [rax+4], ecx
0x1800066d9  jnz     short loc_1800066ED
0x1800066db  cmp     dword ptr [rax+8], 0C0h
0x1800066e2  jnz     short loc_1800066ED
0x1800066e4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800066eb  jz      short loc_1800066F5
0x1800066ed  mov     r8d, 80040110h
0x1800066f3  jmp     short loc_18000670A
0x1800066f5  mov     rdx, rax
0x1800066f8  mov     r8, r9
0x1800066fb  mov     rax, [r11+40h]
0x1800066ff  mov     rcx, r10
0x180006702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006707  mov     r8d, eax
0x18000670a  mov     eax, r8d
0x18000670d  add     rsp, 28h
0x180006711  retn
```
