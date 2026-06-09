# Common::GetFileInUseProcessInformation(ulong,void *,Common::FileInUseProcessInformation &)

- ea: `0x1800ab018`
- end: `0x1800ab82c`
- name: `?GetFileInUseProcessInformation@Common@@YAJKPEAXAEAUFileInUseProcessInformation@1@@Z`
- size: `2068`
- prototype: `int(Common *__hidden this, unsigned int, void *, struct Common::FileInUseProcessInformation *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800aa820`
- `0x1800aadc4`
- `0x180129af0`

## callees

- `0x180005c60`
- `0x180005e08`
- `0x180015590`
- `0x180025270`
- `0x18003bea4`
- `0x1800ab018`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800af85a`
- `0x1800ba475`
- `0x1800da6cc`
- `0x18012a8f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ab5d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ab5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab69c`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800ab7e4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800ab7e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab067`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab067`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab557`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800ab557`
- `ntdll!NtQueryInformationProcess` at `0x1800ab47c`
- `ntdll!NtQueryInformationProcess` at `0x1800ab525`
- `ntdll!NtQueryInformationProcess` at `0x1800ab47c`
- `ntdll!NtQueryInformationProcess` at `0x1800ab525`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab322`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab3d6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab322`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab3d6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ab688`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ab7b2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ab688`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800ab7b2`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800ab1cc`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800ab1cc`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800ab144`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800ab144`

## string_xrefs

- `0x1800ab08d`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ab0c1`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ab0fc`: `<Error 0x%X in OpenProcessToken>`
- `0x1800ab260`: `<Error 0x%X getting the user's SID from the process' token>`
- `0x1800ab18a`: `<Error 0x%X in GetApplicationUserModelIdFromToken>`
- `0x1800ab5fb`: `<Error 0x%X moving command line>`
- `0x1800ab2c7`: `<Error 0x%X converting the user's SID to a string>`
- `0x1800ab704`: `<No commandline present>`
- `0x1800ab0ac`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab0e0`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab11f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab173`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab1a7`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab1fb`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab22f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab27c`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab2e3`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab3b8`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab42d`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab4fb`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab589`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab617`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800ab727`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Common::GetFileInUseProcessInformation(
        Common *this,
        void *a2,
        char *a3,
        struct Common::FileInUseProcessInformation *a4)
{
  PSID v6; // rbx
  __int64 LastError; // r15
  int v8; // eax
  int v9; // eax
  char *v10; // rsi
  int v11; // eax
  unsigned int ApplicationUserModelIdFromToken; // eax
  int v13; // eax
  int v14; // eax
  unsigned int PackageFullNameFromToken; // eax
  int v16; // eax
  int v17; // eax
  int UserSidFromToken; // eax
  int v19; // eax
  _DWORD *v20; // rsi
  int v21; // eax
  int v22; // eax
  DWORD v23; // esi
  const struct std::nothrow_t *v24; // rdx
  WCHAR *v25; // r14
  int v26; // eax
  const struct std::nothrow_t *v27; // rdx
  int v28; // eax
  char *v29; // rax
  ULONG v30; // r12d
  NTSTATUS v31; // eax
  int InformationProcess; // r14d
  const struct std::nothrow_t *v33; // rdx
  void *v34; // r14
  unsigned __int16 *v35; // rsi
  int v36; // eax
  const struct std::nothrow_t *v37; // rdx
  ULONG v38; // eax
  int v39; // eax
  unsigned __int16 *v40; // r14
  const void *v41; // rdx
  unsigned __int64 v42; // rsi
  int v43; // eax
  PSID v44; // r12
  const struct std::nothrow_t *v45; // rdx
  void *v46; // rsi
  void **v47; // r14
  int v48; // eax
  const struct std::nothrow_t *v49; // rdx
  WCHAR *v50; // rsi
  _QWORD *v51; // r15
  void *v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  int ReturnLength; // [rsp+20h] [rbp-50h]
  int ReturnLengtha; // [rsp+20h] [rbp-50h]
  ULONG ProcessInformationLength; // [rsp+40h] [rbp-30h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-28h] BYREF
  PSID Sid; // [rsp+50h] [rbp-20h] BYREF
  PSID peUse; // [rsp+58h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD dwProcessId; // [rsp+B0h] [rbp+40h]
  DWORD dwSize; // [rsp+C8h] [rbp+58h] BYREF

  dwProcessId = (unsigned int)this;
  Common::FileInUseProcessInformation::Reset((Common::FileInUseProcessInformation *)a3);
  v6 = 0;
  peUse = 0;
  Sid = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(a2, 8u, &TokenHandle) )
  {
    applicationUserModelIdLength = 130;
    ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                        TokenHandle,
                                        &applicationUserModelIdLength,
                                        (PWSTR)a3 + 128);
    if ( ApplicationUserModelIdFromToken == 15703 )
    {
      v13 = StringCchCopyW((unsigned __int16 *)a3 + 128, 0x82u, L"<None>");
      if ( v13 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v13,
          ReturnLength);
    }
    else if ( ApplicationUserModelIdFromToken )
    {
      v14 = StringCchPrintfW(
              (unsigned __int16 *)a3 + 128,
              0x82u,
              L"<Error 0x%X in GetApplicationUserModelIdFromToken>",
              ApplicationUserModelIdFromToken);
      if ( v14 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xD4,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v14,
          ReturnLength);
    }
    applicationUserModelIdLength = 128;
    PackageFullNameFromToken = GetPackageFullNameFromToken(TokenHandle, &applicationUserModelIdLength, (PWSTR)a3);
    if ( PackageFullNameFromToken == 15700 )
    {
      v16 = StringCchCopyW((unsigned __int16 *)a3, 0x80u, L"<None>");
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v16,
          ReturnLength);
    }
    else if ( PackageFullNameFromToken )
    {
      v17 = StringCchPrintfW(
              (unsigned __int16 *)a3,
              0x80u,
              L"<Error 0x%X in GetPackageFullName>",
              PackageFullNameFromToken);
      if ( v17 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v17,
          ReturnLength);
    }
    UserSidFromToken = Common::SidHelper::GetUserSidFromToken(TokenHandle, &peUse);
    v6 = peUse;
    if ( UserSidFromToken >= 0 )
    {
      Sid = peUse;
      v20 = a3 + 520;
      v21 = Common::SidHelper::ConvertSidToString(peUse, (struct Common::StringBuffer *)(a3 + 520));
      if ( v21 < 0 )
      {
        v22 = StringCchPrintfW(
                (unsigned __int16 *)a3 + 276,
                0x64u,
                L"<Error 0x%X converting the user's SID to a string>",
                (unsigned int)v21);
        if ( v22 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v22,
            ReturnLength);
      }
    }
    else
    {
      v19 = StringCchPrintfW(
              (unsigned __int16 *)a3 + 276,
              0x64u,
              L"<Error 0x%X getting the user's SID from the process' token>",
              (unsigned int)UserSidFromToken);
      if ( v19 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v19,
          ReturnLength);
      v20 = a3 + 520;
    }
    if ( *v20 )
      v10 = (char *)*((_QWORD *)a3 + 66);
    else
      v10 = a3 + 552;
  }
  else
  {
    LastError = GetLastError();
    v8 = StringCchPrintfW((unsigned __int16 *)a3 + 128, 0x82u, L"<Error 0x%X in OpenProcessToken>", LastError);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
    v9 = StringCchPrintfW((unsigned __int16 *)a3, 0x80u, L"<Error 0x%X in OpenProcessToken>", (unsigned int)LastError);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v9,
        ReturnLength);
    v10 = a3 + 552;
    v11 = StringCchPrintfW(
            (unsigned __int16 *)a3 + 276,
            0x64u,
            L"<Error 0x%X in OpenProcessToken>",
            (unsigned int)LastError);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v11,
        ReturnLength);
  }
  *((_QWORD *)a3 + 68) = v10;
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(a2, 0, (LPWSTR)a3 + 384, &dwSize) )
  {
    v23 = GetLastError();
    if ( v23 == 122 )
    {
      v25 = (WCHAR *)operator new[](saturated_mul(++dwSize, 2u));
      if ( *((WCHAR **)a3 + 95) == v25 )
      {
        v25 = (WCHAR *)*((_QWORD *)a3 + 95);
      }
      else
      {
        operator delete(*((void **)a3 + 95), v24);
        *((_QWORD *)a3 + 95) = v25;
      }
      if ( !v25 )
      {
        v26 = StringCchCopyW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error allocating memory>");
        if ( v26 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v26,
            ReturnLength);
        goto LABEL_43;
      }
      if ( QueryFullProcessImageNameW(a2, 0, v25, &dwSize) )
        goto LABEL_41;
      v23 = GetLastError();
      operator delete(*((void **)a3 + 95), v27);
      *((_QWORD *)a3 + 95) = 0;
    }
    if ( !v23 )
      goto LABEL_43;
LABEL_41:
    v28 = StringCchPrintfW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error 0x%X in QueryFullProcessImageNameW>", v23);
    if ( v28 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v28,
        ReturnLength);
  }
LABEL_43:
  v29 = (char *)*((_QWORD *)a3 + 95);
  if ( !v29 )
    v29 = a3 + 768;
  *((_QWORD *)a3 + 94) = v29;
  ProcessInformationLength = 0;
  v30 = 520;
  v31 = NtQueryInformationProcess(
          a2,
          ProcessImageFileMapping|ProcessUserModeIOPL,
          a3 + 1344,
          0x208u,
          &ProcessInformationLength);
  InformationProcess = v31;
  if ( v31 >= 0 )
  {
    v35 = (unsigned __int16 *)(a3 + 1344);
  }
  else
  {
    if ( v31 != -1073741820 )
    {
      v35 = (unsigned __int16 *)(a3 + 1344);
LABEL_56:
      v38 = RtlNtStatusToDosErrorNoTeb(InformationProcess);
      v39 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X in NtQueryInformationProcess>", v38);
      if ( v39 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v39,
          ReturnLengtha);
      goto LABEL_68;
    }
    v34 = operator new[](ProcessInformationLength);
    if ( *((void **)a3 + 167) == v34 )
    {
      v35 = (unsigned __int16 *)(a3 + 1344);
      v34 = (void *)*((_QWORD *)a3 + 167);
    }
    else
    {
      operator delete(*((void **)a3 + 167), v33);
      *((_QWORD *)a3 + 167) = v34;
      v35 = (unsigned __int16 *)(a3 + 1344);
    }
    if ( !v34 )
    {
      v36 = StringCchCopyW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error allocating memory>");
      if ( v36 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v36,
          ReturnLengtha);
LABEL_68:
      v40 = v35;
      goto LABEL_69;
    }
    InformationProcess = NtQueryInformationProcess(
                           a2,
                           ProcessImageFileMapping|ProcessUserModeIOPL,
                           v34,
                           ProcessInformationLength,
                           0);
    if ( InformationProcess < 0 )
    {
      operator delete(*((void **)a3 + 167), v37);
      *((_QWORD *)a3 + 167) = 0;
      goto LABEL_56;
    }
  }
  v40 = (unsigned __int16 *)*((_QWORD *)a3 + 167);
  if ( v40 )
    v30 = ProcessInformationLength;
  else
    v40 = v35;
  v41 = (const void *)*((_QWORD *)v40 + 1);
  if ( !v41 )
  {
    v48 = StringCchCopyW(v35, 0x104u, L"<No commandline present>");
    if ( v48 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v48,
        ReturnLengtha);
    goto LABEL_68;
  }
  v42 = *v40;
  if ( *v40 )
  {
    if ( v30 < v42 )
    {
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
      v43 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X moving command line>", 34);
      if ( v43 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x152,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v43,
          ReturnLengtha);
      v35 = (unsigned __int16 *)(a3 + 1344);
      goto LABEL_68;
    }
    memmove_0(v40, v41, *v40);
  }
  v40[v42 >> 1] = 0;
LABEL_69:
  *((_QWORD *)a3 + 166) = v40;
  v44 = Sid;
  if ( Sid )
  {
    LODWORD(Sid) = 0;
    cchReferencedDomainName = 0;
    LODWORD(peUse) = 0;
    if ( !LookupAccountSidW(0, v44, 0, (LPDWORD)&Sid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&peUse)
      && GetLastError() == 122 )
    {
      v46 = operator new[](saturated_mul(cchReferencedDomainName, 2u));
      v47 = (void **)(a3 + 1288);
      if ( *((void **)a3 + 161) == v46 )
      {
        v46 = *v47;
      }
      else
      {
        operator delete(*v47, v45);
        *v47 = v46;
      }
      if ( v46 )
      {
        v50 = (WCHAR *)operator new[](saturated_mul((unsigned int)Sid, 2u));
        if ( *((WCHAR **)a3 + 162) == v50 )
        {
          v51 = a3 + 1288;
          v50 = (WCHAR *)*((_QWORD *)a3 + 162);
        }
        else
        {
          operator delete(*((void **)a3 + 162), v49);
          *((_QWORD *)a3 + 162) = v50;
          v51 = a3 + 1288;
        }
        if ( v50
          && LookupAccountSidW(
               0,
               v44,
               v50,
               (LPDWORD)&Sid,
               (LPWSTR)*v47,
               &cchReferencedDomainName,
               (PSID_NAME_USE)&peUse) )
        {
          *((_QWORD *)a3 + 163) = *v51;
          *((_QWORD *)a3 + 164) = *((_QWORD *)a3 + 162);
        }
      }
    }
  }
  if ( !ProcessIdToSessionId(dwProcessId, (DWORD *)a3 + 330) )
    *((_DWORD *)a3 + 330) = -1;
  Common::CloseHandleHelper((Common *)TokenHandle, v52);
  operator delete(v6, v53);
  return 0;
}

```

## disassembly

```asm
0x1800ab018  mov     [rsp-38h+arg_8], rbx
0x1800ab01d  mov     [rsp-38h+dwProcessId], ecx
0x1800ab021  push    rbp
0x1800ab022  push    rsi
0x1800ab023  push    rdi
0x1800ab024  push    r12
0x1800ab026  push    r13
0x1800ab028  push    r14
0x1800ab02a  push    r15
0x1800ab02c  mov     rbp, rsp
0x1800ab02f  sub     rsp, 70h
0x1800ab033  mov     rdi, r8
0x1800ab036  mov     r13, rdx
0x1800ab039  mov     rcx, r8; this
0x1800ab03c  call    ?Reset@FileInUseProcessInformation@Common@@QEAAXXZ; Common::FileInUseProcessInformation::Reset(void)
0x1800ab041  nop
0x1800ab042  xor     r12d, r12d
0x1800ab045  mov     ebx, r12d
0x1800ab048  mov     [rbp+var_18], rbx
0x1800ab04c  mov     [rbp+Sid], r12
0x1800ab050  mov     [rbp+TokenHandle], r12
0x1800ab054  lea     r14, [rdi+100h]
0x1800ab05b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ab05f  lea     edx, [r12+8]; DesiredAccess
0x1800ab064  mov     rcx, r13; ProcessHandle
0x1800ab067  call    cs:__imp_OpenProcessToken
0x1800ab06e  nop     dword ptr [rax+rax+00h]
0x1800ab073  test    eax, eax
0x1800ab075  jnz     loc_1800AB131
0x1800ab07b  call    cs:__imp_GetLastError
0x1800ab082  nop     dword ptr [rax+rax+00h]
0x1800ab087  mov     r15d, eax
0x1800ab08a  mov     r9d, eax
0x1800ab08d  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ab094  mov     edx, 82h; unsigned __int64
0x1800ab099  mov     rcx, r14; unsigned __int16 *
0x1800ab09c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab0a1  mov     rcx, [rbp+38h]; this
0x1800ab0a5  test    eax, eax
0x1800ab0a7  jns     short loc_1800AB0BE
0x1800ab0a9  mov     r9d, eax; char *
0x1800ab0ac  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab0b3  mov     edx, 0C1h; void *
0x1800ab0b8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab0be  mov     r9d, r15d
0x1800ab0c1  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ab0c8  mov     edx, 80h; unsigned __int64
0x1800ab0cd  mov     rcx, rdi; unsigned __int16 *
0x1800ab0d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab0d5  mov     rcx, [rbp+38h]; this
0x1800ab0d9  test    eax, eax
0x1800ab0db  jns     short loc_1800AB0F2
0x1800ab0dd  mov     r9d, eax; char *
0x1800ab0e0  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab0e7  mov     edx, 0C3h; void *
0x1800ab0ec  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab0f2  lea     rsi, [rdi+228h]
0x1800ab0f9  mov     r9d, r15d
0x1800ab0fc  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800ab103  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ab108  mov     rcx, rsi; unsigned __int16 *
0x1800ab10b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab110  mov     rcx, [rbp+38h]; this
0x1800ab114  test    eax, eax
0x1800ab116  jns     loc_1800AB2FC
0x1800ab11c  mov     r9d, eax; char *
0x1800ab11f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab126  mov     edx, 0C5h; void *
0x1800ab12b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab131  mov     esi, 82h
0x1800ab136  mov     [rbp+applicationUserModelIdLength], esi
0x1800ab139  mov     r8, r14; applicationUserModelId
0x1800ab13c  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800ab140  mov     rcx, [rbp+TokenHandle]; token
0x1800ab144  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800ab14b  nop     dword ptr [rax+rax+00h]
0x1800ab150  cmp     eax, 3D57h
0x1800ab155  jnz     short loc_1800AB183
0x1800ab157  lea     r8, aNone_1; "<None>"
0x1800ab15e  mov     edx, esi; unsigned __int64
0x1800ab160  mov     rcx, r14; unsigned __int16 *
0x1800ab163  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ab168  mov     rcx, [rbp+38h]; this
0x1800ab16c  test    eax, eax
0x1800ab16e  jns     short loc_1800AB1B9
0x1800ab170  mov     r9d, eax; char *
0x1800ab173  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab17a  lea     edx, [rsi+4Dh]; void *
0x1800ab17d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab183  test    eax, eax
0x1800ab185  jz      short loc_1800AB1B9
0x1800ab187  mov     r9d, eax
0x1800ab18a  lea     r8, aError0xXInGeta; "<Error 0x%X in GetApplicationUserModelI"...
0x1800ab191  mov     rdx, rsi; unsigned __int64
0x1800ab194  mov     rcx, r14; unsigned __int16 *
0x1800ab197  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab19c  mov     rcx, [rbp+38h]; this
0x1800ab1a0  test    eax, eax
0x1800ab1a2  jns     short loc_1800AB1B9
0x1800ab1a4  mov     r9d, eax; char *
0x1800ab1a7  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab1ae  mov     edx, 0D4h; void *
0x1800ab1b3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab1b9  mov     esi, 80h
0x1800ab1be  mov     [rbp+applicationUserModelIdLength], esi
0x1800ab1c1  mov     r8, rdi; packageFullName
0x1800ab1c4  lea     rdx, [rbp+applicationUserModelIdLength]; packageFullNameLength
0x1800ab1c8  mov     rcx, [rbp+TokenHandle]; token
0x1800ab1cc  call    cs:__imp_GetPackageFullNameFromToken
0x1800ab1d3  nop     dword ptr [rax+rax+00h]
0x1800ab1d8  cmp     eax, 3D54h
0x1800ab1dd  jnz     short loc_1800AB20B
0x1800ab1df  lea     r8, aNone_1; "<None>"
0x1800ab1e6  mov     edx, esi; unsigned __int64
0x1800ab1e8  mov     rcx, rdi; unsigned __int16 *
0x1800ab1eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ab1f0  mov     rcx, [rbp+38h]; this
0x1800ab1f4  test    eax, eax
0x1800ab1f6  jns     short loc_1800AB241
0x1800ab1f8  mov     r9d, eax; char *
0x1800ab1fb  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab202  lea     edx, [rsi+5Ch]; void *
0x1800ab205  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab20b  test    eax, eax
0x1800ab20d  jz      short loc_1800AB241
0x1800ab20f  mov     r9d, eax
0x1800ab212  lea     r8, aError0xXInGetp; "<Error 0x%X in GetPackageFullName>"
0x1800ab219  mov     rdx, rsi; unsigned __int64
0x1800ab21c  mov     rcx, rdi; unsigned __int16 *
0x1800ab21f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab224  mov     rcx, [rbp+38h]; this
0x1800ab228  test    eax, eax
0x1800ab22a  jns     short loc_1800AB241
0x1800ab22c  mov     r9d, eax; char *
0x1800ab22f  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab236  mov     edx, 0E1h; void *
0x1800ab23b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab241  lea     rdx, [rbp+var_18]; void **
0x1800ab245  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800ab249  call    ?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z; Common::SidHelper::GetUserSidFromToken(void *,void * *)
0x1800ab24e  mov     rbx, [rbp+var_18]
0x1800ab252  test    eax, eax
0x1800ab254  jns     short loc_1800AB2A3
0x1800ab256  lea     rcx, [rdi+228h]; unsigned __int16 *
0x1800ab25d  mov     r9d, eax
0x1800ab260  lea     r8, aError0xXGettin; "<Error 0x%X getting the user's SID from"...
0x1800ab267  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ab26c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab271  mov     rcx, [rbp+38h]; this
0x1800ab275  test    eax, eax
0x1800ab277  jns     short loc_1800AB28E
0x1800ab279  mov     r9d, eax; char *
0x1800ab27c  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab283  mov     edx, 0E9h; void *
0x1800ab288  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab28e  lea     rsi, [rdi+208h]
0x1800ab295  cmp     [rsi], r12d
0x1800ab298  jbe     short loc_1800AB2F5
0x1800ab29a  mov     rsi, [rdi+210h]
0x1800ab2a1  jmp     short loc_1800AB2FC
0x1800ab2a3  mov     [rbp+Sid], rbx
0x1800ab2a7  lea     rsi, [rdi+208h]
0x1800ab2ae  mov     rdx, rsi; struct Common::StringBuffer *
0x1800ab2b1  mov     rcx, rbx; Sid
0x1800ab2b4  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800ab2b9  test    eax, eax
0x1800ab2bb  jns     short loc_1800AB295
0x1800ab2bd  lea     rcx, [rdi+228h]; unsigned __int16 *
0x1800ab2c4  mov     r9d, eax
0x1800ab2c7  lea     r8, aError0xXConver; "<Error 0x%X converting the user's SID t"...
0x1800ab2ce  mov     edx, 64h ; 'd'; unsigned __int64
0x1800ab2d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab2d8  mov     rcx, [rbp+38h]; this
0x1800ab2dc  test    eax, eax
0x1800ab2de  jns     short loc_1800AB295
0x1800ab2e0  mov     r9d, eax; char *
0x1800ab2e3  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab2ea  mov     edx, 0F2h; void *
0x1800ab2ef  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab2f5  lea     rsi, [rdi+228h]
0x1800ab2fc  mov     eax, 220h
0x1800ab301  mov     rcx, rdi
0x1800ab304  mov     [rcx+rax], rsi
0x1800ab308  mov     [rbp+dwSize], 104h
0x1800ab30f  lea     r15, [rdi+300h]
0x1800ab316  lea     r9, [rbp+dwSize]; lpdwSize
0x1800ab31a  mov     r8, r15; lpExeName
0x1800ab31d  xor     edx, edx; dwFlags
0x1800ab31f  mov     rcx, r13; hProcess
0x1800ab322  call    cs:__imp_QueryFullProcessImageNameW
0x1800ab329  nop     dword ptr [rax+rax+00h]
0x1800ab32e  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ab332  test    eax, eax
0x1800ab334  jnz     loc_1800AB43F
0x1800ab33a  call    cs:__imp_GetLastError
0x1800ab341  nop     dword ptr [rax+rax+00h]
0x1800ab346  mov     esi, eax
0x1800ab348  cmp     eax, 7Ah ; 'z'
0x1800ab34b  jnz     loc_1800AB407
0x1800ab351  mov     ecx, [rbp+dwSize]
0x1800ab354  inc     ecx
0x1800ab356  mov     [rbp+dwSize], ecx
0x1800ab359  mov     edx, ecx
0x1800ab35b  lea     eax, [rsi-78h]
0x1800ab35e  mul     rdx
0x1800ab361  cmovb   rax, r14
0x1800ab365  mov     rcx, rax; unsigned __int64
0x1800ab368  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ab36d  mov     r14, rax
0x1800ab370  mov     rax, [rdi+2F8h]
0x1800ab377  cmp     rax, r14
0x1800ab37a  jz      short loc_1800AB38D
0x1800ab37c  mov     rcx, rax; void *
0x1800ab37f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab384  mov     [rdi+2F8h], r14
0x1800ab38b  jmp     short loc_1800AB390
0x1800ab38d  mov     r14, rax
0x1800ab390  test    r14, r14
0x1800ab393  jnz     short loc_1800AB3CA
0x1800ab395  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800ab39c  mov     edx, 104h; unsigned __int64
0x1800ab3a1  mov     rcx, r15; unsigned __int16 *
0x1800ab3a4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ab3a9  mov     rcx, [rbp+38h]; this
0x1800ab3ad  test    eax, eax
0x1800ab3af  jns     loc_1800AB43F
0x1800ab3b5  mov     r9d, eax; char *
0x1800ab3b8  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab3bf  mov     edx, 103h; void *
0x1800ab3c4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab3ca  lea     r9, [rbp+dwSize]; lpdwSize
0x1800ab3ce  mov     r8, r14; lpExeName
0x1800ab3d1  xor     edx, edx; dwFlags
0x1800ab3d3  mov     rcx, r13; hProcess
0x1800ab3d6  call    cs:__imp_QueryFullProcessImageNameW
0x1800ab3dd  nop     dword ptr [rax+rax+00h]
0x1800ab3e2  test    eax, eax
0x1800ab3e4  jnz     short loc_1800AB40B
0x1800ab3e6  call    cs:__imp_GetLastError
0x1800ab3ed  nop     dword ptr [rax+rax+00h]
0x1800ab3f2  mov     esi, eax
0x1800ab3f4  mov     rcx, [rdi+2F8h]; void *
0x1800ab3fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab400  mov     [rdi+2F8h], r12
0x1800ab407  test    esi, esi
0x1800ab409  jz      short loc_1800AB43F
0x1800ab40b  mov     r9d, esi
0x1800ab40e  lea     r8, aError0xXInQuer; "<Error 0x%X in QueryFullProcessImageNam"...
0x1800ab415  mov     edx, 104h; unsigned __int64
0x1800ab41a  mov     rcx, r15; unsigned __int16 *
0x1800ab41d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab422  mov     rcx, [rbp+38h]; this
0x1800ab426  test    eax, eax
0x1800ab428  jns     short loc_1800AB43F
0x1800ab42a  mov     r9d, eax; char *
0x1800ab42d  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800ab434  mov     edx, 10Fh; void *
0x1800ab439  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800ab43f  mov     rax, [rdi+2F8h]
0x1800ab446  test    rax, rax
0x1800ab449  cmovz   rax, r15
0x1800ab44d  mov     [rdi+2F0h], rax
0x1800ab454  mov     [rbp+ProcessInformationLength], r12d
0x1800ab458  lea     r15, [rdi+540h]
0x1800ab45f  lea     rax, [rbp+ProcessInformationLength]
0x1800ab463  mov     [rsp+70h+ReturnLength], rax; int
0x1800ab468  mov     r12d, 208h
0x1800ab46e  mov     r9d, r12d; ProcessInformationLength
0x1800ab471  mov     r8, r15; ProcessInformation
0x1800ab474  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1800ab479  mov     rcx, r13; ProcessHandle
0x1800ab47c  call    cs:__imp_NtQueryInformationProcess
0x1800ab483  nop     dword ptr [rax+rax+00h]
0x1800ab488  mov     r14d, eax
0x1800ab48b  test    eax, eax
0x1800ab48d  jns     loc_1800AB59B
0x1800ab493  cmp     eax, 0C0000004h
0x1800ab498  jnz     loc_1800AB551
0x1800ab49e  mov     ecx, [rbp+ProcessInformationLength]; unsigned __int64
0x1800ab4a1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ab4a6  mov     r14, rax
0x1800ab4a9  mov     rax, [rdi+538h]
0x1800ab4b0  cmp     rax, r14
0x1800ab4b3  jz      short loc_1800AB4CD
0x1800ab4b5  mov     rcx, rax; void *
0x1800ab4b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab4bd  mov     [rdi+538h], r14
0x1800ab4c4  lea     rsi, [rdi+540h]
0x1800ab4cb  jmp     short loc_1800AB4D3
0x1800ab4cd  mov     rsi, r15
0x1800ab4d0  mov     r14, rax
0x1800ab4d3  test    r14, r14
0x1800ab4d6  jnz     short loc_1800AB50D
0x1800ab4d8  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800ab4df  mov     edx, 104h; unsigned __int64
0x1800ab4e4  mov     rcx, r15; unsigned __int16 *
0x1800ab4e7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ab4ec  mov     rcx, [rbp+38h]; this
0x1800ab4f0  test    eax, eax
0x1800ab4f2  jns     loc_1800AB630
  ... truncated ...
```
