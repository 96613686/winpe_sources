# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800052e0`
- end: `0x180005342`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800052e0`
- `0x18000b010`

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
0x1800052e0  sub     rsp, 28h
0x1800052e4  mov     r11, rcx
0x1800052e7  mov     rax, r8
0x1800052ea  xor     ecx, ecx
0x1800052ec  mov     r10, rdx
0x1800052ef  mov     r8d, 80004003h
0x1800052f5  test    r9, r9
0x1800052f8  jz      short loc_18000533A
0x1800052fa  mov     [r9], rcx
0x1800052fd  test    rdx, rdx
0x180005300  jz      short loc_180005325
0x180005302  cmp     [rax], ecx
0x180005304  jnz     short loc_18000531D
0x180005306  cmp     [rax+4], ecx
0x180005309  jnz     short loc_18000531D
0x18000530b  cmp     dword ptr [rax+8], 0C0h
0x180005312  jnz     short loc_18000531D
0x180005314  cmp     dword ptr [rax+0Ch], 46000000h
0x18000531b  jz      short loc_180005325
0x18000531d  mov     r8d, 80040110h
0x180005323  jmp     short loc_18000533A
0x180005325  mov     rdx, rax
0x180005328  mov     r8, r9
0x18000532b  mov     rax, [r11+40h]
0x18000532f  mov     rcx, r10
0x180005332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005337  mov     r8d, eax
0x18000533a  mov     eax, r8d
0x18000533d  add     rsp, 28h
0x180005341  retn
```
