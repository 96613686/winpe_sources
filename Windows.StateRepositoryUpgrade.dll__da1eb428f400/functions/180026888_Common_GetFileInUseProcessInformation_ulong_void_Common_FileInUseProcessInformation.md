# Common::GetFileInUseProcessInformation(ulong,void *,Common::FileInUseProcessInformation &)

- ea: `0x180026888`
- end: `0x180027034`
- name: `?GetFileInUseProcessInformation@Common@@YAJKPEAXAEAUFileInUseProcessInformation@1@@Z`
- size: `1964`
- prototype: `int(Common *__hidden this, unsigned int, void *, struct Common::FileInUseProcessInformation *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027404`

## callees

- `0x180003d50`
- `0x1800041cc`
- `0x18000428e`
- `0x180007f70`
- `0x18000a77c`
- `0x18000a7c0`
- `0x180014ca0`
- `0x180026490`
- `0x180026888`
- `0x1800282ac`
- `0x18002d35c`
- `0x18002d3e0`
- `0x18002dc7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026e02`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026eb9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180026ff5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180026ff5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268d6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026d86`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026d86`
- `ntdll!NtQueryInformationProcess` at `0x180026cb7`
- `ntdll!NtQueryInformationProcess` at `0x180026d5a`
- `ntdll!NtQueryInformationProcess` at `0x180026cb7`
- `ntdll!NtQueryInformationProcess` at `0x180026d5a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180026b79`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180026c1d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180026b79`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180026c1d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180026eab`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180026fc9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180026eab`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180026fc9`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800269a7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800269a7`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x180026a29`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageFullNameFromToken` at `0x180026a29`

## string_xrefs

- `0x1800268ea`: `<Error 0x%X in OpenProcessToken>`
- `0x180026924`: `<Error 0x%X in OpenProcessToken>`
- `0x180026962`: `<Error 0x%X in OpenProcessToken>`
- `0x18002690f`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026943`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026982`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800269d0`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026a04`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026a52`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026a86`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026ad3`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026b3a`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026bff`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026c68`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026d30`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026db2`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026e3a`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x180026f3e`: `onecore\private\base\inc\AppModel\Common\FileInUse.hpp`
- `0x1800269e7`: `<Error 0x%X in GetApplicationUserModelIdFromToken>`
- `0x180026ab7`: `<Error 0x%X getting the user's SID from the process' token>`
- `0x180026b1e`: `<Error 0x%X converting the user's SID to a string>`
- `0x180026e1e`: `<Error 0x%X moving command line>`
- `0x180026f1b`: `<No commandline present>`

## pseudocode

```c
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
  WCHAR *v24; // r14
  int v25; // eax
  int v26; // eax
  char *v27; // rax
  ULONG v28; // r12d
  NTSTATUS v29; // eax
  int InformationProcess; // r14d
  unsigned __int64 v31; // rdx
  void *v32; // r14
  unsigned __int16 *v33; // rsi
  int v34; // eax
  unsigned __int64 v35; // rdx
  ULONG v36; // eax
  int v37; // eax
  unsigned __int16 *v38; // r14
  const void *v39; // rdx
  unsigned __int64 v40; // rsi
  int v41; // eax
  PSID v42; // r12
  unsigned __int64 v43; // rax
  void **v44; // r14
  void *v45; // rsi
  int v46; // eax
  WCHAR *v47; // rsi
  _QWORD *v48; // r15
  void *v49; // rdx
  unsigned __int64 v50; // rdx
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
  Sid = 0;
  peUse = 0;
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
      v20 = a3 + 520;
      Sid = peUse;
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
      v24 = (WCHAR *)operator new[](saturated_mul(++dwSize, 2u));
      if ( *((WCHAR **)a3 + 95) == v24 )
      {
        v24 = (WCHAR *)*((_QWORD *)a3 + 95);
      }
      else
      {
        operator delete(*((void **)a3 + 95));
        *((_QWORD *)a3 + 95) = v24;
      }
      if ( !v24 )
      {
        v25 = StringCchCopyW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error allocating memory>");
        if ( v25 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v25,
            ReturnLength);
        goto LABEL_43;
      }
      if ( QueryFullProcessImageNameW(a2, 0, v24, &dwSize) )
        goto LABEL_41;
      v23 = GetLastError();
      operator delete(*((void **)a3 + 95));
      *((_QWORD *)a3 + 95) = 0;
    }
    if ( !v23 )
      goto LABEL_43;
LABEL_41:
    v26 = StringCchPrintfW((unsigned __int16 *)a3 + 384, 0x104u, L"<Error 0x%X in QueryFullProcessImageNameW>", v23);
    if ( v26 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v26,
        ReturnLength);
  }
LABEL_43:
  v27 = (char *)*((_QWORD *)a3 + 95);
  ProcessInformationLength = 0;
  v28 = 520;
  if ( !v27 )
    v27 = a3 + 768;
  *((_QWORD *)a3 + 94) = v27;
  v29 = NtQueryInformationProcess(
          a2,
          ProcessImageFileMapping|ProcessUserModeIOPL,
          a3 + 1344,
          0x208u,
          &ProcessInformationLength);
  InformationProcess = v29;
  if ( v29 >= 0 )
  {
    v33 = (unsigned __int16 *)(a3 + 1344);
    goto LABEL_59;
  }
  if ( v29 != -1073741820 )
  {
    v33 = (unsigned __int16 *)(a3 + 1344);
LABEL_56:
    v36 = RtlNtStatusToDosErrorNoTeb(InformationProcess);
    v37 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X in NtQueryInformationProcess>", v36);
    if ( v37 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
        (const char *)(unsigned int)v37,
        ReturnLengtha);
    goto LABEL_68;
  }
  v32 = operator new[](ProcessInformationLength);
  if ( *((void **)a3 + 167) == v32 )
  {
    v33 = (unsigned __int16 *)(a3 + 1344);
    v32 = (void *)*((_QWORD *)a3 + 167);
  }
  else
  {
    operator delete(*((void **)a3 + 167), v31);
    *((_QWORD *)a3 + 167) = v32;
    v33 = (unsigned __int16 *)(a3 + 1344);
  }
  if ( v32 )
  {
    InformationProcess = NtQueryInformationProcess(
                           a2,
                           ProcessImageFileMapping|ProcessUserModeIOPL,
                           v32,
                           ProcessInformationLength,
                           0);
    if ( InformationProcess < 0 )
    {
      operator delete(*((void **)a3 + 167), v35);
      *((_QWORD *)a3 + 167) = 0;
      goto LABEL_56;
    }
LABEL_59:
    v38 = (unsigned __int16 *)*((_QWORD *)a3 + 167);
    if ( v38 )
      v28 = ProcessInformationLength;
    else
      v38 = v33;
    v39 = (const void *)*((_QWORD *)v38 + 1);
    if ( !v39 )
    {
      v46 = StringCchCopyW(v33, 0x104u, L"<No commandline present>");
      if ( v46 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
          (const char *)(unsigned int)v46,
          ReturnLengtha);
      goto LABEL_68;
    }
    v40 = *v38;
    if ( *v38 )
    {
      if ( v28 < v40 )
      {
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
        v41 = StringCchPrintfW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error 0x%X moving command line>", 34);
        if ( v41 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x152,
            (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
            (const char *)(unsigned int)v41,
            ReturnLengtha);
        v33 = (unsigned __int16 *)(a3 + 1344);
        goto LABEL_68;
      }
      memmove_0(v38, v39, *v38);
    }
    v38[v40 >> 1] = 0;
    goto LABEL_69;
  }
  v34 = StringCchCopyW((unsigned __int16 *)a3 + 672, 0x104u, L"<Error allocating memory>");
  if ( v34 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecore\\private\\base\\inc\\AppModel\\Common\\FileInUse.hpp",
      (const char *)(unsigned int)v34,
      ReturnLengtha);
LABEL_68:
  v38 = v33;
LABEL_69:
  *((_QWORD *)a3 + 166) = v38;
  v42 = Sid;
  if ( Sid )
  {
    LODWORD(Sid) = 0;
    cchReferencedDomainName = 0;
    LODWORD(peUse) = 0;
    if ( !LookupAccountSidW(0, v42, 0, (LPDWORD)&Sid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&peUse)
      && GetLastError() == 122 )
    {
      v43 = 2LL * cchReferencedDomainName;
      if ( !is_mul_ok(cchReferencedDomainName, 2u) )
        v43 = -1;
      v44 = (void **)(a3 + 1288);
      v45 = operator new[](v43);
      if ( *((void **)a3 + 161) == v45 )
      {
        v45 = *v44;
      }
      else
      {
        operator delete(*v44);
        *v44 = v45;
      }
      if ( v45 )
      {
        v47 = (WCHAR *)operator new[](saturated_mul((unsigned int)Sid, 2u));
        if ( *((WCHAR **)a3 + 162) == v47 )
        {
          v48 = a3 + 1288;
          v47 = (WCHAR *)*((_QWORD *)a3 + 162);
        }
        else
        {
          operator delete(*((void **)a3 + 162));
          *((_QWORD *)a3 + 162) = v47;
          v48 = a3 + 1288;
        }
        if ( v47
          && LookupAccountSidW(
               0,
               v42,
               v47,
               (LPDWORD)&Sid,
               (LPWSTR)*v44,
               &cchReferencedDomainName,
               (PSID_NAME_USE)&peUse) )
        {
          *((_QWORD *)a3 + 163) = *v48;
          *((_QWORD *)a3 + 164) = *((_QWORD *)a3 + 162);
        }
      }
    }
  }
  if ( !ProcessIdToSessionId(dwProcessId, (DWORD *)a3 + 330) )
    *((_DWORD *)a3 + 330) = -1;
  Common::CloseHandleHelper((Common *)TokenHandle, v49);
  operator delete(v6, v50);
  return 0;
}

```

## disassembly

```asm
0x180026888  mov     [rsp-38h+arg_8], rbx
0x18002688d  mov     [rsp-38h+dwProcessId], ecx
0x180026891  push    rbp
0x180026892  push    rsi
0x180026893  push    rdi
0x180026894  push    r12
0x180026896  push    r13
0x180026898  push    r14
0x18002689a  push    r15
0x18002689c  mov     rbp, rsp
0x18002689f  sub     rsp, 70h
0x1800268a3  mov     rcx, r8; this
0x1800268a6  mov     rdi, r8
0x1800268a9  mov     r13, rdx
0x1800268ac  call    ?Reset@FileInUseProcessInformation@Common@@QEAAXXZ; Common::FileInUseProcessInformation::Reset(void)
0x1800268b1  xor     r12d, r12d
0x1800268b4  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800268b8  mov     ebx, r12d
0x1800268bb  mov     [rbp+Sid], r12
0x1800268bf  mov     rcx, r13; ProcessHandle
0x1800268c2  mov     [rbp+var_18], rbx
0x1800268c6  mov     [rbp+TokenHandle], r12
0x1800268ca  lea     r14, [rdi+100h]
0x1800268d1  lea     edx, [r12+8]; DesiredAccess
0x1800268d6  call    cs:__imp_OpenProcessToken
0x1800268dc  test    eax, eax
0x1800268de  jnz     loc_180026994
0x1800268e4  call    cs:__imp_GetLastError
0x1800268ea  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800268f1  mov     edx, 82h; unsigned __int64
0x1800268f6  mov     r9d, eax
0x1800268f9  mov     rcx, r14; unsigned __int16 *
0x1800268fc  mov     r15d, eax
0x1800268ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026904  mov     rcx, [rbp+38h]; this
0x180026908  test    eax, eax
0x18002690a  jns     short loc_180026921
0x18002690c  mov     r9d, eax; char *
0x18002690f  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026916  mov     edx, 0C1h; void *
0x18002691b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026921  mov     r9d, r15d
0x180026924  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x18002692b  mov     edx, 80h; unsigned __int64
0x180026930  mov     rcx, rdi; unsigned __int16 *
0x180026933  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026938  mov     rcx, [rbp+38h]; this
0x18002693c  test    eax, eax
0x18002693e  jns     short loc_180026955
0x180026940  mov     r9d, eax; char *
0x180026943  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x18002694a  mov     edx, 0C3h; void *
0x18002694f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026955  lea     rsi, [rdi+228h]
0x18002695c  mov     r9d, r15d
0x18002695f  mov     rcx, rsi; unsigned __int16 *
0x180026962  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x180026969  mov     edx, 64h ; 'd'; unsigned __int64
0x18002696e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026973  mov     rcx, [rbp+38h]; this
0x180026977  test    eax, eax
0x180026979  jns     loc_180026B53
0x18002697f  mov     r9d, eax; char *
0x180026982  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026989  mov     edx, 0C5h; void *
0x18002698e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026994  mov     rcx, [rbp+TokenHandle]; token
0x180026998  lea     rdx, [rbp+applicationUserModelIdLength]; applicationUserModelIdLength
0x18002699c  mov     esi, 82h
0x1800269a1  mov     r8, r14; applicationUserModelId
0x1800269a4  mov     [rbp+applicationUserModelIdLength], esi
0x1800269a7  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800269ad  cmp     eax, 3D57h
0x1800269b2  jnz     short loc_1800269E0
0x1800269b4  lea     r8, aNone; "<None>"
0x1800269bb  mov     edx, esi; unsigned __int64
0x1800269bd  mov     rcx, r14; unsigned __int16 *
0x1800269c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800269c5  mov     rcx, [rbp+38h]; this
0x1800269c9  test    eax, eax
0x1800269cb  jns     short loc_180026A16
0x1800269cd  mov     r9d, eax; char *
0x1800269d0  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x1800269d7  lea     edx, [rsi+4Dh]; void *
0x1800269da  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800269e0  test    eax, eax
0x1800269e2  jz      short loc_180026A16
0x1800269e4  mov     r9d, eax
0x1800269e7  lea     r8, aError0xXInGeta; "<Error 0x%X in GetApplicationUserModelI"...
0x1800269ee  mov     rdx, rsi; unsigned __int64
0x1800269f1  mov     rcx, r14; unsigned __int16 *
0x1800269f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800269f9  mov     rcx, [rbp+38h]; this
0x1800269fd  test    eax, eax
0x1800269ff  jns     short loc_180026A16
0x180026a01  mov     r9d, eax; char *
0x180026a04  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026a0b  mov     edx, 0D4h; void *
0x180026a10  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026a16  mov     rcx, [rbp+TokenHandle]; token
0x180026a1a  lea     rdx, [rbp+applicationUserModelIdLength]; packageFullNameLength
0x180026a1e  mov     esi, 80h
0x180026a23  mov     r8, rdi; packageFullName
0x180026a26  mov     [rbp+applicationUserModelIdLength], esi
0x180026a29  call    cs:__imp_GetPackageFullNameFromToken
0x180026a2f  cmp     eax, 3D54h
0x180026a34  jnz     short loc_180026A62
0x180026a36  lea     r8, aNone; "<None>"
0x180026a3d  mov     edx, esi; unsigned __int64
0x180026a3f  mov     rcx, rdi; unsigned __int16 *
0x180026a42  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026a47  mov     rcx, [rbp+38h]; this
0x180026a4b  test    eax, eax
0x180026a4d  jns     short loc_180026A98
0x180026a4f  mov     r9d, eax; char *
0x180026a52  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026a59  lea     edx, [rsi+5Ch]; void *
0x180026a5c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026a62  test    eax, eax
0x180026a64  jz      short loc_180026A98
0x180026a66  mov     r9d, eax
0x180026a69  lea     r8, aError0xXInGetp; "<Error 0x%X in GetPackageFullName>"
0x180026a70  mov     rdx, rsi; unsigned __int64
0x180026a73  mov     rcx, rdi; unsigned __int16 *
0x180026a76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026a7b  mov     rcx, [rbp+38h]; this
0x180026a7f  test    eax, eax
0x180026a81  jns     short loc_180026A98
0x180026a83  mov     r9d, eax; char *
0x180026a86  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026a8d  mov     edx, 0E1h; void *
0x180026a92  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026a98  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180026a9c  lea     rdx, [rbp+var_18]; void **
0x180026aa0  call    ?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z; Common::SidHelper::GetUserSidFromToken(void *,void * *)
0x180026aa5  mov     rbx, [rbp+var_18]
0x180026aa9  test    eax, eax
0x180026aab  jns     short loc_180026AFA
0x180026aad  lea     rcx, [rdi+228h]; unsigned __int16 *
0x180026ab4  mov     r9d, eax
0x180026ab7  lea     r8, aError0xXGettin; "<Error 0x%X getting the user's SID from"...
0x180026abe  mov     edx, 64h ; 'd'; unsigned __int64
0x180026ac3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026ac8  mov     rcx, [rbp+38h]; this
0x180026acc  test    eax, eax
0x180026ace  jns     short loc_180026AE5
0x180026ad0  mov     r9d, eax; char *
0x180026ad3  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026ada  mov     edx, 0E9h; void *
0x180026adf  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026ae5  lea     rsi, [rdi+208h]
0x180026aec  cmp     [rsi], r12d
0x180026aef  jbe     short loc_180026B4C
0x180026af1  mov     rsi, [rdi+210h]
0x180026af8  jmp     short loc_180026B53
0x180026afa  lea     rsi, [rdi+208h]
0x180026b01  mov     [rbp+Sid], rbx
0x180026b05  mov     rdx, rsi; this
0x180026b08  mov     rcx, rbx; Sid
0x180026b0b  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x180026b10  test    eax, eax
0x180026b12  jns     short loc_180026AEC
0x180026b14  lea     rcx, [rdi+228h]; unsigned __int16 *
0x180026b1b  mov     r9d, eax
0x180026b1e  lea     r8, aError0xXConver; "<Error 0x%X converting the user's SID t"...
0x180026b25  mov     edx, 64h ; 'd'; unsigned __int64
0x180026b2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026b2f  mov     rcx, [rbp+38h]; this
0x180026b33  test    eax, eax
0x180026b35  jns     short loc_180026AEC
0x180026b37  mov     r9d, eax; char *
0x180026b3a  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026b41  mov     edx, 0F2h; void *
0x180026b46  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026b4c  lea     rsi, [rdi+228h]
0x180026b53  mov     eax, 220h
0x180026b58  lea     r15, [rdi+300h]
0x180026b5f  mov     rcx, rdi
0x180026b62  lea     r9, [rbp+dwSize]; lpdwSize
0x180026b66  mov     r8, r15; lpExeName
0x180026b69  xor     edx, edx; dwFlags
0x180026b6b  mov     [rcx+rax], rsi
0x180026b6f  mov     rcx, r13; hProcess
0x180026b72  mov     [rbp+dwSize], 104h
0x180026b79  call    cs:__imp_QueryFullProcessImageNameW
0x180026b7f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180026b83  test    eax, eax
0x180026b85  jnz     loc_180026C7A
0x180026b8b  call    cs:__imp_GetLastError
0x180026b91  mov     esi, eax
0x180026b93  cmp     eax, 7Ah ; 'z'
0x180026b96  jnz     loc_180026C42
0x180026b9c  mov     ecx, [rbp+dwSize]
0x180026b9f  lea     eax, [rsi-78h]
0x180026ba2  inc     ecx
0x180026ba4  mov     edx, ecx
0x180026ba6  mul     rdx
0x180026ba9  mov     [rbp+dwSize], ecx
0x180026bac  cmovb   rax, r14
0x180026bb0  mov     rcx, rax; unsigned __int64
0x180026bb3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026bb8  mov     r14, rax
0x180026bbb  mov     rax, [rdi+2F8h]
0x180026bc2  cmp     rax, r14
0x180026bc5  jz      short loc_180026BD8
0x180026bc7  mov     rcx, rax; Block
0x180026bca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026bcf  mov     [rdi+2F8h], r14
0x180026bd6  jmp     short loc_180026BDB
0x180026bd8  mov     r14, rax
0x180026bdb  test    r14, r14
0x180026bde  jnz     short loc_180026C11
0x180026be0  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x180026be7  mov     edx, 104h; unsigned __int64
0x180026bec  mov     rcx, r15; unsigned __int16 *
0x180026bef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026bf4  mov     rcx, [rbp+38h]; this
0x180026bf8  test    eax, eax
0x180026bfa  jns     short loc_180026C7A
0x180026bfc  mov     r9d, eax; char *
0x180026bff  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026c06  mov     edx, 103h; void *
0x180026c0b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026c11  lea     r9, [rbp+dwSize]; lpdwSize
0x180026c15  mov     r8, r14; lpExeName
0x180026c18  xor     edx, edx; dwFlags
0x180026c1a  mov     rcx, r13; hProcess
0x180026c1d  call    cs:__imp_QueryFullProcessImageNameW
0x180026c23  test    eax, eax
0x180026c25  jnz     short loc_180026C46
0x180026c27  call    cs:__imp_GetLastError
0x180026c2d  mov     rcx, [rdi+2F8h]; Block
0x180026c34  mov     esi, eax
0x180026c36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026c3b  mov     [rdi+2F8h], r12
0x180026c42  test    esi, esi
0x180026c44  jz      short loc_180026C7A
0x180026c46  mov     r9d, esi
0x180026c49  lea     r8, aError0xXInQuer; "<Error 0x%X in QueryFullProcessImageNam"...
0x180026c50  mov     edx, 104h; unsigned __int64
0x180026c55  mov     rcx, r15; unsigned __int16 *
0x180026c58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026c5d  mov     rcx, [rbp+38h]; this
0x180026c61  test    eax, eax
0x180026c63  jns     short loc_180026C7A
0x180026c65  mov     r9d, eax; char *
0x180026c68  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026c6f  mov     edx, 10Fh; void *
0x180026c74  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026c7a  mov     rax, [rdi+2F8h]
0x180026c81  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x180026c86  test    rax, rax
0x180026c89  mov     [rbp+ProcessInformationLength], r12d
0x180026c8d  mov     r12d, 208h
0x180026c93  mov     rcx, r13; ProcessHandle
0x180026c96  cmovz   rax, r15
0x180026c9a  mov     r9d, r12d; ProcessInformationLength
0x180026c9d  mov     [rdi+2F0h], rax
0x180026ca4  lea     r15, [rdi+540h]
0x180026cab  lea     rax, [rbp+ProcessInformationLength]
0x180026caf  mov     r8, r15; ProcessInformation
0x180026cb2  mov     [rsp+70h+ReturnLength], rax; int
0x180026cb7  call    cs:__imp_NtQueryInformationProcess
0x180026cbd  mov     r14d, eax
0x180026cc0  test    eax, eax
0x180026cc2  jns     loc_180026DC4
0x180026cc8  cmp     eax, 0C0000004h
0x180026ccd  jnz     loc_180026D80
0x180026cd3  mov     ecx, [rbp+ProcessInformationLength]; unsigned __int64
0x180026cd6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026cdb  mov     r14, rax
0x180026cde  mov     rax, [rdi+538h]
0x180026ce5  cmp     rax, r14
0x180026ce8  jz      short loc_180026D02
0x180026cea  mov     rcx, rax; void *
0x180026ced  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026cf2  mov     [rdi+538h], r14
0x180026cf9  lea     rsi, [rdi+540h]
0x180026d00  jmp     short loc_180026D08
0x180026d02  mov     rsi, r15
0x180026d05  mov     r14, rax
0x180026d08  test    r14, r14
0x180026d0b  jnz     short loc_180026D42
0x180026d0d  lea     r8, aErrorAllocatin; "<Error allocating memory>"
0x180026d14  mov     edx, 104h; unsigned __int64
0x180026d19  mov     rcx, r15; unsigned __int16 *
0x180026d1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026d21  mov     rcx, [rbp+38h]; this
0x180026d25  test    eax, eax
0x180026d27  jns     loc_180026E53
0x180026d2d  mov     r9d, eax; char *
0x180026d30  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\AppModel\\"...
0x180026d37  mov     edx, 120h; void *
0x180026d3c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026d42  mov     r9d, [rbp+ProcessInformationLength]; ProcessInformationLength
0x180026d46  mov     r8, r14; ProcessInformation
0x180026d49  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x180026d4e  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x180026d57  mov     rcx, r13; ProcessHandle
0x180026d5a  call    cs:__imp_NtQueryInformationProcess
  ... truncated ...
```
