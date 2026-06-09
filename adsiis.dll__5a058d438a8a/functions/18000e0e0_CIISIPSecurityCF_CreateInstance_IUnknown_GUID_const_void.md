# CIISIPSecurityCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000e0e0`
- end: `0x18000e108`
- name: `?CreateInstance@CIISIPSecurityCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISIPSecurityCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0e0`
- `0x18000e490`

## pseudocode

```c
__int64 __fastcall CIISIPSecurityCF::CreateInstance(
        CIISIPSecurityCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147500037LL;
  else
    return CIPSecurity::CreateIPSecurity(a3, a4);
}

```

## disassembly

```asm
0x18000e0e0  test    r9, r9
0x18000e0e3  jnz     short loc_18000E0EB
0x18000e0e5  mov     eax, 80004003h
0x18000e0ea  retn
0x18000e0eb  mov     qword ptr [r9], 0
0x18000e0f2  test    rdx, rdx
0x18000e0f5  jz      short loc_18000E0FD
0x18000e0f7  mov     eax, 80004005h
0x18000e0fc  retn
0x18000e0fd  mov     rdx, r9; void **
0x18000e100  mov     rcx, r8; struct _GUID *
0x18000e103  jmp     ?CreateIPSecurity@CIPSecurity@@SAJAEBU_GUID@@PEAPEAX@Z; CIPSecurity::CreateIPSecurity(_GUID const &,void * *)
```
