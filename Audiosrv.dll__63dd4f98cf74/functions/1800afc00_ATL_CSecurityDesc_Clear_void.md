# ATL::CSecurityDesc::Clear(void)

- ea: `0x1800afc00`
- end: `0x1800afd09`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037a10`
- `0x1800afbe8`
- `0x1800d4000`

## callees

- `0x180072b98`
- `0x1800afc00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afc82`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afc9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcf4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afc82`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afc9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800afcf4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800afcda`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800afcda`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800afcb4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800afcb4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800afc94`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800afc94`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800afc78`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800afc78`

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
0x1800afc00  push    rbp
0x1800afc02  push    rbx
0x1800afc03  mov     rbp, rsp
0x1800afc06  sub     rsp, 48h
0x1800afc0a  cmp     qword ptr [rcx+8], 0
0x1800afc0f  mov     rbx, rcx
0x1800afc12  jz      loc_1800AFD02
0x1800afc18  xor     eax, eax
0x1800afc1a  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1800afc1e  mov     [rbp+arg_0], ax
0x1800afc22  call    ?GetControl@CSecurityDesc@ATL@@QEBA_NPEAG@Z; ATL::CSecurityDesc::GetControl(ushort *)
0x1800afc27  test    al, al
0x1800afc29  jz      loc_1800AFCF0
0x1800afc2f  mov     eax, 8000h
0x1800afc34  test    [rbp+arg_0], ax
0x1800afc38  jnz     loc_1800AFCF0
0x1800afc3e  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800afc42  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800afc46  lea     rdx, [rbp+pOwner]; pOwner
0x1800afc4a  mov     [rbp+pOwner], 0
0x1800afc52  mov     [rbp+pGroup], 0
0x1800afc5a  mov     [rbp+pDacl], 0
0x1800afc62  mov     [rbp+pSacl], 0
0x1800afc6a  mov     [rbp+bOwnerDefaulted], 0
0x1800afc71  mov     [rbp+bDaclPresent], 0
0x1800afc78  call    cs:__imp_GetSecurityDescriptorOwner
0x1800afc7e  mov     rcx, [rbp+pOwner]; Block
0x1800afc82  call    cs:__imp_free
0x1800afc88  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800afc8c  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800afc90  lea     rdx, [rbp+pGroup]; pGroup
0x1800afc94  call    cs:__imp_GetSecurityDescriptorGroup
0x1800afc9a  mov     rcx, [rbp+pGroup]; Block
0x1800afc9e  call    cs:__imp_free
0x1800afca4  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800afca8  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800afcac  lea     r8, [rbp+pDacl]; pDacl
0x1800afcb0  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800afcb4  call    cs:__imp_GetSecurityDescriptorDacl
0x1800afcba  cmp     [rbp+bDaclPresent], 0
0x1800afcbe  jz      short loc_1800AFCCA
0x1800afcc0  mov     rcx, [rbp+pDacl]; Block
0x1800afcc4  call    cs:__imp_free
0x1800afcca  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800afcce  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1800afcd2  lea     r8, [rbp+pSacl]; pSacl
0x1800afcd6  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x1800afcda  call    cs:__imp_GetSecurityDescriptorSacl
0x1800afce0  cmp     [rbp+bDaclPresent], 0
0x1800afce4  jz      short loc_1800AFCF0
0x1800afce6  mov     rcx, [rbp+pSacl]; Block
0x1800afcea  call    cs:__imp_free
0x1800afcf0  mov     rcx, [rbx+8]; Block
0x1800afcf4  call    cs:__imp_free
0x1800afcfa  mov     qword ptr [rbx+8], 0
0x1800afd02  add     rsp, 48h
0x1800afd06  pop     rbx
0x1800afd07  pop     rbp
0x1800afd08  retn
```
