# Common::GetFileInUseProcessInformation(ulong,void *,Common::FileInUseProcessInformation &)

- ea: `0x1800a0764`
- end: `0x1800a0f1e`
- name: `?GetFileInUseProcessInformation@Common@@YAJKPEAXAEAUFileInUseProcessInformation@1@@Z`
- size: `1978`
- prototype: `int(Common *__hidden this, unsigned int, void *, struct Common::FileInUseProcessInformation *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800de0ac`
- `0x180185ce4`
- `0x1801ef2ac`

## callees

- `0x180012964`
- `0x18001c950`
- `0x180021224`
- `0x180052b20`
- `0x1800a0764`
- `0x1800a0f24`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1800f104a`
- `0x1800fc229`
- `0x180186c4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a0cdf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a0cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d96`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a0ed2`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a0ed2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a07b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a07b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0ef4`
- `ntdll!NtQueryInformationProcess` at `0x1800a0b94`
- `ntdll!NtQueryInformationProcess` at `0x1800a0c37`
- `ntdll!NtQueryInformationProcess` at `0x1800a0b94`
- `ntdll!NtQueryInformationProcess` at `0x1800a0c37`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a0c63`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a0c63`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0d88`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0ea6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0d88`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a0ea6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a0a56`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a0afa`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a0a56`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a0afa`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800a0906`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x1800a0906`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800a0884`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800a0884`

## string_xrefs

- `0x1800a07ec`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0820`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a085f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a08ad`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a08e1`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a092f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0963`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a09b0`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0a17`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0adc`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0b45`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0c0d`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0c8f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0d17`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a0e1b`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800a07cd`: `<Error 0x%X in OpenProcessToken>`
- `0x1800a0801`: `<Error 0x%X in OpenProcessToken>`
- `0x1800a083c`: `<Error 0x%X in OpenProcessToken>`
- `0x1800a0994`: `<Error 0x%X getting the user's SID from the process' token>`
- `0x1800a08c4`: `<Error 0x%X in GetApplicationUserModelIdFromToken>`
- `0x1800a0cfb`: `<Error 0x%X moving command line>`
- `0x1800a09fb`: `<Error 0x%X converting the user's SID to a string>`
- `0x1800a0df8`: `<No commandline present>`

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
  unsigned __int64 v24; // rdx
  WCHAR *v25; // r14
  int v26; // eax
  unsigned __int64 v27; // rdx
  int v28; // eax
  char *v29; // rax
  ULONG v30; // r12d
  NTSTATUS v31; // eax
  int InformationProcess; // r14d
  unsigned __int64 v33; // rdx
  void *v34; // r14
  unsigned __int16 *v35; // rsi
  int v36; // eax
  unsigned __int64 v37; // rdx
  ULONG v38; // eax
  int v39; // eax
  unsigned __int16 *v40; // r14
  const void *v41; // rdx
  unsigned __int64 v42; // rsi
  int v43; // eax
  PSID v44; // r12
  unsigned __int64 v45; // rdx
  void *v46; // rsi
  void **v47; // r14
  int v48; // eax
  unsigned __int64 v49; // rdx
  WCHAR *v50; // rsi
  _QWORD *v51; // r15
  unsigned __int64 v52; // rdx
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
              (wchar_t *)a3 + 128,
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
      v17 = StringCchPrintfW((wchar_t *)a3, 0x80u, L"<Error 0x%X in GetPackageFullName>", PackageFullNameFromToken);
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
                (wchar_t *)a3 + 276,
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
              (wchar_t *)a3 + 276,
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
    v8 = StringCchPrintfW((wchar_t *)a3 + 128, 0x82u, L"<Error 0x%X in OpenProcessToken>", LastError);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
    v9 = StringCchPrintfW((wchar_t *)a3, 0x80u, L"<Error 0x%X in OpenProcessToken>", (unsigned int)LastError);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v9,
        ReturnLength);
    v10 = a3 + 552;
    v11 = StringCchPrintfW((wchar_t *)a3 + 276, 0x64u, L"<Error 0x%X in OpenProcessToken>", (unsigned int)LastError);
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
    v28 = StringCchPrintfW((wchar_t *)a3 + 384, 0x104u, L"<Error 0x%X in QueryFullProcessImageNameW>", v23);
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
      v39 = StringCchPrintfW((wchar_t *)a3 + 672, 0x104u, L"<Error 0x%X in NtQueryInformationProcess>", v38);
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
      v43 = StringCchPrintfW((wchar_t *)a3 + 672, 0x104u, L"<Error 0x%X moving command line>", 34);
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
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  operator delete(v6, v52);
  return 0;
}

```

## disassembly

```asm
0x1800a0764  mov     [rsp-38h+arg_8], rbx
0x1800a0769  mov     [rsp-38h+dwProcessId], ecx
0x1800a076d  push    rbp
0x1800a076e  push    rsi
0x1800a076f  push    rdi
0x1800a0770  push    r12
0x1800a0772  push    r13
0x1800a0774  push    r14
0x1800a0776  push    r15
0x1800a0778  mov     rbp, rsp
0x1800a077b  sub     rsp, 70h
0x1800a077f  mov     rdi, r8
0x1800a0782  mov     r13, rdx
0x1800a0785  mov     rcx, r8; this
0x1800a0788  call    ?Reset@FileInUseProcessInformation@Common@@QEAAXXZ; Common::FileInUseProcessInformation::Reset(void)
0x1800a078d  nop
0x1800a078e  xor     r12d, r12d
0x1800a0791  mov     ebx, r12d
0x1800a0794  mov     [rbp+var_18], rbx
0x1800a0798  mov     [rbp+Sid], r12
0x1800a079c  mov     [rbp+TokenHandle], r12
0x1800a07a0  lea     r14, [rdi+100h]
0x1800a07a7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a07ab  lea     edx, [r12+8]; DesiredAccess
0x1800a07b0  mov     rcx, r13; ProcessHandle
0x1800a07b3  call    cs:__imp_OpenProcessToken
0x1800a07b9  test    eax, eax
0x1800a07bb  jnz     loc_1800A0871
0x1800a07c1  call    cs:__imp_GetLastError
0x1800a07c7  mov     r15d, eax
0x1800a07ca  mov     r9d, eax
0x1800a07cd  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800a07d4  mov     edx, 82h; unsigned __int64
0x1800a07d9  mov     rcx, r14; Buffer
0x1800a07dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a07e1  mov     rcx, [rbp+38h]; this
0x1800a07e5  test    eax, eax
0x1800a07e7  jns     short loc_1800A07FE
0x1800a07e9  mov     r9d, eax; char *
0x1800a07ec  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a07f3  mov     edx, 0C1h; void *
0x1800a07f8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a07fe  mov     r9d, r15d
0x1800a0801  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800a0808  mov     edx, 80h; unsigned __int64
0x1800a080d  mov     rcx, rdi; Buffer
0x1800a0810  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0815  mov     rcx, [rbp+38h]; this
0x1800a0819  test    eax, eax
0x1800a081b  jns     short loc_1800A0832
0x1800a081d  mov     r9d, eax; char *
0x1800a0820  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0827  mov     edx, 0C3h; void *
0x1800a082c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0832  lea     rsi, [rdi+228h]
0x1800a0839  mov     r9d, r15d
0x1800a083c  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800a0843  mov     edx, 64h ; 'd'; unsigned __int64
0x1800a0848  mov     rcx, rsi; Buffer
0x1800a084b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0850  mov     rcx, [rbp+38h]; this
0x1800a0854  test    eax, eax
0x1800a0856  jns     loc_1800A0A30
0x1800a085c  mov     r9d, eax; char *
0x1800a085f  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0866  mov     edx, 0C5h; void *
0x1800a086b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0871  mov     esi, 82h
0x1800a0876  mov     [rbp+applicationUserModelIdLength], esi
0x1800a0879  mov     r8, r14; applicationUserModelId
0x1800a087c  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800a0880  mov     rcx, [rbp+TokenHandle]; token
0x1800a0884  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800a088a  cmp     eax, 3D57h
0x1800a088f  jnz     short loc_1800A08BD
0x1800a0891  lea     r8, aNone_1; "<None>"
0x1800a0898  mov     edx, esi; unsigned __int64
0x1800a089a  mov     rcx, r14; unsigned __int16 *
0x1800a089d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a08a2  mov     rcx, [rbp+38h]; this
0x1800a08a6  test    eax, eax
0x1800a08a8  jns     short loc_1800A08F3
0x1800a08aa  mov     r9d, eax; char *
0x1800a08ad  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a08b4  lea     edx, [rsi+4Dh]; void *
0x1800a08b7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a08bd  test    eax, eax
0x1800a08bf  jz      short loc_1800A08F3
0x1800a08c1  mov     r9d, eax
0x1800a08c4  lea     r8, aError0xXInGeta; "<Error 0x%X in GetApplicationUserModelI"...
0x1800a08cb  mov     rdx, rsi; unsigned __int64
0x1800a08ce  mov     rcx, r14; Buffer
0x1800a08d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a08d6  mov     rcx, [rbp+38h]; this
0x1800a08da  test    eax, eax
0x1800a08dc  jns     short loc_1800A08F3
0x1800a08de  mov     r9d, eax; char *
0x1800a08e1  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a08e8  mov     edx, 0D4h; void *
0x1800a08ed  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a08f3  mov     esi, 80h
0x1800a08f8  mov     [rbp+applicationUserModelIdLength], esi
0x1800a08fb  mov     r8, rdi; packageFullName
0x1800a08fe  lea     rdx, [rbp+applicationUserModelIdLength]; packageFullNameLength
0x1800a0902  mov     rcx, [rbp+TokenHandle]; token
0x1800a0906  call    cs:__imp_GetPackageFullNameFromToken
0x1800a090c  cmp     eax, 3D54h
0x1800a0911  jnz     short loc_1800A093F
0x1800a0913  lea     r8, aNone_1; "<None>"
0x1800a091a  mov     edx, esi; unsigned __int64
0x1800a091c  mov     rcx, rdi; unsigned __int16 *
0x1800a091f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0924  mov     rcx, [rbp+38h]; this
0x1800a0928  test    eax, eax
0x1800a092a  jns     short loc_1800A0975
0x1800a092c  mov     r9d, eax; char *
0x1800a092f  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0936  lea     edx, [rsi+5Ch]; void *
0x1800a0939  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a093f  test    eax, eax
0x1800a0941  jz      short loc_1800A0975
0x1800a0943  mov     r9d, eax
0x1800a0946  lea     r8, aError0xXInGetp; "<Error 0x%X in GetPackageFullName>"
0x1800a094d  mov     rdx, rsi; unsigned __int64
0x1800a0950  mov     rcx, rdi; Buffer
0x1800a0953  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0958  mov     rcx, [rbp+38h]; this
0x1800a095c  test    eax, eax
0x1800a095e  jns     short loc_1800A0975
0x1800a0960  mov     r9d, eax; char *
0x1800a0963  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a096a  mov     edx, 0E1h; void *
0x1800a096f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0975  lea     rdx, [rbp+var_18]; void **
0x1800a0979  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a097d  call    ?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z; Common::SidHelper::GetUserSidFromToken(void *,void * *)
0x1800a0982  mov     rbx, [rbp+var_18]
0x1800a0986  test    eax, eax
0x1800a0988  jns     short loc_1800A09D7
0x1800a098a  lea     rcx, [rdi+228h]; Buffer
0x1800a0991  mov     r9d, eax
0x1800a0994  lea     r8, aError0xXGettin; "<Error 0x%X getting the user's SID from"...
0x1800a099b  mov     edx, 64h ; 'd'; unsigned __int64
0x1800a09a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a09a5  mov     rcx, [rbp+38h]; this
0x1800a09a9  test    eax, eax
0x1800a09ab  jns     short loc_1800A09C2
0x1800a09ad  mov     r9d, eax; char *
0x1800a09b0  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a09b7  mov     edx, 0E9h; void *
0x1800a09bc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a09c2  lea     rsi, [rdi+208h]
0x1800a09c9  cmp     [rsi], r12d
0x1800a09cc  jbe     short loc_1800A0A29
0x1800a09ce  mov     rsi, [rdi+210h]
0x1800a09d5  jmp     short loc_1800A0A30
0x1800a09d7  mov     [rbp+Sid], rbx
0x1800a09db  lea     rsi, [rdi+208h]
0x1800a09e2  mov     rdx, rsi; this
0x1800a09e5  mov     rcx, rbx; Sid
0x1800a09e8  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800a09ed  test    eax, eax
0x1800a09ef  jns     short loc_1800A09C9
0x1800a09f1  lea     rcx, [rdi+228h]; Buffer
0x1800a09f8  mov     r9d, eax
0x1800a09fb  lea     r8, aError0xXConver; "<Error 0x%X converting the user's SID t"...
0x1800a0a02  mov     edx, 64h ; 'd'; unsigned __int64
0x1800a0a07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0a0c  mov     rcx, [rbp+38h]; this
0x1800a0a10  test    eax, eax
0x1800a0a12  jns     short loc_1800A09C9
0x1800a0a14  mov     r9d, eax; char *
0x1800a0a17  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0a1e  mov     edx, 0F2h; void *
0x1800a0a23  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0a29  lea     rsi, [rdi+228h]
0x1800a0a30  mov     eax, 220h
0x1800a0a35  mov     rcx, rdi
0x1800a0a38  mov     [rcx+rax], rsi
0x1800a0a3c  mov     [rbp+dwSize], 104h
0x1800a0a43  lea     r15, [rdi+300h]
0x1800a0a4a  lea     r9, [rbp+dwSize]; lpdwSize
0x1800a0a4e  mov     r8, r15; lpExeName
0x1800a0a51  xor     edx, edx; dwFlags
0x1800a0a53  mov     rcx, r13; hProcess
0x1800a0a56  call    cs:__imp_QueryFullProcessImageNameW
0x1800a0a5c  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a0a60  test    eax, eax
0x1800a0a62  jnz     loc_1800A0B57
0x1800a0a68  call    cs:__imp_GetLastError
0x1800a0a6e  mov     esi, eax
0x1800a0a70  cmp     eax, 7Ah ; 'z'
0x1800a0a73  jnz     loc_1800A0B1F
0x1800a0a79  mov     ecx, [rbp+dwSize]
0x1800a0a7c  inc     ecx
0x1800a0a7e  mov     [rbp+dwSize], ecx
0x1800a0a81  mov     edx, ecx
0x1800a0a83  lea     eax, [rsi-78h]
0x1800a0a86  mul     rdx
0x1800a0a89  cmovb   rax, r14
0x1800a0a8d  mov     rcx, rax; unsigned __int64
0x1800a0a90  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a0a95  mov     r14, rax
0x1800a0a98  mov     rax, [rdi+2F8h]
0x1800a0a9f  cmp     rax, r14
0x1800a0aa2  jz      short loc_1800A0AB5
0x1800a0aa4  mov     rcx, rax; void *
0x1800a0aa7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a0aac  mov     [rdi+2F8h], r14
0x1800a0ab3  jmp     short loc_1800A0AB8
0x1800a0ab5  mov     r14, rax
0x1800a0ab8  test    r14, r14
0x1800a0abb  jnz     short loc_1800A0AEE
0x1800a0abd  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800a0ac4  mov     edx, 104h; unsigned __int64
0x1800a0ac9  mov     rcx, r15; unsigned __int16 *
0x1800a0acc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0ad1  mov     rcx, [rbp+38h]; this
0x1800a0ad5  test    eax, eax
0x1800a0ad7  jns     short loc_1800A0B57
0x1800a0ad9  mov     r9d, eax; char *
0x1800a0adc  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0ae3  mov     edx, 103h; void *
0x1800a0ae8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0aee  lea     r9, [rbp+dwSize]; lpdwSize
0x1800a0af2  mov     r8, r14; lpExeName
0x1800a0af5  xor     edx, edx; dwFlags
0x1800a0af7  mov     rcx, r13; hProcess
0x1800a0afa  call    cs:__imp_QueryFullProcessImageNameW
0x1800a0b00  test    eax, eax
0x1800a0b02  jnz     short loc_1800A0B23
0x1800a0b04  call    cs:__imp_GetLastError
0x1800a0b0a  mov     esi, eax
0x1800a0b0c  mov     rcx, [rdi+2F8h]; void *
0x1800a0b13  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a0b18  mov     [rdi+2F8h], r12
0x1800a0b1f  test    esi, esi
0x1800a0b21  jz      short loc_1800A0B57
0x1800a0b23  mov     r9d, esi
0x1800a0b26  lea     r8, aError0xXInQuer; "<Error 0x%X in QueryFullProcessImageNam"...
0x1800a0b2d  mov     edx, 104h; unsigned __int64
0x1800a0b32  mov     rcx, r15; Buffer
0x1800a0b35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a0b3a  mov     rcx, [rbp+38h]; this
0x1800a0b3e  test    eax, eax
0x1800a0b40  jns     short loc_1800A0B57
0x1800a0b42  mov     r9d, eax; char *
0x1800a0b45  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0b4c  mov     edx, 10Fh; void *
0x1800a0b51  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0b57  mov     rax, [rdi+2F8h]
0x1800a0b5e  test    rax, rax
0x1800a0b61  cmovz   rax, r15
0x1800a0b65  mov     [rdi+2F0h], rax
0x1800a0b6c  mov     [rbp+ProcessInformationLength], r12d
0x1800a0b70  lea     r15, [rdi+540h]
0x1800a0b77  lea     rax, [rbp+ProcessInformationLength]
0x1800a0b7b  mov     [rsp+70h+ReturnLength], rax; int
0x1800a0b80  mov     r12d, 208h
0x1800a0b86  mov     r9d, r12d; ProcessInformationLength
0x1800a0b89  mov     r8, r15; ProcessInformation
0x1800a0b8c  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1800a0b91  mov     rcx, r13; ProcessHandle
0x1800a0b94  call    cs:__imp_NtQueryInformationProcess
0x1800a0b9a  mov     r14d, eax
0x1800a0b9d  test    eax, eax
0x1800a0b9f  jns     loc_1800A0CA1
0x1800a0ba5  cmp     eax, 0C0000004h
0x1800a0baa  jnz     loc_1800A0C5D
0x1800a0bb0  mov     ecx, [rbp+ProcessInformationLength]; unsigned __int64
0x1800a0bb3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a0bb8  mov     r14, rax
0x1800a0bbb  mov     rax, [rdi+538h]
0x1800a0bc2  cmp     rax, r14
0x1800a0bc5  jz      short loc_1800A0BDF
0x1800a0bc7  mov     rcx, rax; void *
0x1800a0bca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a0bcf  mov     [rdi+538h], r14
0x1800a0bd6  lea     rsi, [rdi+540h]
0x1800a0bdd  jmp     short loc_1800A0BE5
0x1800a0bdf  mov     rsi, r15
0x1800a0be2  mov     r14, rax
0x1800a0be5  test    r14, r14
0x1800a0be8  jnz     short loc_1800A0C1F
0x1800a0bea  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x1800a0bf1  mov     edx, 104h; unsigned __int64
0x1800a0bf6  mov     rcx, r15; unsigned __int16 *
0x1800a0bf9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a0bfe  mov     rcx, [rbp+38h]; this
0x1800a0c02  test    eax, eax
0x1800a0c04  jns     loc_1800A0D30
0x1800a0c0a  mov     r9d, eax; char *
0x1800a0c0d  lea     r8, aOnecorePrivate_13; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800a0c14  mov     edx, 120h; void *
0x1800a0c19  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800a0c1f  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x1800a0c28  mov     r9d, [rbp+ProcessInformationLength]; ProcessInformationLength
0x1800a0c2c  mov     r8, r14; ProcessInformation
0x1800a0c2f  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x1800a0c34  mov     rcx, r13; ProcessHandle
  ... truncated ...
```
