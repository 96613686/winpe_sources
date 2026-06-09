# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180020630`
- end: `0x180020692`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180020630`
- `0x180024010`

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
0x180020630  sub     rsp, 28h
0x180020634  mov     r11, rcx
0x180020637  mov     rax, r8
0x18002063a  xor     ecx, ecx
0x18002063c  mov     r10, rdx
0x18002063f  mov     r8d, 80004003h
0x180020645  test    r9, r9
0x180020648  jz      short loc_18002068A
0x18002064a  mov     [r9], rcx
0x18002064d  test    rdx, rdx
0x180020650  jz      short loc_180020675
0x180020652  cmp     [rax], ecx
0x180020654  jnz     short loc_18002066D
0x180020656  cmp     [rax+4], ecx
0x180020659  jnz     short loc_18002066D
0x18002065b  cmp     dword ptr [rax+8], 0C0h
0x180020662  jnz     short loc_18002066D
0x180020664  cmp     dword ptr [rax+0Ch], 46000000h
0x18002066b  jz      short loc_180020675
0x18002066d  mov     r8d, 80040110h
0x180020673  jmp     short loc_18002068A
0x180020675  mov     rdx, rax
0x180020678  mov     r8, r9
0x18002067b  mov     rax, [r11+40h]
0x18002067f  mov     rcx, r10
0x180020682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020687  mov     r8d, eax
0x18002068a  mov     eax, r8d
0x18002068d  add     rsp, 28h
0x180020691  retn
```
