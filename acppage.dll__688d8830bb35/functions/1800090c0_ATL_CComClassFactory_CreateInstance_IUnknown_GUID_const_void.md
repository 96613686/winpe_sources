# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800090c0`
- end: `0x180009122`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800090c0`
- `0x180017010`

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
0x1800090c0  sub     rsp, 28h
0x1800090c4  mov     r11, rcx
0x1800090c7  mov     rax, r8
0x1800090ca  xor     ecx, ecx
0x1800090cc  mov     r10, rdx
0x1800090cf  mov     r8d, 80004003h
0x1800090d5  test    r9, r9
0x1800090d8  jz      short loc_18000911A
0x1800090da  mov     [r9], rcx
0x1800090dd  test    rdx, rdx
0x1800090e0  jz      short loc_180009105
0x1800090e2  cmp     [rax], ecx
0x1800090e4  jnz     short loc_1800090FD
0x1800090e6  cmp     [rax+4], ecx
0x1800090e9  jnz     short loc_1800090FD
0x1800090eb  cmp     dword ptr [rax+8], 0C0h
0x1800090f2  jnz     short loc_1800090FD
0x1800090f4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800090fb  jz      short loc_180009105
0x1800090fd  mov     r8d, 80040110h
0x180009103  jmp     short loc_18000911A
0x180009105  mov     rdx, rax
0x180009108  mov     r8, r9
0x18000910b  mov     rax, [r11+40h]
0x18000910f  mov     rcx, r10
0x180009112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009117  mov     r8d, eax
0x18000911a  mov     eax, r8d
0x18000911d  add     rsp, 28h
0x180009121  retn
```
