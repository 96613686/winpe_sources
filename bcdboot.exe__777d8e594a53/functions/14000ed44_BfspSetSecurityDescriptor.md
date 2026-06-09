# BfspSetSecurityDescriptor

- ea: `0x14000ed44`
- end: `0x14000efbf`
- name: `BfspSetSecurityDescriptor`
- size: `635`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140009fd4`
- `0x14000ec18`

## callees

- `0x140003368`
- `0x14000e628`
- `0x14000ed44`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000efa0`
- `KERNEL32!SetLastError` at `0x14000efa0`
- `KERNEL32!GetLastError` at `0x14000edbc`
- `KERNEL32!GetLastError` at `0x14000edeb`
- `KERNEL32!GetLastError` at `0x14000ee1a`
- `KERNEL32!GetLastError` at `0x14000ee49`
- `KERNEL32!GetLastError` at `0x14000edbc`
- `KERNEL32!GetLastError` at `0x14000edeb`
- `KERNEL32!GetLastError` at `0x14000ee1a`
- `KERNEL32!GetLastError` at `0x14000ee49`
- `KERNEL32!LocalFree` at `0x14000ef94`
- `KERNEL32!LocalFree` at `0x14000ef94`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000ee8c`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x14000ee8c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14000ee70`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14000ee70`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14000ee3d`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x14000ee3d`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14000eed0`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14000ef53`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14000eed0`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14000ef53`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14000eddf`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x14000eddf`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14000ee0e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x14000ee0e`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000edb0`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000edb0`

## string_xrefs

- `0x14000edc4`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed! Error code = %#x`
- `0x14000ee22`: `GetSecurityDescriptorOwner failed! Error code = %#x`
- `0x14000edf3`: `GetSecurityDescriptorControl failed! Error code = %#x`
- `0x14000eedf`: `SetNamedSecurityInfo failed! Error code = %#x`
- `0x14000ef7a`: `SetNamedSecurityInfo failed! Error code = %#x`
- `0x14000ee51`: `GetSecurityDescriptorGroup failed! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspSetSecurityDescriptor(WCHAR *lpFileName, LPCWSTR StringSecurityDescriptor)
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
            && (v6 = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, v5, pOwner, pGroup, 0, 0),
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
              v8 = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, v7, 0, 0, pDacl, pSacl);
              LODWORD(LastError) = v8;
              if ( v8 )
              {
                SecurityDescriptorControl = 0;
                if ( v8 == 5 || v8 - 32 <= 1 )
                  BfspPrintFileOwnerProcess(lpFileName);
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
0x14000ed44  mov     [rsp-8+arg_0], rbx
0x14000ed49  push    rbp
0x14000ed4a  push    rsi
0x14000ed4b  push    rdi
0x14000ed4c  push    r14
0x14000ed4e  push    r15
0x14000ed50  lea     rbp, [rsp-37h]
0x14000ed55  sub     rsp, 90h
0x14000ed5c  xor     r14d, r14d
0x14000ed5f  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x14000ed63  mov     r10, rdx
0x14000ed66  mov     [rbp+57h+pDacl], r14
0x14000ed6a  mov     rsi, rcx
0x14000ed6d  mov     [rbp+57h+bDaclPresent], r14d
0x14000ed71  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14000ed75  mov     [rbp+57h+bDaclDefaulted], r14d
0x14000ed79  lea     r15d, [r14+1]
0x14000ed7d  mov     [rbp+57h+pGroup], r14
0x14000ed81  mov     edx, r15d; StringSDRevision
0x14000ed84  mov     [rbp+57h+bGroupDefaulted], r14d
0x14000ed88  mov     rcx, r10; StringSecurityDescriptor
0x14000ed8b  mov     [rbp+57h+pOwner], r14
0x14000ed8f  mov     [rbp+57h+bOwnerDefaulted], r14d
0x14000ed93  mov     [rbp+57h+pSacl], r14
0x14000ed97  mov     [rbp+57h+bSaclPresent], r14d
0x14000ed9b  mov     [rbp+57h+bSaclDefaulted], r14d
0x14000ed9f  mov     [rbp+57h+pControl], r14w
0x14000eda4  mov     [rbp+57h+dwRevision], r14d
0x14000eda8  mov     [rbp+57h+SecurityDescriptorSize], r14d
0x14000edac  mov     [rbp+57h+SecurityDescriptor], r14
0x14000edb0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14000edb6  mov     edi, eax
0x14000edb8  test    eax, eax
0x14000edba  jnz     short loc_14000EDD3
0x14000edbc  call    cs:__imp_GetLastError
0x14000edc2  mov     ebx, eax
0x14000edc4  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x14000edcb  mov     r8d, eax
0x14000edce  jmp     loc_14000EF81
0x14000edd3  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14000edd7  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x14000eddb  lea     rdx, [rbp+57h+pControl]; pControl
0x14000eddf  call    cs:__imp_GetSecurityDescriptorControl
0x14000ede5  mov     edi, eax
0x14000ede7  test    eax, eax
0x14000ede9  jnz     short loc_14000EE02
0x14000edeb  call    cs:__imp_GetLastError
0x14000edf1  mov     ebx, eax
0x14000edf3  lea     rdx, aGetsecuritydes_1; "GetSecurityDescriptorControl failed! Er"...
0x14000edfa  mov     r8d, eax
0x14000edfd  jmp     loc_14000EF81
0x14000ee02  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14000ee06  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x14000ee0a  lea     rdx, [rbp+57h+pOwner]; pOwner
0x14000ee0e  call    cs:__imp_GetSecurityDescriptorOwner
0x14000ee14  mov     edi, eax
0x14000ee16  test    eax, eax
0x14000ee18  jnz     short loc_14000EE31
0x14000ee1a  call    cs:__imp_GetLastError
0x14000ee20  mov     ebx, eax
0x14000ee22  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorOwner failed! Erro"...
0x14000ee29  mov     r8d, eax
0x14000ee2c  jmp     loc_14000EF81
0x14000ee31  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14000ee35  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x14000ee39  lea     rdx, [rbp+57h+pGroup]; pGroup
0x14000ee3d  call    cs:__imp_GetSecurityDescriptorGroup
0x14000ee43  mov     edi, eax
0x14000ee45  test    eax, eax
0x14000ee47  jnz     short loc_14000EE60
0x14000ee49  call    cs:__imp_GetLastError
0x14000ee4f  mov     ebx, eax
0x14000ee51  lea     rdx, aGetsecuritydes; "GetSecurityDescriptorGroup failed! Erro"...
0x14000ee58  mov     r8d, eax
0x14000ee5b  jmp     loc_14000EF81
0x14000ee60  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14000ee64  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x14000ee68  lea     r8, [rbp+57h+pDacl]; pDacl
0x14000ee6c  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x14000ee70  call    cs:__imp_GetSecurityDescriptorDacl
0x14000ee76  mov     edi, eax
0x14000ee78  test    eax, eax
0x14000ee7a  jz      short loc_14000EE49
0x14000ee7c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14000ee80  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x14000ee84  lea     r8, [rbp+57h+pSacl]; pSacl
0x14000ee88  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x14000ee8c  call    cs:__imp_GetSecurityDescriptorSacl
0x14000ee92  mov     edi, eax
0x14000ee94  test    eax, eax
0x14000ee96  jz      short loc_14000EE49
0x14000ee98  mov     r9, [rbp+57h+pOwner]; psidOwner
0x14000ee9c  mov     r8d, r14d
0x14000ee9f  mov     rax, [rbp+57h+pGroup]
0x14000eea3  test    r9, r9
0x14000eea6  mov     ebx, r14d
0x14000eea9  cmovnz  r8d, r15d
0x14000eead  test    rax, rax
0x14000eeb0  jz      short loc_14000EEB6
0x14000eeb2  or      r8d, 2; SecurityInfo
0x14000eeb6  test    r8d, r8d
0x14000eeb9  jz      short loc_14000EEF3
0x14000eebb  mov     [rsp+0B0h+var_80], r14; pSacl
0x14000eec0  mov     edx, r15d; ObjectType
0x14000eec3  mov     [rsp+0B0h+var_88], r14; pDacl
0x14000eec8  mov     rcx, rsi; pObjectName
0x14000eecb  mov     [rsp+0B0h+psidGroup], rax; psidGroup
0x14000eed0  call    cs:__imp_SetNamedSecurityInfoW
0x14000eed6  mov     ebx, eax
0x14000eed8  test    eax, eax
0x14000eeda  jz      short loc_14000EEF3
0x14000eedc  mov     edi, r14d
0x14000eedf  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x14000eee6  mov     r8d, eax
0x14000eee9  mov     ecx, 2
0x14000eeee  jmp     loc_14000EF86
0x14000eef3  mov     r8d, r14d
0x14000eef6  cmp     [rbp+57h+bDaclPresent], r14d
0x14000eefa  jz      short loc_14000EF14
0x14000eefc  mov     eax, 1000h
0x14000ef01  mov     r8d, 4
0x14000ef07  test    [rbp+57h+pControl], ax
0x14000ef0b  mov     eax, 80000004h
0x14000ef10  cmovnz  r8d, eax
0x14000ef14  cmp     [rbp+57h+bSaclPresent], r14d
0x14000ef18  jz      short loc_14000EF2E
0x14000ef1a  or      r8d, 8
0x14000ef1e  mov     eax, 2000h
0x14000ef23  test    [rbp+57h+pControl], ax
0x14000ef27  jz      short loc_14000EF2E
0x14000ef29  bts     r8d, 1Eh; SecurityInfo
0x14000ef2e  test    r8d, r8d
0x14000ef31  jz      short loc_14000EF8B
0x14000ef33  mov     rax, [rbp+57h+pSacl]
0x14000ef37  xor     r9d, r9d; psidOwner
0x14000ef3a  mov     [rsp+0B0h+var_80], rax; pSacl
0x14000ef3f  mov     edx, r15d; ObjectType
0x14000ef42  mov     rax, [rbp+57h+pDacl]
0x14000ef46  mov     rcx, rsi; pObjectName
0x14000ef49  mov     [rsp+0B0h+var_88], rax; pDacl
0x14000ef4e  mov     [rsp+0B0h+psidGroup], r14; psidGroup
0x14000ef53  call    cs:__imp_SetNamedSecurityInfoW
0x14000ef59  mov     ebx, eax
0x14000ef5b  test    eax, eax
0x14000ef5d  jz      short loc_14000EF8B
0x14000ef5f  mov     edi, r14d
0x14000ef62  cmp     eax, 5
0x14000ef65  jz      short loc_14000EF6F
0x14000ef67  add     eax, 0FFFFFFE0h
0x14000ef6a  cmp     eax, r15d
0x14000ef6d  ja      short loc_14000EF77
0x14000ef6f  mov     rcx, rsi; lpFileName
0x14000ef72  call    BfspPrintFileOwnerProcess
0x14000ef77  mov     r8d, ebx
0x14000ef7a  lea     rdx, aSetnamedsecuri; "SetNamedSecurityInfo failed! Error code"...
0x14000ef81  mov     ecx, 4
0x14000ef86  call    BfspLogMessage
0x14000ef8b  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x14000ef8f  test    rcx, rcx
0x14000ef92  jz      short loc_14000EF9A
0x14000ef94  call    cs:__imp_LocalFree
0x14000ef9a  test    edi, edi
0x14000ef9c  jnz     short loc_14000EFA6
0x14000ef9e  mov     ecx, ebx; dwErrCode
0x14000efa0  call    cs:__imp_SetLastError
0x14000efa6  mov     rbx, [rsp+0B0h+arg_0]
0x14000efae  mov     eax, edi
0x14000efb0  add     rsp, 90h
0x14000efb7  pop     r15
0x14000efb9  pop     r14
0x14000efbb  pop     rdi
0x14000efbc  pop     rsi
0x14000efbd  pop     rbp
0x14000efbe  retn
```
