# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800078e0`
- end: `0x180007942`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800078e0`
- `0x18000e010`

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
0x1800078e0  sub     rsp, 28h
0x1800078e4  mov     r11, rcx
0x1800078e7  mov     rax, r8
0x1800078ea  xor     ecx, ecx
0x1800078ec  mov     r10, rdx
0x1800078ef  mov     r8d, 80004003h
0x1800078f5  test    r9, r9
0x1800078f8  jz      short loc_18000793A
0x1800078fa  mov     [r9], rcx
0x1800078fd  test    rdx, rdx
0x180007900  jz      short loc_180007925
0x180007902  cmp     [rax], ecx
0x180007904  jnz     short loc_18000791D
0x180007906  cmp     [rax+4], ecx
0x180007909  jnz     short loc_18000791D
0x18000790b  cmp     dword ptr [rax+8], 0C0h
0x180007912  jnz     short loc_18000791D
0x180007914  cmp     dword ptr [rax+0Ch], 46000000h
0x18000791b  jz      short loc_180007925
0x18000791d  mov     r8d, 80040110h
0x180007923  jmp     short loc_18000793A
0x180007925  mov     rdx, rax
0x180007928  mov     r8, r9
0x18000792b  mov     rax, [r11+40h]
0x18000792f  mov     rcx, r10
0x180007932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007937  mov     r8d, eax
0x18000793a  mov     eax, r8d
0x18000793d  add     rsp, 28h
0x180007941  retn
```
