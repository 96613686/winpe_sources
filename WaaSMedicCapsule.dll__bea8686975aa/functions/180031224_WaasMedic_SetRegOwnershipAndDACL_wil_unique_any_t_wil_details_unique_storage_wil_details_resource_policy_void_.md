# WaasMedic::SetRegOwnershipAndDACL(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x180031224`
- end: `0x180031705`
- name: `?SetRegOwnershipAndDACL@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029d14`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a34`
- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x18003100c`
- `0x180031224`
- `0x180032408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003156e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003156e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003139b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031581`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003139b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800316bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800315b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800315b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031297`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031579`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800316cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031297`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031579`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800316cf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800312cb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800312cb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031334`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800313de`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180031334`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800313de`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031502`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031688`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031502`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031688`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003135f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180031373`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180031393`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800314ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800314bb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003135f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180031373`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180031393`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800314ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800314bb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180031455`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180031455`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003162c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18003162c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800316dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031557`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800316dd`

## string_xrefs

- `0x1800314c4`: `SeTakeOwnershipPrivilege`
- `0x180031279`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180031347`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180031487`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x1800314e8`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x1800315ea`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x18003165e`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x1800315de`: `Failed to open reg key for %ws.`
- `0x180031478`: `Failed to SetEntriesInAcl`
- `0x1800312db`: `Using default DACL`
- `0x180031674`: `Successfully changed DACL after taking ownership`
- `0x18003164f`: `SetSecurityInfo Failed after take ownership`
- `0x180031518`: `Failed to revert the thread token: 0%x08X`
- `0x18003169e`: `Failed to revert the thread token: 0%x08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::SetRegOwnershipAndDACL(__int64 a1, HKEY *a2, const WCHAR *a3, void *a4)
{
  int v7; // eax
  unsigned int LastError; // ebx
  PACL v10; // rbx
  const char *v11; // r9
  __int64 v12; // rdx
  PSID v13; // rdi
  DWORD v14; // ebx
  signed int v15; // eax
  int v16; // eax
  signed int v17; // edi
  DWORD v18; // eax
  bool v19; // cc
  const WCHAR *v20; // rdx
  LSTATUS v21; // eax
  signed int v22; // eax
  DWORD v23; // eax
  int nSubAuthority2; // [rsp+20h] [rbp-E0h]
  const char *nSubAuthority3; // [rsp+28h] [rbp-D8h]
  const char *nSubAuthority3a; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bDaclDefaulted[2]; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject[2]; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp-78h] BYREF
  PACL pDacl[2]; // [rsp+90h] [rbp-70h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D4h] [rbp-2Ch]
  int v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+ECh] [rbp-14h]
  int v38; // [rsp+F0h] [rbp-10h]
  PSID v39; // [rsp+F8h] [rbp-8h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pDacl[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  hKey = 0;
  v7 = WaasMedic::SetRegOwnership();
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46F,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
      (const char *)(unsigned int)v7,
      nSubAuthority2);
    return LastError;
  }
  bDaclPresent = 0;
  if ( !a4
    || (bDaclDefaulted[0] = 0,
        v10 = 0,
        GetSecurityDescriptorDacl(a4, &bDaclPresent, pDacl, bDaclDefaulted),
        !bDaclPresent) )
  {
    LogLevelW(4u, L"Using default DACL");
    *(_QWORD *)bDaclDefaulted = 0;
    pSid = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x221u, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      v12 = 1163;
LABEL_8:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
                    v11);
LABEL_9:
      if ( pSid )
        FreeSid(pSid);
      if ( *(_QWORD *)bDaclDefaulted )
        FreeSid(*(PSID *)bDaclDefaulted);
      return LastError;
    }
    v13 = *(PSID *)bDaclDefaulted;
    if ( *(_QWORD *)bDaclDefaulted )
    {
      v14 = GetLastError();
      FreeSid(v13);
      SetLastError(v14);
    }
    *(_QWORD *)bDaclDefaulted = 0;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)bDaclDefaulted) )
    {
      v12 = 1173;
      goto LABEL_8;
    }
    memset_0(&pListOfExplicitEntries, 0, 0x60u);
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    pListOfExplicitEntries.grfInheritance = 3;
    v36 = 3;
    v39 = *(PSID *)bDaclDefaulted;
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    v34 = 0x10000000;
    v35 = 2;
    v37 = 0;
    v38 = 2;
    v15 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, pDacl);
    LastError = v15;
    if ( v15 )
    {
      if ( v15 > 0 )
        LastError = (unsigned __int16)v15 | 0x80070000;
      if ( (LastError & 0x80000000) != 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x4AA,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
          (const char *)LastError,
          (int)"Failed to SetEntriesInAcl",
          nSubAuthority3);
      goto LABEL_9;
    }
    v10 = pDacl[0];
    if ( pSid )
      FreeSid(pSid);
    if ( *(_QWORD *)bDaclDefaulted )
      FreeSid(*(PSID *)bDaclDefaulted);
  }
  *(_OWORD *)hObject = 0;
  v16 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
          (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
          L"SeTakeOwnershipPrivilege");
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B0,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
      (const char *)(unsigned int)v16,
      nSubAuthority2);
LABEL_28:
    if ( LOBYTE(hObject[1]) )
    {
      if ( RevertToSelf() )
      {
        LOBYTE(hObject[1]) = 0;
      }
      else
      {
        v18 = GetLastError();
        LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v18);
      }
    }
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v10 )
      LocalFree(v10);
    return (unsigned int)v17;
  }
  v19 = *((_QWORD *)a3 + 3) <= 7u;
  hKey = 0;
  if ( v19 )
    v20 = a3;
  else
    v20 = *(const WCHAR **)a3;
  v21 = RegOpenKeyExW(*a2, v20, 0, 0x80000u, &hKey);
  v17 = v21;
  if ( v21 )
  {
    if ( v21 > 0 )
      v17 = (unsigned __int16)v21 | 0x80070000;
    if ( v17 < 0 )
    {
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4B9,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
        (const char *)(unsigned int)v17,
        (int)"Failed to open reg key for %ws.",
        (const char *)a3);
    }
    goto LABEL_28;
  }
  v22 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 4u, 0, 0, pDacl[0], 0);
  v17 = v22;
  if ( v22 )
  {
    if ( v22 > 0 )
      v17 = (unsigned __int16)v22 | 0x80070000;
    if ( v17 < 0 )
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4C5,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
        (const char *)(unsigned int)v17,
        (int)"SetSecurityInfo Failed after take ownership",
        nSubAuthority3a);
    goto LABEL_28;
  }
  LogLevelW(4u, L"Successfully changed DACL after taking ownership");
  if ( LOBYTE(hObject[1]) )
  {
    if ( RevertToSelf() )
    {
      LOBYTE(hObject[1]) = 0;
    }
    else
    {
      v23 = GetLastError();
      LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v23);
    }
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180031224  push    rbp
0x180031226  push    rbx
0x180031227  push    rsi
0x180031228  push    rdi
0x180031229  push    r12
0x18003122b  push    r13
0x18003122d  push    r14
0x18003122f  push    r15
0x180031231  lea     rbp, [rsp-18h]
0x180031236  sub     rsp, 118h
0x18003123d  mov     rax, cs:__security_cookie
0x180031244  xor     rax, rsp
0x180031247  mov     [rbp+50h+var_48], rax
0x18003124b  xor     r12d, r12d
0x18003124e  mov     word ptr [rbp+50h+pIdentifierAuthority.Value+4], 500h
0x180031254  mov     [rbp+50h+pDacl], r12
0x180031258  mov     rdi, r9
0x18003125b  mov     dword ptr [rbp+50h+pIdentifierAuthority.Value], r12d
0x18003125f  mov     rsi, r8
0x180031262  mov     [rsp+150h+hKey], r12
0x180031267  mov     r15, rdx
0x18003126a  call    ?SetRegOwnership@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::SetRegOwnership(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18003126f  mov     ebx, eax
0x180031271  test    eax, eax
0x180031273  jns     short loc_1800312A4
0x180031275  mov     rcx, [rbp+58h]; this
0x180031279  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180031280  mov     r9d, eax; char *
0x180031283  mov     edx, 46Fh; void *
0x180031288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003128d  mov     rcx, [rsp+150h+hKey]; hKey
0x180031292  test    rcx, rcx
0x180031295  jz      short loc_18003129D
0x180031297  call    cs:__imp_RegCloseKey
0x18003129d  mov     eax, ebx
0x18003129f  jmp     loc_1800316E5
0x1800312a4  mov     [rbp+50h+bDaclPresent], r12d
0x1800312a8  mov     r13d, 2
0x1800312ae  test    rdi, rdi
0x1800312b1  jz      short loc_1800312DB
0x1800312b3  lea     r9, [rsp+150h+bDaclDefaulted]; lpbDaclDefaulted
0x1800312b8  mov     [rsp+150h+bDaclDefaulted], r12d
0x1800312bd  lea     r8, [rbp+50h+pDacl]; pDacl
0x1800312c1  mov     rcx, rdi; pSecurityDescriptor
0x1800312c4  lea     rdx, [rbp+50h+bDaclPresent]; lpbDaclPresent
0x1800312c8  mov     rbx, r12
0x1800312cb  call    cs:__imp_GetSecurityDescriptorDacl
0x1800312d1  cmp     [rbp+50h+bDaclPresent], r12d
0x1800312d5  jnz     loc_1800314C1
0x1800312db  lea     rdx, aUsingDefaultDa; "Using default DACL"
0x1800312e2  mov     ecx, 4; unsigned __int8
0x1800312e7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800312ec  lea     rax, [rsp+150h+var_E0]
0x1800312f1  mov     qword ptr [rsp+150h+bDaclDefaulted], r12
0x1800312f6  mov     [rsp+150h+pSid], rax; pSid
0x1800312fb  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x1800312ff  mov     [rsp+150h+nSubAuthority7], r12d; nSubAuthority7
0x180031304  mov     r14d, 20h ; ' '
0x18003130a  mov     [rsp+150h+nSubAuthority6], r12d; nSubAuthority6
0x18003130f  mov     r9d, 221h; nSubAuthority1
0x180031315  mov     [rsp+150h+nSubAuthority5], r12d; nSubAuthority5
0x18003131a  mov     r8d, r14d; nSubAuthority0
0x18003131d  mov     [rsp+150h+nSubAuthority4], r12d; nSubAuthority4
0x180031322  mov     dl, r13b; nSubAuthorityCount
0x180031325  mov     [rsp+150h+nSubAuthority3], r12d; nSubAuthority3
0x18003132a  mov     [rsp+150h+nSubAuthority2], r12d; nSubAuthority2
0x18003132f  mov     [rsp+150h+var_E0], r12
0x180031334  call    cs:__imp_AllocateAndInitializeSid
0x18003133a  test    eax, eax
0x18003133c  jnz     short loc_18003137E
0x18003133e  mov     edx, 48Bh; void *
0x180031343  mov     rcx, [rbp+58h]; this
0x180031347  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003134e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031353  mov     ebx, eax
0x180031355  mov     rcx, [rsp+150h+var_E0]; pSid
0x18003135a  test    rcx, rcx
0x18003135d  jz      short loc_180031365
0x18003135f  call    cs:__imp_FreeSid
0x180031365  mov     rcx, qword ptr [rsp+150h+bDaclDefaulted]; pSid
0x18003136a  test    rcx, rcx
0x18003136d  jz      loc_18003128D
0x180031373  call    cs:__imp_FreeSid
0x180031379  jmp     loc_18003128D
0x18003137e  mov     rdi, qword ptr [rsp+150h+bDaclDefaulted]
0x180031383  test    rdi, rdi
0x180031386  jz      short loc_1800313A1
0x180031388  call    cs:__imp_GetLastError
0x18003138e  mov     rcx, rdi; pSid
0x180031391  mov     ebx, eax
0x180031393  call    cs:__imp_FreeSid
0x180031399  mov     ecx, ebx; dwErrCode
0x18003139b  call    cs:__imp_SetLastError
0x1800313a1  lea     rax, [rsp+150h+bDaclDefaulted]
0x1800313a6  mov     qword ptr [rsp+150h+bDaclDefaulted], r12
0x1800313ab  mov     [rsp+150h+pSid], rax; pSid
0x1800313b0  lea     rcx, [rbp+50h+pIdentifierAuthority]; pIdentifierAuthority
0x1800313b4  mov     [rsp+150h+nSubAuthority7], r12d; nSubAuthority7
0x1800313b9  mov     r9d, 220h; nSubAuthority1
0x1800313bf  mov     [rsp+150h+nSubAuthority6], r12d; nSubAuthority6
0x1800313c4  mov     r8d, r14d; nSubAuthority0
0x1800313c7  mov     [rsp+150h+nSubAuthority5], r12d; nSubAuthority5
0x1800313cc  mov     dl, r13b; nSubAuthorityCount
0x1800313cf  mov     [rsp+150h+nSubAuthority4], r12d; nSubAuthority4
0x1800313d4  mov     [rsp+150h+nSubAuthority3], r12d; char *
0x1800313d9  mov     [rsp+150h+nSubAuthority2], r12d; int
0x1800313de  call    cs:__imp_AllocateAndInitializeSid
0x1800313e4  test    eax, eax
0x1800313e6  jnz     short loc_1800313F2
0x1800313e8  mov     edx, 495h
0x1800313ed  jmp     loc_180031343
0x1800313f2  xor     edx, edx; Val
0x1800313f4  lea     rcx, [rbp+50h+pListOfExplicitEntries]; void *
0x1800313f8  lea     r8d, [rdx+60h]; Size
0x1800313fc  call    memset_0
0x180031401  mov     rax, [rsp+150h+var_E0]
0x180031406  lea     r9, [rbp+50h+pDacl]; NewAcl
0x18003140a  mov     ecx, 3
0x18003140f  mov     [rbp+50h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x180031413  mov     rax, qword ptr [rsp+150h+bDaclDefaulted]
0x180031418  lea     rdx, [rbp+50h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18003141c  mov     [rbp+50h+pListOfExplicitEntries.grfInheritance], ecx
0x18003141f  xor     r8d, r8d; OldAcl
0x180031422  mov     [rbp+50h+var_78], ecx
0x180031425  mov     ecx, r13d; cCountOfExplicitEntries
0x180031428  mov     [rbp+50h+var_58], rax
0x18003142c  mov     [rbp+50h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x180031433  mov     [rbp+50h+pListOfExplicitEntries.grfAccessMode], r13d
0x180031437  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x18003143b  mov     [rbp+50h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x180031442  mov     [rbp+50h+var_80], 10000000h
0x180031449  mov     [rbp+50h+var_7C], r13d
0x18003144d  mov     [rbp+50h+var_64], r12d
0x180031451  mov     [rbp+50h+var_60], r13d
0x180031455  call    cs:__imp_SetEntriesInAclW
0x18003145b  mov     ebx, eax
0x18003145d  test    eax, eax
0x18003145f  jz      short loc_18003149D
0x180031461  jle     short loc_18003146C
0x180031463  movzx   ebx, ax
0x180031466  or      ebx, 80070000h
0x18003146c  test    ebx, ebx
0x18003146e  jns     loc_180031355
0x180031474  mov     rcx, [rbp+58h]; this
0x180031478  lea     rax, aFailedToSetent; "Failed to SetEntriesInAcl"
0x18003147f  mov     r9d, ebx; char *
0x180031482  mov     qword ptr [rsp+150h+nSubAuthority2], rax; int
0x180031487  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003148e  mov     edx, 4AAh; void *
0x180031493  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031498  jmp     loc_180031355
0x18003149d  mov     rcx, [rsp+150h+var_E0]; pSid
0x1800314a2  mov     rbx, [rbp+50h+pDacl]
0x1800314a6  test    rcx, rcx
0x1800314a9  jz      short loc_1800314B1
0x1800314ab  call    cs:__imp_FreeSid
0x1800314b1  mov     rcx, qword ptr [rsp+150h+bDaclDefaulted]; pSid
0x1800314b6  test    rcx, rcx
0x1800314b9  jz      short loc_1800314C1
0x1800314bb  call    cs:__imp_FreeSid
0x1800314c1  xorps   xmm0, xmm0
0x1800314c4  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x1800314cb  lea     rcx, [rsp+150h+hObject]; this
0x1800314d0  movups  xmmword ptr [rsp+150h+hObject], xmm0
0x1800314d5  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x1800314da  mov     edi, eax
0x1800314dc  test    eax, eax
0x1800314de  jns     loc_180031564
0x1800314e4  mov     rcx, [rbp+58h]; this
0x1800314e8  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800314ef  mov     r9d, eax; char *
0x1800314f2  mov     edx, 4B0h; void *
0x1800314f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800314fc  cmp     byte ptr [rbp+50h+hObject+8], r12b
0x180031500  jz      short loc_18003152A
0x180031502  call    cs:__imp_RevertToSelf
0x180031508  test    eax, eax
0x18003150a  jz      short loc_180031512
0x18003150c  mov     byte ptr [rbp+50h+hObject+8], r12b
0x180031510  jmp     short loc_18003152A
0x180031512  call    cs:__imp_GetLastError
0x180031518  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18003151f  mov     ecx, r13d; unsigned __int8
0x180031522  mov     r8d, eax
0x180031525  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003152a  mov     rcx, [rsp+150h+hObject]; hObject
0x18003152f  lea     rax, [rcx-1]
0x180031533  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031537  ja      short loc_18003153F
0x180031539  call    cs:__imp_CloseHandle
0x18003153f  mov     rcx, [rsp+150h+hKey]; hKey
0x180031544  test    rcx, rcx
0x180031547  jz      short loc_18003154F
0x180031549  call    cs:__imp_RegCloseKey
0x18003154f  test    rbx, rbx
0x180031552  jz      short loc_18003155D
0x180031554  mov     rcx, rbx; hMem
0x180031557  call    cs:__imp_LocalFree
0x18003155d  mov     eax, edi
0x18003155f  jmp     loc_1800316E5
0x180031564  mov     r14, [rsp+150h+hKey]
0x180031569  test    r14, r14
0x18003156c  jz      short loc_180031587
0x18003156e  call    cs:__imp_GetLastError
0x180031574  mov     rcx, r14; hKey
0x180031577  mov     edi, eax
0x180031579  call    cs:__imp_RegCloseKey
0x18003157f  mov     ecx, edi; dwErrCode
0x180031581  call    cs:__imp_SetLastError
0x180031587  cmp     qword ptr [rsi+18h], 7
0x18003158c  mov     [rsp+150h+hKey], r12
0x180031591  jbe     short loc_180031598
0x180031593  mov     rdx, [rsi]
0x180031596  jmp     short loc_18003159B
0x180031598  mov     rdx, rsi; lpSubKey
0x18003159b  mov     rcx, [r15]; hKey
0x18003159e  lea     rax, [rsp+150h+hKey]
0x1800315a3  mov     r9d, 80000h; samDesired
0x1800315a9  mov     qword ptr [rsp+150h+nSubAuthority2], rax; phkResult
0x1800315ae  xor     r8d, r8d; ulOptions
0x1800315b1  call    cs:__imp_RegOpenKeyExW
0x1800315b7  mov     edi, eax
0x1800315b9  test    eax, eax
0x1800315bb  jz      short loc_180031608
0x1800315bd  jle     short loc_1800315C8
0x1800315bf  movzx   edi, ax
0x1800315c2  or      edi, 80070000h
0x1800315c8  test    edi, edi
0x1800315ca  jns     loc_1800314FC
0x1800315d0  cmp     qword ptr [rsi+18h], 7
0x1800315d5  jbe     short loc_1800315DA
0x1800315d7  mov     rsi, [rsi]
0x1800315da  mov     rcx, [rbp+58h]; this
0x1800315de  lea     rax, aFailedToOpenRe_0; "Failed to open reg key for %ws."
0x1800315e5  mov     qword ptr [rsp+150h+nSubAuthority3], rsi; char *
0x1800315ea  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x1800315f1  mov     r9d, edi; char *
0x1800315f4  mov     qword ptr [rsp+150h+nSubAuthority2], rax; int
0x1800315f9  mov     edx, 4B9h; void *
0x1800315fe  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031603  jmp     loc_1800314FC
0x180031608  mov     rax, [rbp+50h+pDacl]
0x18003160c  xor     r9d, r9d; psidOwner
0x18003160f  mov     rcx, [rsp+150h+hKey]; handle
0x180031614  mov     qword ptr [rsp+150h+nSubAuthority4], r12; pSacl
0x180031619  mov     qword ptr [rsp+150h+nSubAuthority3], rax; char *
0x18003161e  lea     esi, [r9+4]
0x180031622  mov     qword ptr [rsp+150h+nSubAuthority2], r12; psidGroup
0x180031627  mov     r8d, esi; SecurityInfo
0x18003162a  mov     edx, esi; ObjectType
0x18003162c  call    cs:__imp_SetSecurityInfo
0x180031632  mov     edi, eax
0x180031634  test    eax, eax
0x180031636  jz      short loc_180031674
0x180031638  jle     short loc_180031643
0x18003163a  movzx   edi, ax
0x18003163d  or      edi, 80070000h
0x180031643  test    edi, edi
0x180031645  jns     loc_1800314FC
0x18003164b  mov     rcx, [rbp+58h]; this
0x18003164f  lea     rax, aSetsecurityinf; "SetSecurityInfo Failed after take owner"...
0x180031656  mov     r9d, edi; char *
0x180031659  mov     qword ptr [rsp+150h+nSubAuthority2], rax; int
0x18003165e  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180031665  mov     edx, 4C5h; void *
0x18003166a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003166f  jmp     loc_1800314FC
0x180031674  lea     rdx, aSuccessfullyCh; "Successfully changed DACL after taking "...
0x18003167b  mov     ecx, esi; unsigned __int8
0x18003167d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180031682  cmp     byte ptr [rbp+50h+hObject+8], r12b
0x180031686  jz      short loc_1800316B0
0x180031688  call    cs:__imp_RevertToSelf
0x18003168e  test    eax, eax
0x180031690  jz      short loc_180031698
0x180031692  mov     byte ptr [rbp+50h+hObject+8], r12b
0x180031696  jmp     short loc_1800316B0
0x180031698  call    cs:__imp_GetLastError
0x18003169e  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x1800316a5  mov     ecx, r13d; unsigned __int8
0x1800316a8  mov     r8d, eax
0x1800316ab  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800316b0  mov     rcx, [rsp+150h+hObject]; hObject
0x1800316b5  lea     rax, [rcx-1]
0x1800316b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800316bd  ja      short loc_1800316C5
0x1800316bf  call    cs:__imp_CloseHandle
0x1800316c5  mov     rcx, [rsp+150h+hKey]; hKey
0x1800316ca  test    rcx, rcx
0x1800316cd  jz      short loc_1800316D5
0x1800316cf  call    cs:__imp_RegCloseKey
0x1800316d5  test    rbx, rbx
0x1800316d8  jz      short loc_1800316E3
0x1800316da  mov     rcx, rbx; hMem
0x1800316dd  call    cs:__imp_LocalFree
0x1800316e3  xor     eax, eax
0x1800316e5  mov     rcx, [rbp+50h+var_48]
0x1800316e9  xor     rcx, rsp; StackCookie
0x1800316ec  call    __security_check_cookie
0x1800316f1  add     rsp, 118h
  ... truncated ...
```
