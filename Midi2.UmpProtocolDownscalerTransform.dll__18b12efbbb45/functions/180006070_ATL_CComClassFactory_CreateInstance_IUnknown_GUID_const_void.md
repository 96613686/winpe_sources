# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006070`
- end: `0x1800060d2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006070`
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
0x180006070  sub     rsp, 28h
0x180006074  mov     r11, rcx
0x180006077  mov     rax, r8
0x18000607a  xor     ecx, ecx
0x18000607c  mov     r10, rdx
0x18000607f  mov     r8d, 80004003h
0x180006085  test    r9, r9
0x180006088  jz      short loc_1800060CA
0x18000608a  mov     [r9], rcx
0x18000608d  test    rdx, rdx
0x180006090  jz      short loc_1800060B5
0x180006092  cmp     [rax], ecx
0x180006094  jnz     short loc_1800060AD
0x180006096  cmp     [rax+4], ecx
0x180006099  jnz     short loc_1800060AD
0x18000609b  cmp     dword ptr [rax+8], 0C0h
0x1800060a2  jnz     short loc_1800060AD
0x1800060a4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800060ab  jz      short loc_1800060B5
0x1800060ad  mov     r8d, 80040110h
0x1800060b3  jmp     short loc_1800060CA
0x1800060b5  mov     rdx, rax
0x1800060b8  mov     r8, r9
0x1800060bb  mov     rax, [r11+40h]
0x1800060bf  mov     rcx, r10
0x1800060c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c7  mov     r8d, eax
0x1800060ca  mov     eax, r8d
0x1800060cd  add     rsp, 28h
0x1800060d1  retn
```
