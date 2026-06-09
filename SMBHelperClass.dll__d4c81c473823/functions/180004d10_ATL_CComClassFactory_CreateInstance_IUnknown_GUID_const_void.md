# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004d10`
- end: `0x180004d72`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004d10`
- `0x180012010`

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
0x180004d10  sub     rsp, 28h
0x180004d14  mov     r11, rcx
0x180004d17  mov     rax, r8
0x180004d1a  xor     ecx, ecx
0x180004d1c  mov     r10, rdx
0x180004d1f  mov     r8d, 80004003h
0x180004d25  test    r9, r9
0x180004d28  jz      short loc_180004D6A
0x180004d2a  mov     [r9], rcx
0x180004d2d  test    rdx, rdx
0x180004d30  jz      short loc_180004D55
0x180004d32  cmp     [rax], ecx
0x180004d34  jnz     short loc_180004D4D
0x180004d36  cmp     [rax+4], ecx
0x180004d39  jnz     short loc_180004D4D
0x180004d3b  cmp     dword ptr [rax+8], 0C0h
0x180004d42  jnz     short loc_180004D4D
0x180004d44  cmp     dword ptr [rax+0Ch], 46000000h
0x180004d4b  jz      short loc_180004D55
0x180004d4d  mov     r8d, 80040110h
0x180004d53  jmp     short loc_180004D6A
0x180004d55  mov     rdx, rax
0x180004d58  mov     r8, r9
0x180004d5b  mov     rax, [r11+40h]
0x180004d5f  mov     rcx, r10
0x180004d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d67  mov     r8d, eax
0x180004d6a  mov     eax, r8d
0x180004d6d  add     rsp, 28h
0x180004d71  retn
```
