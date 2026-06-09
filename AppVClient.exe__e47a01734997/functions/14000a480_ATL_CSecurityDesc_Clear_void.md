# ATL::CSecurityDesc::Clear(void)

- ea: `0x14000a480`
- end: `0x14000a597`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `279`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009218`
- `0x140009bf0`
- `0x14000e140`

## callees

- `0x14000a480`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14000a506`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14000a506`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14000a4af`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14000a4af`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14000a522`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14000a522`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14000a542`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14000a542`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000a568`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000a568`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a52c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a552`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a578`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a582`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a510`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a52c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a552`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a578`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a582`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  WORD pControl; // [rsp+60h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp+20h] BYREF
  BOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( GetSecurityDescriptorControl(v2, &pControl, &dwRevision) && (pControl & 0x8000u) == 0 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      dwRevision = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v3, &pOwner, (LPBOOL)&dwRevision);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, (LPBOOL)&dwRevision);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, (LPBOOL)&dwRevision);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, (LPBOOL)&dwRevision);
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
0x14000a480  push    rbp
0x14000a482  push    rbx
0x14000a483  mov     rbp, rsp
0x14000a486  sub     rsp, 48h
0x14000a48a  mov     rbx, rcx
0x14000a48d  mov     rcx, [rcx+8]; pSecurityDescriptor
0x14000a491  test    rcx, rcx
0x14000a494  jz      loc_14000A590
0x14000a49a  xor     eax, eax
0x14000a49c  mov     [rbp+dwRevision], 0
0x14000a4a3  lea     r8, [rbp+dwRevision]; lpdwRevision
0x14000a4a7  mov     [rbp+pControl], ax
0x14000a4ab  lea     rdx, [rbp+pControl]; pControl
0x14000a4af  call    cs:__imp_GetSecurityDescriptorControl
0x14000a4b5  test    eax, eax
0x14000a4b7  jz      loc_14000A57E
0x14000a4bd  mov     eax, 8000h
0x14000a4c2  test    [rbp+pControl], ax
0x14000a4c6  jnz     loc_14000A57E
0x14000a4cc  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000a4d0  lea     r8, [rbp+dwRevision]; lpbOwnerDefaulted
0x14000a4d4  lea     rdx, [rbp+pOwner]; pOwner
0x14000a4d8  mov     [rbp+pOwner], 0
0x14000a4e0  mov     [rbp+pGroup], 0
0x14000a4e8  mov     [rbp+pDacl], 0
0x14000a4f0  mov     [rbp+pSacl], 0
0x14000a4f8  mov     [rbp+dwRevision], 0
0x14000a4ff  mov     [rbp+bDaclPresent], 0
0x14000a506  call    cs:__imp_GetSecurityDescriptorOwner
0x14000a50c  mov     rcx, [rbp+pOwner]; Block
0x14000a510  call    cs:__imp_free
0x14000a516  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000a51a  lea     r8, [rbp+dwRevision]; lpbGroupDefaulted
0x14000a51e  lea     rdx, [rbp+pGroup]; pGroup
0x14000a522  call    cs:__imp_GetSecurityDescriptorGroup
0x14000a528  mov     rcx, [rbp+pGroup]; Block
0x14000a52c  call    cs:__imp_free
0x14000a532  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000a536  lea     r9, [rbp+dwRevision]; lpbDaclDefaulted
0x14000a53a  lea     r8, [rbp+pDacl]; pDacl
0x14000a53e  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x14000a542  call    cs:__imp_GetSecurityDescriptorDacl
0x14000a548  cmp     [rbp+bDaclPresent], 0
0x14000a54c  jz      short loc_14000A558
0x14000a54e  mov     rcx, [rbp+pDacl]; Block
0x14000a552  call    cs:__imp_free
0x14000a558  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000a55c  lea     r9, [rbp+dwRevision]; lpbSaclDefaulted
0x14000a560  lea     r8, [rbp+pSacl]; pSacl
0x14000a564  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x14000a568  call    cs:__imp_GetSecurityDescriptorSacl
0x14000a56e  cmp     [rbp+bDaclPresent], 0
0x14000a572  jz      short loc_14000A57E
0x14000a574  mov     rcx, [rbp+pSacl]; Block
0x14000a578  call    cs:__imp_free
0x14000a57e  mov     rcx, [rbx+8]; Block
0x14000a582  call    cs:__imp_free
0x14000a588  mov     qword ptr [rbx+8], 0
0x14000a590  add     rsp, 48h
0x14000a594  pop     rbx
0x14000a595  pop     rbp
0x14000a596  retn
```
