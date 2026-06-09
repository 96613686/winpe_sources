# CRAGroupPolicy::SetMachinePermissions(ushort *,ushort *,void *)

- ea: `0x140010dc4`
- end: `0x1400111c0`
- name: `?SetMachinePermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z`
- size: `1020`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fc0c`

## callees

- `0x14000f458`
- `0x140010dc4`
- `0x1400111c8`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x140010f39`
- `ADVAPI32!InitializeAcl` at `0x140010f39`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400110da`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1400110da`
- `ADVAPI32!GetLengthSid` at `0x140010ed7`
- `ADVAPI32!GetLengthSid` at `0x140010ed7`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010fd0`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001104a`
- `ADVAPI32!AddAccessAllowedAce` at `0x140010fd0`
- `ADVAPI32!AddAccessAllowedAce` at `0x14001104a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140011072`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140011072`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140011097`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x140011097`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400110bc`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1400110bc`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140010e65`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140010e65`
- `ADVAPI32!IsValidAcl` at `0x140010e83`
- `ADVAPI32!IsValidAcl` at `0x140010e83`
- `ADVAPI32!GetAclInformation` at `0x140010eaf`
- `ADVAPI32!GetAclInformation` at `0x140010eaf`
- `ADVAPI32!GetAce` at `0x140010f90`
- `ADVAPI32!GetAce` at `0x140010f90`
- `ADVAPI32!EqualSid` at `0x140010fb0`
- `ADVAPI32!EqualSid` at `0x140010fb0`
- `ADVAPI32!AddAccessDeniedAce` at `0x140010ff9`
- `ADVAPI32!AddAccessDeniedAce` at `0x140010ff9`
- `KERNEL32!GetLastError` at `0x140010e6f`
- `KERNEL32!GetLastError` at `0x140010e8d`
- `KERNEL32!GetLastError` at `0x140010eb9`
- `KERNEL32!GetLastError` at `0x140010f46`
- `KERNEL32!GetLastError` at `0x14001102a`
- `KERNEL32!GetLastError` at `0x140011054`
- `KERNEL32!GetLastError` at `0x14001107c`
- `KERNEL32!GetLastError` at `0x1400110a1`
- `KERNEL32!GetLastError` at `0x1400110c6`
- `KERNEL32!GetLastError` at `0x140010e6f`
- `KERNEL32!GetLastError` at `0x140010e8d`
- `KERNEL32!GetLastError` at `0x140010eb9`
- `KERNEL32!GetLastError` at `0x140010f46`
- `KERNEL32!GetLastError` at `0x14001102a`
- `KERNEL32!GetLastError` at `0x140011054`
- `KERNEL32!GetLastError` at `0x14001107c`
- `KERNEL32!GetLastError` at `0x1400110a1`
- `KERNEL32!GetLastError` at `0x1400110c6`
- `KERNEL32!HeapAlloc` at `0x140010eee`
- `KERNEL32!HeapAlloc` at `0x140010eee`
- `KERNEL32!GetProcessHeap` at `0x140010ee0`
- `KERNEL32!GetProcessHeap` at `0x140011121`
- `KERNEL32!GetProcessHeap` at `0x14001113e`
- `KERNEL32!GetProcessHeap` at `0x14001115c`
- `KERNEL32!GetProcessHeap` at `0x140011177`
- `KERNEL32!GetProcessHeap` at `0x140011191`
- `KERNEL32!GetProcessHeap` at `0x140010ee0`
- `KERNEL32!GetProcessHeap` at `0x140011121`
- `KERNEL32!GetProcessHeap` at `0x14001113e`
- `KERNEL32!GetProcessHeap` at `0x14001115c`
- `KERNEL32!GetProcessHeap` at `0x140011177`
- `KERNEL32!GetProcessHeap` at `0x140011191`
- `KERNEL32!HeapFree` at `0x14001112f`
- `KERNEL32!HeapFree` at `0x14001114c`
- `KERNEL32!HeapFree` at `0x14001116b`
- `KERNEL32!HeapFree` at `0x140011186`
- `KERNEL32!HeapFree` at `0x14001119f`
- `KERNEL32!HeapFree` at `0x14001112f`
- `KERNEL32!HeapFree` at `0x14001114c`
- `KERNEL32!HeapFree` at `0x14001116b`
- `KERNEL32!HeapFree` at `0x140011186`
- `KERNEL32!HeapFree` at `0x14001119f`

## string_xrefs

- `0x140010e40`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x140010f16`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x140010f60`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::SetMachinePermissions(
        CRAGroupPolicy *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        void *a4)
{
  DWORD SDFromRegistry; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  struct _SECURITY_DESCRIPTOR *v7; // rdi
  DWORD LastError; // ebx
  unsigned int v9; // r9d
  int v10; // r14d
  DWORD v11; // r14d
  HANDLE ProcessHeap; // rax
  ACL *v13; // rax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  ACL *v15; // rsi
  DWORD v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  unsigned int v18; // r9d
  DWORD i; // ebx
  CRAGroupPolicy *v20; // rcx
  HANDLE v21; // rax
  PACL v22; // rsi
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  PACL pDacl; // [rsp+30h] [rbp-48h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-40h] BYREF
  PSID pOwner; // [rsp+40h] [rbp-38h] BYREF
  PSID pGroup; // [rsp+48h] [rbp-30h] BYREF
  BOOL bDaclDefaulted; // [rsp+50h] [rbp-28h] BYREF
  BOOL bDaclPresent; // [rsp+54h] [rbp-24h] BYREF
  __int64 pAclInformation; // [rsp+58h] [rbp-20h] BYREF
  int v35; // [rsp+60h] [rbp-18h]

  pAclInformation = 0;
  v35 = 0;
  pSecurityDescriptor = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  SDFromRegistry = CRAGroupPolicy::GetSDFromRegistry(this, a2, a3, &pSecurityDescriptor, (PACL)&pOwner, &pGroup);
  v7 = (struct _SECURITY_DESCRIPTOR *)pSecurityDescriptor;
  LastError = SDFromRegistry;
  if ( SDFromRegistry )
  {
    v9 = 735;
LABEL_3:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetMachinePermissions",
      v6,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v9,
      L"CRAGroupPolicy::SetMachinePermissions",
      0);
    goto LABEL_44;
  }
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v9 = 754;
    goto LABEL_3;
  }
  if ( !IsValidAcl(pDacl) )
  {
    LastError = GetLastError();
    v9 = 760;
    goto LABEL_3;
  }
  if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastError = GetLastError();
    v9 = 776;
    goto LABEL_3;
  }
  v10 = HIDWORD(pAclInformation) + 8;
  v11 = GetLengthSid(a4) + v10;
  ProcessHeap = GetProcessHeap();
  v13 = (ACL *)HeapAlloc(ProcessHeap, 0, v11);
  v15 = v13;
  if ( v13 )
  {
    if ( InitializeAcl(v13, v11, 2u) )
    {
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        pSecurityDescriptor = 0;
        if ( !GetAce(pDacl, i, &pSecurityDescriptor) )
        {
          v16 = GetLastError();
          v18 = 821;
          goto LABEL_14;
        }
        if ( *(_BYTE *)pSecurityDescriptor )
        {
          if ( *(_BYTE *)pSecurityDescriptor != 1 )
          {
            LastError = -2147418113;
            v18 = 882;
            goto LABEL_15;
          }
          if ( !AddAccessDeniedAce(v15, 2u, *((_DWORD *)pSecurityDescriptor + 1), (char *)pSecurityDescriptor + 8) )
          {
            LastError = -2147467259;
            v18 = 872;
            goto LABEL_15;
          }
        }
        else
        {
          if ( EqualSid(a4, (char *)pSecurityDescriptor + 8) )
            goto LABEL_42;
          if ( !AddAccessAllowedAce(v15, 2u, *((_DWORD *)pSecurityDescriptor + 1), (char *)pSecurityDescriptor + 8) )
          {
            v18 = 852;
LABEL_41:
            LastError = -2147467259;
            goto LABEL_15;
          }
        }
      }
      if ( !AddAccessAllowedAce(v15, 2u, 0x15u, a4) )
      {
        v16 = GetLastError();
        v18 = 903;
        goto LABEL_14;
      }
      if ( !SetSecurityDescriptorDacl(v7, 1, v15, 0) )
      {
        v16 = GetLastError();
        v18 = 918;
        goto LABEL_14;
      }
      if ( !SetSecurityDescriptorOwner(v7, pOwner, 0) )
      {
        v16 = GetLastError();
        v18 = 927;
        goto LABEL_14;
      }
      if ( !SetSecurityDescriptorGroup(v7, pGroup, 0) )
      {
        v16 = GetLastError();
        v18 = 936;
        goto LABEL_14;
      }
      if ( !IsValidSecurityDescriptor(v7) )
      {
        LastError = -2147467259;
        v18 = 942;
        goto LABEL_15;
      }
      if ( CRAGroupPolicy::SetSDToRegistry(v20, L"SOFTWARE\\Microsoft\\Ole", L"MachineLaunchRestriction", v7) )
      {
        v18 = 952;
        goto LABEL_41;
      }
LABEL_42:
      LastError = 0;
    }
    else
    {
      v16 = GetLastError();
      v18 = 804;
LABEL_14:
      LastError = v16;
LABEL_15:
      CEventLogger::LogError(
        (CEventLogger *)L"CRAGroupPolicy::SetMachinePermissions",
        v17,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        v18,
        L"CRAGroupPolicy::SetMachinePermissions",
        0);
    }
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v15);
  }
  else
  {
    LastError = 8;
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::SetMachinePermissions",
      v14,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      0x319u,
      L"CRAGroupPolicy::SetMachinePermissions",
      0x8007000E);
  }
LABEL_44:
  v22 = pDacl;
  if ( pDacl )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
    pDacl = 0;
  }
  if ( pOwner )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, pOwner);
  }
  if ( pGroup )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, pGroup);
  }
  if ( v7 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x140010dc4  push    rbp
0x140010dc6  push    rbx
0x140010dc7  push    rsi
0x140010dc8  push    rdi
0x140010dc9  push    r14
0x140010dcb  push    r15
0x140010dcd  mov     rbp, rsp
0x140010dd0  sub     rsp, 78h
0x140010dd4  mov     rax, cs:__security_cookie
0x140010ddb  xor     rax, rsp
0x140010dde  mov     [rbp+var_10], rax
0x140010de2  xor     r14d, r14d
0x140010de5  xor     eax, eax
0x140010de7  mov     [rbp+pAclInformation], rax
0x140010deb  mov     r15, r9
0x140010dee  mov     [rbp+var_18], eax
0x140010df1  lea     r9, [rbp+pSecurityDescriptor]; struct _SECURITY_DESCRIPTOR **
0x140010df5  lea     rax, [rbp+pGroup]
0x140010df9  mov     [rbp+pSecurityDescriptor], r14
0x140010dfd  mov     [rsp+78h+var_50], rax; void **
0x140010e02  lea     rax, [rbp+pOwner]
0x140010e06  mov     [rsp+78h+pSacl], rax; pSacl
0x140010e0b  mov     [rbp+bDaclPresent], r14d
0x140010e0f  mov     [rbp+bDaclDefaulted], r14d
0x140010e13  mov     [rbp+pOwner], r14
0x140010e17  mov     [rbp+pGroup], r14
0x140010e1b  mov     [rbp+pDacl], r14
0x140010e1f  call    ?GetSDFromRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAPEAU_SECURITY_DESCRIPTOR@@PEAPEAX2@Z; CRAGroupPolicy::GetSDFromRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR * *,void * *,void * *)
0x140010e24  mov     rdi, [rbp+pSecurityDescriptor]
0x140010e28  mov     ebx, eax
0x140010e2a  test    eax, eax
0x140010e2c  jz      short loc_140010E56
0x140010e2e  mov     r9d, 2DFh; unsigned int
0x140010e34  lea     rcx, aCragrouppolicy_0; "CRAGroupPolicy::SetMachinePermissions"
0x140010e3b  mov     dword ptr [rsp+78h+var_50], r14d; unsigned int
0x140010e40  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010e47  mov     [rsp+78h+pSacl], rcx; unsigned __int16 *
0x140010e4c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010e51  jmp     loc_140011135
0x140010e56  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x140010e5a  mov     rcx, rdi; pSecurityDescriptor
0x140010e5d  lea     r8, [rbp+pDacl]; pDacl
0x140010e61  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140010e65  call    cs:__imp_GetSecurityDescriptorDacl
0x140010e6b  test    eax, eax
0x140010e6d  jnz     short loc_140010E7F
0x140010e6f  call    cs:__imp_GetLastError
0x140010e75  mov     ebx, eax
0x140010e77  mov     r9d, 2F2h
0x140010e7d  jmp     short loc_140010E34
0x140010e7f  mov     rcx, [rbp+pDacl]; pAcl
0x140010e83  call    cs:__imp_IsValidAcl
0x140010e89  test    eax, eax
0x140010e8b  jnz     short loc_140010E9D
0x140010e8d  call    cs:__imp_GetLastError
0x140010e93  mov     ebx, eax
0x140010e95  mov     r9d, 2F8h
0x140010e9b  jmp     short loc_140010E34
0x140010e9d  mov     rcx, [rbp+pDacl]; pAcl
0x140010ea1  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140010ea5  mov     r9d, 2; dwAclInformationClass
0x140010eab  lea     r8d, [r9+0Ah]; nAclInformationLength
0x140010eaf  call    cs:__imp_GetAclInformation
0x140010eb5  test    eax, eax
0x140010eb7  jnz     short loc_140010ECC
0x140010eb9  call    cs:__imp_GetLastError
0x140010ebf  mov     ebx, eax
0x140010ec1  mov     r9d, 308h
0x140010ec7  jmp     loc_140010E34
0x140010ecc  mov     r14d, dword ptr [rbp+pAclInformation+4]
0x140010ed0  mov     rcx, r15; pSid
0x140010ed3  add     r14d, 8
0x140010ed7  call    cs:__imp_GetLengthSid
0x140010edd  add     r14d, eax
0x140010ee0  call    cs:__imp_GetProcessHeap
0x140010ee6  mov     r8d, r14d; dwBytes
0x140010ee9  xor     edx, edx; dwFlags
0x140010eeb  mov     rcx, rax; hHeap
0x140010eee  call    cs:__imp_HeapAlloc
0x140010ef4  mov     rsi, rax
0x140010ef7  test    rax, rax
0x140010efa  jnz     short loc_140010F2D
0x140010efc  lea     rcx, aCragrouppolicy_0; "CRAGroupPolicy::SetMachinePermissions"
0x140010f03  mov     dword ptr [rsp+78h+var_50], 8007000Eh; unsigned int
0x140010f0b  mov     r9d, 319h; unsigned int
0x140010f11  mov     [rsp+78h+pSacl], rcx; unsigned __int16 *
0x140010f16  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010f1d  lea     ebx, [rax+8]
0x140010f20  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010f25  xor     r14d, r14d
0x140010f28  jmp     loc_140011135
0x140010f2d  mov     r8d, 2; dwAclRevision
0x140010f33  mov     edx, r14d; nAclLength
0x140010f36  mov     rcx, rsi; pAcl
0x140010f39  call    cs:__imp_InitializeAcl
0x140010f3f  xor     r14d, r14d
0x140010f42  test    eax, eax
0x140010f44  jnz     short loc_140010F76
0x140010f46  call    cs:__imp_GetLastError
0x140010f4c  mov     r9d, 324h; unsigned int
0x140010f52  mov     ebx, eax
0x140010f54  lea     rcx, aCragrouppolicy_0; "CRAGroupPolicy::SetMachinePermissions"
0x140010f5b  mov     dword ptr [rsp+78h+var_50], r14d; unsigned int
0x140010f60  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010f67  mov     [rsp+78h+pSacl], rcx; unsigned __int16 *
0x140010f6c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140010f71  jmp     loc_140011121
0x140010f76  mov     ebx, r14d
0x140010f79  cmp     ebx, dword ptr [rbp+pAclInformation]
0x140010f7c  jnb     loc_14001103B
0x140010f82  mov     rcx, [rbp+pDacl]; pAcl
0x140010f86  lea     r8, [rbp+pSecurityDescriptor]; pAce
0x140010f8a  mov     edx, ebx; dwAceIndex
0x140010f8c  mov     [rbp+pSecurityDescriptor], r14
0x140010f90  call    cs:__imp_GetAce
0x140010f96  test    eax, eax
0x140010f98  jz      loc_14001102A
0x140010f9e  mov     r8, [rbp+pSecurityDescriptor]
0x140010fa2  mov     al, [r8]
0x140010fa5  test    al, al
0x140010fa7  jnz     short loc_140010FE5
0x140010fa9  lea     rdx, [r8+8]; pSid2
0x140010fad  mov     rcx, r15; pSid1
0x140010fb0  call    cs:__imp_EqualSid
0x140010fb6  test    eax, eax
0x140010fb8  jnz     loc_14001111E
0x140010fbe  mov     r8, [rbp+pSecurityDescriptor]
0x140010fc2  lea     edx, [rax+2]; dwAceRevision
0x140010fc5  mov     rcx, rsi; pAcl
0x140010fc8  lea     r9, [r8+8]; pSid
0x140010fcc  mov     r8d, [r8+4]; AccessMask
0x140010fd0  call    cs:__imp_AddAccessAllowedAce
0x140010fd6  test    eax, eax
0x140010fd8  jnz     short loc_140011003
0x140010fda  mov     r9d, 354h
0x140010fe0  jmp     loc_140011114
0x140010fe5  cmp     al, 1
0x140010fe7  jnz     short loc_14001101A
0x140010fe9  lea     r9, [r8+8]; pSid
0x140010fed  mov     edx, 2; dwAceRevision
0x140010ff2  mov     r8d, [r8+4]; AccessMask
0x140010ff6  mov     rcx, rsi; pAcl
0x140010ff9  call    cs:__imp_AddAccessDeniedAce
0x140010fff  test    eax, eax
0x140011001  jz      short loc_14001100A
0x140011003  inc     ebx
0x140011005  jmp     loc_140010F79
0x14001100a  mov     ebx, 80004005h
0x14001100f  mov     r9d, 368h
0x140011015  jmp     loc_140010F54
0x14001101a  mov     ebx, 8000FFFFh
0x14001101f  mov     r9d, 372h
0x140011025  jmp     loc_140010F54
0x14001102a  call    cs:__imp_GetLastError
0x140011030  mov     r9d, 335h
0x140011036  jmp     loc_140010F52
0x14001103b  mov     edx, 2; dwAceRevision
0x140011040  mov     r9, r15; pSid
0x140011043  mov     rcx, rsi; pAcl
0x140011046  lea     r8d, [rdx+13h]; AccessMask
0x14001104a  call    cs:__imp_AddAccessAllowedAce
0x140011050  test    eax, eax
0x140011052  jnz     short loc_140011065
0x140011054  call    cs:__imp_GetLastError
0x14001105a  mov     r9d, 387h
0x140011060  jmp     loc_140010F52
0x140011065  xor     r9d, r9d; bDaclDefaulted
0x140011068  mov     r8, rsi; pDacl
0x14001106b  mov     rcx, rdi; pSecurityDescriptor
0x14001106e  lea     edx, [r9+1]; bDaclPresent
0x140011072  call    cs:__imp_SetSecurityDescriptorDacl
0x140011078  test    eax, eax
0x14001107a  jnz     short loc_14001108D
0x14001107c  call    cs:__imp_GetLastError
0x140011082  mov     r9d, 396h
0x140011088  jmp     loc_140010F52
0x14001108d  mov     rdx, [rbp+pOwner]; pOwner
0x140011091  xor     r8d, r8d; bOwnerDefaulted
0x140011094  mov     rcx, rdi; pSecurityDescriptor
0x140011097  call    cs:__imp_SetSecurityDescriptorOwner
0x14001109d  test    eax, eax
0x14001109f  jnz     short loc_1400110B2
0x1400110a1  call    cs:__imp_GetLastError
0x1400110a7  mov     r9d, 39Fh
0x1400110ad  jmp     loc_140010F52
0x1400110b2  mov     rdx, [rbp+pGroup]; pGroup
0x1400110b6  xor     r8d, r8d; bGroupDefaulted
0x1400110b9  mov     rcx, rdi; pSecurityDescriptor
0x1400110bc  call    cs:__imp_SetSecurityDescriptorGroup
0x1400110c2  test    eax, eax
0x1400110c4  jnz     short loc_1400110D7
0x1400110c6  call    cs:__imp_GetLastError
0x1400110cc  mov     r9d, 3A8h
0x1400110d2  jmp     loc_140010F52
0x1400110d7  mov     rcx, rdi; pSecurityDescriptor
0x1400110da  call    cs:__imp_IsValidSecurityDescriptor
0x1400110e0  test    eax, eax
0x1400110e2  jnz     short loc_1400110F4
0x1400110e4  mov     ebx, 80004005h
0x1400110e9  mov     r9d, 3AEh
0x1400110ef  jmp     loc_140010F54
0x1400110f4  mov     r9, rdi; struct _SECURITY_DESCRIPTOR *
0x1400110f7  lea     r8, ValueName; "MachineLaunchRestriction"
0x1400110fe  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Ole"
0x140011105  call    ?SetSDToRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAU_SECURITY_DESCRIPTOR@@@Z; CRAGroupPolicy::SetSDToRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR *)
0x14001110a  test    eax, eax
0x14001110c  jz      short loc_14001111E
0x14001110e  mov     r9d, 3B8h
0x140011114  mov     ebx, 80004005h
0x140011119  jmp     loc_140010F54
0x14001111e  mov     ebx, r14d
0x140011121  call    cs:__imp_GetProcessHeap
0x140011127  mov     r8, rsi; lpMem
0x14001112a  xor     edx, edx; dwFlags
0x14001112c  mov     rcx, rax; hHeap
0x14001112f  call    cs:__imp_HeapFree
0x140011135  mov     rsi, [rbp+pDacl]
0x140011139  test    rsi, rsi
0x14001113c  jz      short loc_140011156
0x14001113e  call    cs:__imp_GetProcessHeap
0x140011144  mov     r8, rsi; lpMem
0x140011147  xor     edx, edx; dwFlags
0x140011149  mov     rcx, rax; hHeap
0x14001114c  call    cs:__imp_HeapFree
0x140011152  mov     [rbp+pDacl], r14
0x140011156  cmp     [rbp+pOwner], r14
0x14001115a  jz      short loc_140011171
0x14001115c  call    cs:__imp_GetProcessHeap
0x140011162  mov     r8, [rbp+pOwner]; lpMem
0x140011166  xor     edx, edx; dwFlags
0x140011168  mov     rcx, rax; hHeap
0x14001116b  call    cs:__imp_HeapFree
0x140011171  cmp     [rbp+pGroup], r14
0x140011175  jz      short loc_14001118C
0x140011177  call    cs:__imp_GetProcessHeap
0x14001117d  mov     r8, [rbp+pGroup]; lpMem
0x140011181  xor     edx, edx; dwFlags
0x140011183  mov     rcx, rax; hHeap
0x140011186  call    cs:__imp_HeapFree
0x14001118c  test    rdi, rdi
0x14001118f  jz      short loc_1400111A5
0x140011191  call    cs:__imp_GetProcessHeap
0x140011197  mov     r8, rdi; lpMem
0x14001119a  xor     edx, edx; dwFlags
0x14001119c  mov     rcx, rax; hHeap
0x14001119f  call    cs:__imp_HeapFree
0x1400111a5  mov     eax, ebx
0x1400111a7  mov     rcx, [rbp+var_10]
0x1400111ab  xor     rcx, rsp; StackCookie
0x1400111ae  call    __security_check_cookie
0x1400111b3  add     rsp, 78h
0x1400111b7  pop     r15
0x1400111b9  pop     r14
0x1400111bb  pop     rdi
0x1400111bc  pop     rsi
0x1400111bd  pop     rbx
0x1400111be  pop     rbp
0x1400111bf  retn
```
