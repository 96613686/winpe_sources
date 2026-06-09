# OSIntegration::DEH::RuntimeExtensionHandler::LogDestroyDMRFileErrorDueToSharingViolation(long,ARI::Package const &,ushort const *)

- ea: `0x1800a3a28`
- end: `0x1800a4223`
- name: `?LogDestroyDMRFileErrorDueToSharingViolation@RuntimeExtensionHandler@DEH@OSIntegration@@IEBAXJAEBVPackage@ARI@@PEBG@Z`
- size: `2043`
- prototype: `void(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, int, const struct ARI::Package *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180082354`

## callees

- `0x18000e6e0`
- `0x180012964`
- `0x18001b84c`
- `0x18001c950`
- `0x180021224`
- `0x180052b20`
- `0x18007efc8`
- `0x1800a219c`
- `0x1800a3a28`
- `0x1800cd2f8`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x180126ca0`
- `0x180128894`
- `0x1801289a8`
- `0x180128ae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3e03`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a3ea8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800a3ea8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a3d0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a3d0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a41e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a40cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a41e7`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a3df5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a3e88`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a3df5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800a3e88`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a3b46`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800a3b46`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a3c3c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a3c91`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a3c3c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800a3c91`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800a3b78`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x1800a3b78`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1800a3bd3`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFullName` at `0x1800a3bd3`

## string_xrefs

- `0x1800a3ab5`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x1800a3ee2`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x1800a410d`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x1800a3d1a`: `<Error 0x%X in OpenProcessToken>`
- `0x1800a3d37`: `<Error 0x%X getting the user's SID from the process' token>`
- `0x1800a3d6d`: `<Error 0x%X converting the user's SID to a string>`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall OSIntegration::DEH::RuntimeExtensionHandler::LogDestroyDMRFileErrorDueToSharingViolation(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        const unsigned __int16 *a2,
        const struct ARI::Package *a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // rsi
  const struct ARI::Package *v5; // r15
  struct Common::StringBuffer *v6; // r8
  int v7; // r12d
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // rbx
  __int64 v11; // r13
  unsigned int v12; // r14d
  char *v13; // rdi
  struct Common::StringBuffer *v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // eax
  WCHAR *v17; // rbx
  DWORD LastError; // esi
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  PSID v21; // rsi
  DWORD v22; // eax
  int UserSidFromToken; // eax
  int v24; // eax
  wchar_t *v25; // rax
  WCHAR *v26; // r14
  WCHAR *v27; // r15
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  struct Common::StringBuffer *v30; // r8
  int v31; // ecx
  DWORD v32; // edx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  int v37; // edx
  int v38; // ecx
  __int64 v39; // rbx
  unsigned int *ReferencedDomainName; // [rsp+20h] [rbp-F0h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-F0h]
  LPDWORD cchReferencedDomainName; // [rsp+28h] [rbp-E8h]
  DWORD v43; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v44; // [rsp+98h] [rbp-78h] BYREF
  DWORD dwSize; // [rsp+9Ch] [rbp-74h] BYREF
  DWORD pSessionId; // [rsp+A0h] [rbp-70h] BYREF
  DWORD dwMessageId; // [rsp+A4h] [rbp-6Ch]
  UINT32 applicationUserModelIdLength; // [rsp+A8h] [rbp-68h] BYREF
  DWORD v49; // [rsp+ACh] [rbp-64h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp-60h] BYREF
  DWORD v51; // [rsp+B8h] [rbp-58h] BYREF
  unsigned int v52; // [rsp+C0h] [rbp-50h] BYREF
  const wchar_t *v53; // [rsp+C8h] [rbp-48h] BYREF
  PSID Sid; // [rsp+D0h] [rbp-40h] BYREF
  __int128 v55; // [rsp+D8h] [rbp-38h] BYREF
  int v56; // [rsp+E8h] [rbp-28h]
  enum _SID_NAME_USE peUse; // [rsp+F0h] [rbp-20h] BYREF
  WCHAR *v58; // [rsp+F8h] [rbp-18h] BYREF
  const wchar_t *v59; // [rsp+100h] [rbp-10h] BYREF
  wchar_t *v60; // [rsp+108h] [rbp-8h] BYREF
  const unsigned __int16 *v61; // [rsp+110h] [rbp+0h]
  const struct ARI::Package *v62; // [rsp+118h] [rbp+8h]
  PSID v63; // [rsp+120h] [rbp+10h] BYREF
  __int64 v64; // [rsp+128h] [rbp+18h] BYREF
  const unsigned __int16 *v65; // [rsp+130h] [rbp+20h] BYREF
  __int64 v66; // [rsp+138h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+140h] [rbp+30h] BYREF
  WCHAR *v68; // [rsp+148h] [rbp+38h]
  __int128 v69; // [rsp+150h] [rbp+40h] BYREF
  int v70; // [rsp+160h] [rbp+50h]
  WCHAR *v71; // [rsp+168h] [rbp+58h] BYREF
  WCHAR *v72; // [rsp+170h] [rbp+60h] BYREF
  WCHAR *v73; // [rsp+178h] [rbp+68h]
  WCHAR *v74; // [rsp+180h] [rbp+70h]
  _QWORD v75[3]; // [rsp+188h] [rbp+78h] BYREF
  unsigned int dwProcessId[100]; // [rsp+1A0h] [rbp+90h] BYREF
  wchar_t Buffer[104]; // [rsp+330h] [rbp+220h] BYREF
  WCHAR packageFullName[128]; // [rsp+400h] [rbp+2F0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+500h] [rbp+3F0h] BYREF
  WCHAR ExeName[264]; // [rsp+610h] [rbp+500h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+868h] [rbp+758h]

  v4 = a4;
  v61 = a4;
  v5 = a3;
  v62 = a3;
  dwMessageId = (unsigned int)a2;
  v44 = 0;
  v7 = Common::FileInUseByProcesses(a4, a2, (unsigned int)&v44, dwProcessId, ReferencedDomainName);
  if ( !v7 )
  {
    v11 = 0;
    v12 = v44;
    if ( !v44 )
      return;
    while ( 1 )
    {
      v43 = dwProcessId[v11];
      v13 = (char *)OpenProcess(0x1000u, 0, v43);
      v75[1] = v13;
      if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        v55 = 0;
        v56 = 0;
        OSIntegration::Tools::FormatMessageInternal(v7, (Common::StringBuffer *)&v55, v14);
        v38 = (int)retaddr;
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA27,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
            (const char *)(unsigned int)v7,
            ReferencedDomainNamea);
        v39 = *((_QWORD *)&v55 + 1);
        if ( (byte_1802E21C6 & 0x40) != 0 )
          McTemplateU0zzdzqqq_EventWriteTransfer(
            v38,
            v37,
            *((_QWORD *)v5 + 8),
            (_DWORD)v4,
            v7,
            *((__int64 *)&v55 + 1),
            v11,
            v12,
            v43);
        LODWORD(v53) = v12;
        v66 = v39;
        v64 = *((_QWORD *)v5 + 8);
        LODWORD(Sid) = v43;
        v52 = v11;
        v51 = v7;
        v65 = v4;
        SetAppXErrorFromLogMessage(
          v7,
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
          &RuntimeErrorGetProcessInformation,
          7u,
          &v64,
          &v65,
          &v51,
          &v66,
          &v52,
          &v53,
          &Sid);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v55);
        if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v13);
        goto LABEL_53;
      }
      applicationUserModelIdLength = 130;
      v15 = GetApplicationUserModelId(v13, &applicationUserModelIdLength, applicationUserModelId);
      if ( v15 == 15703 )
      {
        StringCchCopyW(applicationUserModelId, 0x82u, L"<None>");
      }
      else if ( v15 )
      {
        StringCchPrintfW(applicationUserModelId, 0x82u, L"<Error 0x%X in GetApplicationUserModelId>", v15);
      }
      applicationUserModelIdLength = 128;
      v16 = GetPackageFullName(v13, &applicationUserModelIdLength, packageFullName);
      v7 = v16;
      if ( v16 == 15700 )
      {
        StringCchCopyW(packageFullName, 0x80u, L"<None>");
      }
      else if ( v16 )
      {
        StringCchPrintfW(packageFullName, 0x80u, L"<Error 0x%X in GetPackageFullName>", v16);
      }
      v17 = 0;
      v68 = 0;
      dwSize = 260;
      if ( QueryFullProcessImageNameW(v13, 0, ExeName, &dwSize) )
      {
LABEL_24:
        v58 = ExeName;
        goto LABEL_25;
      }
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        v17 = (WCHAR *)operator new[](saturated_mul(++dwSize, 2u));
        operator delete(0, v19);
        v68 = v17;
        if ( QueryFullProcessImageNameW(v13, 0, v17, &dwSize) )
          goto LABEL_22;
        LastError = GetLastError();
        operator delete(v17, v20);
        v17 = 0;
        v68 = 0;
      }
      if ( !LastError )
        goto LABEL_24;
LABEL_22:
      StringCchPrintfW(ExeName, 0x104u, L"<Error 0x%X in QueryFullProcessImageNameW>", LastError);
      if ( !v17 )
        goto LABEL_24;
      v58 = v17;
LABEL_25:
      Sid = 0;
      v21 = 0;
      v63 = 0;
      v55 = 0;
      v56 = 0;
      TokenHandle = 0;
      if ( OpenProcessToken(v13, 8u, &TokenHandle) )
      {
        UserSidFromToken = Common::SidHelper::GetUserSidFromToken(TokenHandle, &v63);
        if ( UserSidFromToken >= 0 )
        {
          v21 = v63;
          Sid = v63;
          v24 = Common::SidHelper::ConvertSidToString(v63, (struct Common::StringBuffer *)&v55);
          if ( v24 < 0 )
            StringCchPrintfW(Buffer, 0x64u, L"<Error 0x%X converting the user's SID to a string>", (unsigned int)v24);
        }
        else
        {
          StringCchPrintfW(
            Buffer,
            0x64u,
            L"<Error 0x%X getting the user's SID from the process' token>",
            (unsigned int)UserSidFromToken);
          v21 = v63;
        }
      }
      else
      {
        v22 = GetLastError();
        StringCchPrintfW(Buffer, 0x64u, L"<Error 0x%X in OpenProcessToken>", v22);
      }
      v25 = Buffer;
      if ( (_DWORD)v55 )
        v25 = (wchar_t *)*((_QWORD *)&v55 + 1);
      v60 = v25;
      v26 = 0;
      v73 = 0;
      v27 = 0;
      v74 = 0;
      v59 = L"<Unknown>";
      v53 = L"<Unknown>";
      if ( Sid )
      {
        cchName = 0;
        v49 = 0;
        peUse = 0;
        if ( !LookupAccountSidW(0, Sid, 0, &cchName, 0, &v49, &peUse) && GetLastError() == 122 )
        {
          v26 = (WCHAR *)operator new[](saturated_mul(v49, 2u));
          operator delete(0, v28);
          v73 = v26;
          v27 = (WCHAR *)operator new[](saturated_mul(cchName, 2u));
          operator delete(0, v29);
          v74 = v27;
          if ( LookupAccountSidW(0, Sid, v27, &cchName, v26, &v49, &peUse) )
          {
            v59 = v26;
            v53 = v27;
          }
        }
      }
      pSessionId = 0;
      if ( !ProcessIdToSessionId(v43, &pSessionId) )
        pSessionId = -1;
      v69 = 0;
      v70 = 0;
      OSIntegration::Tools::FormatMessageInternal(dwMessageId, (Common::StringBuffer *)&v69, v30);
      v31 = (int)retaddr;
      v32 = dwMessageId;
      if ( (dwMessageId & 0x80000000) != 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xABD,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
          (const char *)dwMessageId,
          ReferencedDomainNamea);
        v32 = dwMessageId;
      }
      if ( (byte_1802E21C6 & 0x40) != 0 )
        McTemplateU0zzdzqqqzzzzzzq_EventWriteTransfer(
          v31,
          v32,
          *((_QWORD *)v62 + 8),
          (_DWORD)v61,
          v32,
          *((__int64 *)&v69 + 1),
          v11,
          v44,
          v43,
          (__int64)applicationUserModelId,
          (__int64)packageFullName,
          (__int64)v58,
          (__int64)v60,
          (__int64)v59,
          (__int64)v53,
          pSessionId);
      v51 = pSessionId;
      v52 = v44;
      v64 = *((_QWORD *)&v69 + 1);
      v66 = *((_QWORD *)v62 + 8);
      v75[0] = v53;
      v71 = packageFullName;
      v72 = applicationUserModelId;
      LODWORD(v53) = v11;
      LODWORD(Sid) = dwMessageId;
      v65 = v61;
      SetAppXErrorFromLogMessage(
        dwMessageId,
        &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
        &RuntimeErrorFileInUse,
        0xEu,
        &v66,
        &v65,
        &Sid,
        &v64,
        &v53,
        &v52,
        &v43,
        &v72,
        &v71,
        &v58,
        &v60,
        &v59,
        v75,
        &v51);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v69);
      operator delete(v27, v33);
      operator delete(v26, v34);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v55);
      operator delete(v21, v35);
      operator delete(v17, v36);
      CloseHandle(v13);
      v4 = v61;
      v12 = v44;
      v5 = v62;
LABEL_53:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= v12 )
        return;
    }
  }
  v55 = 0;
  v56 = 0;
  OSIntegration::Tools::FormatMessageInternal(v7, (Common::StringBuffer *)&v55, v6);
  v9 = (int)retaddr;
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
      (const char *)(unsigned int)v7,
      ReferencedDomainNamea);
  v10 = *((_QWORD *)&v55 + 1);
  if ( (byte_1802E21C6 & 0x40) != 0 )
    McTemplateU0zzdz_EventWriteTransfer(
      v9,
      (unsigned int)RuntimeErrorIdentifyFileInUse,
      *((_QWORD *)v5 + 8),
      (_DWORD)v4,
      v7,
      *((__int64 *)&v55 + 1));
  LODWORD(cchReferencedDomainName) = v7;
  details::appxLog<_SID const *,unsigned short const *,unsigned short const *,long>(
    v7,
    v8,
    (const struct _EVENT_DESCRIPTOR *)RuntimeErrorIdentifyFileInUse,
    *((_QWORD *)v5 + 8),
    v4,
    cchReferencedDomainName,
    v10);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v55);
}

```

## disassembly

```asm
0x1800a3a28  mov     [rsp-8+arg_0], rbx
0x1800a3a2d  push    rbp
0x1800a3a2e  push    rsi
0x1800a3a2f  push    rdi
0x1800a3a30  push    r12
0x1800a3a32  push    r13
0x1800a3a34  push    r14
0x1800a3a36  push    r15
0x1800a3a38  lea     rbp, [rsp-720h]
0x1800a3a40  sub     rsp, 830h
0x1800a3a47  mov     rax, cs:__security_cookie
0x1800a3a4e  xor     rax, rsp
0x1800a3a51  mov     [rbp+750h+var_40], rax
0x1800a3a58  mov     rsi, r9
0x1800a3a5b  mov     [rbp+750h+var_750], r9
0x1800a3a5f  mov     r15, r8
0x1800a3a62  mov     [rbp+750h+var_748], r8
0x1800a3a66  mov     [rbp+750h+dwMessageId], edx
0x1800a3a69  mov     [rbp+750h+var_7C8], 0
0x1800a3a70  lea     r9, [rbp+750h+dwProcessId]; unsigned int *
0x1800a3a77  lea     r8, [rbp+750h+var_7C8]; unsigned int
0x1800a3a7b  mov     rcx, rsi; lpFileName
0x1800a3a7e  call    ?FileInUseByProcesses@Common@@YAJPEBGIPEAIPEAK@Z; Common::FileInUseByProcesses(ushort const *,uint,uint *,ulong *)
0x1800a3a83  mov     r12d, eax
0x1800a3a86  test    eax, eax
0x1800a3a88  jz      loc_1800A3B21
0x1800a3a8e  xor     eax, eax
0x1800a3a90  xorps   xmm0, xmm0
0x1800a3a93  movups  [rbp+750h+var_788], xmm0
0x1800a3a97  mov     [rbp+750h+var_778], eax
0x1800a3a9a  lea     rdx, [rbp+750h+var_788]; this
0x1800a3a9e  mov     ecx, r12d; dwMessageId
0x1800a3aa1  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800a3aa6  mov     rcx, [rbp+758h]; this
0x1800a3aad  test    r12d, r12d
0x1800a3ab0  jns     short loc_1800A3AC6
0x1800a3ab2  mov     r9d, r12d; char *
0x1800a3ab5  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800a3abc  mov     edx, 0A17h; void *
0x1800a3ac1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3ac6  mov     rbx, qword ptr [rbp+750h+var_788+8]
0x1800a3aca  test    cs:byte_1802E21C6, 40h
0x1800a3ad1  jz      short loc_1800A3AF0
0x1800a3ad3  mov     [rsp+860h+cchReferencedDomainName], rbx
0x1800a3ad8  mov     dword ptr [rsp+860h+ReferencedDomainName], r12d
0x1800a3add  mov     r9, rsi
0x1800a3ae0  mov     r8, [r15+40h]
0x1800a3ae4  lea     rdx, RuntimeErrorIdentifyFileInUse
0x1800a3aeb  call    McTemplateU0zzdz_EventWriteTransfer
0x1800a3af0  mov     [rsp+860h+peUse], rbx
0x1800a3af5  mov     dword ptr [rsp+860h+cchReferencedDomainName], r12d
0x1800a3afa  mov     [rsp+860h+ReferencedDomainName], rsi
0x1800a3aff  mov     r9, [r15+40h]
0x1800a3b03  lea     r8, RuntimeErrorIdentifyFileInUse
0x1800a3b0a  mov     ecx, r12d
0x1800a3b0d  call    ??$appxLog@PEBU_SID@@PEBGPEBGJ@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBU_SID@@PEBG3J@Z; details::appxLog<_SID const *,ushort const *,ushort const *,long>(long,_GUID const &,_EVENT_DESCRIPTOR const &,_SID const *,ushort const *,ushort const *,long)
0x1800a3b12  nop
0x1800a3b13  lea     rcx, [rbp+750h+var_788]; this
0x1800a3b17  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800a3b1c  jmp     loc_1800A41F9
0x1800a3b21  xor     r13d, r13d
0x1800a3b24  mov     r14d, [rbp+750h+var_7C8]
0x1800a3b28  test    r14d, r14d
0x1800a3b2b  jz      loc_1800A41F9
0x1800a3b31  mov     eax, [rbp+r13*4+750h+dwProcessId]
0x1800a3b39  mov     [rbp+750h+var_7D0], eax
0x1800a3b3c  mov     r8d, eax; dwProcessId
0x1800a3b3f  xor     edx, edx; bInheritHandle
0x1800a3b41  mov     ecx, 1000h; dwDesiredAccess
0x1800a3b46  call    cs:__imp_OpenProcess
0x1800a3b4c  mov     rdi, rax
0x1800a3b4f  mov     [rbp+750h+var_6D0], rax
0x1800a3b56  dec     rax
0x1800a3b59  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a3b5d  ja      loc_1800A40E6
0x1800a3b63  mov     [rbp+750h+applicationUserModelIdLength], 82h
0x1800a3b6a  lea     r8, [rbp+750h+applicationUserModelId]; applicationUserModelId
0x1800a3b71  lea     rdx, [rbp+750h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800a3b75  mov     rcx, rdi; hProcess
0x1800a3b78  call    cs:__imp_GetApplicationUserModelId
0x1800a3b7e  cmp     eax, 3D57h
0x1800a3b83  jnz     short loc_1800A3B9F
0x1800a3b85  lea     r8, aNone_1; "<None>"
0x1800a3b8c  mov     edx, 82h; unsigned __int64
0x1800a3b91  lea     rcx, [rbp+750h+applicationUserModelId]; unsigned __int16 *
0x1800a3b98  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3b9d  jmp     short loc_1800A3BBE
0x1800a3b9f  test    eax, eax
0x1800a3ba1  jz      short loc_1800A3BBE
0x1800a3ba3  mov     r9d, eax
0x1800a3ba6  lea     r8, aError0xXInGeta_0; "<Error 0x%X in GetApplicationUserModelI"...
0x1800a3bad  mov     edx, 82h; unsigned __int64
0x1800a3bb2  lea     rcx, [rbp+750h+applicationUserModelId]; Buffer
0x1800a3bb9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3bbe  mov     [rbp+750h+applicationUserModelIdLength], 80h
0x1800a3bc5  lea     r8, [rbp+750h+packageFullName]; packageFullName
0x1800a3bcc  lea     rdx, [rbp+750h+applicationUserModelIdLength]; packageFullNameLength
0x1800a3bd0  mov     rcx, rdi; hProcess
0x1800a3bd3  call    cs:__imp_GetPackageFullName
0x1800a3bd9  mov     r12d, eax
0x1800a3bdc  cmp     eax, 3D54h
0x1800a3be1  jnz     short loc_1800A3BFD
0x1800a3be3  lea     r8, aNone_1; "<None>"
0x1800a3bea  mov     edx, 80h; unsigned __int64
0x1800a3bef  lea     rcx, [rbp+750h+packageFullName]; unsigned __int16 *
0x1800a3bf6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3bfb  jmp     short loc_1800A3C1C
0x1800a3bfd  test    eax, eax
0x1800a3bff  jz      short loc_1800A3C1C
0x1800a3c01  mov     r9d, eax
0x1800a3c04  lea     r8, aError0xXInGetp; "<Error 0x%X in GetPackageFullName>"
0x1800a3c0b  mov     edx, 80h; unsigned __int64
0x1800a3c10  lea     rcx, [rbp+750h+packageFullName]; Buffer
0x1800a3c17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3c1c  xor     ebx, ebx
0x1800a3c1e  mov     [rbp+750h+var_718], rbx
0x1800a3c22  mov     r14d, 104h
0x1800a3c28  mov     [rbp+750h+dwSize], r14d
0x1800a3c2c  lea     r9, [rbp+750h+dwSize]; lpdwSize
0x1800a3c30  lea     r8, [rbp+750h+ExeName]; lpExeName
0x1800a3c37  xor     edx, edx; dwFlags
0x1800a3c39  mov     rcx, rdi; hProcess
0x1800a3c3c  call    cs:__imp_QueryFullProcessImageNameW
0x1800a3c42  test    eax, eax
0x1800a3c44  jnz     loc_1800A3CD9
0x1800a3c4a  call    cs:__imp_GetLastError
0x1800a3c50  mov     esi, eax
0x1800a3c52  cmp     eax, 7Ah ; 'z'
0x1800a3c55  jnz     short loc_1800A3CB1
0x1800a3c57  mov     ecx, [rbp+750h+dwSize]
0x1800a3c5a  inc     ecx
0x1800a3c5c  mov     [rbp+750h+dwSize], ecx
0x1800a3c5f  mov     edx, ecx
0x1800a3c61  lea     eax, [rbx+2]
0x1800a3c64  mul     rdx
0x1800a3c67  lea     rcx, [rbx-1]
0x1800a3c6b  cmovb   rax, rcx
0x1800a3c6f  mov     rcx, rax; unsigned __int64
0x1800a3c72  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a3c77  mov     rbx, rax
0x1800a3c7a  xor     ecx, ecx; void *
0x1800a3c7c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a3c81  mov     [rbp+750h+var_718], rbx
0x1800a3c85  lea     r9, [rbp+750h+dwSize]; lpdwSize
0x1800a3c89  mov     r8, rbx; lpExeName
0x1800a3c8c  xor     edx, edx; dwFlags
0x1800a3c8e  mov     rcx, rdi; hProcess
0x1800a3c91  call    cs:__imp_QueryFullProcessImageNameW
0x1800a3c97  test    eax, eax
0x1800a3c99  jnz     short loc_1800A3CB5
0x1800a3c9b  call    cs:__imp_GetLastError
0x1800a3ca1  mov     esi, eax
0x1800a3ca3  mov     rcx, rbx; void *
0x1800a3ca6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a3cab  xor     ebx, ebx
0x1800a3cad  mov     [rbp+750h+var_718], rbx
0x1800a3cb1  test    esi, esi
0x1800a3cb3  jz      short loc_1800A3CD9
0x1800a3cb5  mov     r9d, esi
0x1800a3cb8  lea     r8, aError0xXInQuer; "<Error 0x%X in QueryFullProcessImageNam"...
0x1800a3cbf  mov     rdx, r14; unsigned __int64
0x1800a3cc2  lea     rcx, [rbp+750h+ExeName]; Buffer
0x1800a3cc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3cce  test    rbx, rbx
0x1800a3cd1  jz      short loc_1800A3CD9
0x1800a3cd3  mov     [rbp+750h+var_768], rbx
0x1800a3cd7  jmp     short loc_1800A3CE4
0x1800a3cd9  lea     rax, [rbp+750h+ExeName]
0x1800a3ce0  mov     [rbp+750h+var_768], rax
0x1800a3ce4  xor     edx, edx
0x1800a3ce6  mov     [rbp+750h+Sid], rdx
0x1800a3cea  xor     esi, esi
0x1800a3cec  mov     [rbp+750h+var_740], rsi
0x1800a3cf0  xor     eax, eax
0x1800a3cf2  xorps   xmm0, xmm0
0x1800a3cf5  movups  [rbp+750h+var_788], xmm0
0x1800a3cf9  mov     [rbp+750h+var_778], eax
0x1800a3cfc  mov     [rbp+750h+TokenHandle], rax
0x1800a3d00  lea     r8, [rbp+750h+TokenHandle]; TokenHandle
0x1800a3d04  lea     edx, [rsi+8]; DesiredAccess
0x1800a3d07  mov     rcx, rdi; ProcessHandle
0x1800a3d0a  call    cs:__imp_OpenProcessToken
0x1800a3d10  test    eax, eax
0x1800a3d12  jnz     short loc_1800A3D23
0x1800a3d14  call    cs:__imp_GetLastError
0x1800a3d1a  lea     r8, aError0xXInOpen; "<Error 0x%X in OpenProcessToken>"
0x1800a3d21  jmp     short loc_1800A3D74
0x1800a3d23  lea     rdx, [rbp+750h+var_740]; void **
0x1800a3d27  mov     rcx, [rbp+750h+TokenHandle]; TokenHandle
0x1800a3d2b  call    ?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z; Common::SidHelper::GetUserSidFromToken(void *,void * *)
0x1800a3d30  test    eax, eax
0x1800a3d32  jns     short loc_1800A3D55
0x1800a3d34  mov     r9d, eax
0x1800a3d37  lea     r8, aError0xXGettin; "<Error 0x%X getting the user's SID from"...
0x1800a3d3e  mov     edx, 64h ; 'd'; unsigned __int64
0x1800a3d43  lea     rcx, [rbp+750h+Buffer]; Buffer
0x1800a3d4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3d4f  mov     rsi, [rbp+750h+var_740]
0x1800a3d53  jmp     short loc_1800A3D88
0x1800a3d55  mov     rsi, [rbp+750h+var_740]
0x1800a3d59  mov     [rbp+750h+Sid], rsi
0x1800a3d5d  lea     rdx, [rbp+750h+var_788]; this
0x1800a3d61  mov     rcx, rsi; Sid
0x1800a3d64  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x1800a3d69  test    eax, eax
0x1800a3d6b  jns     short loc_1800A3D88
0x1800a3d6d  lea     r8, aError0xXConver; "<Error 0x%X converting the user's SID t"...
0x1800a3d74  mov     r9d, eax
0x1800a3d77  mov     edx, 64h ; 'd'; unsigned __int64
0x1800a3d7c  lea     rcx, [rbp+750h+Buffer]; Buffer
0x1800a3d83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a3d88  lea     rax, [rbp+750h+Buffer]
0x1800a3d8f  cmp     dword ptr [rbp+750h+var_788], 0
0x1800a3d93  cmova   rax, qword ptr [rbp+750h+var_788+8]
0x1800a3d98  mov     [rbp+750h+var_758], rax
0x1800a3d9c  xor     r14d, r14d
0x1800a3d9f  mov     [rbp+750h+var_6E8], r14
0x1800a3da3  xor     r15d, r15d
0x1800a3da6  mov     [rbp+750h+var_6E0], r15
0x1800a3daa  lea     rax, aUnknown_0; "<Unknown>"
0x1800a3db1  mov     [rbp+750h+var_760], rax
0x1800a3db5  mov     [rbp+750h+var_798], rax
0x1800a3db9  mov     rax, [rbp+750h+Sid]
0x1800a3dbd  test    rax, rax
0x1800a3dc0  jz      loc_1800A3E9A
0x1800a3dc6  mov     [rbp+750h+cchName], r15d
0x1800a3dca  mov     [rbp+750h+var_7B4], r15d
0x1800a3dce  mov     [rbp+750h+var_770], r15d
0x1800a3dd2  lea     rcx, [rbp+750h+var_770]
0x1800a3dd6  mov     [rsp+860h+peUse], rcx; peUse
0x1800a3ddb  lea     rcx, [rbp+750h+var_7B4]
0x1800a3ddf  mov     [rsp+860h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800a3de4  mov     [rsp+860h+ReferencedDomainName], r15; ReferencedDomainName
0x1800a3de9  lea     r9, [rbp+750h+cchName]; cchName
0x1800a3ded  xor     r8d, r8d; Name
0x1800a3df0  mov     rdx, rax; Sid
0x1800a3df3  xor     ecx, ecx; lpSystemName
0x1800a3df5  call    cs:__imp_LookupAccountSidW
0x1800a3dfb  test    eax, eax
0x1800a3dfd  jnz     loc_1800A3E9A
0x1800a3e03  call    cs:__imp_GetLastError
0x1800a3e09  cmp     eax, 7Ah ; 'z'
0x1800a3e0c  jnz     loc_1800A3E9A
0x1800a3e12  mov     ecx, [rbp+750h+var_7B4]
0x1800a3e15  lea     r15d, [r14+2]
0x1800a3e19  mov     eax, r15d
0x1800a3e1c  mul     rcx
0x1800a3e1f  lea     rcx, [r14-1]
0x1800a3e23  cmovb   rax, rcx
0x1800a3e27  mov     rcx, rax; unsigned __int64
0x1800a3e2a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a3e2f  mov     r14, rax
0x1800a3e32  xor     ecx, ecx; void *
0x1800a3e34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a3e39  mov     [rbp+750h+var_6E8], r14
0x1800a3e3d  mov     ecx, [rbp+750h+cchName]
0x1800a3e40  mov     eax, r15d
0x1800a3e43  mul     rcx
0x1800a3e46  lea     rcx, [r15-3]
0x1800a3e4a  cmovb   rax, rcx
0x1800a3e4e  mov     rcx, rax; unsigned __int64
0x1800a3e51  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800a3e56  mov     r15, rax
0x1800a3e59  xor     ecx, ecx; void *
0x1800a3e5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a3e60  mov     [rbp+750h+var_6E0], r15
0x1800a3e64  lea     rax, [rbp+750h+var_770]
0x1800a3e68  mov     [rsp+860h+peUse], rax; peUse
0x1800a3e6d  lea     rax, [rbp+750h+var_7B4]
0x1800a3e71  mov     [rsp+860h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a3e76  mov     [rsp+860h+ReferencedDomainName], r14; int
0x1800a3e7b  lea     r9, [rbp+750h+cchName]; cchName
0x1800a3e7f  mov     r8, r15; Name
0x1800a3e82  mov     rdx, [rbp+750h+Sid]; Sid
0x1800a3e86  xor     ecx, ecx; lpSystemName
0x1800a3e88  call    cs:__imp_LookupAccountSidW
0x1800a3e8e  test    eax, eax
0x1800a3e90  jz      short loc_1800A3E9A
0x1800a3e92  mov     [rbp+750h+var_760], r14
0x1800a3e96  mov     [rbp+750h+var_798], r15
0x1800a3e9a  mov     [rbp+750h+pSessionId], 0
0x1800a3ea1  lea     rdx, [rbp+750h+pSessionId]; pSessionId
0x1800a3ea5  mov     ecx, [rbp+750h+var_7D0]; dwProcessId
0x1800a3ea8  call    cs:__imp_ProcessIdToSessionId
0x1800a3eae  test    eax, eax
0x1800a3eb0  jnz     short loc_1800A3EB9
0x1800a3eb2  mov     [rbp+750h+pSessionId], 0FFFFFFFFh
0x1800a3eb9  xor     eax, eax
0x1800a3ebb  xorps   xmm0, xmm0
0x1800a3ebe  movups  [rbp+750h+var_710], xmm0
0x1800a3ec2  mov     [rbp+750h+var_700], eax
0x1800a3ec5  lea     rdx, [rbp+750h+var_710]; this
0x1800a3ec9  mov     ecx, [rbp+750h+dwMessageId]; dwMessageId
0x1800a3ecc  call    ?FormatMessageInternal@Tools@OSIntegration@@YAJJPEAVStringBuffer@Common@@@Z; OSIntegration::Tools::FormatMessageInternal(long,Common::StringBuffer *)
0x1800a3ed1  mov     rcx, [rbp+758h]; this
0x1800a3ed8  mov     edx, [rbp+750h+dwMessageId]
0x1800a3edb  test    edx, edx
0x1800a3edd  jns     short loc_1800A3EF6
0x1800a3edf  mov     r9d, edx; char *
0x1800a3ee2  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
  ... truncated ...
```
