# WaasMedic::TakeOwnership(std::basic_string_view<ushort,std::char_traits<ushort>> const &)

- ea: `0x18002c2a8`
- end: `0x18002c4d5`
- name: `?TakeOwnership@WaasMedic@@YAJAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002aa74`

## callees

- `0x180009a34`
- `0x180024fc4`
- `0x1800251a8`
- `0x18002543c`
- `0x18002c284`
- `0x18002c2a8`
- `0x18002c814`
- `0x180032408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c33f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c33f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c49c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c32f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c48c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c32f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002c48c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c2fd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c396`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c3f7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c438`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c2fd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c396`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c3f7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c438`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002c3c7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002c469`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002c3c7`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002c469`

## string_xrefs

- `0x18002c2cd`: `SeTakeOwnershipPrivilege`
- `0x18002c348`: `Failed to revert the thread token: 0%x08X`
- `0x18002c4a5`: `Failed to revert the thread token: 0%x08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::TakeOwnership(LPWSTR *a1)
{
  void *v2; // rbx
  const char *v3; // r9
  __int64 v4; // rdx
  int LastError; // eax
  unsigned int v6; // ebx
  DWORD v7; // eax
  unsigned __int64 v9; // rdx
  bool v10; // r8
  DWORD v11; // eax
  void *v12; // rdx
  __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  bool v15; // r8
  DWORD v16; // eax
  unsigned int psidGroup; // [rsp+20h] [rbp-38h]
  HANDLE hObject[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  DWORD cbSid; // [rsp+88h] [rbp+30h] BYREF

  v2 = 0;
  cbSid = 0;
  hObject[0] = 0;
  hObject[1] = 0;
  WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
    (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
    L"SeTakeOwnershipPrivilege");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted>::GetImpl'::`2'::impl) )
  {
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, 0, &cbSid) && GetLastError() != 122 )
    {
      v4 = 588;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v4,
                    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                    v3);
LABEL_6:
      v6 = LastError;
      if ( LOBYTE(hObject[1]) )
      {
        if ( RevertToSelf() )
        {
          LOBYTE(hObject[1]) = 0;
        }
        else
        {
          v7 = GetLastError();
          LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v7);
        }
      }
      if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(hObject[0]);
      return v6;
    }
    if ( GetLastError() == 122 )
    {
      v2 = WaasMedic::SafeAlloc((WaasMedic *)cbSid, v9, v10);
      if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v2, &cbSid) )
      {
        v4 = 593;
        goto LABEL_5;
      }
    }
    v11 = SetNamedSecurityInfoW(*a1, SE_FILE_OBJECT, 1u, v2, 0, 0, 0);
    if ( v11 )
    {
      v13 = 596;
LABEL_18:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                    (const char *)v11,
                    psidGroup);
      goto LABEL_6;
    }
  }
  else
  {
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) && GetLastError() != 122 )
    {
      v4 = 602;
      goto LABEL_5;
    }
    if ( GetLastError() == 122 )
    {
      v2 = WaasMedic::SafeAlloc((WaasMedic *)cbSid, v14, v15);
      if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v2, &cbSid) )
      {
        v4 = 607;
        goto LABEL_5;
      }
    }
    v11 = SetNamedSecurityInfoW(*a1, SE_FILE_OBJECT, 1u, v2, 0, 0, 0);
    if ( v11 )
    {
      v13 = 610;
      goto LABEL_18;
    }
  }
  WaasMedic::SafeFree((WaasMedic *)v2, v12);
  if ( LOBYTE(hObject[1]) )
  {
    if ( RevertToSelf() )
    {
      LOBYTE(hObject[1]) = 0;
    }
    else
    {
      v16 = GetLastError();
      LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v16);
    }
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  return 0;
}

```

## disassembly

```asm
0x18002c2a8  push    rbp
0x18002c2aa  push    rbx
0x18002c2ab  push    rsi
0x18002c2ac  push    rdi
0x18002c2ad  mov     rbp, rsp
0x18002c2b0  sub     rsp, 58h
0x18002c2b4  mov     rdi, rcx
0x18002c2b7  xor     esi, esi
0x18002c2b9  mov     ebx, esi
0x18002c2bb  mov     [rbp+cbSid], esi
0x18002c2be  xorps   xmm0, xmm0
0x18002c2c1  movups  xmmword ptr [rbp+hObject], xmm0
0x18002c2c5  mov     [rbp+hObject], rsi
0x18002c2c9  mov     byte ptr [rbp+hObject+8], sil
0x18002c2cd  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x18002c2d4  lea     rcx, [rbp+hObject]; this
0x18002c2d8  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18002c2dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted> `wil::Feature<__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted>::GetImpl(void)'::`2'::impl
0x18002c2e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VerifyExpiredOldDatastoreIsDeleted>::__private_IsEnabled(void)
0x18002c2e9  lea     r9, [rbp+cbSid]; cbSid
0x18002c2ed  xor     r8d, r8d; pSid
0x18002c2f0  xor     edx, edx; DomainSid
0x18002c2f2  test    al, al
0x18002c2f4  jz      loc_18002C3F2
0x18002c2fa  lea     ecx, [rsi+16h]; WellKnownSidType
0x18002c2fd  call    cs:__imp_CreateWellKnownSid
0x18002c303  test    eax, eax
0x18002c305  jnz     short loc_18002C374
0x18002c307  call    cs:__imp_GetLastError
0x18002c30d  cmp     eax, 7Ah ; 'z'
0x18002c310  jz      short loc_18002C374
0x18002c312  mov     edx, 24Ch; void *
0x18002c317  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002c31e  mov     rcx, [rbp+20h]; this
0x18002c322  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c327  mov     ebx, eax
0x18002c329  cmp     byte ptr [rbp+hObject+8], sil
0x18002c32d  jz      short loc_18002C359
0x18002c32f  call    cs:__imp_RevertToSelf
0x18002c335  test    eax, eax
0x18002c337  jz      short loc_18002C33F
0x18002c339  mov     byte ptr [rbp+hObject+8], sil
0x18002c33d  jmp     short loc_18002C359
0x18002c33f  call    cs:__imp_GetLastError
0x18002c345  mov     r8d, eax
0x18002c348  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18002c34f  mov     ecx, 2; unsigned __int8
0x18002c354  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c359  mov     rcx, [rbp+hObject]; hObject
0x18002c35d  lea     rax, [rcx-1]
0x18002c361  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c365  ja      short loc_18002C36D
0x18002c367  call    cs:__imp_CloseHandle
0x18002c36d  mov     eax, ebx
0x18002c36f  jmp     loc_18002C4CC
0x18002c374  call    cs:__imp_GetLastError
0x18002c37a  cmp     eax, 7Ah ; 'z'
0x18002c37d  jnz     short loc_18002C3AA
0x18002c37f  mov     ecx, [rbp+cbSid]; this
0x18002c382  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18002c387  mov     rbx, rax
0x18002c38a  lea     r9, [rbp+cbSid]; cbSid
0x18002c38e  mov     r8, rax; pSid
0x18002c391  xor     edx, edx; DomainSid
0x18002c393  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002c396  call    cs:__imp_CreateWellKnownSid
0x18002c39c  test    eax, eax
0x18002c39e  jnz     short loc_18002C3AA
0x18002c3a0  mov     edx, 251h
0x18002c3a5  jmp     loc_18002C317
0x18002c3aa  mov     [rsp+58h+pSacl], rsi; pSacl
0x18002c3af  mov     [rsp+58h+pDacl], rsi; pDacl
0x18002c3b4  mov     [rsp+58h+psidGroup], rsi; unsigned int
0x18002c3b9  mov     r9, rbx; psidOwner
0x18002c3bc  mov     edx, 1; ObjectType
0x18002c3c1  mov     r8d, edx; SecurityInfo
0x18002c3c4  mov     rcx, [rdi]; pObjectName
0x18002c3c7  call    cs:__imp_SetNamedSecurityInfoW
0x18002c3cd  test    eax, eax
0x18002c3cf  jz      loc_18002C47D
0x18002c3d5  mov     edx, 254h; void *
0x18002c3da  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18002c3e1  mov     r9d, eax; char *
0x18002c3e4  mov     rcx, [rbp+20h]; this
0x18002c3e8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c3ed  jmp     loc_18002C327
0x18002c3f2  mov     ecx, 1Ah; WellKnownSidType
0x18002c3f7  call    cs:__imp_CreateWellKnownSid
0x18002c3fd  test    eax, eax
0x18002c3ff  jnz     short loc_18002C416
0x18002c401  call    cs:__imp_GetLastError
0x18002c407  cmp     eax, 7Ah ; 'z'
0x18002c40a  jz      short loc_18002C416
0x18002c40c  mov     edx, 25Ah
0x18002c411  jmp     loc_18002C317
0x18002c416  call    cs:__imp_GetLastError
0x18002c41c  cmp     eax, 7Ah ; 'z'
0x18002c41f  jnz     short loc_18002C44C
0x18002c421  mov     ecx, [rbp+cbSid]; this
0x18002c424  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18002c429  mov     rbx, rax
0x18002c42c  lea     r9, [rbp+cbSid]; cbSid
0x18002c430  mov     r8, rax; pSid
0x18002c433  xor     edx, edx; DomainSid
0x18002c435  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002c438  call    cs:__imp_CreateWellKnownSid
0x18002c43e  test    eax, eax
0x18002c440  jnz     short loc_18002C44C
0x18002c442  mov     edx, 25Fh
0x18002c447  jmp     loc_18002C317
0x18002c44c  mov     [rsp+58h+pSacl], rsi; pSacl
0x18002c451  mov     [rsp+58h+pDacl], rsi; pDacl
0x18002c456  mov     [rsp+58h+psidGroup], rsi; psidGroup
0x18002c45b  mov     r9, rbx; psidOwner
0x18002c45e  mov     edx, 1; ObjectType
0x18002c463  mov     r8d, edx; SecurityInfo
0x18002c466  mov     rcx, [rdi]; pObjectName
0x18002c469  call    cs:__imp_SetNamedSecurityInfoW
0x18002c46f  test    eax, eax
0x18002c471  jz      short loc_18002C47D
0x18002c473  mov     edx, 262h
0x18002c478  jmp     loc_18002C3DA
0x18002c47d  mov     rcx, rbx; this
0x18002c480  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002c485  nop
0x18002c486  cmp     byte ptr [rbp+hObject+8], sil
0x18002c48a  jz      short loc_18002C4B6
0x18002c48c  call    cs:__imp_RevertToSelf
0x18002c492  test    eax, eax
0x18002c494  jz      short loc_18002C49C
0x18002c496  mov     byte ptr [rbp+hObject+8], sil
0x18002c49a  jmp     short loc_18002C4B6
0x18002c49c  call    cs:__imp_GetLastError
0x18002c4a2  mov     r8d, eax
0x18002c4a5  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18002c4ac  mov     ecx, 2; unsigned __int8
0x18002c4b1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c4b6  mov     rcx, [rbp+hObject]; hObject
0x18002c4ba  lea     rax, [rcx-1]
0x18002c4be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c4c2  ja      short loc_18002C4CA
0x18002c4c4  call    cs:__imp_CloseHandle
0x18002c4ca  xor     eax, eax
0x18002c4cc  add     rsp, 58h
0x18002c4d0  pop     rdi
0x18002c4d1  pop     rsi
0x18002c4d2  pop     rbx
0x18002c4d3  pop     rbp
0x18002c4d4  retn
```
