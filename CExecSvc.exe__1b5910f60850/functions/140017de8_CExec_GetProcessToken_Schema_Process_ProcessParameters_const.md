# CExec::GetProcessToken(Schema::Process::ProcessParameters const &)

- ea: `0x140017de8`
- end: `0x140018373`
- name: `?GetProcessToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUProcessParameters@Process@Schema@@@Z`
- size: `1419`
- prototype: `void **__fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002310`
- `0x140003ce0`
- `0x14000410c`
- `0x1400068ac`
- `0x140008160`
- `0x14000d338`
- `0x14000e828`
- `0x140015cdc`
- `0x140016808`
- `0x140017de8`
- `0x1400188cc`
- `0x14001ae30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017f8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018023`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018045`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018143`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001815b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017f8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018023`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018045`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018143`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001815b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001807b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001810f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001807b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001810f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018229`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001808e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018186`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400181d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001823c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001808e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140018186`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400181d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001823c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400181a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400181a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140018190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140018190`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400180eb`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1400180eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400180a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001811a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001817e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400181ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018234`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400180a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001811a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001817e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400181ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018234`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x140017f2f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x140017f2f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140017fb0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140017fb0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140017fe3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x140017fe3`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x140018204`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x140018275`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x140018204`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x140018275`

## string_xrefs

- `0x1400182ca`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400182e6`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400182f7`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018309`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14001831b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018337`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018349`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018361`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
void **__fastcall CExec::GetProcessToken(void **a1, __int64 a2)
{
  __int64 v2; // r13
  const WCHAR *v4; // rdi
  const WCHAR *v5; // r15
  __int64 v6; // rax
  const WCHAR *v7; // r12
  const WCHAR *v8; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v10; // rsi
  __int64 v11; // r8
  const WCHAR *v12; // rdx
  const unsigned __int16 *v13; // r8
  const char *v14; // r9
  PWTS_SESSION_INFO_1W v15; // rbx
  struct _WTS_SESSION_INFO_1W *v16; // rdi
  CExec *pDomainName; // rcx
  const unsigned __int16 *v18; // rdx
  const char *v19; // r9
  __int64 v20; // rdx
  HANDLE *ContainerVirtualAccountToken; // rdi
  HANDLE v22; // rsi
  HANDLE v23; // r15
  DWORD v24; // ebx
  const char *v25; // r9
  void *v26; // rbx
  HANDLE v27; // rsi
  DWORD v28; // edi
  LPCWSTR *v29; // rcx
  int v30; // eax
  HANDLE v31; // rdi
  bool v32; // zf
  char *v33; // rax
  DWORD v34; // ebx
  HANDLE CurrentProcess; // rax
  const char *v36; // r9
  DWORD v37; // ebx
  const WCHAR *v38; // rdx
  const char *v39; // r9
  HANDLE v40; // rsi
  DWORD LastError; // ebx
  const char *v42; // r9
  unsigned int pCount; // [rsp+20h] [rbp-89h]
  unsigned int pCounta; // [rsp+20h] [rbp-89h]
  __int128 v46; // [rsp+58h] [rbp-51h] BYREF
  __int128 v47; // [rsp+68h] [rbp-41h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+78h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-29h] BYREF
  void *phToken; // [rsp+88h] [rbp-21h] BYREF
  DWORD NumberOfEntries; // [rsp+90h] [rbp-19h] BYREF
  LPCWSTR lpszDomain[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-1h]
  unsigned __int64 v54; // [rsp+B0h] [rbp+7h]
  DWORD pLevel; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v2 = a2;
  phToken = a1;
  *(_OWORD *)lpszDomain = 0;
  v53 = 0;
  v54 = 7;
  LOWORD(lpszDomain[0]) = 0;
  v4 = (const WCHAR *)(a2 + 88);
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v5 = (const WCHAR *)(a2 + 88);
  else
    v5 = *(const WCHAR **)v4;
  v6 = *(_QWORD *)(a2 + 104);
  if ( *(_QWORD *)(a2 + 112) <= 7u )
    v7 = (const WCHAR *)(a2 + 88);
  else
    v7 = *(const WCHAR **)v4;
  if ( v6 )
  {
    v8 = &v7[v6];
    trivial_2 = _std_find_trivial_2(v7, v8, 92);
    if ( (const WCHAR *)trivial_2 != v8 )
    {
      v10 = (trivial_2 - (__int64)v7) >> 1;
      if ( v10 != -1 )
      {
        v46 = 0;
        v47 = 0;
        v11 = (trivial_2 - (__int64)v7) >> 1;
        if ( *((_QWORD *)v4 + 2) < v10 )
          v11 = *((_QWORD *)v4 + 2);
        if ( *((_QWORD *)v4 + 3) <= 7u )
          v12 = v4;
        else
          v12 = *(const WCHAR **)v4;
        std::wstring::_Construct<1,unsigned short const *>(&v46, v12, v11);
        std::wstring::operator=(lpszDomain, &v46);
        std::wstring::~wstring(&v46);
        v5 += v10 + 1;
      }
    }
  }
  if ( *(_BYTE *)(v2 + 179) )
  {
    if ( !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4E1,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        (const char *)0x32,
        pCount);
    ppSessionInfo = 0;
    NumberOfEntries = 0;
    *(_QWORD *)&v46 = &ppSessionInfo;
    *((_QWORD *)&v46 + 1) = &NumberOfEntries;
    LOBYTE(v47) = 1;
    pLevel = 1;
    if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4EF,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v14);
    v15 = ppSessionInfo;
    if ( !ppSessionInfo && NumberOfEntries )
      gsl::details::terminate(retaddr);
    v16 = &ppSessionInfo[NumberOfEntries];
    while ( 1 )
    {
      if ( v15 == v16 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x4FD,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          (const char *)0x520,
          pCounta);
      pDomainName = (CExec *)v15->pDomainName;
      if ( pDomainName && v15->pUserName )
      {
        v18 = (const unsigned __int16 *)lpszDomain;
        if ( v54 > 7 )
          v18 = lpszDomain[0];
        if ( CExec::DomainMatchesSession(pDomainName, v18, v13) && !(unsigned int)_o__wcsicmp(v15->pUserName, v5) )
          break;
      }
      ++v15;
    }
    phToken = 0;
    if ( !WTSQueryUserToken(v15->SessionId, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4F8,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v19);
    *a1 = phToken;
    phToken = 0;
    if ( ppSessionInfo )
      WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries);
    goto LABEL_75;
  }
  if ( !*(_QWORD *)(v2 + 104) )
  {
    LOBYTE(a2) = *(_BYTE *)(v2 + 168) == 0;
    CExec::MakeContainerVirtualAccountToken(a1, a2);
    goto LABEL_75;
  }
  hObject = 0;
  if ( v53 )
    goto LABEL_53;
  if ( (unsigned int)_o__wcsicmp(v5, L"ContainerAdministrator") )
  {
    if ( !v53 && !(unsigned int)_o__wcsicmp(v5, L"ContainerUser") )
    {
      v20 = 0;
      goto LABEL_42;
    }
LABEL_53:
    v29 = lpszDomain;
    if ( v54 > 7 )
      v29 = (LPCWSTR *)lpszDomain[0];
    if ( (unsigned int)_o__wcsicmp(v29, L"NT AUTHORITY") )
    {
      v40 = hObject;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v40);
        SetLastError(LastError);
      }
      hObject = 0;
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const WCHAR **)v4;
      if ( !LogonUserW(v4, L".", &szPassword, 2u, 0, &hObject) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x52B,
          (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
          v42);
    }
    else
    {
      v30 = _o__wcsicmp(v5, L"SYSTEM");
      v31 = hObject;
      v32 = v30 == 0;
      v33 = (char *)hObject - 1;
      if ( v32 )
      {
        if ( (unsigned __int64)v33 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v34 = GetLastError();
          CloseHandle(v31);
          SetLastError(v34);
        }
        hObject = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 0xF01FFu, &hObject) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x515,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
            v36);
      }
      else
      {
        if ( (unsigned __int64)v33 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v37 = GetLastError();
          CloseHandle(v31);
          SetLastError(v37);
        }
        hObject = 0;
        v38 = (const WCHAR *)lpszDomain;
        if ( v54 > 7 )
          v38 = lpszDomain[0];
        if ( !LogonUserW(v5, v38, 0, 5u, 0, &hObject) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x51F,
            (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
            v39);
      }
    }
    goto LABEL_48;
  }
  LOBYTE(v20) = 1;
LABEL_42:
  ContainerVirtualAccountToken = (HANDLE *)CExec::MakeContainerVirtualAccountToken(&phToken, v20);
  if ( &hObject != ContainerVirtualAccountToken )
  {
    v22 = hObject;
    v23 = *ContainerVirtualAccountToken;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v24 = GetLastError();
      CloseHandle(v22);
      SetLastError(v24);
    }
    hObject = v23;
    *ContainerVirtualAccountToken = 0;
  }
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
LABEL_48:
  if ( *(_BYTE *)(v2 + 168) )
  {
    phToken = 0;
    if ( !CreateRestrictedToken(hObject, 4u, 0, 0, 0, 0, 0, 0, &phToken) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v25);
    v26 = phToken;
    v27 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v28 = GetLastError();
      CloseHandle(v27);
      SetLastError(v28);
    }
  }
  else
  {
    v26 = hObject;
  }
  *a1 = v26;
  hObject = 0;
LABEL_75:
  std::wstring::~wstring(lpszDomain);
  return a1;
}

```

## disassembly

```asm
0x140017de8  mov     [rsp-8+arg_10], rbx
0x140017ded  push    rbp
0x140017dee  push    rsi
0x140017def  push    rdi
0x140017df0  push    r12
0x140017df2  push    r13
0x140017df4  push    r14
0x140017df6  push    r15
0x140017df8  lea     rbp, [rsp-27h]
0x140017dfd  sub     rsp, 0D0h
0x140017e04  mov     rax, cs:__security_cookie
0x140017e0b  xor     rax, rsp
0x140017e0e  mov     [rbp+57h+var_40], rax
0x140017e12  mov     r13, rdx
0x140017e15  mov     r14, rcx
0x140017e18  mov     [rbp+57h+phToken], rcx
0x140017e1c  xorps   xmm0, xmm0
0x140017e1f  movups  xmmword ptr [rbp+57h+lpszDomain], xmm0
0x140017e23  mov     [rbp+57h+var_58], 0
0x140017e2b  mov     [rbp+57h+var_50], 7
0x140017e33  xor     eax, eax
0x140017e35  mov     word ptr [rbp+57h+lpszDomain], ax
0x140017e39  lea     rdi, [rdx+58h]
0x140017e3d  cmp     qword ptr [rdi+18h], 7
0x140017e42  jbe     short loc_140017E49
0x140017e44  mov     r15, [rdi]
0x140017e47  jmp     short loc_140017E4C
0x140017e49  mov     r15, rdi
0x140017e4c  mov     rax, [rdi+10h]
0x140017e50  jbe     short loc_140017E57
0x140017e52  mov     r12, [rdi]
0x140017e55  jmp     short loc_140017E5A
0x140017e57  mov     r12, rdi
0x140017e5a  test    rax, rax
0x140017e5d  jz      short loc_140017ED9
0x140017e5f  lea     rbx, [r12+rax*2]
0x140017e63  mov     r8d, 5Ch ; '\'
0x140017e69  mov     rdx, rbx
0x140017e6c  mov     rcx, r12
0x140017e6f  call    __std_find_trivial_2
0x140017e74  mov     rsi, rax
0x140017e77  cmp     rax, rbx
0x140017e7a  jz      short loc_140017ED9
0x140017e7c  sub     rsi, r12
0x140017e7f  sar     rsi, 1
0x140017e82  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140017e86  jz      short loc_140017ED9
0x140017e88  xorps   xmm0, xmm0
0x140017e8b  movups  [rbp+57h+var_A8], xmm0
0x140017e8f  xorps   xmm1, xmm1
0x140017e92  movdqu  [rbp+57h+var_98], xmm1
0x140017e97  mov     r8, rsi
0x140017e9a  cmp     [rdi+10h], rsi
0x140017e9e  cmovb   r8, [rdi+10h]
0x140017ea3  cmp     qword ptr [rdi+18h], 7
0x140017ea8  jbe     short loc_140017EAF
0x140017eaa  mov     rdx, [rdi]
0x140017ead  jmp     short loc_140017EB2
0x140017eaf  mov     rdx, rdi
0x140017eb2  lea     rcx, [rbp+57h+var_A8]
0x140017eb6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140017ebb  lea     rdx, [rbp+57h+var_A8]
0x140017ebf  lea     rcx, [rbp+57h+lpszDomain]
0x140017ec3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140017ec8  lea     rcx, [rbp+57h+var_A8]
0x140017ecc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017ed1  lea     r15, [r15+rsi*2]
0x140017ed5  add     r15, 2
0x140017ed9  xor     r12d, r12d
0x140017edc  cmp     [r13+0B3h], r12b
0x140017ee3  jz      loc_140017FEE
0x140017ee9  call    IsWTSEnumerateSessionsExWPresent
0x140017eee  test    al, al
0x140017ef0  jz      loc_14001832D
0x140017ef6  mov     [rbp+57h+ppSessionInfo], r12
0x140017efa  mov     [rbp+57h+NumberOfEntries], r12d
0x140017efe  lea     rax, [rbp+57h+ppSessionInfo]
0x140017f02  mov     qword ptr [rbp+57h+var_A8], rax
0x140017f06  lea     rax, [rbp+57h+NumberOfEntries]
0x140017f0a  mov     qword ptr [rbp+57h+var_A8+8], rax
0x140017f0e  mov     byte ptr [rbp+57h+var_98], 1
0x140017f12  mov     [rbp+57h+pLevel], 1
0x140017f19  lea     rax, [rbp+57h+NumberOfEntries]
0x140017f1d  mov     [rsp+100h+pCount], rax; pCount
0x140017f22  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x140017f26  xor     r8d, r8d; Filter
0x140017f29  lea     rdx, [rbp+57h+pLevel]; pLevel
0x140017f2d  xor     ecx, ecx; hServer
0x140017f2f  call    cs:__imp_WTSEnumerateSessionsExW
0x140017f35  mov     rcx, [rbp+5Fh]; this
0x140017f39  test    eax, eax
0x140017f3b  jz      loc_140018349
0x140017f41  mov     eax, [rbp+57h+NumberOfEntries]
0x140017f44  mov     rbx, [rbp+57h+ppSessionInfo]
0x140017f48  test    rbx, rbx
0x140017f4b  jnz     short loc_140017F56
0x140017f4d  test    rax, rax
0x140017f50  jnz     loc_14001835B
0x140017f56  imul    rdi, rax, 38h ; '8'
0x140017f5a  add     rdi, rbx
0x140017f5d  jmp     short loc_140017F9A
0x140017f5f  mov     rcx, [rbx+28h]; this
0x140017f63  test    rcx, rcx
0x140017f66  jz      short loc_140017F96
0x140017f68  cmp     [rbx+20h], r12
0x140017f6c  jz      short loc_140017F96
0x140017f6e  lea     rdx, [rbp+57h+lpszDomain]
0x140017f72  cmp     [rbp+57h+var_50], 7
0x140017f77  cmova   rdx, [rbp+57h+lpszDomain]; unsigned __int16 *
0x140017f7c  call    ?DomainMatchesSession@CExec@@YA_NPEBG0@Z; CExec::DomainMatchesSession(ushort const *,ushort const *)
0x140017f81  test    al, al
0x140017f83  jz      short loc_140017F96
0x140017f85  mov     rdx, r15
0x140017f88  mov     rcx, [rbx+20h]
0x140017f8c  call    cs:__imp__o__wcsicmp
0x140017f92  test    eax, eax
0x140017f94  jz      short loc_140017FA5
0x140017f96  add     rbx, 38h ; '8'
0x140017f9a  cmp     rbx, rdi
0x140017f9d  jz      loc_1400182DC
0x140017fa3  jmp     short loc_140017F5F
0x140017fa5  mov     [rbp+57h+phToken], r12
0x140017fa9  lea     rdx, [rbp+57h+phToken]; phToken
0x140017fad  mov     ecx, [rbx+8]; SessionId
0x140017fb0  call    cs:__imp_WTSQueryUserToken
0x140017fb6  mov     rcx, [rbp+5Fh]; this
0x140017fba  test    eax, eax
0x140017fbc  jz      loc_140018361
0x140017fc2  mov     rax, [rbp+57h+phToken]
0x140017fc6  mov     [r14], rax
0x140017fc9  mov     [rbp+57h+phToken], r12
0x140017fcd  mov     rdx, [rbp+57h+ppSessionInfo]; pMemory
0x140017fd1  test    rdx, rdx
0x140017fd4  jz      loc_140018297
0x140017fda  mov     r8d, [rbp+57h+NumberOfEntries]; NumberOfEntries
0x140017fde  mov     ecx, 2; WTSTypeClass
0x140017fe3  call    cs:__imp_WTSFreeMemoryExW
0x140017fe9  jmp     loc_140018297
0x140017fee  cmp     [r13+68h], r12
0x140017ff2  jnz     short loc_14001800B
0x140017ff4  cmp     [r13+0A8h], r12b
0x140017ffb  setz    dl
0x140017ffe  mov     rcx, r14
0x140018001  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x140018006  jmp     loc_140018297
0x14001800b  mov     [rbp+57h+hObject], r12
0x14001800f  cmp     [rbp+57h+var_58], r12
0x140018013  jnz     loc_14001812E
0x140018019  lea     rdx, aContaineradmin; "ContainerAdministrator"
0x140018020  mov     rcx, r15
0x140018023  call    cs:__imp__o__wcsicmp
0x140018029  test    eax, eax
0x14001802b  jnz     short loc_140018031
0x14001802d  mov     dl, 1
0x14001802f  jmp     short loc_140018055
0x140018031  cmp     [rbp+57h+var_58], r12
0x140018035  jnz     loc_14001812E
0x14001803b  lea     rdx, aContaineruser; "ContainerUser"
0x140018042  mov     rcx, r15
0x140018045  call    cs:__imp__o__wcsicmp
0x14001804b  test    eax, eax
0x14001804d  jnz     loc_14001812E
0x140018053  xor     edx, edx
0x140018055  lea     rcx, [rbp+57h+phToken]
0x140018059  call    ?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z; CExec::MakeContainerVirtualAccountToken(bool)
0x14001805e  mov     rdi, rax
0x140018061  lea     rax, [rbp+57h+hObject]
0x140018065  cmp     rax, rdi
0x140018068  jz      short loc_14001809B
0x14001806a  mov     rsi, [rbp+57h+hObject]
0x14001806e  lea     rcx, [rsi-1]
0x140018072  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140018076  mov     r15, [rdi]
0x140018079  ja      short loc_140018094
0x14001807b  call    cs:__imp_GetLastError
0x140018081  mov     ebx, eax
0x140018083  mov     rcx, rsi; hObject
0x140018086  call    cs:__imp_CloseHandle
0x14001808c  mov     ecx, ebx; dwErrCode
0x14001808e  call    cs:__imp_SetLastError
0x140018094  mov     [rbp+57h+hObject], r15
0x140018098  mov     [rdi], r12
0x14001809b  mov     rcx, [rbp+57h+phToken]; hObject
0x14001809f  lea     rax, [rcx-1]
0x1400180a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400180a7  ja      short loc_1400180AF
0x1400180a9  call    cs:__imp_CloseHandle
0x1400180af  cmp     [r13+0A8h], r12b
0x1400180b6  jz      loc_14001828C
0x1400180bc  mov     [rbp+57h+phToken], r12
0x1400180c0  lea     rax, [rbp+57h+phToken]
0x1400180c4  mov     [rsp+100h+NewTokenHandle], rax; NewTokenHandle
0x1400180c9  mov     [rsp+100h+SidsToRestrict], r12; SidsToRestrict
0x1400180ce  mov     [rsp+100h+RestrictedSidCount], r12d; RestrictedSidCount
0x1400180d3  mov     [rsp+100h+PrivilegesToDelete], r12; PrivilegesToDelete
0x1400180d8  mov     dword ptr [rsp+100h+pCount], r12d; DeletePrivilegeCount
0x1400180dd  xor     r9d, r9d; SidsToDisable
0x1400180e0  xor     r8d, r8d; DisableSidCount
0x1400180e3  lea     edx, [r9+4]; Flags
0x1400180e7  mov     rcx, [rbp+57h+hObject]; ExistingTokenHandle
0x1400180eb  call    cs:__imp_CreateRestrictedToken
0x1400180f1  mov     rcx, [rbp+5Fh]; this
0x1400180f5  test    eax, eax
0x1400180f7  jz      loc_1400182CA
0x1400180fd  mov     rbx, [rbp+57h+phToken]
0x140018101  mov     rsi, [rbp+57h+hObject]
0x140018105  lea     rax, [rsi-1]
0x140018109  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001810d  ja      short loc_140018129
0x14001810f  call    cs:__imp_GetLastError
0x140018115  mov     edi, eax
0x140018117  mov     rcx, rsi; hObject
0x14001811a  call    cs:__imp_CloseHandle
0x140018120  mov     ecx, edi; dwErrCode
0x140018122  call    cs:__imp_SetLastError
0x140018128  nop
0x140018129  jmp     loc_140018290
0x14001812e  lea     rcx, [rbp+57h+lpszDomain]
0x140018132  cmp     [rbp+57h+var_50], 7
0x140018137  cmova   rcx, [rbp+57h+lpszDomain]
0x14001813c  lea     rdx, aNtAuthority; "NT AUTHORITY"
0x140018143  call    cs:__imp__o__wcsicmp
0x140018149  test    eax, eax
0x14001814b  jnz     loc_14001821B
0x140018151  lea     rdx, aSystem_0; "SYSTEM"
0x140018158  mov     rcx, r15
0x14001815b  call    cs:__imp__o__wcsicmp
0x140018161  mov     rdi, [rbp+57h+hObject]
0x140018165  test    eax, eax
0x140018167  lea     rax, [rdi-1]
0x14001816b  jnz     short loc_1400181B9
0x14001816d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018171  ja      short loc_14001818C
0x140018173  call    cs:__imp_GetLastError
0x140018179  mov     ebx, eax
0x14001817b  mov     rcx, rdi; hObject
0x14001817e  call    cs:__imp_CloseHandle
0x140018184  mov     ecx, ebx; dwErrCode
0x140018186  call    cs:__imp_SetLastError
0x14001818c  mov     [rbp+57h+hObject], r12
0x140018190  call    cs:__imp_GetCurrentProcess
0x140018196  lea     r8, [rbp+57h+hObject]; TokenHandle
0x14001819a  mov     edx, 0F01FFh; DesiredAccess
0x14001819f  mov     rcx, rax; ProcessHandle
0x1400181a2  call    cs:__imp_OpenProcessToken
0x1400181a8  mov     rcx, [rbp+5Fh]; this
0x1400181ac  test    eax, eax
0x1400181ae  jz      loc_1400182F7
0x1400181b4  jmp     loc_1400180AF
0x1400181b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400181bd  ja      short loc_1400181D8
0x1400181bf  call    cs:__imp_GetLastError
0x1400181c5  mov     ebx, eax
0x1400181c7  mov     rcx, rdi; hObject
0x1400181ca  call    cs:__imp_CloseHandle
0x1400181d0  mov     ecx, ebx; dwErrCode
0x1400181d2  call    cs:__imp_SetLastError
0x1400181d8  mov     [rbp+57h+hObject], r12
0x1400181dc  lea     rdx, [rbp+57h+lpszDomain]
0x1400181e0  cmp     [rbp+57h+var_50], 7
0x1400181e5  cmova   rdx, [rbp+57h+lpszDomain]; lpszDomain
0x1400181ea  lea     rax, [rbp+57h+hObject]
0x1400181ee  mov     [rsp+100h+PrivilegesToDelete], rax; phToken
0x1400181f3  mov     dword ptr [rsp+100h+pCount], r12d; dwLogonProvider
0x1400181f8  mov     r9d, 5; dwLogonType
0x1400181fe  xor     r8d, r8d; lpszPassword
0x140018201  mov     rcx, r15; lpszUsername
0x140018204  call    cs:__imp_LogonUserW
0x14001820a  mov     rcx, [rbp+5Fh]; this
0x14001820e  test    eax, eax
0x140018210  jz      loc_140018309
0x140018216  jmp     loc_1400180AF
0x14001821b  mov     rsi, [rbp+57h+hObject]
0x14001821f  lea     rax, [rsi-1]
0x140018223  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140018227  ja      short loc_140018242
0x140018229  call    cs:__imp_GetLastError
0x14001822f  mov     ebx, eax
0x140018231  mov     rcx, rsi; hObject
0x140018234  call    cs:__imp_CloseHandle
0x14001823a  mov     ecx, ebx; dwErrCode
0x14001823c  call    cs:__imp_SetLastError
0x140018242  mov     [rbp+57h+hObject], r12
0x140018246  cmp     qword ptr [rdi+18h], 7
0x14001824b  jbe     short loc_140018250
0x14001824d  mov     rdi, [rdi]
0x140018250  lea     rax, [rbp+57h+hObject]
0x140018254  mov     [rsp+100h+PrivilegesToDelete], rax; phToken
0x140018259  mov     dword ptr [rsp+100h+pCount], r12d; dwLogonProvider
0x14001825e  mov     r9d, 2; dwLogonType
0x140018264  lea     r8, szPassword; lpszPassword
0x14001826b  lea     rdx, szDomain; "."
0x140018272  mov     rcx, rdi; lpszUsername
0x140018275  call    cs:__imp_LogonUserW
0x14001827b  mov     rcx, [rbp+5Fh]; this
0x14001827f  test    eax, eax
0x140018281  jz      loc_14001831B
0x140018287  jmp     loc_1400180AF
0x14001828c  mov     rbx, [rbp+57h+hObject]
0x140018290  mov     [r14], rbx
  ... truncated ...
```
