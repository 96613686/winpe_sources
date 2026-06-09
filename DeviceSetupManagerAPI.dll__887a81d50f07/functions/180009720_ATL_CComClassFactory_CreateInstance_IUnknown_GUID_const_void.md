# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009720`
- end: `0x180009782`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009720`
- `0x18000f010`

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
0x180009720  sub     rsp, 28h
0x180009724  mov     r11, rcx
0x180009727  mov     rax, r8
0x18000972a  xor     ecx, ecx
0x18000972c  mov     r10, rdx
0x18000972f  mov     r8d, 80004003h
0x180009735  test    r9, r9
0x180009738  jz      short loc_18000977A
0x18000973a  mov     [r9], rcx
0x18000973d  test    rdx, rdx
0x180009740  jz      short loc_180009765
0x180009742  cmp     [rax], ecx
0x180009744  jnz     short loc_18000975D
0x180009746  cmp     [rax+4], ecx
0x180009749  jnz     short loc_18000975D
0x18000974b  cmp     dword ptr [rax+8], 0C0h
0x180009752  jnz     short loc_18000975D
0x180009754  cmp     dword ptr [rax+0Ch], 46000000h
0x18000975b  jz      short loc_180009765
0x18000975d  mov     r8d, 80040110h
0x180009763  jmp     short loc_18000977A
0x180009765  mov     rdx, rax
0x180009768  mov     r8, r9
0x18000976b  mov     rax, [r11+40h]
0x18000976f  mov     rcx, r10
0x180009772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009777  mov     r8d, eax
0x18000977a  mov     eax, r8d
0x18000977d  add     rsp, 28h
0x180009781  retn
```
