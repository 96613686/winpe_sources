# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004e00`
- end: `0x180004e62`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004e00`
- `0x18000c010`

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
0x180004e00  sub     rsp, 28h
0x180004e04  mov     r11, rcx
0x180004e07  mov     rax, r8
0x180004e0a  xor     ecx, ecx
0x180004e0c  mov     r10, rdx
0x180004e0f  mov     r8d, 80004003h
0x180004e15  test    r9, r9
0x180004e18  jz      short loc_180004E5A
0x180004e1a  mov     [r9], rcx
0x180004e1d  test    rdx, rdx
0x180004e20  jz      short loc_180004E45
0x180004e22  cmp     [rax], ecx
0x180004e24  jnz     short loc_180004E3D
0x180004e26  cmp     [rax+4], ecx
0x180004e29  jnz     short loc_180004E3D
0x180004e2b  cmp     dword ptr [rax+8], 0C0h
0x180004e32  jnz     short loc_180004E3D
0x180004e34  cmp     dword ptr [rax+0Ch], 46000000h
0x180004e3b  jz      short loc_180004E45
0x180004e3d  mov     r8d, 80040110h
0x180004e43  jmp     short loc_180004E5A
0x180004e45  mov     rdx, rax
0x180004e48  mov     r8, r9
0x180004e4b  mov     rax, [r11+40h]
0x180004e4f  mov     rcx, r10
0x180004e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e57  mov     r8d, eax
0x180004e5a  mov     eax, r8d
0x180004e5d  add     rsp, 28h
0x180004e61  retn
```
