# ATL::CSecurityDesc::Clear(void)

- ea: `0x1800178e0`
- end: `0x180017a1a`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `314`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017308`
- `0x180017324`
- `0x18001733c`
- `0x18009b528`
- `0x1800bf880`

## callees

- `0x1800178e0`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017981`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001799d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017a12`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017981`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001799d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800179e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017a12`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800179d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800179d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800179b3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800179b3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180017993`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180017993`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180017920`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180017920`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180017977`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180017977`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  PSID pOwner; // [rsp+20h] [rbp-40h] BYREF
  PSID pGroup; // [rsp+28h] [rbp-38h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-30h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-28h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp-20h] BYREF
  WORD pControl; // [rsp+44h] [rbp-1Ch] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+48h] [rbp-18h] BYREF

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
      bOwnerDefaulted = 0;
      dwRevision = 0;
      GetSecurityDescriptorOwner(v3, &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), (LPBOOL)&dwRevision, &pDacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), (LPBOOL)&dwRevision, &pSacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x1800178e0  mov     [rsp-8+arg_8], rbx
0x1800178e5  push    rbp
0x1800178e6  mov     rbp, rsp
0x1800178e9  sub     rsp, 60h
0x1800178ed  mov     rax, cs:__security_cookie
0x1800178f4  xor     rax, rsp
0x1800178f7  mov     [rbp+var_10], rax
0x1800178fb  mov     rbx, rcx
0x1800178fe  mov     rcx, [rcx+8]; pSecurityDescriptor
0x180017902  test    rcx, rcx
0x180017905  jz      loc_1800179F7
0x18001790b  xor     eax, eax
0x18001790d  mov     [rbp+dwRevision], 0
0x180017914  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180017918  mov     [rbp+pControl], ax
0x18001791c  lea     rdx, [rbp+pControl]; pControl
0x180017920  call    cs:__imp_GetSecurityDescriptorControl
0x180017926  test    eax, eax
0x180017928  jz      loc_1800179E5
0x18001792e  mov     eax, 8000h
0x180017933  test    [rbp+pControl], ax
0x180017937  jnz     loc_1800179E5
0x18001793d  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180017941  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180017945  lea     rdx, [rbp+pOwner]; pOwner
0x180017949  mov     [rbp+pOwner], 0
0x180017951  mov     [rbp+pGroup], 0
0x180017959  mov     [rbp+pDacl], 0
0x180017961  mov     [rbp+pSacl], 0
0x180017969  mov     [rbp+bOwnerDefaulted], 0
0x180017970  mov     [rbp+dwRevision], 0
0x180017977  call    cs:__imp_GetSecurityDescriptorOwner
0x18001797d  mov     rcx, [rbp+pOwner]; Block
0x180017981  call    cs:__imp_free
0x180017987  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18001798b  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18001798f  lea     rdx, [rbp+pGroup]; pGroup
0x180017993  call    cs:__imp_GetSecurityDescriptorGroup
0x180017999  mov     rcx, [rbp+pGroup]; Block
0x18001799d  call    cs:__imp_free
0x1800179a3  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800179a7  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800179ab  lea     r8, [rbp+pDacl]; pDacl
0x1800179af  lea     rdx, [rbp+dwRevision]; lpbDaclPresent
0x1800179b3  call    cs:__imp_GetSecurityDescriptorDacl
0x1800179b9  cmp     [rbp+dwRevision], 0
0x1800179bd  jz      short loc_1800179C9
0x1800179bf  mov     rcx, [rbp+pDacl]; Block
0x1800179c3  call    cs:__imp_free
0x1800179c9  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800179cd  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x1800179d1  lea     r8, [rbp+pSacl]; pSacl
0x1800179d5  lea     rdx, [rbp+dwRevision]; lpbSaclPresent
0x1800179d9  call    cs:__imp_GetSecurityDescriptorSacl
0x1800179df  cmp     [rbp+dwRevision], 0
0x1800179e3  jnz     short loc_180017A0E
0x1800179e5  mov     rcx, [rbx+8]; Block
0x1800179e9  call    cs:__imp_free
0x1800179ef  mov     qword ptr [rbx+8], 0
0x1800179f7  mov     rcx, [rbp+var_10]
0x1800179fb  xor     rcx, rsp; StackCookie
0x1800179fe  call    __security_check_cookie
0x180017a03  mov     rbx, [rsp+60h+arg_8]
0x180017a08  add     rsp, 60h
0x180017a0c  pop     rbp
0x180017a0d  retn
0x180017a0e  mov     rcx, [rbp+pSacl]; Block
0x180017a12  call    cs:__imp_free
0x180017a18  jmp     short loc_1800179E5
```
