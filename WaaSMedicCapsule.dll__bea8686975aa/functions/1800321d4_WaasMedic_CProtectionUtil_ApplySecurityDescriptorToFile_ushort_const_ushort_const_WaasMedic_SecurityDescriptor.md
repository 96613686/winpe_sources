# WaasMedic::CProtectionUtil::ApplySecurityDescriptorToFile(ushort const *,ushort const *,WaasMedic::SecurityDescriptorValidationOptions)

- ea: `0x1800321d4`
- end: `0x1800323ff`
- name: `?ApplySecurityDescriptorToFile@CProtectionUtil@WaasMedic@@SAJPEBG0VSecurityDescriptorValidationOptions@2@@Z`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005b214`

## callees

- `0x180009a34`
- `0x180009a54`
- `0x1800321d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800322af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800322af`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180032287`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180032287`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800322f1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800322f1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180032351`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180032351`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800323ba`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800323ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003223d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003223d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800323ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032258`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032258`

## pseudocode

```c
__int64 __fastcall WaasMedic::CProtectionUtil::ApplySecurityDescriptorToFile(WCHAR *a1, const WCHAR *a2, int a3)
{
  char v3; // bl
  unsigned int LastError; // ebx
  __int64 v6; // rdx
  const char *v8; // r9
  __int64 v9; // rdx
  SECURITY_INFORMATION v10; // edi
  signed int v11; // eax
  int psidGroup; // [rsp+20h] [rbp-50h]
  WINBOOL bSaclPresent; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-20h] BYREF
  PSID pGroup; // [rsp+58h] [rbp-18h] BYREF
  PSID pOwner; // [rsp+60h] [rbp-10h] BYREF
  PACL pSacl; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  WINBOOL bOwnerDefaulted; // [rsp+A0h] [rbp+30h] BYREF
  int v21; // [rsp+B0h] [rbp+40h]
  WINBOOL bDaclPresent; // [rsp+B8h] [rbp+48h] BYREF

  v21 = a3;
  v3 = a3;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  bSaclPresent = 0;
  bOwnerDefaulted = 0;
  hMem = 0;
  if ( !a1 )
  {
    LastError = -2147024809;
    v6 = 454;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\protectionutil.cpp",
      (const char *)LastError,
      psidGroup);
LABEL_4:
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, &hMem, 0) )
  {
    v9 = 455;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\protectionutil.cpp",
                  v8);
    goto LABEL_4;
  }
  if ( !GetSecurityDescriptorOwner(hMem, &pOwner, &bOwnerDefaulted) )
  {
    v9 = 458;
    goto LABEL_9;
  }
  if ( pOwner )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( BYTE2(v21) )
    {
      LastError = -1023410170;
      v6 = 460;
      goto LABEL_3;
    }
  }
  if ( !GetSecurityDescriptorGroup(hMem, &pGroup, &bOwnerDefaulted) )
  {
    v9 = 462;
    goto LABEL_9;
  }
  if ( pGroup )
  {
    v10 |= 2u;
  }
  else if ( BYTE1(v21) )
  {
    LastError = -1023410171;
    v6 = 464;
    goto LABEL_3;
  }
  if ( !GetSecurityDescriptorDacl(hMem, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    v9 = 466;
    goto LABEL_9;
  }
  if ( !pDacl )
  {
LABEL_27:
    if ( bDaclPresent )
      goto LABEL_30;
    goto LABEL_28;
  }
  if ( bDaclPresent )
  {
    v10 |= 4u;
    goto LABEL_27;
  }
LABEL_28:
  if ( v3 )
  {
    LastError = -1023410172;
    v6 = 468;
    goto LABEL_3;
  }
LABEL_30:
  if ( !GetSecurityDescriptorSacl(hMem, &bSaclPresent, &pSacl, &bOwnerDefaulted) )
  {
    v9 = 470;
    goto LABEL_9;
  }
  if ( !pSacl )
  {
LABEL_35:
    if ( bSaclPresent )
      goto LABEL_38;
    goto LABEL_36;
  }
  if ( bSaclPresent )
  {
    v10 |= 0x40000088u;
    goto LABEL_35;
  }
LABEL_36:
  if ( HIBYTE(v21) )
  {
    LastError = -1023410169;
    v6 = 472;
    goto LABEL_3;
  }
LABEL_38:
  v11 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, v10, pOwner, pGroup, pDacl, pSacl);
  LastError = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      LastError = (unsigned __int16)v11 | 0x80070000;
    if ( (LastError & 0x80000000) == 0 )
      goto LABEL_4;
    v6 = 475;
    goto LABEL_3;
  }
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x1800321d4  mov     [rsp-28h+arg_10], r8d
0x1800321d9  push    rbp
0x1800321da  push    rbx
0x1800321db  push    rsi
0x1800321dc  push    rdi
0x1800321dd  push    r14
0x1800321df  mov     rbp, rsp
0x1800321e2  sub     rsp, 70h
0x1800321e6  xor     r14d, r14d
0x1800321e9  mov     ebx, r8d
0x1800321ec  mov     [rbp+pOwner], r14
0x1800321f0  mov     rax, rdx
0x1800321f3  mov     [rbp+pGroup], r14
0x1800321f7  mov     rsi, rcx
0x1800321fa  mov     [rbp+pDacl], r14
0x1800321fe  mov     [rbp+pSacl], r14
0x180032202  mov     [rbp+bDaclPresent], r14d
0x180032206  mov     [rbp+bSaclPresent], r14d
0x18003220a  mov     [rbp+bOwnerDefaulted], r14d
0x18003220e  mov     [rbp+hMem], r14
0x180032212  test    rcx, rcx
0x180032215  jnz     short loc_18003224A
0x180032217  mov     ebx, 80070057h
0x18003221c  mov     edx, 1C6h; void *
0x180032221  mov     rcx, [rbp+28h]; this
0x180032225  lea     r8, aOnecoreEnduser_48; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003222c  mov     r9d, ebx; char *
0x18003222f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032234  mov     rcx, [rbp+hMem]; hMem
0x180032238  test    rcx, rcx
0x18003223b  jz      short loc_180032243
0x18003223d  call    cs:__imp_LocalFree
0x180032243  mov     eax, ebx
0x180032245  jmp     loc_1800323F4
0x18003224a  xor     r9d, r9d; SecurityDescriptorSize
0x18003224d  lea     r8, [rbp+hMem]; SecurityDescriptor
0x180032251  mov     rcx, rax; StringSecurityDescriptor
0x180032254  lea     edx, [r9+1]; StringSDRevision
0x180032258  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003225e  test    eax, eax
0x180032260  jnz     short loc_18003227B
0x180032262  mov     edx, 1C7h; void *
0x180032267  mov     rcx, [rbp+28h]; this
0x18003226b  lea     r8, aOnecoreEnduser_48; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180032272  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032277  mov     ebx, eax
0x180032279  jmp     short loc_180032234
0x18003227b  mov     rcx, [rbp+hMem]; pSecurityDescriptor
0x18003227f  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180032283  lea     rdx, [rbp+pOwner]; pOwner
0x180032287  call    cs:__imp_GetSecurityDescriptorOwner
0x18003228d  test    eax, eax
0x18003228f  jnz     short loc_180032298
0x180032291  mov     edx, 1CAh
0x180032296  jmp     short loc_180032267
0x180032298  cmp     [rbp+pOwner], r14
0x18003229c  jz      short loc_1800322C0
0x18003229e  mov     edi, 1
0x1800322a3  mov     rcx, [rbp+hMem]; pSecurityDescriptor
0x1800322a7  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x1800322ab  lea     rdx, [rbp+pGroup]; pGroup
0x1800322af  call    cs:__imp_GetSecurityDescriptorGroup
0x1800322b5  test    eax, eax
0x1800322b7  jnz     short loc_1800322D8
0x1800322b9  mov     edx, 1CEh
0x1800322be  jmp     short loc_180032267
0x1800322c0  mov     edi, r14d
0x1800322c3  cmp     byte ptr [rbp+arg_10+2], r14b
0x1800322c7  jz      short loc_1800322A3
0x1800322c9  mov     ebx, 0C3000006h
0x1800322ce  mov     edx, 1CCh
0x1800322d3  jmp     loc_180032221
0x1800322d8  cmp     [rbp+pGroup], r14
0x1800322dc  jz      short loc_180032305
0x1800322de  or      edi, 2
0x1800322e1  mov     rcx, [rbp+hMem]; pSecurityDescriptor
0x1800322e5  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x1800322e9  lea     r8, [rbp+pDacl]; pDacl
0x1800322ed  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800322f1  call    cs:__imp_GetSecurityDescriptorDacl
0x1800322f7  test    eax, eax
0x1800322f9  jnz     short loc_18003231A
0x1800322fb  mov     edx, 1D2h
0x180032300  jmp     loc_180032267
0x180032305  cmp     byte ptr [rbp+arg_10+1], r14b
0x180032309  jz      short loc_1800322E1
0x18003230b  mov     ebx, 0C3000005h
0x180032310  mov     edx, 1D0h
0x180032315  jmp     loc_180032221
0x18003231a  mov     eax, [rbp+bDaclPresent]
0x18003231d  cmp     [rbp+pDacl], r14
0x180032321  jz      short loc_18003232A
0x180032323  test    eax, eax
0x180032325  jz      short loc_18003232E
0x180032327  or      edi, 4
0x18003232a  test    eax, eax
0x18003232c  jnz     short loc_180032341
0x18003232e  test    bl, bl
0x180032330  jz      short loc_180032341
0x180032332  mov     ebx, 0C3000004h
0x180032337  mov     edx, 1D4h
0x18003233c  jmp     loc_180032221
0x180032341  mov     rcx, [rbp+hMem]; pSecurityDescriptor
0x180032345  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x180032349  lea     r8, [rbp+pSacl]; pSacl
0x18003234d  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180032351  call    cs:__imp_GetSecurityDescriptorSacl
0x180032357  test    eax, eax
0x180032359  jnz     short loc_180032365
0x18003235b  mov     edx, 1D6h
0x180032360  jmp     loc_180032267
0x180032365  mov     rcx, [rbp+pSacl]
0x180032369  mov     eax, [rbp+bSaclPresent]
0x18003236c  test    rcx, rcx
0x18003236f  jz      short loc_18003237B
0x180032371  test    eax, eax
0x180032373  jz      short loc_18003237F
0x180032375  or      edi, 40000088h
0x18003237b  test    eax, eax
0x18003237d  jnz     short loc_180032394
0x18003237f  cmp     byte ptr [rbp+arg_10+3], r14b
0x180032383  jz      short loc_180032394
0x180032385  mov     ebx, 0C3000007h
0x18003238a  mov     edx, 1D8h
0x18003238f  jmp     loc_180032221
0x180032394  mov     rax, [rbp+pDacl]
0x180032398  mov     r8d, edi; SecurityInfo
0x18003239b  mov     r9, [rbp+pOwner]; psidOwner
0x18003239f  mov     edx, 1; ObjectType
0x1800323a4  mov     [rsp+70h+var_40], rcx; pSacl
0x1800323a9  mov     rcx, rsi; pObjectName
0x1800323ac  mov     [rsp+70h+var_48], rax; pDacl
0x1800323b1  mov     rax, [rbp+pGroup]
0x1800323b5  mov     [rsp+70h+psidGroup], rax; psidGroup
0x1800323ba  call    cs:__imp_SetNamedSecurityInfoW
0x1800323c0  mov     ebx, eax
0x1800323c2  test    eax, eax
0x1800323c4  jz      short loc_1800323E3
0x1800323c6  jle     short loc_1800323D1
0x1800323c8  movzx   ebx, ax
0x1800323cb  or      ebx, 80070000h
0x1800323d1  test    ebx, ebx
0x1800323d3  jns     loc_180032234
0x1800323d9  mov     edx, 1DBh
0x1800323de  jmp     loc_180032221
0x1800323e3  mov     rcx, [rbp+hMem]; hMem
0x1800323e7  test    rcx, rcx
0x1800323ea  jz      short loc_1800323F2
0x1800323ec  call    cs:__imp_LocalFree
0x1800323f2  xor     eax, eax
0x1800323f4  add     rsp, 70h
0x1800323f8  pop     r14
0x1800323fa  pop     rdi
0x1800323fb  pop     rsi
0x1800323fc  pop     rbx
0x1800323fd  pop     rbp
0x1800323fe  retn
```
