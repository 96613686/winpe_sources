# BfspSetSecurityDescriptor

- ea: `0x18004d500`
- end: `0x18004d770`
- name: `BfspSetSecurityDescriptor`
- size: `624`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180049234`
- `0x18004d3e0`

## callees

- `0x180047280`
- `0x18004cdd4`
- `0x18004d500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d751`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d745`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004d62c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004d62c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004d648`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18004d648`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004d5f9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18004d5f9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004d59b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004d59b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004d5ca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18004d5ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d56c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d56c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004d68c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004d70f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004d68c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004d70f`

## string_xrefs

- `0x18004d60d`: `GetSecurityDescriptorGroup failed! Error code = %#x`
- `0x18004d5de`: `GetSecurityDescriptorOwner failed! Error code = %#x`
- `0x18004d5af`: `GetSecurityDescriptorControl failed! Error code = %#x`
- `0x18004d580`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed! Error code = %#x`
- `0x18004d69b`: `SetNamedSecurityInfo failed! Error code = %#x`
- `0x18004d72b`: `SetNamedSecurityInfo failed! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspSetSecurityDescriptor(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)
{
  unsigned int SecurityDescriptorControl; // edi
  __int64 LastError; // rbx
  SECURITY_INFORMATION v5; // r8d
  DWORD v6; // eax
  SECURITY_INFORMATION v7; // r8d
  DWORD v8; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL bSaclPresent; // [rsp+48h] [rbp-11h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD dwRevision; // [rsp+50h] [rbp-9h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+54h] [rbp-5h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+58h] [rbp-1h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+5Ch] [rbp+3h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+60h] [rbp+7h] BYREF
  PSID pOwner; // [rsp+68h] [rbp+Fh] BYREF
  PSID pGroup; // [rsp+70h] [rbp+17h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+1Fh] BYREF
  PACL pDacl; // [rsp+80h] [rbp+27h] BYREF
  WORD pControl; // [rsp+D0h] [rbp+77h] BYREF
  WINBOOL bDaclPresent; // [rsp+D8h] [rbp+7Fh] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pGroup = 0;
  bGroupDefaulted = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pControl = 0;
  dwRevision = 0;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorControl = ConvertStringSecurityDescriptorToSecurityDescriptorW(
                                StringSecurityDescriptor,
                                1u,
                                &SecurityDescriptor,
                                &SecurityDescriptorSize);
  if ( SecurityDescriptorControl )
  {
    SecurityDescriptorControl = GetSecurityDescriptorControl(SecurityDescriptor, &pControl, &dwRevision);
    if ( SecurityDescriptorControl )
    {
      SecurityDescriptorControl = GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted);
      if ( SecurityDescriptorControl )
      {
        SecurityDescriptorControl = GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bGroupDefaulted);
        if ( SecurityDescriptorControl
          && (SecurityDescriptorControl = GetSecurityDescriptorDacl(
                                            SecurityDescriptor,
                                            &bDaclPresent,
                                            &pDacl,
                                            &bDaclDefaulted)) != 0
          && (SecurityDescriptorControl = GetSecurityDescriptorSacl(
                                            SecurityDescriptor,
                                            &bSaclPresent,
                                            &pSacl,
                                            &bSaclDefaulted)) != 0 )
        {
          LODWORD(LastError) = 0;
          v5 = pOwner != 0;
          if ( pGroup )
            v5 |= 2u;
          if ( v5
            && (v6 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, v5, pOwner, pGroup, 0, 0),
                (LODWORD(LastError) = v6) != 0) )
          {
            SecurityDescriptorControl = 0;
            BfspLogMessage(2, L"SetNamedSecurityInfo failed! Error code = %#x", v6);
          }
          else
          {
            v7 = 0;
            if ( bDaclPresent )
            {
              v7 = 4;
              if ( (pControl & 0x1000) != 0 )
                v7 = -2147483644;
            }
            if ( bSaclPresent )
            {
              v7 |= 8u;
              if ( (pControl & 0x2000) != 0 )
                v7 |= 0x40000000u;
            }
            if ( v7 )
            {
              v8 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, v7, 0, 0, pDacl, pSacl);
              LODWORD(LastError) = v8;
              if ( v8 )
              {
                SecurityDescriptorControl = 0;
                BfspPrintOwnerProcessOnSharingError(pObjectName, v8);
                BfspLogMessage(4, L"SetNamedSecurityInfo failed! Error code = %#x", (unsigned int)LastError);
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          BfspLogMessage(4, L"GetSecurityDescriptorGroup failed! Error code = %#x", LastError);
        }
      }
      else
      {
        LastError = GetLastError();
        BfspLogMessage(4, L"GetSecurityDescriptorOwner failed! Error code = %#x", LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      BfspLogMessage(4, L"GetSecurityDescriptorControl failed! Error code = %#x", LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    BfspLogMessage(4, L"ConvertStringSecurityDescriptorToSecurityDescriptor failed! Error code = %#x", LastError);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( !SecurityDescriptorControl )
    SetLastError(LastError);
  return SecurityDescriptorControl;
}

```

## disassembly

```asm
0x18004d500  mov     [rsp-8+arg_0], rbx
0x18004d505  push    rbp
0x18004d506  push    rsi
0x18004d507  push    rdi
0x18004d508  push    r14
0x18004d50a  push    r15
0x18004d50c  lea     rbp, [rsp-37h]
0x18004d511  sub     rsp, 90h
0x18004d518  xor     r14d, r14d
0x18004d51b  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18004d51f  mov     r10, rdx
0x18004d522  mov     [rbp+57h+pDacl], r14
0x18004d526  mov     rsi, rcx
0x18004d529  mov     [rbp+57h+bDaclPresent], r14d
0x18004d52d  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004d531  mov     [rbp+57h+bDaclDefaulted], r14d
0x18004d535  lea     r15d, [r14+1]
0x18004d539  mov     [rbp+57h+pGroup], r14
0x18004d53d  mov     edx, r15d; StringSDRevision
0x18004d540  mov     [rbp+57h+bGroupDefaulted], r14d
0x18004d544  mov     rcx, r10; StringSecurityDescriptor
0x18004d547  mov     [rbp+57h+pOwner], r14
0x18004d54b  mov     [rbp+57h+bOwnerDefaulted], r14d
0x18004d54f  mov     [rbp+57h+pSacl], r14
0x18004d553  mov     [rbp+57h+bSaclPresent], r14d
0x18004d557  mov     [rbp+57h+bSaclDefaulted], r14d
0x18004d55b  mov     [rbp+57h+pControl], r14w
0x18004d560  mov     [rbp+57h+dwRevision], r14d
0x18004d564  mov     [rbp+57h+SecurityDescriptorSize], r14d
0x18004d568  mov     [rbp+57h+SecurityDescriptor], r14
0x18004d56c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d572  mov     edi, eax
0x18004d574  test    eax, eax
0x18004d576  jnz     short loc_18004D58F
0x18004d578  call    cs:__imp_GetLastError
0x18004d57e  mov     ebx, eax
0x18004d580  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x18004d587  mov     r8d, eax
0x18004d58a  jmp     loc_18004D732
0x18004d58f  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d593  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18004d597  lea     rdx, [rbp+57h+pControl]; pControl
0x18004d59b  call    cs:__imp_GetSecurityDescriptorControl
0x18004d5a1  mov     edi, eax
0x18004d5a3  test    eax, eax
0x18004d5a5  jnz     short loc_18004D5BE
0x18004d5a7  call    cs:__imp_GetLastError
0x18004d5ad  mov     ebx, eax
0x18004d5af  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorControl failed! Er"...
0x18004d5b6  mov     r8d, eax
0x18004d5b9  jmp     loc_18004D732
0x18004d5be  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d5c2  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004d5c6  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18004d5ca  call    cs:__imp_GetSecurityDescriptorOwner
0x18004d5d0  mov     edi, eax
0x18004d5d2  test    eax, eax
0x18004d5d4  jnz     short loc_18004D5ED
0x18004d5d6  call    cs:__imp_GetLastError
0x18004d5dc  mov     ebx, eax
0x18004d5de  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorOwner failed! Erro"...
0x18004d5e5  mov     r8d, eax
0x18004d5e8  jmp     loc_18004D732
0x18004d5ed  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d5f1  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x18004d5f5  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18004d5f9  call    cs:__imp_GetSecurityDescriptorGroup
0x18004d5ff  mov     edi, eax
0x18004d601  test    eax, eax
0x18004d603  jnz     short loc_18004D61C
0x18004d605  call    cs:__imp_GetLastError
0x18004d60b  mov     ebx, eax
0x18004d60d  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorGroup failed! Erro"...
0x18004d614  mov     r8d, eax
0x18004d617  jmp     loc_18004D732
0x18004d61c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d620  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18004d624  lea     r8, [rbp+57h+pDacl]; pDacl
0x18004d628  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18004d62c  call    cs:__imp_GetSecurityDescriptorDacl
0x18004d632  mov     edi, eax
0x18004d634  test    eax, eax
0x18004d636  jz      short loc_18004D605
0x18004d638  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18004d63c  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18004d640  lea     r8, [rbp+57h+pSacl]; pSacl
0x18004d644  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18004d648  call    cs:__imp_GetSecurityDescriptorSacl
0x18004d64e  mov     edi, eax
0x18004d650  test    eax, eax
0x18004d652  jz      short loc_18004D605
0x18004d654  mov     r9, [rbp+57h+pOwner]; psidOwner
0x18004d658  mov     r8d, r14d
0x18004d65b  mov     rax, [rbp+57h+pGroup]
0x18004d65f  test    r9, r9
0x18004d662  mov     ebx, r14d
0x18004d665  cmovnz  r8d, r15d
0x18004d669  test    rax, rax
0x18004d66c  jz      short loc_18004D672
0x18004d66e  or      r8d, 2; SecurityInfo
0x18004d672  test    r8d, r8d
0x18004d675  jz      short loc_18004D6AF
0x18004d677  mov     [rsp+0B0h+var_80], r14; pSacl
0x18004d67c  mov     edx, r15d; ObjectType
0x18004d67f  mov     [rsp+0B0h+var_88], r14; pDacl
0x18004d684  mov     rcx, rsi; pObjectName
0x18004d687  mov     [rsp+0B0h+psidGroup], rax; psidGroup
0x18004d68c  call    cs:__imp_SetNamedSecurityInfoW
0x18004d692  mov     ebx, eax
0x18004d694  test    eax, eax
0x18004d696  jz      short loc_18004D6AF
0x18004d698  mov     edi, r14d
0x18004d69b  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x18004d6a2  mov     r8d, eax
0x18004d6a5  mov     ecx, 2
0x18004d6aa  jmp     loc_18004D737
0x18004d6af  mov     r8d, r14d
0x18004d6b2  cmp     [rbp+57h+bDaclPresent], r14d
0x18004d6b6  jz      short loc_18004D6D0
0x18004d6b8  mov     eax, 1000h
0x18004d6bd  mov     r8d, 4
0x18004d6c3  test    [rbp+57h+pControl], ax
0x18004d6c7  mov     eax, 80000004h
0x18004d6cc  cmovnz  r8d, eax
0x18004d6d0  cmp     [rbp+57h+bSaclPresent], r14d
0x18004d6d4  jz      short loc_18004D6EA
0x18004d6d6  or      r8d, 8
0x18004d6da  mov     eax, 2000h
0x18004d6df  test    [rbp+57h+pControl], ax
0x18004d6e3  jz      short loc_18004D6EA
0x18004d6e5  bts     r8d, 1Eh; SecurityInfo
0x18004d6ea  test    r8d, r8d
0x18004d6ed  jz      short loc_18004D73C
0x18004d6ef  mov     rax, [rbp+57h+pSacl]
0x18004d6f3  xor     r9d, r9d; psidOwner
0x18004d6f6  mov     [rsp+0B0h+var_80], rax; pSacl
0x18004d6fb  mov     edx, r15d; ObjectType
0x18004d6fe  mov     rax, [rbp+57h+pDacl]
0x18004d702  mov     rcx, rsi; pObjectName
0x18004d705  mov     [rsp+0B0h+var_88], rax; pDacl
0x18004d70a  mov     [rsp+0B0h+psidGroup], r14; psidGroup
0x18004d70f  call    cs:__imp_SetNamedSecurityInfoW
0x18004d715  mov     ebx, eax
0x18004d717  test    eax, eax
0x18004d719  jz      short loc_18004D73C
0x18004d71b  mov     edx, eax
0x18004d71d  mov     rcx, rsi
0x18004d720  mov     edi, r14d
0x18004d723  call    BfspPrintOwnerProcessOnSharingError
0x18004d728  mov     r8d, ebx
0x18004d72b  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x18004d732  mov     ecx, 4
0x18004d737  call    BfspLogMessage
0x18004d73c  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18004d740  test    rcx, rcx
0x18004d743  jz      short loc_18004D74B
0x18004d745  call    cs:__imp_LocalFree
0x18004d74b  test    edi, edi
0x18004d74d  jnz     short loc_18004D757
0x18004d74f  mov     ecx, ebx; dwErrCode
0x18004d751  call    cs:__imp_SetLastError
0x18004d757  mov     rbx, [rsp+0B0h+arg_0]
0x18004d75f  mov     eax, edi
0x18004d761  add     rsp, 90h
0x18004d768  pop     r15
0x18004d76a  pop     r14
0x18004d76c  pop     rdi
0x18004d76d  pop     rsi
0x18004d76e  pop     rbp
0x18004d76f  retn
```
