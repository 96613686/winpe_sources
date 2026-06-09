# ATL::CSecurityDesc::Clear(void)

- ea: `0x180042510`
- end: `0x180042621`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `273`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041ef8`
- `0x180042240`
- `0x1800435fc`

## callees

- `0x180042510`
- `0x18004291c`

## import_xrefs

- `msvcrt!free` at `0x18004259a`
- `msvcrt!free` at `0x1800425b6`
- `msvcrt!free` at `0x1800425dc`
- `msvcrt!free` at `0x180042602`
- `msvcrt!free` at `0x18004260c`
- `msvcrt!free` at `0x18004259a`
- `msvcrt!free` at `0x1800425b6`
- `msvcrt!free` at `0x1800425dc`
- `msvcrt!free` at `0x180042602`
- `msvcrt!free` at `0x18004260c`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180042590`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180042590`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800425ac`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800425ac`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800425cc`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800425cc`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800425f2`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800425f2`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(PSECURITY_DESCRIPTOR *this)
{
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 v5; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  pSacl[1] = (PACL)-2LL;
  if ( this[1] )
  {
    v5 = 0;
    if ( ATL::CSecurityDesc::GetControl((ATL::CSecurityDesc *)this, &v5) && (v5 & 0x8000u) == 0 )
    {
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl[0] = 0;
      bOwnerDefaulted = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(this[1], &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(this[1], &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(this[1], &bDaclPresent, &pDacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(this[1], &bDaclPresent, pSacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pSacl[0]);
    }
    free(this[1]);
    this[1] = 0;
  }
}

```

## disassembly

```asm
0x180042510  push    rbp
0x180042512  push    rbx
0x180042513  mov     rbp, rsp
0x180042516  sub     rsp, 48h
0x18004251a  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180042522  mov     rbx, rcx
0x180042525  cmp     qword ptr [rcx+8], 0
0x18004252a  jz      loc_18004261A
0x180042530  xor     eax, eax
0x180042532  mov     [rbp+arg_0], ax
0x180042536  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x18004253a  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x18004253f  test    al, al
0x180042541  jz      loc_180042608
0x180042547  mov     eax, 8000h
0x18004254c  test    [rbp+arg_0], ax
0x180042550  jnz     loc_180042608
0x180042556  mov     [rbp+pOwner], 0
0x18004255e  mov     [rbp+pGroup], 0
0x180042566  mov     [rbp+pDacl], 0
0x18004256e  mov     [rbp+pSacl], 0
0x180042576  mov     [rbp+bOwnerDefaulted], 0
0x18004257d  mov     [rbp+bDaclPresent], 0
0x180042584  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180042588  lea     rdx, [rbp+pOwner]; pOwner
0x18004258c  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180042590  call    cs:__imp_GetSecurityDescriptorOwner
0x180042596  mov     rcx, [rbp+pOwner]; Block
0x18004259a  call    cs:__imp_free
0x1800425a0  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800425a4  lea     rdx, [rbp+pGroup]; pGroup
0x1800425a8  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800425ac  call    cs:__imp_GetSecurityDescriptorGroup
0x1800425b2  mov     rcx, [rbp+pGroup]; Block
0x1800425b6  call    cs:__imp_free
0x1800425bc  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800425c0  lea     r8, [rbp+pDacl]; pDacl
0x1800425c4  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800425c8  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800425cc  call    cs:__imp_GetSecurityDescriptorDacl
0x1800425d2  cmp     [rbp+bDaclPresent], 0
0x1800425d6  jz      short loc_1800425E2
0x1800425d8  mov     rcx, [rbp+pDacl]; Block
0x1800425dc  call    cs:__imp_free
0x1800425e2  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1800425e6  lea     r8, [rbp+pSacl]; pSacl
0x1800425ea  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x1800425ee  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800425f2  call    cs:__imp_GetSecurityDescriptorSacl
0x1800425f8  cmp     [rbp+bDaclPresent], 0
0x1800425fc  jz      short loc_180042608
0x1800425fe  mov     rcx, [rbp+pSacl]; Block
0x180042602  call    cs:__imp_free
0x180042608  mov     rcx, [rbx+8]; Block
0x18004260c  call    cs:__imp_free
0x180042612  mov     qword ptr [rbx+8], 0
0x18004261a  add     rsp, 48h
0x18004261e  pop     rbx
0x18004261f  pop     rbp
0x180042620  retn
```
