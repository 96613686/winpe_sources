# CDeploymentSession::WriteOSInstallXML(wchar_t const *,ActionList *)

- ea: `0x180098f98`
- end: `0x18009a002`
- name: `?WriteOSInstallXML@CDeploymentSession@@AEAAJPEB_WPEAUActionList@@@Z`
- size: `4202`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, const wchar_t *, struct ActionList *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004e598`

## callees

- `0x1800059d0`
- `0x180008f00`
- `0x180009908`
- `0x180013b34`
- `0x180025064`
- `0x1800403f0`
- `0x180078b9c`
- `0x180094d0c`
- `0x180094d2c`
- `0x180098f98`
- `0x18009b6b0`
- `0x18009b6cc`
- `0x1801efbc8`
- `0x1801f250c`
- `0x1802067c4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180099c2e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180099c2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099be2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099be2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009965c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099690`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800996c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800996f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009972c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099760`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099794`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099800`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009986c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800998d8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099944`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800999ad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009965c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099690`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800996c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800996f8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009972c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099760`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099794`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099800`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009986c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800998d8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180099944`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800999ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099fb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180099c4d`

## string_xrefs

- `0x18009959f`: `MSIXFramework`
- `0x180099d5c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099d73`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099d88`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099d9c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099db0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099dc4`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099dd8`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099dec`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e00`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e14`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e28`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e3c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e50`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e64`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e78`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099e8c`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099ea0`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099eb4`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099ec8`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099edc`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099ef1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f05`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f19`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f2d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f41`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f55`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f69`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f7d`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099f91`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099fa3`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099fef`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\UpdateActionsGenerator.h`
- `0x180099596`: `MSIXApps`
- `0x180099094`: `OSInstall file path: %s`
- `0x18009960a`: `Using express package path for Stage Partial Action [%ws]`
- `0x180099fd3`: `Failed to create OS install plan file: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CDeploymentSession::WriteOSInstallXML(
        CDeploymentSession *this,
        const wchar_t *a2,
        struct ActionList *a3)
{
  struct ActionList *v3; // r14
  int v5; // eax
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rbx
  unsigned int v9; // edx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int v12; // r10d
  unsigned int i; // r8d
  __int64 *v14; // rdi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  const WCHAR *v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  unsigned int j; // ebx
  int v32; // eax
  __int64 (__fastcall *v33)(__int64 *, _QWORD, __int64 *, __int64 *); // r10
  const WCHAR *v34; // r8
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  const WCHAR *v40; // rbx
  __int64 v41; // r15
  __int64 v42; // r8
  int v43; // edx
  __int64 v44; // rsi
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // r14
  __int64 v48; // r15
  _QWORD *v49; // rdx
  __int128 *v50; // rcx
  _QWORD *v51; // rdx
  int v52; // eax
  __int64 v53; // r9
  int v54; // eax
  __int64 v55; // r9
  int v56; // eax
  __int64 v57; // r9
  int v58; // eax
  __int64 v59; // r9
  int v60; // eax
  __int64 v61; // r9
  int v62; // eax
  __int64 v63; // r9
  int v64; // eax
  int v65; // eax
  void (__fastcall ***v66)(_QWORD); // rsi
  int v67; // eax
  struct ActionList *FileW; // rbx
  const char *v69; // r9
  const char *v70; // r9
  __int64 result; // rax
  __int64 v72; // rcx
  DWORD LastError; // ebx
  int lpString2; // [rsp+20h] [rbp-198h]
  unsigned int lpString2a; // [rsp+20h] [rbp-198h]
  DWORD *v76; // [rsp+40h] [rbp-178h] BYREF
  __int64 v77; // [rsp+48h] [rbp-170h] BYREF
  __int64 v78; // [rsp+50h] [rbp-168h]
  const WCHAR *v79; // [rsp+58h] [rbp-160h]
  __int64 v80; // [rsp+60h] [rbp-158h]
  void (__fastcall ***v81)(_QWORD); // [rsp+68h] [rbp-150h] BYREF
  __int64 *v82; // [rsp+70h] [rbp-148h] BYREF
  void (__fastcall ***v83)(_QWORD); // [rsp+78h] [rbp-140h] BYREF
  struct ActionList *v84; // [rsp+80h] [rbp-138h]
  CDeploymentSession *v85; // [rsp+88h] [rbp-130h]
  void (__fastcall ***v86)(_QWORD); // [rsp+90h] [rbp-128h]
  __int64 v87; // [rsp+98h] [rbp-120h]
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-118h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+A8h] [rbp-110h] BYREF
  DWORD nNumberOfBytesToWrite[4]; // [rsp+B0h] [rbp-108h] BYREF
  LPCVOID lpBuffer; // [rsp+C0h] [rbp-F8h]
  __int128 v92; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v93; // [rsp+D8h] [rbp-E0h]
  __int128 v94; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v95; // [rsp+F0h] [rbp-C8h]
  __int128 v96; // [rsp+F8h] [rbp-C0h] BYREF
  __int64 v97; // [rsp+108h] [rbp-B0h]
  __int128 v98; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v99; // [rsp+120h] [rbp-98h]
  __int128 v100; // [rsp+128h] [rbp-90h] BYREF
  __int64 v101; // [rsp+138h] [rbp-80h]
  __int128 v102; // [rsp+140h] [rbp-78h] BYREF
  __int64 v103; // [rsp+150h] [rbp-68h]
  __int128 v104; // [rsp+158h] [rbp-60h] BYREF
  __int64 v105; // [rsp+168h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v87 = -2;
  try
  {
    v3 = a3;
    v84 = a3;
    v85 = this;
    lpFileName = a2;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)0x80004003LL,
        lpString2);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)0x80004003LL,
        lpString2);
    v83 = 0;
    v81 = 0;
    v82 = 0;
    *(_OWORD *)nNumberOfBytesToWrite = 0;
    lpBuffer = 0;
    v5 = RtlCreateUtf8UCSStringBuilder(retaddr, a2, &v83, &v81);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x134,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v5,
        lpString2);
    v86 = v81;
    v6 = RtlCreateDefaultXmlWriter(26, v81, &v82);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v6,
        lpString2);
    v7 = *((_QWORD *)this + 75);
    if ( v7 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v7, 2, L"OSInstall file path: %s", lpFileName);
    v8 = 0;
    if ( *((_DWORD *)v3 + 18) )
    {
      v9 = 0;
      v10 = *((_QWORD *)v3 + 8);
      do
      {
        v11 = 168LL * v9;
        v12 = *(_DWORD *)(v11 + v10 + 120);
        if ( v12 )
        {
          for ( i = 0; i < v12; ++i )
            v8 += *(_QWORD *)(184LL * i + *(_QWORD *)(v11 + v10 + 112));
        }
        ++v9;
      }
      while ( v9 < *((_DWORD *)v3 + 18) );
    }
    v14 = v82;
    v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v82 + 24))(
            v82,
            0,
            ___LiteralObject__2U__BaseLiteralBuffer__0O_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EP__0FD__0EJ__0GO__0HD__0HE__0GB__0GM__0GM__0FA__0GM__0GB__0GO__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v15,
        lpString2);
    v16 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, __int64 *))(*v14 + 96))(
            v14,
            0,
            ___LiteralObject__2U__BaseLiteralBuffer__05U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HI__0GN__0GM__0GO__0HD__0A_____0A__00_01_02_03_04_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            ___LiteralObject__2U__BaseLiteralBuffer__0CN_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HF__0HC__0GO__0DK__0HD__0GD__0GI__0GF__0GN__0GB__0HD__0CN__0GN__0GJ__0GD__0HC__0GP__0HD__0GP__0GG__0HE__0CN__0GD__0GP__0GN__0DK__0GP__0HD__0CN__0GJ__0GO__0HD__0HE__0GB__0GM__0GM__0CN__0GB__0GD__0HE__0GJ__0GP__0GO__0HD__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x14B,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v16,
        lpString2);
    v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v14 + 48))(v14, 0);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v17,
        lpString2);
    v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v14 + 24))(
            v14,
            0,
            ___LiteralObject__2U__BaseLiteralBuffer__09U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EE__0GP__0HH__0GO__0GM__0GP__0GB__0GE__0HD__0A_____0A__00_01_02_03_04_05_06_07_08_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x150,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v18,
        lpString2);
    v76 = nNumberOfBytesToWrite;
    v19 = Windows::StringUtil::Rtl::FormatInteger<Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>,unsigned __int64>(
            retaddr,
            v8,
            &v76);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v19,
        lpString2);
    v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, DWORD *))(*v14 + 96))(
            v14,
            0,
            ___LiteralObject__2U__BaseLiteralBuffer__0P_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EP__0FD__0EE__0GP__0HH__0GO__0GM__0GP__0GB__0GE__0FD__0GJ__0HK__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            nNumberOfBytesToWrite);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v20,
        lpString2);
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 48))(v14, 1);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x155,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v21,
        lpString2);
    v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *))(*v14 + 24))(
            v14,
            0,
            &___LiteralObject__2U__BaseLiteralBuffer__05U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GF__0GE__0GJ__0GB__0A_____0A__00_01_02_03_04_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v22,
        lpString2);
    v23 = *((_QWORD *)v3 + 10);
    if ( v23 )
    {
      v24 = *v14;
      v25 = *(const WCHAR **)(v23 + 24);
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      v77 = 2 * v26;
      v78 = 2 * v26 + 2;
      v79 = v25;
      v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, __int64 *))(v24 + 88))(
              v14,
              0,
              ___LiteralObject__2U__BaseLiteralBuffer__04U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0EO__0GB__0GN__0GF__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
              &v77);
      if ( v27 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x15F,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
          (const char *)(unsigned int)v27,
          lpString2);
      v76 = nNumberOfBytesToWrite;
      v28 = Windows::StringUtil::Rtl::FormatInteger<Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>,unsigned __int64>(
              retaddr,
              *(_QWORD *)(*((_QWORD *)v3 + 10) + 48LL),
              &v76);
      if ( v28 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
          (const char *)(unsigned int)v28,
          lpString2);
      v29 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, DWORD *))(*v14 + 96))(
              v14,
              0,
              ___LiteralObject__2U__BaseLiteralBuffer__0O_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EJ__0GO__0HD__0HE__0GB__0GM__0GM__0GF__0GE__0FD__0GJ__0HK__0GF__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_LUTF8_STRING__B,
              nNumberOfBytesToWrite);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
          (const char *)(unsigned int)v29,
          lpString2);
    }
    v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v14 + 48))(v14, 0);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v30,
        lpString2);
    if ( *((_QWORD *)v3 + 10) )
    {
      for ( j = 0; j < *(_DWORD *)(*((_QWORD *)v3 + 10) + 8LL); ++j )
      {
        v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v14 + 24))(
                v14,
                0,
                ___LiteralObject__2U__BaseLiteralBuffer__07U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FA__0GB__0GD__0GL__0GB__0GH__0GF__0A_____0A__00_01_02_03_04_05_06_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        if ( v32 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x16A,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
            (const char *)(unsigned int)v32,
            lpString2);
        v33 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, __int64 *))(*v14 + 88);
        v34 = *(const WCHAR **)(**((_QWORD **)v3 + 10) + 24LL * j + 8);
        v35 = -1;
        do
          ++v35;
        while ( v34[v35] );
        v77 = 2 * v35;
        v78 = 2 * v35 + 2;
        v79 = v34;
        v36 = v33(
                v14,
                0,
                ___LiteralObject__2U__BaseLiteralBuffer__0M_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FA__0GB__0GD__0GL__0GB__0GH__0GF__0FA__0GB__0HE__0GI__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_LUNICODE_STRING__B,
                &v77);
        if ( v36 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x16B,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
            (const char *)(unsigned int)v36,
            lpString2);
        v37 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 48))(v14, 1);
        if ( v37 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x16C,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
            (const char *)(unsigned int)v37,
            lpString2);
      }
    }
    v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *))(*v14 + 64))(
            v14,
            0,
            &___LiteralObject__2U__BaseLiteralBuffer__05U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GF__0GE__0GJ__0GB__0A_____0A__00_01_02_03_04_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v38 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v38,
        lpString2);
    v104 = 0;
    v105 = 0;
    v102 = 0;
    v103 = 0;
    v100 = 0;
    v101 = 0;
    v98 = 0;
    v99 = 0;
    v96 = 0;
    v97 = 0;
    v94 = 0;
    v95 = 0;
    v92 = 0;
    v93 = 0;
    v39 = 0;
    while ( 1 )
    {
      v40 = L"LCU";
      LODWORD(v76) = v39;
      if ( (unsigned int)v39 >= *((_DWORD *)v3 + 24) )
        break;
      v41 = 168 * v39;
      v42 = *((_QWORD *)v3 + 11);
      v43 = *(_DWORD *)(168 * v39 + v42 + 88);
      if ( v43 > 10000 )
        goto LABEL_75;
      if ( v43 == 10000 )
      {
LABEL_74:
        v40 = L"Media";
        goto LABEL_76;
      }
      if ( v43 > 13 )
      {
        switch ( v43 )
        {
          case 14:
            v40 = L"SafeOSDU";
            break;
          case 15:
            v40 = L"SetupDU";
            break;
          case 16:
            v40 = L"Driver";
            break;
          case 17:
            v40 = L"LXP";
            break;
          case 19:
            v40 = L"MSIXFramework";
            break;
          default:
            if ( v43 != 20 && (unsigned int)(v43 - 21) > 1 )
            {
LABEL_75:
              v40 = L"Unknown";
              break;
            }
            v40 = L"MSIXApps";
            break;
        }
      }
      else
      {
        switch ( v43 )
        {
          case 13:
            v40 = L"CritDU";
            break;
          case 2:
            v40 = L"OnDemand";
            break;
          case 3:
            v40 = L"Satellite";
            break;
          case 4:
LABEL_57:
            v40 = L"LangPack";
            break;
          case 5:
            v40 = L"GDR";
            break;
          default:
            if ( v43 != 6 )
            {
              switch ( v43 )
              {
                case 7:
                  v40 = L"Critical";
                  break;
                case 9:
                  goto LABEL_57;
                case 11:
                  goto LABEL_74;
                case 12:
                  v40 = L"Tools";
                  break;
                default:
                  goto LABEL_75;
              }
            }
            break;
        }
      }
LABEL_76:
      v44 = *(_QWORD *)(v41 + v42 + 56);
      if ( *(_DWORD *)(v41 + v42 + 96) == 4 && v43 == 6 )
      {
        v44 = *(_QWORD *)(v41 + v42 + 72);
        v45 = *((_QWORD *)v85 + 75);
        if ( v45 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v45,
            2,
            L"Using express package path for Stage Partial Action [%ws]",
            *(_QWORD *)(v41 + v42 + 72));
      }
      v46 = *((_QWORD *)v3 + 11);
      v47 = *(_QWORD *)(v41 + v46 + 40);
      v77 = v47;
      v78 = v44;
      v79 = v40;
      v48 = *(_QWORD *)(v41 + v46 + 8);
      v80 = v48;
      if ( CompareStringW(0x409u, 1u, v40, -1, L"OnDemand", -1) == 2
        || CompareStringW(0x409u, 1u, v40, -1, L"Satellite", -1) == 2
        || CompareStringW(0x409u, 1u, v40, -1, L"LangPack", -1) == 2
        || CompareStringW(0x409u, 1u, v40, -1, L"GDR", -1) == 2
        || CompareStringW(0x409u, 1u, v40, -1, L"LCU", -1) == 2
        || CompareStringW(0x409u, 1u, v40, -1, L"Critical", -1) == 2 )
      {
        v51 = (_QWORD *)*((_QWORD *)&v104 + 1);
        if ( *((_QWORD *)&v104 + 1) == v105 )
        {
          std::vector<CDeviceInfo::FeatureDependency>::_Emplace_reallocate<CDeviceInfo::FeatureDependency>(
            &v104,
            *((_QWORD *)&v104 + 1),
            &v77);
        }
        else
        {
          **((_QWORD **)&v104 + 1) = v47;
          v51[1] = v44;
          v51[2] = v40;
          v51[3] = v48;
          *((_QWORD *)&v104 + 1) += 32LL;
        }
      }
      else
      {
        if ( CompareStringW(0x409u, 1u, v40, -1, L"LXP", -1) == 2 )
        {
          v49 = (_QWORD *)*((_QWORD *)&v102 + 1);
          if ( *((_QWORD *)&v102 + 1) != v103 )
          {
            **((_QWORD **)&v102 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v102 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v102;
        }
        else if ( CompareStringW(0x409u, 1u, v40, -1, L"Tools", -1) == 2 )
        {
          v49 = (_QWORD *)*((_QWORD *)&v100 + 1);
          if ( *((_QWORD *)&v100 + 1) != v101 )
          {
            **((_QWORD **)&v100 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v100 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v100;
        }
        else if ( CompareStringW(0x409u, 1u, v40, -1, L"Driver", -1) == 2 )
        {
          v49 = (_QWORD *)*((_QWORD *)&v98 + 1);
          if ( *((_QWORD *)&v98 + 1) != v99 )
          {
            **((_QWORD **)&v98 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v98 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v98;
        }
        else if ( CompareStringW(0x409u, 1u, v40, -1, L"SafeOSDU", -1) == 2 )
        {
          v49 = (_QWORD *)*((_QWORD *)&v96 + 1);
          if ( *((_QWORD *)&v96 + 1) != v97 )
          {
            **((_QWORD **)&v96 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v96 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v96;
        }
        else if ( CompareStringW(0x409u, 1u, v40, -1, L"SetupDU", -1) == 2 )
        {
          v49 = (_QWORD *)*((_QWORD *)&v94 + 1);
          if ( *((_QWORD *)&v94 + 1) != v95 )
          {
            **((_QWORD **)&v94 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v94 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v94;
        }
        else
        {
          if ( CompareStringW(0x409u, 1u, v40, -1, L"CritDU", -1) != 2 )
            goto LABEL_114;
          v49 = (_QWORD *)*((_QWORD *)&v92 + 1);
          if ( *((_QWORD *)&v92 + 1) != v93 )
          {
            **((_QWORD **)&v92 + 1) = v47;
            v49[1] = v44;
            v49[2] = v40;
            v49[3] = v48;
            *((_QWORD *)&v92 + 1) += 32LL;
            goto LABEL_114;
          }
          v50 = &v92;
        }
        std::vector<CDeviceInfo::FeatureDependency>::_Emplace_reallocate<CDeviceInfo::FeatureDependency>(v50, v49, &v77);
      }
LABEL_114:
      v39 = (unsigned int)((_DWORD)v76 + 1);
      v3 = v84;
    }
    v52 = CreateInstallSection(
            ___LiteralObject__2U__BaseLiteralBuffer__0L_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EP__0FD__0FA__0GB__0GD__0GL__0GB__0GH__0GF__0HD__0A_____0A__00_01_02_03_04_05_06_07_08_09_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v104,
            v14,
            L"Satellite");
    if ( v52 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v52,
        lpString2);
    v54 = CreateInstallSection(
            &___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EM__0FI__0FA__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v102,
            v14,
            v53);
    if ( v54 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v54,
        lpString2);
    v56 = CreateInstallSection(
            ___LiteralObject__2U__BaseLiteralBuffer__05U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FE__0GP__0GP__0GM__0HD__0A_____0A__00_01_02_03_04_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v100,
            v14,
            v55);
    if ( v56 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v56,
        lpString2);
    v58 = CreateInstallSection(
            &___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EE__0HC__0GJ__0HG__0GF__0HC__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v98,
            v14,
            v57);
    if ( v58 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v58,
        lpString2);
    v60 = CreateInstallSection(
            &___LiteralObject__2U__BaseLiteralBuffer__08U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FD__0GB__0GG__0GF__0EP__0FD__0EE__0FF__0A_____0A__00_01_02_03_04_05_06_07_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v96,
            v14,
            v59);
    if ( v60 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v60,
        lpString2);
    v62 = CreateInstallSection(
            &___LiteralObject__2U__BaseLiteralBuffer__07U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FD__0GF__0HE__0HF__0HA__0EE__0FF__0A_____0A__00_01_02_03_04_05_06_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v94,
            v14,
            v61);
    if ( v62 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v62,
        lpString2);
    v64 = CreateInstallSection(
            &___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0ED__0HC__0GJ__0HE__0EE__0FF__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
            &v92,
            v14,
            v63);
    if ( v64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v64,
        lpString2);
    v65 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v14 + 64))(
            v14,
            0,
            ___LiteralObject__2U__BaseLiteralBuffer__0O_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EP__0FD__0EJ__0GO__0HD__0HE__0GB__0GM__0GM__0FA__0GM__0GB__0GO__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v65 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v65,
        lpString2);
    v66 = v83;
    v67 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _QWORD, DWORD *))(*v83)[2])(
            v83,
            0,
            nNumberOfBytesToWrite);
    if ( v67 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)(unsigned int)v67,
        lpString2);
    FileW = (struct ActionList *)CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v84 = FileW;
    if ( (unsigned __int64)FileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
        LogAdapter::Logger::Log<wchar_t const *>(v72, 3, "Failed to create OS install plan file: {}", &lpFileName);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        (const char *)LastError,
        lpString2a);
    }
    NumberOfBytesWritten = 0;
    if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
        v69);
    CloseHandle(FileW);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v92);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v94);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v96);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v98);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v100);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v102);
    std::vector<CDeviceInfo::FeatureDependency>::~vector<CDeviceInfo::FeatureDependency>(&v104);
    if ( lpBuffer )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(lpBuffer);
      *(_OWORD *)nNumberOfBytesToWrite = 0;
      lpBuffer = 0;
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64 *))*v14)(v14);
    if ( v86 )
      (**v86)(v86);
    if ( v66 )
      (**v66)(v66);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CC,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\UpdateActionsGenerator.h",
                           v70);
  }
  return result;
}

```

## disassembly

```asm
0x180098f98  push    rbx
0x180098f9a  push    rsi
0x180098f9b  push    rdi
0x180098f9c  push    r12
0x180098f9e  push    r13
0x180098fa0  push    r14
0x180098fa2  push    r15
0x180098fa4  sub     rsp, 180h
0x180098fab  mov     [rsp+1B8h+var_120], 0FFFFFFFFFFFFFFFEh
0x180098fb7  mov     rax, cs:__security_cookie
0x180098fbe  xor     rax, rsp
0x180098fc1  mov     [rsp+1B8h+var_48], rax
0x180098fc9  mov     r14, r8
0x180098fcc  mov     [rsp+1B8h+var_138], r8
0x180098fd4  mov     rbx, rcx
0x180098fd7  mov     [rsp+1B8h+var_130], rcx
0x180098fdf  mov     [rsp+1B8h+lpFileName], rdx
0x180098fe7  mov     rcx, [rsp+1B8h]; this
0x180098fef  xor     edi, edi
0x180098ff1  test    rdx, rdx
0x180098ff4  jz      loc_180099D56
0x180098ffa  mov     rcx, [rsp+1B8h]; this
0x180099002  test    r14, r14
0x180099005  jz      loc_180099D6D
0x18009900b  mov     [rsp+1B8h+var_140], rdi
0x180099010  mov     [rsp+1B8h+var_150], rdi
0x180099015  mov     [rsp+1B8h+var_148], rdi
0x18009901a  xorps   xmm0, xmm0
0x18009901d  xor     eax, eax
0x18009901f  movups  xmmword ptr [rsp+1B8h+nNumberOfBytesToWrite], xmm0
0x180099027  mov     [rsp+1B8h+lpBuffer], rax
0x18009902f  lea     r9, [rsp+1B8h+var_150]
0x180099034  lea     r8, [rsp+1B8h+var_140]
0x180099039  call    RtlCreateUtf8UCSStringBuilder
0x18009903e  mov     rcx, [rsp+1B8h]; this
0x180099046  test    eax, eax
0x180099048  js      loc_180099D85
0x18009904e  lea     r8, [rsp+1B8h+var_148]
0x180099053  mov     r15, [rsp+1B8h+var_150]
0x180099058  mov     [rsp+1B8h+var_128], r15
0x180099060  mov     rdx, r15
0x180099063  mov     ecx, 1Ah
0x180099068  call    RtlCreateDefaultXmlWriter
0x18009906d  mov     rcx, [rsp+1B8h]; this
0x180099075  xor     r15d, r15d
0x180099078  test    eax, eax
0x18009907a  js      loc_180099D99
0x180099080  mov     rcx, [rbx+258h]
0x180099087  test    rcx, rcx
0x18009908a  jz      short loc_1800990A5
0x18009908c  mov     r9, [rsp+1B8h+lpFileName]
0x180099094  lea     r8, aOsinstallFileP; "OSInstall file path: %s"
0x18009909b  mov     edx, 2
0x1800990a0  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800990a5  mov     rbx, r15
0x1800990a8  mov     r13d, 1
0x1800990ae  cmp     [r14+48h], r15d
0x1800990b2  jbe     short loc_1800990F5
0x1800990b4  mov     edx, r15d
0x1800990b7  mov     r9, [r14+40h]
0x1800990bb  mov     eax, edx
0x1800990bd  imul    rcx, rax, 0A8h
0x1800990c4  mov     r10d, [rcx+r9+78h]
0x1800990c9  test    r10d, r10d
0x1800990cc  jz      short loc_1800990EC
0x1800990ce  mov     r8d, r15d
0x1800990d1  mov     r11, [rcx+r9+70h]
0x1800990d6  mov     eax, r8d
0x1800990d9  imul    rcx, rax, 0B8h
0x1800990e0  add     rbx, [rcx+r11]
0x1800990e4  add     r8d, r13d
0x1800990e7  cmp     r8d, r10d
0x1800990ea  jb      short loc_1800990D6
0x1800990ec  add     edx, r13d
0x1800990ef  cmp     edx, [r14+48h]
0x1800990f3  jb      short loc_1800990BB
0x1800990f5  mov     rdi, [rsp+1B8h+var_148]
0x1800990fa  mov     rax, [rdi]
0x1800990fd  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0O@U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EP@@0FD@@0EJ@@0GO@@0HD@@0HE@@0GB@@0GM@@0GM@@0FA@@0GM@@0GB@@0GO@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180099104  xor     edx, edx
0x180099106  mov     rcx, rdi
0x180099109  mov     rax, [rax+18h]
0x18009910d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099112  mov     rcx, [rsp+1B8h]; this
0x18009911a  test    eax, eax
0x18009911c  js      loc_180099DAD
0x180099122  mov     rax, [rdi]
0x180099125  lea     r9, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0CN@U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HF@@0HC@@0GO@@0DK@@0HD@@0GD@@0GI@@0GF@@0GN@@0GB@@0HD@@0CN@@0GN@@0GJ@@0GD@@0HC@@0GP@@0HD@@0GP@@0GG@@0HE@@0CN@@0GD@@0GP@@0GN@@0DK@@0GP@@0HD@@0CN@@0GJ@@0GO@@0HD@@0HE@@0GB@@0GM@@0GM@@0CN@@0GB@@0GD@@0HE@@0GJ@@0GP@@0GO@@0HD@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@$0BD@$0BE@$0BF@$0BG@$0BH@$0BI@$0BJ@$0BK@$0BL@$0BM@$0BN@$0BO@$0BP@$0CA@$0CB@$0CC@$0CD@$0CE@$0CF@$0CG@$0CH@$0CI@$0CJ@$0CK@$0CL@$0CM@@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18009912c  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$05U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HI@@0GN@@0GM@@0GO@@0HD@@0A@@@@$0A@$00$01$02$03$04@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180099133  xor     edx, edx
0x180099135  mov     rcx, rdi
0x180099138  mov     rax, [rax+60h]
0x18009913c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099141  mov     rcx, [rsp+1B8h]; this
0x180099149  test    eax, eax
0x18009914b  js      loc_180099DC1
0x180099151  mov     rax, [rdi]
0x180099154  xor     edx, edx
0x180099156  mov     rcx, rdi
0x180099159  mov     rax, [rax+30h]
0x18009915d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099162  mov     rcx, [rsp+1B8h]; this
0x18009916a  test    eax, eax
0x18009916c  js      loc_180099DD5
0x180099172  mov     rax, [rdi]
0x180099175  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$09U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EE@@0GP@@0HH@@0GO@@0GM@@0GP@@0GB@@0GE@@0HD@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x18009917c  xor     edx, edx
0x18009917e  mov     rcx, rdi
0x180099181  mov     rax, [rax+18h]
0x180099185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009918a  mov     rcx, [rsp+1B8h]; this
0x180099192  test    eax, eax
0x180099194  js      loc_180099DE9
0x18009919a  lea     rax, [rsp+1B8h+nNumberOfBytesToWrite]
0x1800991a2  mov     [rsp+1B8h+var_178], rax
0x1800991a7  lea     r8, [rsp+1B8h+var_178]
0x1800991ac  mov     rdx, rbx
0x1800991af  call    ??$FormatInteger@V?$AutoOperatorAmpersandHelper@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Windows@@_K@Rtl@StringUtil@Windows@@YAJK_KV?$AutoOperatorAmpersandHelper@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::FormatInteger<Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>,unsigned __int64>(ulong,unsigned __int64,Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>)
0x1800991b4  mov     rcx, [rsp+1B8h]; this
0x1800991bc  test    eax, eax
0x1800991be  js      loc_180099DFD
0x1800991c4  mov     rax, [rdi]
0x1800991c7  lea     r9, [rsp+1B8h+nNumberOfBytesToWrite]
0x1800991cf  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0P@U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EP@@0FD@@0EE@@0GP@@0HH@@0GO@@0GM@@0GP@@0GB@@0GE@@0FD@@0GJ@@0HK@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800991d6  xor     edx, edx
0x1800991d8  mov     rcx, rdi
0x1800991db  mov     rax, [rax+60h]
0x1800991df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800991e4  mov     rcx, [rsp+1B8h]; this
0x1800991ec  test    eax, eax
0x1800991ee  js      loc_180099E11
0x1800991f4  mov     rax, [rdi]
0x1800991f7  mov     edx, r13d
0x1800991fa  mov     rcx, rdi
0x1800991fd  mov     rax, [rax+30h]
0x180099201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099206  mov     rcx, [rsp+1B8h]; this
0x18009920e  test    eax, eax
0x180099210  js      loc_180099E25
0x180099216  mov     rax, [rdi]
0x180099219  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$05U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EN@@0GF@@0GE@@0GJ@@0GB@@0A@@@@$0A@$00$01$02$03$04@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180099220  xor     edx, edx
0x180099222  mov     rcx, rdi
0x180099225  mov     rax, [rax+18h]
0x180099229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009922e  mov     rcx, [rsp+1B8h]; this
0x180099236  test    eax, eax
0x180099238  js      loc_180099E39
0x18009923e  mov     rcx, [r14+50h]
0x180099242  or      r12, 0FFFFFFFFFFFFFFFFh
0x180099246  test    rcx, rcx
0x180099249  jz      loc_180099302
0x18009924f  mov     rax, [rdi]
0x180099252  mov     rdx, [rcx+18h]
0x180099256  mov     rcx, r12
0x180099259  inc     rcx
0x18009925c  cmp     [rdx+rcx*2], r15w
0x180099261  jnz     short loc_180099259
0x180099263  add     rcx, rcx
0x180099266  mov     [rsp+1B8h+var_170], rcx
0x18009926b  add     rcx, 2
0x18009926f  mov     [rsp+1B8h+var_168], rcx
0x180099274  mov     [rsp+1B8h+var_160], rdx
0x180099279  lea     r9, [rsp+1B8h+var_170]
0x18009927e  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0EO@@0GB@@0GN@@0GF@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x180099285  xor     edx, edx
0x180099287  mov     rcx, rdi
0x18009928a  mov     rax, [rax+58h]
0x18009928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099293  mov     rcx, [rsp+1B8h]; this
0x18009929b  test    eax, eax
0x18009929d  js      loc_180099E4D
0x1800992a3  lea     rax, [rsp+1B8h+nNumberOfBytesToWrite]
0x1800992ab  mov     [rsp+1B8h+var_178], rax
0x1800992b0  mov     rdx, [r14+50h]
0x1800992b4  lea     r8, [rsp+1B8h+var_178]
0x1800992b9  mov     rdx, [rdx+30h]
0x1800992bd  call    ??$FormatInteger@V?$AutoOperatorAmpersandHelper@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Windows@@_K@Rtl@StringUtil@Windows@@YAJK_KV?$AutoOperatorAmpersandHelper@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::FormatInteger<Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>,unsigned __int64>(ulong,unsigned __int64,Windows::AutoOperatorAmpersandHelper<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>)
0x1800992c2  mov     rcx, [rsp+1B8h]; this
0x1800992ca  test    eax, eax
0x1800992cc  js      loc_180099E61
0x1800992d2  mov     rax, [rdi]
0x1800992d5  lea     r9, [rsp+1B8h+nNumberOfBytesToWrite]
0x1800992dd  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0O@U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EJ@@0GO@@0HD@@0HE@@0GB@@0GM@@0GM@@0GF@@0GE@@0FD@@0GJ@@0HK@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800992e4  xor     edx, edx
0x1800992e6  mov     rcx, rdi
0x1800992e9  mov     rax, [rax+60h]
0x1800992ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800992f2  mov     rcx, [rsp+1B8h]; this
0x1800992fa  test    eax, eax
0x1800992fc  js      loc_180099E75
0x180099302  mov     rax, [rdi]
0x180099305  xor     edx, edx
0x180099307  mov     rcx, rdi
0x18009930a  mov     rax, [rax+30h]
0x18009930e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099313  mov     rcx, [rsp+1B8h]; this
0x18009931b  test    eax, eax
0x18009931d  js      loc_180099E89
0x180099323  cmp     [r14+50h], r15
0x180099327  jz      loc_1800993F4
0x18009932d  mov     ebx, r15d
0x180099330  mov     rax, [r14+50h]
0x180099334  cmp     ebx, [rax+8]
0x180099337  jnb     loc_1800993F4
0x18009933d  mov     rax, [rdi]
0x180099340  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$07U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FA@@0GB@@0GD@@0GL@@0GB@@0GH@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x180099347  xor     edx, edx
0x180099349  mov     rcx, rdi
0x18009934c  mov     rax, [rax+18h]
0x180099350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099355  mov     rcx, [rsp+1B8h]; this
0x18009935d  test    eax, eax
0x18009935f  js      loc_180099E9D
0x180099365  mov     rax, [rdi]
0x180099368  mov     r10, [rax+58h]
0x18009936c  mov     eax, ebx
0x18009936e  lea     rdx, [rax+rax*2]
0x180099372  mov     rax, [r14+50h]
0x180099376  mov     rcx, [rax]
0x180099379  mov     r8, [rcx+rdx*8+8]
0x18009937e  mov     rcx, r12
0x180099381  inc     rcx
0x180099384  cmp     [r8+rcx*2], r15w
0x180099389  jnz     short loc_180099381
0x18009938b  add     rcx, rcx
0x18009938e  mov     [rsp+1B8h+var_170], rcx
0x180099393  add     rcx, 2
0x180099397  mov     [rsp+1B8h+var_168], rcx
0x18009939c  mov     [rsp+1B8h+var_160], r8
0x1800993a1  lea     r9, [rsp+1B8h+var_170]
0x1800993a6  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FA@@0GB@@0GD@@0GL@@0GB@@0GH@@0GF@@0FA@@0GB@@0HE@@0GI@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B
0x1800993ad  xor     edx, edx
0x1800993af  mov     rcx, rdi
0x1800993b2  mov     rax, r10
0x1800993b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800993ba  mov     rcx, [rsp+1B8h]; this
0x1800993c2  test    eax, eax
0x1800993c4  js      loc_180099EB1
0x1800993ca  mov     rax, [rdi]
0x1800993cd  mov     edx, r13d
0x1800993d0  mov     rcx, rdi
0x1800993d3  mov     rax, [rax+30h]
0x1800993d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800993dc  mov     rcx, [rsp+1B8h]; this
0x1800993e4  test    eax, eax
0x1800993e6  js      loc_180099EC5
0x1800993ec  add     ebx, r13d
0x1800993ef  jmp     loc_180099330
0x1800993f4  mov     rax, [rdi]
0x1800993f7  lea     r8, ??$LiteralObject@$2U?$BaseLiteralBuffer@$05U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0EN@@0GF@@0GE@@0GJ@@0GB@@0A@@@@$0A@$00$01$02$03$04@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1800993fe  xor     edx, edx
0x180099400  mov     rcx, rdi
0x180099403  mov     rax, [rax+40h]
0x180099407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009940c  mov     rcx, [rsp+1B8h]; this
0x180099414  test    eax, eax
0x180099416  js      loc_180099ED9
0x18009941c  xorps   xmm0, xmm0
0x18009941f  movdqu  [rsp+1B8h+var_60], xmm0
0x180099428  mov     [rsp+1B8h+var_50], r15
0x180099430  movdqu  [rsp+1B8h+var_78], xmm0
0x180099439  mov     [rsp+1B8h+var_68], r15
0x180099441  movdqu  [rsp+1B8h+var_90], xmm0
0x18009944a  mov     [rsp+1B8h+var_80], r15
0x180099452  movdqu  [rsp+1B8h+var_A8], xmm0
0x18009945b  mov     [rsp+1B8h+var_98], r15
0x180099463  movdqu  [rsp+1B8h+var_C0], xmm0
0x18009946c  mov     [rsp+1B8h+var_B0], r15
0x180099474  movdqu  [rsp+1B8h+var_D8], xmm0
0x18009947d  mov     [rsp+1B8h+var_C8], r15
0x180099485  movdqu  [rsp+1B8h+var_F0], xmm0
0x18009948e  mov     [rsp+1B8h+var_E0], r15
0x180099496  mov     eax, r15d
0x180099499  lea     rcx, aCritdu_1; "CritDU"
0x1800994a0  lea     r9, aSatellite_0; "Satellite"
0x1800994a7  lea     r10, aLangpack_0; "LangPack"
0x1800994ae  lea     r11, aGdr; "GDR"
0x1800994b5  lea     rbx, String1; "LCU"
0x1800994bc  lea     rsi, aCritical; "Critical"
0x1800994c3  mov     dword ptr [rsp+1B8h+var_178], eax
0x1800994c7  cmp     eax, [r14+60h]
0x1800994cb  jnb     loc_180099A50
0x1800994d1  imul    r15, rax, 0A8h
0x1800994d8  mov     r8, [r14+58h]
0x1800994dc  mov     edx, [r15+r8+58h]
0x1800994e1  cmp     edx, 2710h
0x1800994e7  jg      loc_1800995D5
0x1800994ed  jz      loc_1800995CC
0x1800994f3  cmp     edx, 0Dh
0x1800994f6  jg      short loc_18009956C
0x1800994f8  jz      short loc_180099567
0x1800994fa  mov     ecx, edx
0x1800994fc  sub     ecx, 2
0x1800994ff  jz      short loc_18009955E
0x180099501  sub     ecx, 1
0x180099504  jz      short loc_180099559
0x180099506  sub     ecx, 1
0x180099509  jz      short loc_180099551
0x18009950b  sub     ecx, 1
  ... truncated ...
```
