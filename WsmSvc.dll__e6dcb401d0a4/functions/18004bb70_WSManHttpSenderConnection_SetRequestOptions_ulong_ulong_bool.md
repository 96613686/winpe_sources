# WSManHttpSenderConnection::SetRequestOptions(ulong,ulong,bool)

- ea: `0x18004bb70`
- end: `0x18004d277`
- name: `?SetRequestOptions@WSManHttpSenderConnection@@AEAAKKK_N@Z`
- size: `5895`
- prototype: `unsigned int __fastcall(WSManHttpSenderConnection *__hidden this, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a9b0`
- `0x1800ad180`

## callees

- `0x180005d10`
- `0x180019950`
- `0x180033c90`
- `0x18004a900`
- `0x18004bb70`
- `0x18004d280`
- `0x18004e0d0`
- `0x18005c09c`
- `0x18005d800`
- `0x180062fc0`
- `0x180067150`
- `0x180071cdc`
- `0x18007e530`
- `0x180080288`
- `0x1800e43f4`
- `0x1800f49ec`
- `0x1800fb998`
- `0x180103b44`
- `0x180112380`
- `0x1801123a8`
- `0x18011349c`
- `0x18011a6d4`
- `0x18013268c`
- `0x180132954`
- `0x180134238`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_scprintf` at `0x18004bf0d`
- `msvcrt!_scprintf` at `0x18004bf0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c8b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ccc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cedd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d21e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c10b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c83d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c8b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ccc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cedd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cf51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d1b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d21e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c1c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c23f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c37e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c1c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c23f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c37e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004c461`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004c4a1`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004c461`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004c4a1`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004c4e7`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004c4e7`
- `SspiCli!QueryContextAttributesW` at `0x18004beec`
- `SspiCli!QueryContextAttributesW` at `0x18004beec`
- `WINHTTP!WinHttpSetOption` at `0x18004bc90`
- `WINHTTP!WinHttpSetOption` at `0x18004c82e`
- `WINHTTP!WinHttpSetOption` at `0x18004c8a3`
- `WINHTTP!WinHttpSetOption` at `0x18004c918`
- `WINHTTP!WinHttpSetOption` at `0x18004c9f0`
- `WINHTTP!WinHttpSetOption` at `0x18004ca6c`
- `WINHTTP!WinHttpSetOption` at `0x18004ccbd`
- `WINHTTP!WinHttpSetOption` at `0x18004bc90`
- `WINHTTP!WinHttpSetOption` at `0x18004c82e`
- `WINHTTP!WinHttpSetOption` at `0x18004c8a3`
- `WINHTTP!WinHttpSetOption` at `0x18004c918`
- `WINHTTP!WinHttpSetOption` at `0x18004c9f0`
- `WINHTTP!WinHttpSetOption` at `0x18004ca6c`
- `WINHTTP!WinHttpSetOption` at `0x18004ccbd`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bdc1`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bf73`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c0fc`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c3fe`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c62c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004ced2`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004d20f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bdc1`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004bf73`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c0fc`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c3fe`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004c62c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004ced2`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18004d20f`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004bd69`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004bd69`

## string_xrefs

- `0x18004d093`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004d0bb`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004d18e`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004bdba`: `Content-Type:application/soap+xml;charset=UTF-8`
- `0x18004c0f5`: `Content-Type:application/soap+xml;charset=UTF-16`
- `0x18004bf03`: `OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\n`

## pseudocode

```c
__int64 __fastcall WSManHttpSenderConnection::SetRequestOptions(
        WSManHttpSenderConnection *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 a4)
{
  WSMan::Client::ProxySelection *v5; // rcx
  unsigned __int8 v6; // r14
  struct IRequestContext **v7; // rdi
  __int64 v8; // rcx
  int v9; // edx
  int v10; // eax
  void *v11; // rcx
  PVOID *v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rcx
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // r13d
  int v18; // r12d
  unsigned int v19; // r8d
  unsigned int v20; // eax
  unsigned int v21; // ecx
  int nReceiveTimeout; // r14d
  void *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  __int64 LastError; // r12
  int v27; // ecx
  unsigned int v28; // r13d
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  bool v30; // zf
  const char *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r15
  unsigned int v34; // r14d
  unsigned int v35; // edi
  unsigned int v36; // eax
  int v37; // ecx
  int v38; // eax
  unsigned int v39; // ecx
  unsigned int v40; // edx
  int TotalEncryptedSizeInternalSsl; // eax
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  int v44; // r14d
  CHeap *v46; // rcx
  void *v47; // rax
  struct _SLIST_ENTRY *v48; // rax
  PSLIST_ENTRY v49; // rdi
  volatile signed __int32 *v50; // rax
  struct _SLIST_ENTRY *Next; // rcx
  CHeap *v52; // rcx
  void *Handle; // rax
  struct _SLIST_ENTRY *v54; // rax
  struct _SLIST_ENTRY *v55; // rcx
  _BYTE *v56; // r11
  unsigned __int8 *v57; // r8
  unsigned int v58; // r10d
  __int64 v59; // rax
  const CHAR *v60; // rdi
  unsigned int v61; // edx
  unsigned int v62; // eax
  char v63; // r14
  unsigned int v64; // r14d
  __int64 v65; // rdi
  SIZE_T v66; // rax
  const void *v67; // r15
  CHeap *v68; // rcx
  CHeap *v69; // rcx
  void *v70; // rax
  void *v71; // rax
  __int64 *v72; // rdx
  DWORD v73; // r8d
  __int64 *v74; // rdx
  void *v75; // rax
  __int64 v76; // rax
  void *Heap; // rax
  SIZE_T v78; // rax
  PSLIST_ENTRY v79; // rax
  CHeap *v80; // rcx
  int v81; // eax
  PVOID v82; // rcx
  __int64 v83; // r9
  unsigned int v84; // ecx
  char v85; // al
  wchar_t *v86; // rdx
  unsigned int v87; // eax
  void *v88; // rcx
  void *v89; // rcx
  void *v90; // rcx
  DWORD v91; // eax
  struct IRequestContext *v92; // rcx
  __int64 v93; // rax
  void *v94; // rcx
  int v95; // eax
  void *v96; // rcx
  DWORD v97; // eax
  unsigned int v98; // eax
  __int64 v99; // r8
  char v101; // [rsp+60h] [rbp-29h]
  SECURITY_STATUS Buffer; // [rsp+64h] [rbp-25h] BYREF
  char v103; // [rsp+68h] [rbp-21h]
  unsigned int v104; // [rsp+6Ch] [rbp-1Dh] BYREF
  int dwBytes; // [rsp+70h] [rbp-19h] BYREF
  unsigned int dwBytes_4; // [rsp+74h] [rbp-15h]
  unsigned int i; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v108; // [rsp+7Ch] [rbp-Dh]
  LPCVOID lpMem; // [rsp+80h] [rbp-9h]
  char *v110; // [rsp+88h] [rbp-1h]
  _BYTE *v111; // [rsp+90h] [rbp+7h]
  __int128 pBuffer; // [rsp+98h] [rbp+Fh] BYREF

  v5 = (WSMan::Client::ProxySelection *)*((_QWORD *)this + 1033);
  v6 = a4;
  v104 = a3;
  i = a2;
  v7 = (struct IRequestContext **)((char *)this + 9024);
  if ( v5 && !WSMan::Client::ProxySelection::SetProxyOption(v5, *v7, *((HINTERNET *)this + 1134)) )
  {
    LODWORD(LastError) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v87 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)*v7 + 152LL))(*v7);
    v42 = WPP_GLOBAL_Control;
    v43 = 368;
    v83 = v87;
    goto LABEL_295;
  }
  if ( *((_BYTE *)this + 50) )
  {
    v88 = (void *)*((_QWORD *)this + 1134);
    Buffer = 256;
    if ( !WinHttpSetOption(v88, 0x1Fu, &Buffer, 4u) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)*v7 + 72LL))(*v7, LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 369;
      goto LABEL_294;
    }
  }
  if ( *((_BYTE *)this + 51) )
  {
    v89 = (void *)*((_QWORD *)this + 1134);
    Buffer = 4096;
    if ( !WinHttpSetOption(v89, 0x1Fu, &Buffer, 4u) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)*v7 + 72LL))(*v7, LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 370;
      goto LABEL_294;
    }
  }
  if ( *((_BYTE *)this + 49) )
  {
    v90 = (void *)*((_QWORD *)this + 1134);
    Buffer = 1;
    if ( !WinHttpSetOption(v90, 0x60u, &Buffer, 4u) )
    {
      v91 = GetLastError();
      v92 = *v7;
      LODWORD(LastError) = v91;
      v93 = *(_QWORD *)*v7;
      if ( (_DWORD)LastError == 12009 )
      {
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64))(v93 + 64))(v92, 12009, 1077134357);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 371, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
        return (unsigned int)LastError;
      }
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(v93 + 72))(v92, (unsigned int)LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v43 = 372;
LABEL_294:
        v83 = (unsigned int)LastError;
LABEL_295:
        v82 = (PVOID)v42[2];
LABEL_296:
        WPP_SF_d(v82, v43, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v83);
      }
      return (unsigned int)LastError;
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) == 2 && !*((_BYTE *)this + 52) )
  {
    v94 = (void *)*((_QWORD *)this + 1134);
    Buffer = 1;
    if ( !WinHttpSetOption(v94, 0x4Fu, &Buffer, 4u) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 373;
      goto LABEL_294;
    }
  }
  v8 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
  if ( *(_DWORD *)(v8 + 528) == 2
    && !*(_QWORD *)(v8 + 928)
    && !WinHttpSetOption(*((HINTERNET *)this + 1134), 0x2Fu, 0, 0) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v43 = 374;
    goto LABEL_294;
  }
  v9 = *((_DWORD *)this + 2848);
  if ( v9 != 5 )
  {
    v10 = *((_DWORD *)this + 2849);
    if ( v10 == 4 )
      goto LABEL_9;
    if ( v10 == 5 )
      goto LABEL_10;
    if ( v9 == 4 )
    {
LABEL_9:
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) != 2 )
        goto LABEL_10;
    }
    else if ( v9 == 7 )
    {
      goto LABEL_10;
    }
    if ( v9 != 6 )
    {
LABEL_15:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_16;
    }
  }
LABEL_10:
  if ( !*((_QWORD *)this + 1134) )
  {
    LODWORD(LastError) = 1359;
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
      7543,
      L"7543",
      0x54Fu,
      *((struct IRequestContext **)this + 1128));
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_154;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      410,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      this,
      *((_QWORD *)this + 1));
  v11 = (void *)*((_QWORD *)this + 1134);
  Buffer = 4;
  if ( WinHttpSetOption(v11, 0x3Fu, &Buffer, 4u) )
    goto LABEL_15;
  LastError = GetLastError();
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      411,
      &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
      (unsigned int)LastError);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (_DWORD)LastError )
  {
LABEL_154:
    if ( v12 == &WPP_GLOBAL_Control || (*((_DWORD *)v12 + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v82 = v12[2];
    v43 = 375;
    v83 = (unsigned int)LastError;
    goto LABEL_296;
  }
LABEL_16:
  v13 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
  if ( (*(_BYTE *)(v13 + 896) & 1) == 0 && *((_DWORD *)this + 2074) )
  {
    v44 = *((_DWORD *)this + 2848);
    if ( v44 == 2 )
    {
      if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
        WSMan::LogEvent<unsigned short *>((__int64)&LOG_WSMAN_AN_AUTH_MECHANISM, L"Basic");
      if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 960LL) )
      {
        LODWORD(LastError) = WSManHttpSenderConnection::SetProxyCredentials(this);
        if ( (_DWORD)LastError )
          return (unsigned int)LastError;
      }
      LODWORD(LastError) = WSManHttpSenderConnection::SetBasicCredentials(
                             this,
                             0,
                             (const struct WSMan::Client::AuthenticationInfo *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL)
                                                                              + 896LL));
      if ( (_DWORD)LastError )
        return (unsigned int)LastError;
      goto LABEL_250;
    }
    if ( *(_DWORD *)(v13 + 528) == 2 )
    {
      if ( v44 == 4 || (v95 = *((_DWORD *)this + 2849), v95 == 4) )
      {
        if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
          WSMan::LogEvent<unsigned short *>((__int64)&LOG_WSMAN_AN_AUTH_MECHANISM, L"Negotiate");
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 960LL) )
        {
          LODWORD(LastError) = WSManHttpSenderConnection::SetProxyCredentials(this);
          if ( (_DWORD)LastError )
            return (unsigned int)LastError;
        }
        if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 904LL) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              376,
              &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
              this,
              *((_QWORD *)this + 1));
          v96 = (void *)*((_QWORD *)this + 1134);
          Buffer = 1;
          if ( !WinHttpSetOption(v96, 0x4Du, &Buffer, 4u) )
          {
            v97 = GetLastError();
            LODWORD(LastError) = v97;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 377, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v97);
            (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)*v7 + 72LL))(
              *v7,
              (unsigned int)LastError);
            return (unsigned int)LastError;
          }
          *((_DWORD *)this + 2867) = 1;
          if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTOLOGONPOLICY_LOW) )
            WSMan::EventHandler::Write(&LOG_WSMAN_AN_AUTOLOGONPOLICY_LOW, 0, 0);
        }
        v98 = WSManHttpSenderConnection::SetNegotiateCredentials(
                this,
                0,
                (const struct WSMan::Client::AuthenticationInfo *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 896LL));
        LODWORD(LastError) = v98;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 378, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v98);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (_DWORD)LastError )
          return (unsigned int)LastError;
        goto LABEL_251;
      }
      if ( !*((_BYTE *)this + 11444) )
      {
        if ( v44 == 5 || v95 == 5 )
        {
          if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x200) != 0 )
            WPP_SF_(v12[2], 381, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
          if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
            WSMan::LogEvent<unsigned short *>((__int64)&LOG_WSMAN_AN_AUTH_MECHANISM, L"Kerberos");
          *((_BYTE *)this + 8254) = 0;
          goto LABEL_250;
        }
LABEL_235:
        if ( v44 == 7 )
        {
          if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
          {
            v86 = (wchar_t *)L"CredSSP";
            goto LABEL_246;
          }
          goto LABEL_247;
        }
        if ( !v44 )
          goto LABEL_247;
        if ( v44 != 3 )
        {
LABEL_251:
          v6 = a4;
          goto LABEL_17;
        }
        if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
          WSMan::LogEvent<unsigned short *>((__int64)&LOG_WSMAN_AN_AUTH_MECHANISM, L"Digest");
        if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 960LL) )
        {
          LODWORD(LastError) = WSManHttpSenderConnection::SetProxyCredentials(this);
          if ( (_DWORD)LastError )
            return (unsigned int)LastError;
        }
        LODWORD(LastError) = WSManHttpSenderConnection::SetDigestCredentials(
                               this,
                               0,
                               (const struct WSMan::Client::AuthenticationInfo *)(*(_QWORD *)(*((_QWORD *)this + 5)
                                                                                            + 128LL)
                                                                                + 896LL));
        if ( (_DWORD)LastError )
          return (unsigned int)LastError;
LABEL_250:
        v12 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_251;
      }
    }
    else if ( v44 == 4 )
    {
      if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
      {
        v86 = (wchar_t *)L"Negotiate";
LABEL_246:
        WSMan::LogEvent<unsigned short *>((__int64)&LOG_WSMAN_AN_AUTH_MECHANISM, v86);
        goto LABEL_247;
      }
      goto LABEL_247;
    }
    if ( v44 == 5 )
    {
      if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTH_MECHANISM) )
      {
        v86 = (wchar_t *)L"Kerberos";
        goto LABEL_246;
      }
LABEL_247:
      LODWORD(LastError) = WSManHttpSenderConnection::CreateNewNegotiateAuthTokens(this);
      if ( (_DWORD)LastError )
        return (unsigned int)LastError;
      if ( !v44 )
        *((_DWORD *)this + 2848) = 0;
      goto LABEL_250;
    }
    goto LABEL_235;
  }
LABEL_17:
  v14 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
  if ( (*(_BYTE *)(v14 + 896) & 1) == 0 && *(_QWORD *)(v14 + 928) )
  {
    if ( !WinHttpAddRequestHeaders(
            *((HINTERNET *)this + 1134),
            L"Authorization:http://schemas.dmtf.org/wbem/wsman/1/wsman/secprofile/https/mutual",
            0x50u,
            0xA0000000) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)*v7 + 72LL))(*v7, LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 382;
      goto LABEL_294;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v15 = (const WCHAR *)*((_QWORD *)this + 1038);
  if ( v15 )
  {
    v99 = -1;
    do
      ++v99;
    while ( v15[v99] );
    if ( !WinHttpAddRequestHeaders(*((HINTERNET *)this + 1134), v15, v99, 0xA0000000) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)*v7 + 72LL))(*v7, LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 383;
      goto LABEL_294;
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v16 = *((_QWORD *)this + 1138);
  if ( !v16 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 7110, L"7110", 0x54Fu, *v7);
    return 1359;
  }
  v17 = *(_DWORD *)(v16 + 80);
  v18 = *(_DWORD *)(*((_QWORD *)this + 5) + 164LL);
  if ( v6 || *((_DWORD *)this + 2862) == 2 )
  {
    v81 = (*(__int64 (__fastcall **)(WSManHttpSenderConnection *, _QWORD, _QWORD))(*(_QWORD *)this + 120LL))(
            this,
            v17,
            v6);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    nReceiveTimeout = v81;
    v19 = v104;
  }
  else
  {
    v19 = v104;
    v20 = v104 - 1;
    if ( v18 == 2 )
    {
      if ( v20 <= 0xEA5E )
        v21 = v104;
      else
        v21 = 60000;
    }
    else
    {
      v21 = 60000;
      if ( v20 <= 0x7FFFFFFD )
        v21 = v104;
    }
    nReceiveTimeout = v21 + v17;
    if ( (int)(v21 + v17) <= 0 )
      nReceiveTimeout = 0x7FFFFFFF;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x400) != 0 )
    WPP_SF_qdddd(v12[2], 384, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this, nReceiveTimeout, v19, v17, v18);
  if ( !WinHttpSetTimeouts(
          *((HINTERNET *)this + 1134),
          nReceiveTimeout,
          nReceiveTimeout,
          nReceiveTimeout,
          nReceiveTimeout) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)*v7 + 72LL))(*v7, LastError);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v43 = 385;
    goto LABEL_294;
  }
  if ( (((*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 896LL) & 1) == 0)
      & _bittest((const signed __int32 *)&i, 0xCu)) != 0
    && !WinHttpAddRequestHeaders(*((HINTERNET *)this + 1134), L"Content-Encoding:SLDC", 0x15u, 0xA0000000) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v43 = 386;
    goto LABEL_294;
  }
  v23 = (void *)*((_QWORD *)this + 1134);
  if ( *((_BYTE *)this + 54) )
  {
    if ( !WinHttpAddRequestHeaders(v23, L"Content-Type:application/soap+xml;charset=UTF-16", 0x30u, 0xA0000000) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return (unsigned int)LastError;
      v43 = 387;
      goto LABEL_294;
    }
  }
  else if ( !WinHttpAddRequestHeaders(v23, L"Content-Type:application/soap+xml;charset=UTF-8", 0x2Fu, 0xA0000000) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v43 = 388;
    goto LABEL_294;
  }
  v24 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
  if ( (*(_BYTE *)(v24 + 896) & 1) == 0
    && *(_DWORD *)(v24 + 528) != 2
    && !*((_BYTE *)this + 48)
    && *((_BYTE *)this + 8254) )
  {
    v25 = *((_DWORD *)this + 2848);
    LODWORD(LastError) = 1359;
    if ( v25 != 5 )
    {
      v27 = *((_DWORD *)this + 2849);
      if ( v27 == 4 )
        goto LABEL_38;
      if ( v27 != 5 )
      {
        if ( v25 != 4 )
        {
          if ( v25 == 7 )
          {
            v28 = 2;
          }
          else
          {
            WSManError(
              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp",
              7212,
              L"7212",
              0x54Fu,
              0);
            v28 = 3;
          }
LABEL_39:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 389, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids);
          v29 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1132);
          if ( v29 && v29 != *((void (__fastcall ****)(_QWORD, __int64))this + 1129) )
            (**v29)(v29, 1);
          v30 = *((_BYTE *)this + 54) == 0;
          v31 = "UTF-16";
          *((_QWORD *)this + 1132) = 0;
          if ( v30 )
            v31 = "UTF-8";
          v110 = (char *)v31;
          if ( this == (WSManHttpSenderConnection *)-8328LL )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 4869, L"4869", 0x54Fu, 0);
            goto LABEL_140;
          }
          v32 = 120LL * v28;
          v111 = *(struct _AUTHENTICATION_STRINGS near **)((char *)&g_authStrings + v32 + 8);
          if ( !v111 )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 4871, L"4871", 0x54Fu, 0);
            goto LABEL_140;
          }
          v33 = *((_QWORD *)this + 1129);
          v34 = 0;
          v104 = 0;
          if ( *(_QWORD *)(v33 + 40) )
            v35 = *(_DWORD *)(v33 + 48);
          else
            v35 = 0;
          if ( v28 >= 3 )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 4844, L"4844", 0x54Fu, 0);
            TotalEncryptedSizeInternalSsl = 1359;
          }
          else
          {
            v36 = *(_DWORD *)((char *)&g_authStrings + v32 + 16);
            v108 = v36;
            if ( v28 == 2 )
            {
              TotalEncryptedSizeInternalSsl = EncryptDecryptHelper::GetTotalEncryptedSizeInternalSsl(
                                                (EncryptDecryptHelper *)&v104,
                                                (struct _SecHandle *)((char *)this + 8328),
                                                v35,
                                                v31,
                                                0,
                                                v36,
                                                0x12u,
                                                &v104);
              v34 = v104;
            }
            else
            {
              pBuffer = 0;
              Buffer = QueryContextAttributesW((PCtxtHandle)((char *)this + 8328), 0, &pBuffer);
              v37 = Buffer;
              if ( Buffer < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    124,
                    &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
                    (unsigned int)Buffer);
                  v37 = Buffer;
                }
                TotalEncryptedSizeInternalSsl = SecurityStatusToWin32(v37);
              }
              else
              {
                v38 = _scprintf("OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\r\n", v110, v35);
                v34 = -1;
                v39 = v38 + v108 + 135;
                v40 = v39 + HIDWORD(pBuffer);
                if ( v39 + HIDWORD(pBuffer) >= v39 )
                {
                  if ( v35 + v40 >= v40 )
                    v34 = v35 + v40;
                  TotalEncryptedSizeInternalSsl = v35 + v40 < v40 ? 0x216 : 0;
                }
                else
                {
                  TotalEncryptedSizeInternalSsl = 534;
                }
              }
            }
            if ( !TotalEncryptedSizeInternalSsl )
            {
              *((_QWORD *)this + 1132) = 0;
              lpMem = *(LPCVOID *)(v33 + 24);
              v79 = InterlockedPopEntrySList((PSLIST_HEADER)lpMem + 1);
              v49 = v79 - 1;
              if ( !v79 )
                v49 = 0;
              if ( v49 )
              {
                *((_QWORD *)this + 1132) = v49;
LABEL_90:
                Next = v49[2].Next;
                lpMem = Next;
                *(_QWORD *)&pBuffer = v34;
                if ( Next )
                {
                  Heap = WSManMemory::GetHeap();
                  v78 = HeapSize(Heap, 0, lpMem);
                  Next = (struct _SLIST_ENTRY *)v34;
                  if ( v78 >= v34 )
                  {
                    v54 = v49[2].Next;
                    goto LABEL_97;
                  }
                }
                else
                {
                  *(_QWORD *)&pBuffer = v34;
                }
                if ( CHeap::GetHandle((CHeap *)Next) )
                {
                  Handle = CHeap::GetHandle(v52);
                  v54 = (struct _SLIST_ENTRY *)HeapAlloc(Handle, 0, pBuffer);
                  *(_QWORD *)&pBuffer = v54;
                  if ( v54 )
                  {
                    v55 = v49[2].Next;
                    if ( v55 )
                    {
                      WSManMemory::Free(v55, 0);
                      v54 = (struct _SLIST_ENTRY *)pBuffer;
                    }
                    v49[2].Next = v54;
LABEL_97:
                    *((_QWORD *)&v49[2].Next + 1) = v54;
                    v56 = (char *)this + 11332;
                    LODWORD(v49[3].Next) = v34;
                    v57 = *(unsigned __int8 **)(v33 + 40);
                    *(_QWORD *)&pBuffer = v57;
                    if ( v57 )
                    {
                      v58 = *(_DWORD *)(v33 + 48);
                    }
                    else
                    {
                      v57 = (unsigned __int8 *)Buf1;
                      v58 = 0;
                      *(_QWORD *)&pBuffer = Buf1;
                    }
                    v59 = *((_QWORD *)this + 1132);
                    v104 = v58;
                    v60 = *(const CHAR **)(v59 + 40);
                    if ( v60 )
                    {
                      v61 = *(_DWORD *)(v59 + 48);
                    }
                    else
                    {
                      v60 = Buf1;
                      v61 = 0;
                    }
                    dwBytes_4 = v61;
                    dwBytes = 0;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                    {
                      WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        134,
                        &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
                        (char *)this + 11332);
                      v61 = dwBytes_4;
                      v56 = (char *)this + 11332;
                      v57 = (unsigned __int8 *)pBuffer;
                      v58 = v104;
                    }
                    if ( v28 == 2 && v58 > 0x4000 )
                    {
                      v101 = 1;
                      dwBytes = 0;
                      for ( i = 0; ; dwBytes_4 -= i )
                      {
                        if ( v58 >= 0x4000 )
                        {
                          v84 = 0x4000;
                          v104 = v58 - 0x4000;
                          v85 = v58 == 0x4000;
                        }
                        else
                        {
                          v84 = v58;
                          v85 = 1;
                        }
                        v103 = v85;
                        Buffer = v84;
                        v62 = EncryptDecryptHelper::DoPartEncryption(
                                v56,
                                (struct _SecHandle *)((char *)this + 8328),
                                v84,
                                v57,
                                v110,
                                v111,
                                v108,
                                2,
                                v85,
                                v61,
                                v60,
                                &i);
                        if ( v62 )
                          break;
                        v64 = i + dwBytes;
                        dwBytes += i;
                        if ( v103 )
                          goto LABEL_107;
                        v56 = (char *)this + 11332;
                        v61 = dwBytes_4 - i;
                        v58 = v104;
                        v57 = (unsigned __int8 *)((unsigned int)Buffer + (_QWORD)pBuffer);
                        *(_QWORD *)&pBuffer = v57;
                        v60 += i;
                      }
                      v63 = 1;
                    }
                    else
                    {
                      v62 = EncryptDecryptHelper::DoPartEncryption(
                              v56,
                              (struct _SecHandle *)((char *)this + 8328),
                              v58,
                              v57,
                              v110,
                              v111,
                              v108,
                              v28,
                              1,
                              v61,
                              v60,
                              &dwBytes);
                      v63 = 0;
                      v101 = 0;
                      if ( !v62 )
                      {
                        v64 = dwBytes;
LABEL_107:
                        v65 = *((_QWORD *)this + 1132);
                        v66 = v64;
                        v67 = *(const void **)(v65 + 32);
                        if ( v67 )
                        {
                          v75 = WSManMemory::GetHeap();
                          if ( HeapSize(v75, 0, v67) >= v64 )
                          {
                            v76 = *(_QWORD *)(v65 + 32);
                            *(_DWORD *)(v65 + 48) = v64;
                            LODWORD(LastError) = 0;
                            v63 = v101;
                            *(_QWORD *)(v65 + 40) = v76;
                            goto LABEL_113;
                          }
                          v66 = v64;
                        }
                        v68 = *(CHeap **)(v65 + 32);
                        if ( v68 )
                        {
                          v71 = WSManMemory::ReAlloc(v68, v66);
                        }
                        else if ( CHeap::GetHandle(0) )
                        {
                          v70 = CHeap::GetHandle(v69);
                          v71 = HeapAlloc(v70, 0, v64);
                        }
                        else
                        {
                          WSManError(
                            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp",
                            170,
                            L"170",
                            0x54Fu,
                            0);
                          v71 = 0;
                        }
                        if ( v71 )
                        {
                          *(_DWORD *)(v65 + 48) = v64;
                          LODWORD(LastError) = 0;
                          v63 = v101;
                          *(_QWORD *)(v65 + 32) = v71;
                          *(_QWORD *)(v65 + 40) = v71;
                          goto LABEL_113;
                        }
                        v63 = v101;
                        LODWORD(LastError) = 14;
LABEL_164:
                        Packet::Recycle(*((Packet **)this + 1132));
                        *((_QWORD *)this + 1132) = 0;
LABEL_113:
                        if ( !(_DWORD)LastError )
                        {
                          v72 = &qword_18027B120;
                          if ( !v63 )
                            v72 = qword_18027B100;
                          v73 = v72[15 * v28];
                          v74 = &qword_18027B118;
                          if ( !v63 )
                            v74 = (__int64 *)&off_18027B0F8;
                          if ( !WinHttpAddRequestHeaders(
                                  *((HINTERNET *)this + 1134),
                                  (LPCWSTR)v74[15 * v28],
                                  v73,
                                  0xA0000000) )
                          {
                            LastError = GetLastError();
                            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(
                              *((_QWORD *)this + 1128),
                              LastError);
                            v42 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
                            {
                              return (unsigned int)LastError;
                            }
                            v43 = 391;
                            goto LABEL_294;
                          }
                          goto LABEL_119;
                        }
LABEL_140:
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            390,
                            &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
                            (unsigned int)LastError);
                        }
                        WSManHttpSenderConnection::ResetNegotiationContext(this);
                        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1128) + 72LL))(
                          *((_QWORD *)this + 1128),
                          (unsigned int)LastError);
                        return (unsigned int)LastError;
                      }
                    }
                    LODWORD(LastError) = v62;
                    goto LABEL_164;
                  }
                }
                else
                {
                  WSManError(
                    (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp",
                    170,
                    L"170",
                    0x54Fu,
                    0);
                }
                Packet::Recycle(*((Packet **)this + 1132));
                *((_QWORD *)this + 1132) = 0;
LABEL_279:
                LODWORD(LastError) = 14;
                goto LABEL_140;
              }
              if ( CHeap::GetHandle(v80) )
              {
                v47 = CHeap::GetHandle(v46);
                v48 = (struct _SLIST_ENTRY *)HeapAlloc(v47, 0, 0x40u);
                v49 = v48;
                if ( v48 )
                {
                  v48[2].Next = 0;
                  v48->Next = (struct _SLIST_ENTRY *)&Packet::`vftable';
                  v50 = (volatile signed __int32 *)lpMem;
                  *((_QWORD *)&v49[2].Next + 1) = 0;
                  LODWORD(v49[3].Next) = 0;
                  *((_QWORD *)&v49[1].Next + 1) = v50;
                  _InterlockedIncrement(v50 + 8);
                  goto LABEL_89;
                }
              }
              else
              {
                WSManError(
                  (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp",
                  170,
                  L"170",
                  0x54Fu,
                  0);
              }
              v49 = 0;
LABEL_89:
              *((_QWORD *)this + 1132) = v49;
              if ( !v49 )
                goto LABEL_279;
              goto LABEL_90;
            }
          }
          LODWORD(LastError) = TotalEncryptedSizeInternalSsl;
          goto LABEL_140;
        }
LABEL_38:
        v28 = 1;
        goto LABEL_39;
      }
    }
    v28 = 0;
    goto LABEL_39;
  }
LABEL_119:
  if ( *((_BYTE *)this + 11424)
    && !WinHttpAddRequestHeaders(*((HINTERNET *)this + 1134), L"WSMANIDENTIFY: unauthenticated\r\n", 0x20u, 0xA0000000) )
  {
    LastError = GetLastError();
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1128) + 72LL))(*((_QWORD *)this + 1128), LastError);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return (unsigned int)LastError;
    v43 = 392;
    goto LABEL_294;
  }
  return 0;
}

```

## disassembly

```asm
0x18004bb70  mov     [rsp-8+arg_8], rbx
0x18004bb75  push    rbp
0x18004bb76  push    rsi
0x18004bb77  push    rdi
0x18004bb78  push    r12
0x18004bb7a  push    r13
0x18004bb7c  push    r14
0x18004bb7e  push    r15
0x18004bb80  lea     rbp, [rsp-27h]
0x18004bb85  sub     rsp, 0B0h
0x18004bb8c  mov     rax, cs:__security_cookie
0x18004bb93  xor     rax, rsp
0x18004bb96  mov     [rbp+57h+var_38], rax
0x18004bb9a  mov     rbx, rcx
0x18004bb9d  mov     [rbp+57h+var_80], r9b
0x18004bba1  mov     rcx, [rcx+2048h]; this
0x18004bba8  movzx   r14d, r9b
0x18004bbac  mov     [rbp+57h+var_74], r8d
0x18004bbb0  mov     [rbp+57h+var_68], edx
0x18004bbb3  lea     rdi, [rbx+2340h]
0x18004bbba  test    rcx, rcx
0x18004bbbd  jnz     loc_18004C16B
0x18004bbc3  cmp     byte ptr [rbx+32h], 0
0x18004bbc7  jnz     loc_18004C811
0x18004bbcd  cmp     byte ptr [rbx+33h], 0
0x18004bbd1  jnz     loc_18004C886
0x18004bbd7  cmp     byte ptr [rbx+31h], 0
0x18004bbdb  jnz     loc_18004C8FB
0x18004bbe1  mov     rax, [rbx+28h]
0x18004bbe5  mov     rcx, [rax+80h]
0x18004bbec  cmp     dword ptr [rcx+210h], 2
0x18004bbf3  jz      loc_18004C9C9
0x18004bbf9  mov     rax, [rbx+28h]
0x18004bbfd  mov     rcx, [rax+80h]
0x18004bc04  cmp     dword ptr [rcx+210h], 2
0x18004bc0b  jz      loc_18004CA4C
0x18004bc11  mov     edx, [rbx+2C80h]
0x18004bc17  lea     r15, WPP_GLOBAL_Control
0x18004bc1e  cmp     edx, 5
0x18004bc21  jz      short loc_18004BC4A
0x18004bc23  mov     eax, [rbx+2C84h]
0x18004bc29  cmp     eax, 4
0x18004bc2c  jnz     loc_18004C033
0x18004bc32  mov     rax, [rbx+28h]
0x18004bc36  mov     rcx, [rax+80h]
0x18004bc3d  cmp     dword ptr [rcx+210h], 2
0x18004bc44  jz      loc_18004C04E
0x18004bc4a  mov     rax, [rbx+2370h]
0x18004bc51  test    rax, rax
0x18004bc54  jz      loc_18004CAC8
0x18004bc5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc61  cmp     rcx, r15
0x18004bc64  jz      short loc_18004BC73
0x18004bc66  test    dword ptr [rcx+1Ch], 400h
0x18004bc6d  jnz     loc_18004CB01
0x18004bc73  mov     rcx, [rbx+2370h]; hInternet
0x18004bc7a  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18004bc7e  mov     r9d, 4; dwBufferLength
0x18004bc84  mov     [rbp+57h+Buffer], 4
0x18004bc8b  mov     edx, 3Fh ; '?'; dwOption
0x18004bc90  call    cs:__imp_WinHttpSetOption
0x18004bc96  test    eax, eax
0x18004bc98  jz      loc_18004CB27
0x18004bc9e  mov     r10, cs:WPP_GLOBAL_Control
0x18004bca5  mov     rax, [rbx+28h]
0x18004bca9  xor     esi, esi
0x18004bcab  mov     rcx, [rax+80h]
0x18004bcb2  test    byte ptr [rcx+380h], 1
0x18004bcb9  jz      loc_18004C05C
0x18004bcbf  mov     rax, [rbx+28h]
0x18004bcc3  mov     rcx, [rax+80h]
0x18004bcca  test    byte ptr [rcx+380h], 1
0x18004bcd1  jz      loc_18004BF4C
0x18004bcd7  mov     rdx, [rbx+2070h]; lpszHeaders
0x18004bcde  test    rdx, rdx
0x18004bce1  jnz     loc_18004CEB4
0x18004bce7  mov     rax, [rbx+2390h]
0x18004bcee  test    rax, rax
0x18004bcf1  jz      loc_18004C681
0x18004bcf7  mov     r13d, [rax+50h]
0x18004bcfb  mov     rax, [rbx+28h]
0x18004bcff  mov     r12d, [rax+0A4h]
0x18004bd06  test    r14b, r14b
0x18004bd09  jnz     loc_18004C5E9
0x18004bd0f  cmp     dword ptr [rbx+2CB8h], 2
0x18004bd16  jz      loc_18004C5E9
0x18004bd1c  mov     r8d, [rbp+57h+var_74]
0x18004bd20  lea     eax, [r8-1]
0x18004bd24  cmp     r12d, 2
0x18004bd28  jnz     loc_18004CF33
0x18004bd2e  cmp     eax, 0EA5Eh
0x18004bd33  jbe     loc_18004CF2B
0x18004bd39  mov     ecx, 0EA60h
0x18004bd3e  lea     r14d, [rcx+r13]
0x18004bd42  test    r14d, r14d
0x18004bd45  jle     loc_18004CF46
0x18004bd4b  cmp     r10, r15
0x18004bd4e  jnz     loc_18004BFF4
0x18004bd54  mov     rcx, [rbx+2370h]; hInternet
0x18004bd5b  mov     r9d, r14d; nSendTimeout
0x18004bd5e  mov     r8d, r14d; nConnectTimeout
0x18004bd61  mov     [rsp+0E0h+nReceiveTimeout], r14d; nReceiveTimeout
0x18004bd66  mov     edx, r14d; nResolveTimeout
0x18004bd69  call    cs:__imp_WinHttpSetTimeouts
0x18004bd6f  cmp     eax, 1
0x18004bd72  jnz     loc_18004C50D
0x18004bd78  mov     rax, [rbx+28h]
0x18004bd7c  mov     rcx, [rax+80h]
0x18004bd83  test    byte ptr [rcx+380h], 1
0x18004bd8a  setz    cl
0x18004bd8d  bt      [rbp+57h+var_68], 0Ch
0x18004bd92  setb    al
0x18004bd95  test    al, cl
0x18004bd97  jnz     loc_18004C612
0x18004bd9d  mov     r9d, 0A0000000h; dwModifiers
0x18004bda3  mov     rcx, [rbx+2370h]; hRequest
0x18004bdaa  cmp     [rbx+36h], sil
0x18004bdae  jnz     loc_18004C0EF
0x18004bdb4  mov     r8d, 2Fh ; '/'; dwHeadersLength
0x18004bdba  lea     rdx, aContentTypeApp_0; "Content-Type:application/soap+xml;chars"...
0x18004bdc1  call    cs:__imp_WinHttpAddRequestHeaders
0x18004bdc7  cmp     eax, 1
0x18004bdca  jnz     loc_18004CF51
0x18004bdd0  mov     rax, [rbx+28h]
0x18004bdd4  mov     rcx, [rax+80h]
0x18004bddb  test    byte ptr [rcx+380h], 1
0x18004bde2  jnz     loc_18004C40D
0x18004bde8  cmp     dword ptr [rcx+210h], 2
0x18004bdef  jz      loc_18004C40D
0x18004bdf5  cmp     [rbx+30h], sil
0x18004bdf9  jnz     loc_18004C40D
0x18004bdff  cmp     [rbx+203Eh], sil
0x18004be06  jz      loc_18004C40D
0x18004be0c  mov     eax, [rbx+2C80h]
0x18004be12  mov     r12d, 54Fh
0x18004be18  cmp     eax, 5
0x18004be1b  jz      loc_18004BF44
0x18004be21  mov     ecx, [rbx+2C84h]
0x18004be27  cmp     ecx, 4
0x18004be2a  jnz     loc_18004BF3B
0x18004be30  mov     r13d, 1
0x18004be36  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be3d  cmp     rcx, r15
0x18004be40  jnz     loc_18004BFCD
0x18004be46  mov     rcx, [rbx+2360h]
0x18004be4d  test    rcx, rcx
0x18004be50  jnz     loc_18004C149
0x18004be56  cmp     [rbx+36h], sil
0x18004be5a  lea     rax, aUtf8_1; "UTF-8"
0x18004be61  lea     rdx, aUtf16_0; "UTF-16"
0x18004be68  mov     [rbx+2360h], rsi
0x18004be6f  cmovz   rdx, rax
0x18004be73  lea     r10, [rbx+2088h]
0x18004be7a  mov     [rbp+57h+var_58], rdx
0x18004be7e  test    r10, r10
0x18004be81  jz      loc_18004CFC2
0x18004be87  mov     eax, r13d
0x18004be8a  lea     r8, ?g_authStrings@@3PAU_AUTHENTICATION_STRINGS@@A; _AUTHENTICATION_STRINGS near * g_authStrings
0x18004be91  imul    rcx, rax, 78h ; 'x'
0x18004be95  mov     rax, [rcx+r8+8]
0x18004be9a  mov     [rbp+57h+var_50], rax
0x18004be9e  test    rax, rax
0x18004bea1  jz      loc_18004CFE7
0x18004bea7  mov     r15, [rbx+2348h]
0x18004beae  mov     r14d, esi
0x18004beb1  mov     [rbp+57h+var_74], esi
0x18004beb4  cmp     [r15+28h], rsi
0x18004beb8  jnz     loc_18004BFC4
0x18004bebe  mov     edi, esi
0x18004bec0  cmp     r13d, 3
0x18004bec4  jnb     loc_18004C54F
0x18004beca  mov     eax, [rcx+r8+10h]
0x18004becf  mov     [rbp+57h+var_64], eax
0x18004bed2  cmp     r13d, 2
0x18004bed6  jz      loc_18004D00C
0x18004bedc  xorps   xmm0, xmm0
0x18004bedf  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x18004bee3  xor     edx, edx; ulAttribute
0x18004bee5  mov     rcx, r10; phContext
0x18004bee8  movups  [rbp+57h+pBuffer], xmm0
0x18004beec  call    cs:__imp_QueryContextAttributesW
0x18004bef2  mov     [rbp+57h+Buffer], eax
0x18004bef5  mov     ecx, eax
0x18004bef7  test    eax, eax
0x18004bef9  js      loc_18004D03D
0x18004beff  mov     rdx, [rbp+57h+var_58]
0x18004bf03  lea     rcx, aOriginalconten_0; "OriginalContent: type=application/soap+"...
0x18004bf0a  mov     r8d, edi
0x18004bf0d  call    cs:__imp__scprintf
0x18004bf13  mov     ecx, [rbp+57h+var_64]
0x18004bf16  mov     r14d, 0FFFFFFFFh
0x18004bf1c  mov     edx, dword ptr [rbp+57h+pBuffer+0Ch]
0x18004bf1f  add     ecx, 87h
0x18004bf25  add     ecx, eax
0x18004bf27  add     edx, ecx
0x18004bf29  cmp     edx, ecx
0x18004bf2b  jnb     loc_18004C4BC
0x18004bf31  mov     eax, 216h
0x18004bf36  jmp     loc_18004C4CC
0x18004bf3b  cmp     ecx, 5
0x18004bf3e  jnz     loc_18004C5CC
0x18004bf44  mov     r13d, esi
0x18004bf47  jmp     loc_18004BE36
0x18004bf4c  cmp     [rcx+3A0h], rsi
0x18004bf53  jz      loc_18004BCD7
0x18004bf59  mov     rcx, [rbx+2370h]; hRequest
0x18004bf60  lea     rdx, aAuthorizationH; "Authorization:http://schemas.dmtf.org/w"...
0x18004bf67  mov     r9d, 0A0000000h; dwModifiers
0x18004bf6d  mov     r8d, 50h ; 'P'; dwHeadersLength
0x18004bf73  call    cs:__imp_WinHttpAddRequestHeaders
0x18004bf79  cmp     eax, 1
0x18004bf7c  jz      loc_18004CEA8
0x18004bf82  call    cs:__imp_GetLastError
0x18004bf88  mov     rcx, [rdi]
0x18004bf8b  mov     r12d, eax
0x18004bf8e  mov     edx, r12d
0x18004bf91  mov     rax, [rcx]
0x18004bf94  mov     rax, [rax+48h]
0x18004bf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bfa4  cmp     rcx, r15
0x18004bfa7  jz      loc_18004C19E
0x18004bfad  test    dword ptr [rcx+1Ch], 200h
0x18004bfb4  jz      loc_18004C19E
0x18004bfba  mov     edx, 17Eh
0x18004bfbf  jmp     loc_18004D25F
0x18004bfc4  mov     edi, [r15+30h]
0x18004bfc8  jmp     loc_18004BEC0
0x18004bfcd  test    dword ptr [rcx+1Ch], 400h
0x18004bfd4  jz      loc_18004BE46
0x18004bfda  mov     rcx, [rcx+10h]
0x18004bfde  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004bfe5  mov     edx, 185h
0x18004bfea  call    WPP_SF_
0x18004bfef  jmp     loc_18004BE46
0x18004bff4  test    dword ptr [r10+1Ch], 400h
0x18004bffc  jz      loc_18004BD54
0x18004c002  mov     rcx, [r10+10h]
0x18004c006  mov     edx, 180h
0x18004c00b  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x18004c010  mov     r9, rbx
0x18004c013  mov     [rsp+0E0h+var_B0], r13d
0x18004c018  mov     [rsp+0E0h+var_B8], r8d
0x18004c01d  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18004c024  mov     [rsp+0E0h+nReceiveTimeout], r14d
0x18004c029  call    WPP_SF_qdddd
0x18004c02e  jmp     loc_18004BD54
0x18004c033  cmp     eax, 5
0x18004c036  jz      loc_18004BC4A
0x18004c03c  cmp     edx, 4
0x18004c03f  jz      loc_18004BC32
0x18004c045  cmp     edx, 7
0x18004c048  jz      loc_18004BC4A
0x18004c04e  cmp     edx, 6
0x18004c051  jnz     loc_18004BC9E
0x18004c057  jmp     loc_18004BC4A
0x18004c05c  cmp     [rbx+2068h], esi
0x18004c062  jz      loc_18004BCBF
0x18004c068  mov     r14d, [rbx+2C80h]
0x18004c06f  cmp     r14d, 2
0x18004c073  jnz     loc_18004C7A7
0x18004c079  lea     rcx, LOG_WSMAN_AN_AUTH_MECHANISM; struct _EVENT_DESCRIPTOR *
0x18004c080  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x18004c085  test    al, al
0x18004c087  jz      short loc_18004C09C
0x18004c089  lea     rdx, aBasic_1; "Basic"
0x18004c090  lea     rcx, LOG_WSMAN_AN_AUTH_MECHANISM
0x18004c097  call    ??$LogEvent@PEAG@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@PEAG@Z; WSMan::LogEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18004c09c  mov     rax, [rbx+28h]
0x18004c0a0  mov     rcx, [rax+80h]
0x18004c0a7  cmp     [rcx+3C0h], rsi
0x18004c0ae  jz      short loc_18004C0C3
0x18004c0b0  mov     rcx, rbx; this
0x18004c0b3  call    ?SetProxyCredentials@WSManHttpSenderConnection@@AEAAKXZ; WSManHttpSenderConnection::SetProxyCredentials(void)
0x18004c0b8  mov     r12d, eax
0x18004c0bb  test    eax, eax
0x18004c0bd  jnz     loc_18004C19E
0x18004c0c3  mov     rax, [rbx+28h]
0x18004c0c7  xor     edx, edx; unsigned int
0x18004c0c9  mov     rcx, rbx; this
0x18004c0cc  mov     r8, [rax+80h]
0x18004c0d3  add     r8, 380h; struct WSMan::Client::AuthenticationInfo *
0x18004c0da  call    ?SetBasicCredentials@WSManHttpSenderConnection@@AEAAKKAEBUAuthenticationInfo@Client@WSMan@@@Z; WSManHttpSenderConnection::SetBasicCredentials(ulong,WSMan::Client::AuthenticationInfo const &)
0x18004c0df  mov     r12d, eax
0x18004c0e2  test    eax, eax
0x18004c0e4  jnz     loc_18004C19E
0x18004c0ea  jmp     loc_18004CE97
0x18004c0ef  mov     r8d, 30h ; '0'; dwHeadersLength
0x18004c0f5  lea     rdx, aContentTypeApp_1; "Content-Type:application/soap+xml;chars"...
0x18004c0fc  call    cs:__imp_WinHttpAddRequestHeaders
0x18004c102  cmp     eax, 1
0x18004c105  jz      loc_18004BDD0
0x18004c10b  call    cs:__imp_GetLastError
0x18004c111  mov     rcx, [rbx+2340h]
0x18004c118  mov     r12d, eax
0x18004c11b  mov     edx, r12d
0x18004c11e  mov     rax, [rcx]
0x18004c121  mov     rax, [rax+48h]
0x18004c125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c12a  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
