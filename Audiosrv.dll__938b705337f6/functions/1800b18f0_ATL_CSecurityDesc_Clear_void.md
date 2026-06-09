# ATL::CSecurityDesc::Clear(void)

- ea: `0x1800b18f0`
- end: `0x1800b19f9`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800378b0`
- `0x1800b18d8`
- `0x1800d5ff0`

## callees

- `0x180073098`
- `0x1800b18f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1972`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b198e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19e4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b1972`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b198e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800b19e4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800b19ca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800b19ca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800b19a4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800b19a4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800b1984`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800b1984`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800b1968`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800b1968`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 v6; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    v6 = 0;
    if ( ATL::CSecurityDesc::GetControl(this, &v6) && (v6 & 0x8000u) == 0 )
    {
      v2 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      bOwnerDefaulted = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, &bOwnerDefaulted);
      if ( bDaclPresent )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1800b18f0  push    rbp
0x1800b18f2  push    rbx
0x1800b18f3  mov     rbp, rsp
0x1800b18f6  sub     rsp, 48h
0x1800b18fa  cmp     qword ptr [rcx+8], 0
0x1800b18ff  mov     rbx, rcx
0x1800b1902  jz      loc_1800B19F2
0x1800b1908  xor     eax, eax
0x1800b190a  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800b190e  mov     [rbp+arg_0], ax
0x1800b1912  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x1800b1917  test    al, al
0x1800b1919  jz      loc_1800B19E0
0x1800b191f  mov     eax, 8000h
0x1800b1924  test    [rbp+arg_0], ax
0x1800b1928  jnz     loc_1800B19E0
0x1800b192e  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800b1932  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800b1936  lea     rdx, [rbp+pOwner]; pOwner
0x1800b193a  mov     [rbp+pOwner], 0
0x1800b1942  mov     [rbp+pGroup], 0
0x1800b194a  mov     [rbp+pDacl], 0
0x1800b1952  mov     [rbp+pSacl], 0
0x1800b195a  mov     [rbp+bOwnerDefaulted], 0
0x1800b1961  mov     [rbp+bDaclPresent], 0
0x1800b1968  call    cs:__imp_GetSecurityDescriptorOwner
0x1800b196e  mov     rcx, [rbp+pOwner]; Block
0x1800b1972  call    cs:__imp_free
0x1800b1978  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800b197c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800b1980  lea     rdx, [rbp+pGroup]; pGroup
0x1800b1984  call    cs:__imp_GetSecurityDescriptorGroup
0x1800b198a  mov     rcx, [rbp+pGroup]; Block
0x1800b198e  call    cs:__imp_free
0x1800b1994  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800b1998  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800b199c  lea     r8, [rbp+pDacl]; pDacl
0x1800b19a0  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800b19a4  call    cs:__imp_GetSecurityDescriptorDacl
0x1800b19aa  cmp     [rbp+bDaclPresent], 0
0x1800b19ae  jz      short loc_1800B19BA
0x1800b19b0  mov     rcx, [rbp+pDacl]; Block
0x1800b19b4  call    cs:__imp_free
0x1800b19ba  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800b19be  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1800b19c2  lea     r8, [rbp+pSacl]; pSacl
0x1800b19c6  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x1800b19ca  call    cs:__imp_GetSecurityDescriptorSacl
0x1800b19d0  cmp     [rbp+bDaclPresent], 0
0x1800b19d4  jz      short loc_1800B19E0
0x1800b19d6  mov     rcx, [rbp+pSacl]; Block
0x1800b19da  call    cs:__imp_free
0x1800b19e0  mov     rcx, [rbx+8]; Block
0x1800b19e4  call    cs:__imp_free
0x1800b19ea  mov     qword ptr [rbx+8], 0
0x1800b19f2  add     rsp, 48h
0x1800b19f6  pop     rbx
0x1800b19f7  pop     rbp
0x1800b19f8  retn
```
