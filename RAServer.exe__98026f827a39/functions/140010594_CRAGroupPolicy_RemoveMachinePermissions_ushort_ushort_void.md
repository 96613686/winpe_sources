# CRAGroupPolicy::RemoveMachinePermissions(ushort *,ushort *,void *)

- ea: `0x140010594`
- end: `0x140010860`
- name: `?RemoveMachinePermissions@CRAGroupPolicy@@AEAAKPEAG0PEAX@Z`
- size: `716`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000fcf4`

## callees

- `0x14000f458`
- `0x140010594`
- `0x1400111c8`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x140010783`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140010783`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140010702`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140010702`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14001073c`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14001073c`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140010763`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x140010763`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140010640`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140010640`
- `ADVAPI32!IsValidAcl` at `0x14001065e`
- `ADVAPI32!IsValidAcl` at `0x14001065e`
- `ADVAPI32!GetAclInformation` at `0x14001068a`
- `ADVAPI32!GetAclInformation` at `0x14001068a`
- `ADVAPI32!GetAce` at `0x1400106b9`
- `ADVAPI32!GetAce` at `0x1400106b9`
- `ADVAPI32!EqualSid` at `0x1400106d8`
- `ADVAPI32!EqualSid` at `0x1400106d8`
- `ADVAPI32!DeleteAce` at `0x1400106ec`
- `ADVAPI32!DeleteAce` at `0x1400106ec`
- `KERNEL32!GetLastError` at `0x14001064a`
- `KERNEL32!GetLastError` at `0x140010668`
- `KERNEL32!GetLastError` at `0x140010694`
- `KERNEL32!GetLastError` at `0x14001070c`
- `KERNEL32!GetLastError` at `0x14001071f`
- `KERNEL32!GetLastError` at `0x140010746`
- `KERNEL32!GetLastError` at `0x14001076d`
- `KERNEL32!GetLastError` at `0x14001064a`
- `KERNEL32!GetLastError` at `0x140010668`
- `KERNEL32!GetLastError` at `0x140010694`
- `KERNEL32!GetLastError` at `0x14001070c`
- `KERNEL32!GetLastError` at `0x14001071f`
- `KERNEL32!GetLastError` at `0x140010746`
- `KERNEL32!GetLastError` at `0x14001076d`
- `KERNEL32!GetProcessHeap` at `0x1400107d3`
- `KERNEL32!GetProcessHeap` at `0x1400107f1`
- `KERNEL32!GetProcessHeap` at `0x14001080c`
- `KERNEL32!GetProcessHeap` at `0x140010826`
- `KERNEL32!GetProcessHeap` at `0x1400107d3`
- `KERNEL32!GetProcessHeap` at `0x1400107f1`
- `KERNEL32!GetProcessHeap` at `0x14001080c`
- `KERNEL32!GetProcessHeap` at `0x140010826`
- `KERNEL32!HeapFree` at `0x1400107e1`
- `KERNEL32!HeapFree` at `0x140010800`
- `KERNEL32!HeapFree` at `0x14001081b`
- `KERNEL32!HeapFree` at `0x140010834`
- `KERNEL32!HeapFree` at `0x1400107e1`
- `KERNEL32!HeapFree` at `0x140010800`
- `KERNEL32!HeapFree` at `0x14001081b`
- `KERNEL32!HeapFree` at `0x140010834`

## string_xrefs

- `0x14001061b`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14001060f`: `CRAGroupPolicy::RemoveMachinePermissions`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::RemoveMachinePermissions(
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
  DWORD i; // ebx
  CRAGroupPolicy *v11; // rcx
  PACL v12; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  PACL pDacl; // [rsp+30h] [rbp-50h] BYREF
  PSID pOwner; // [rsp+38h] [rbp-48h] BYREF
  PSID pGroup; // [rsp+40h] [rbp-40h] BYREF
  BOOL bDaclDefaulted; // [rsp+48h] [rbp-38h] BYREF
  BOOL bDaclPresent; // [rsp+4Ch] [rbp-34h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+68h] [rbp-18h]

  pAclInformation = 0;
  v26 = 0;
  pSecurityDescriptor = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pAce = 0;
  SDFromRegistry = CRAGroupPolicy::GetSDFromRegistry(this, a2, a3, &pSecurityDescriptor, (PACL)&pOwner, &pGroup);
  v7 = (struct _SECURITY_DESCRIPTOR *)pSecurityDescriptor;
  LastError = SDFromRegistry;
  if ( SDFromRegistry )
  {
    v9 = 999;
LABEL_3:
    CEventLogger::LogError(
      (CEventLogger *)L"CRAGroupPolicy::RemoveMachinePermissions",
      v6,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v9,
      L"CRAGroupPolicy::RemoveMachinePermissions",
      0);
    goto LABEL_29;
  }
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v9 = 1016;
    goto LABEL_3;
  }
  if ( !IsValidAcl(pDacl) )
  {
    LastError = GetLastError();
    v9 = 1022;
    goto LABEL_3;
  }
  if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastError = GetLastError();
    v9 = 1037;
    goto LABEL_3;
  }
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(pDacl, i, &pAce) )
    {
      LastError = GetLastError();
      v9 = 1048;
      goto LABEL_3;
    }
    if ( *(_BYTE *)pAce <= 1u && EqualSid(a4, (char *)pAce + 8) )
    {
      DeleteAce(pDacl, i);
      break;
    }
  }
  if ( !SetSecurityDescriptorDacl(v7, 1, pDacl, 1) )
  {
    LastError = GetLastError();
    v9 = 1084;
    goto LABEL_3;
  }
  if ( !SetSecurityDescriptorOwner(v7, pOwner, 0) )
  {
    LastError = GetLastError();
    v9 = 1093;
    goto LABEL_3;
  }
  if ( !SetSecurityDescriptorGroup(v7, pGroup, 0) )
  {
    LastError = GetLastError();
    v9 = 1102;
    goto LABEL_3;
  }
  if ( !IsValidSecurityDescriptor(v7) )
  {
    LastError = -2147467259;
    v9 = 1111;
    goto LABEL_3;
  }
  if ( CRAGroupPolicy::SetSDToRegistry(v11, L"SOFTWARE\\Microsoft\\Ole", L"MachineLaunchRestriction", v7) )
  {
    LastError = -2147467259;
    v9 = 1121;
    goto LABEL_3;
  }
  LastError = 0;
LABEL_29:
  v12 = pDacl;
  if ( pDacl )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    pDacl = 0;
  }
  if ( pOwner )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, pOwner);
  }
  if ( pGroup )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, pGroup);
  }
  if ( v7 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x140010594  mov     r11, rsp
0x140010597  mov     [r11+8], rbx
0x14001059b  mov     [r11+10h], rsi
0x14001059f  push    rbp
0x1400105a0  push    rdi
0x1400105a1  push    r12
0x1400105a3  mov     rbp, rsp
0x1400105a6  sub     rsp, 80h
0x1400105ad  mov     rax, cs:__security_cookie
0x1400105b4  xor     rax, rsp
0x1400105b7  mov     [rbp+var_10], rax
0x1400105bb  xor     r12d, r12d
0x1400105be  xor     eax, eax
0x1400105c0  mov     [rbp+pAclInformation], rax
0x1400105c4  mov     rsi, r9
0x1400105c7  mov     [rbp+var_18], eax
0x1400105ca  lea     r9, [rbp+pSecurityDescriptor]; struct _SECURITY_DESCRIPTOR **
0x1400105ce  lea     rax, [rbp+pGroup]
0x1400105d2  mov     [rbp+pSecurityDescriptor], r12
0x1400105d6  mov     [r11-70h], rax
0x1400105da  lea     rax, [rbp+pOwner]
0x1400105de  mov     [r11-78h], rax
0x1400105e2  mov     [rbp+bDaclPresent], r12d
0x1400105e6  mov     [rbp+bDaclDefaulted], r12d
0x1400105ea  mov     [rbp+pOwner], r12
0x1400105ee  mov     [rbp+pGroup], r12
0x1400105f2  mov     [rbp+pDacl], r12
0x1400105f6  mov     [rbp+pAce], r12
0x1400105fa  call    ?GetSDFromRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAPEAU_SECURITY_DESCRIPTOR@@PEAPEAX2@Z; CRAGroupPolicy::GetSDFromRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR * *,void * *,void * *)
0x1400105ff  mov     rdi, [rbp+pSecurityDescriptor]
0x140010603  mov     ebx, eax
0x140010605  test    eax, eax
0x140010607  jz      short loc_140010631
0x140010609  mov     r9d, 3E7h; unsigned int
0x14001060f  lea     rcx, aCragrouppolicy_8; "CRAGroupPolicy::RemoveMachinePermission"...
0x140010616  mov     [rsp+80h+var_58], r12d; unsigned int
0x14001061b  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x140010622  mov     [rsp+80h+var_60], rcx; unsigned __int16 *
0x140010627  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001062c  jmp     loc_1400107CA
0x140010631  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x140010635  mov     rcx, rdi; pSecurityDescriptor
0x140010638  lea     r8, [rbp+pDacl]; pDacl
0x14001063c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140010640  call    cs:__imp_GetSecurityDescriptorDacl
0x140010646  test    eax, eax
0x140010648  jnz     short loc_14001065A
0x14001064a  call    cs:__imp_GetLastError
0x140010650  mov     ebx, eax
0x140010652  mov     r9d, 3F8h
0x140010658  jmp     short loc_14001060F
0x14001065a  mov     rcx, [rbp+pDacl]; pAcl
0x14001065e  call    cs:__imp_IsValidAcl
0x140010664  test    eax, eax
0x140010666  jnz     short loc_140010678
0x140010668  call    cs:__imp_GetLastError
0x14001066e  mov     ebx, eax
0x140010670  mov     r9d, 3FEh
0x140010676  jmp     short loc_14001060F
0x140010678  mov     rcx, [rbp+pDacl]; pAcl
0x14001067c  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140010680  mov     r9d, 2; dwAclInformationClass
0x140010686  lea     r8d, [r9+0Ah]; nAclInformationLength
0x14001068a  call    cs:__imp_GetAclInformation
0x140010690  test    eax, eax
0x140010692  jnz     short loc_1400106A7
0x140010694  call    cs:__imp_GetLastError
0x14001069a  mov     ebx, eax
0x14001069c  mov     r9d, 40Dh
0x1400106a2  jmp     loc_14001060F
0x1400106a7  mov     ebx, r12d
0x1400106aa  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1400106ad  jnb     short loc_1400106F2
0x1400106af  mov     rcx, [rbp+pDacl]; pAcl
0x1400106b3  lea     r8, [rbp+pAce]; pAce
0x1400106b7  mov     edx, ebx; dwAceIndex
0x1400106b9  call    cs:__imp_GetAce
0x1400106bf  test    eax, eax
0x1400106c1  jz      short loc_14001071F
0x1400106c3  mov     rdx, [rbp+pAce]
0x1400106c7  mov     al, [rdx]
0x1400106c9  test    al, al
0x1400106cb  jz      short loc_1400106D1
0x1400106cd  cmp     al, 1
0x1400106cf  jnz     short loc_1400106E2
0x1400106d1  add     rdx, 8; pSid2
0x1400106d5  mov     rcx, rsi; pSid1
0x1400106d8  call    cs:__imp_EqualSid
0x1400106de  test    eax, eax
0x1400106e0  jnz     short loc_1400106E6
0x1400106e2  inc     ebx
0x1400106e4  jmp     short loc_1400106AA
0x1400106e6  mov     rcx, [rbp+pDacl]; pAcl
0x1400106ea  mov     edx, ebx; dwAceIndex
0x1400106ec  call    cs:__imp_DeleteAce
0x1400106f2  mov     r8, [rbp+pDacl]; pDacl
0x1400106f6  mov     r9d, 1; bDaclDefaulted
0x1400106fc  mov     edx, r9d; bDaclPresent
0x1400106ff  mov     rcx, rdi; pSecurityDescriptor
0x140010702  call    cs:__imp_SetSecurityDescriptorDacl
0x140010708  test    eax, eax
0x14001070a  jnz     short loc_140010732
0x14001070c  call    cs:__imp_GetLastError
0x140010712  mov     ebx, eax
0x140010714  mov     r9d, 43Ch
0x14001071a  jmp     loc_14001060F
0x14001071f  call    cs:__imp_GetLastError
0x140010725  mov     ebx, eax
0x140010727  mov     r9d, 418h
0x14001072d  jmp     loc_14001060F
0x140010732  mov     rdx, [rbp+pOwner]; pOwner
0x140010736  xor     r8d, r8d; bOwnerDefaulted
0x140010739  mov     rcx, rdi; pSecurityDescriptor
0x14001073c  call    cs:__imp_SetSecurityDescriptorOwner
0x140010742  test    eax, eax
0x140010744  jnz     short loc_140010759
0x140010746  call    cs:__imp_GetLastError
0x14001074c  mov     ebx, eax
0x14001074e  mov     r9d, 445h
0x140010754  jmp     loc_14001060F
0x140010759  mov     rdx, [rbp+pGroup]; pGroup
0x14001075d  xor     r8d, r8d; bGroupDefaulted
0x140010760  mov     rcx, rdi; pSecurityDescriptor
0x140010763  call    cs:__imp_SetSecurityDescriptorGroup
0x140010769  test    eax, eax
0x14001076b  jnz     short loc_140010780
0x14001076d  call    cs:__imp_GetLastError
0x140010773  mov     ebx, eax
0x140010775  mov     r9d, 44Eh
0x14001077b  jmp     loc_14001060F
0x140010780  mov     rcx, rdi; pSecurityDescriptor
0x140010783  call    cs:__imp_IsValidSecurityDescriptor
0x140010789  test    eax, eax
0x14001078b  jnz     short loc_14001079D
0x14001078d  mov     ebx, 80004005h
0x140010792  mov     r9d, 457h
0x140010798  jmp     loc_14001060F
0x14001079d  mov     r9, rdi; struct _SECURITY_DESCRIPTOR *
0x1400107a0  lea     r8, ValueName; "MachineLaunchRestriction"
0x1400107a7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Ole"
0x1400107ae  call    ?SetSDToRegistry@CRAGroupPolicy@@AEAAKPEAG0PEAU_SECURITY_DESCRIPTOR@@@Z; CRAGroupPolicy::SetSDToRegistry(ushort *,ushort *,_SECURITY_DESCRIPTOR *)
0x1400107b3  test    eax, eax
0x1400107b5  jz      short loc_1400107C7
0x1400107b7  mov     ebx, 80004005h
0x1400107bc  mov     r9d, 461h
0x1400107c2  jmp     loc_14001060F
0x1400107c7  mov     ebx, r12d
0x1400107ca  mov     rsi, [rbp+pDacl]
0x1400107ce  test    rsi, rsi
0x1400107d1  jz      short loc_1400107EB
0x1400107d3  call    cs:__imp_GetProcessHeap
0x1400107d9  mov     r8, rsi; lpMem
0x1400107dc  xor     edx, edx; dwFlags
0x1400107de  mov     rcx, rax; hHeap
0x1400107e1  call    cs:__imp_HeapFree
0x1400107e7  mov     [rbp+pDacl], r12
0x1400107eb  cmp     [rbp+pOwner], r12
0x1400107ef  jz      short loc_140010806
0x1400107f1  call    cs:__imp_GetProcessHeap
0x1400107f7  mov     r8, [rbp+pOwner]; lpMem
0x1400107fb  xor     edx, edx; dwFlags
0x1400107fd  mov     rcx, rax; hHeap
0x140010800  call    cs:__imp_HeapFree
0x140010806  cmp     [rbp+pGroup], r12
0x14001080a  jz      short loc_140010821
0x14001080c  call    cs:__imp_GetProcessHeap
0x140010812  mov     r8, [rbp+pGroup]; lpMem
0x140010816  xor     edx, edx; dwFlags
0x140010818  mov     rcx, rax; hHeap
0x14001081b  call    cs:__imp_HeapFree
0x140010821  test    rdi, rdi
0x140010824  jz      short loc_14001083A
0x140010826  call    cs:__imp_GetProcessHeap
0x14001082c  mov     r8, rdi; lpMem
0x14001082f  xor     edx, edx; dwFlags
0x140010831  mov     rcx, rax; hHeap
0x140010834  call    cs:__imp_HeapFree
0x14001083a  mov     eax, ebx
0x14001083c  mov     rcx, [rbp+var_10]
0x140010840  xor     rcx, rsp; StackCookie
0x140010843  call    __security_check_cookie
0x140010848  lea     r11, [rsp+80h+var_s0]
0x140010850  mov     rbx, [r11+20h]
0x140010854  mov     rsi, [r11+28h]
0x140010858  mov     rsp, r11
0x14001085b  pop     r12
0x14001085d  pop     rdi
0x14001085e  pop     rbp
0x14001085f  retn
```
