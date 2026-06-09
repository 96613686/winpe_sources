# CRdpUdpStream::InitializeInstance(IRDPENCCONStreamWorker *,IRDPENCTcpEndpointInfo *,IRdpUdpConnection *,RDPUDP_TRANSPORT_SETTINGS *)

- ea: `0x180121af0`
- end: `0x180123096`
- name: `?InitializeInstance@CRdpUdpStream@@UEAAJPEAUIRDPENCCONStreamWorker@@PEAUIRDPENCTcpEndpointInfo@@PEAUIRdpUdpConnection@@PEAURDPUDP_TRANSPORT_SETTINGS@@@Z`
- size: `5542`
- prototype: `__int64 __fastcall(CRdpUdpStream *__hidden this, struct IRDPENCCONStreamWorker *, struct IRDPENCTcpEndpointInfo *, struct IRdpUdpConnection *, struct RDPUDP_TRANSPORT_SETTINGS *)`
- caller_count: `0`
- callee_count: `31`
- tags: `registry_config, loader_planting`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x1800025dc`
- `0x180002c8c`
- `0x180003158`
- `0x180004970`
- `0x180004a94`
- `0x180005090`
- `0x180018930`
- `0x180018974`
- `0x180019a80`
- `0x180019ab0`
- `0x18006ce24`
- `0x1800787d4`
- `0x180078c20`
- `0x18007969c`
- `0x18012095c`
- `0x180120bec`
- `0x180121aa0`
- `0x180121af0`
- `0x180123300`
- `0x1801233cc`
- `0x1801242c0`
- `0x180141348`
- `0x180141568`
- `0x180142d04`
- `0x180143000`
- `0x180143b70`
- `0x1801441ac`
- `0x18014b788`
- `0x180162010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18012275d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18012275d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801228ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801228ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180122933`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180123080`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180122933`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180123080`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180122669`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180122669`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18012264a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18012264a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012202b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012202b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801226fd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180122013`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180122013`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18012283f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18012283f`
- `WS2_32!__imp_htons` at `0x180122b41`
- `WS2_32!__imp_htons` at `0x180122b41`

## string_xrefs

- `0x1801227a7`: `StringCchCat of file path failed`
- `0x180122763`: `rdpnanoTransport.dll`
- `0x180122810`: `Loading dll`
- `0x180121fe4`: `UDP stream failed to create server state transition logger `
- `0x180121fb4`: `UDP stream failed to create client state transition logger `
- `0x18012204f`: `Failed to create the stream event`
- `0x1801221eb`: `Illegal value for CWndBeta was read from the registry - Resetting to default`
- `0x1801228a3`: `CreateRdpUdpStreamWrapper`
- `0x180122871`: `Failed to loadLibrary RdpNanoTransport.dll for URCP. Fall back to UDP v2`
- `0x1801228df`: `CreateRdpUdpStreamWrapper failed`

## pseudocode

```c
__int64 __fastcall CRdpUdpStream::InitializeInstance(
        CRdpUdpStream *this,
        struct IRDPENCCONStreamWorker *a2,
        struct IRDPENCTcpEndpointInfo *a3,
        struct IRdpUdpConnection *a4,
        struct RDPUDP_TRANSPORT_SETTINGS *a5)
{
  signed int ClientEventLogCallback; // ebx
  char *v9; // rdx
  const char **v10; // rax
  char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rdi
  const char *v14; // rdi
  struct RDPUDP_TRANSPORT_SETTINGS *v15; // rdi
  CRdpUdpStream *v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int16 *v20; // rdx
  const char *v21; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v24; // ecx
  unsigned int v25; // r8d
  int v26; // r9d
  float v27; // xmm6_4
  CRdpUdpStream *v28; // rcx
  CRdpUdpStream *v29; // rcx
  CRdpUdpStream *v30; // rcx
  CRdpUdpStream *v31; // rcx
  CRdpUdpStream *v32; // rcx
  CRdpUdpStream *v33; // rcx
  CRdpUdpStream *v34; // rcx
  CRdpUdpStream *v35; // rcx
  CRdpUdpStream *v36; // rcx
  CRdpUdpStream *v37; // rcx
  int v38; // r8d
  int v39; // r9d
  CRdpUdpStream *v40; // rcx
  int v41; // r9d
  unsigned int v42; // ecx
  _DWORD *v43; // r13
  int v44; // edx
  BOOL v45; // ecx
  signed int v46; // eax
  bool v47; // zf
  int v48; // edx
  CRdpUdpStream *v49; // rcx
  const struct _GUID *v50; // rdx
  int v51; // r8d
  int v52; // r9d
  RdpUdpETWEvents *v53; // rcx
  CRdpUdpTimer *v54; // rax
  int v55; // r8d
  int v56; // r9d
  int v57; // ecx
  int v58; // r9d
  unsigned int v59; // eax
  DWORD ModuleFileNameW; // eax
  signed int v61; // eax
  bool v62; // sf
  signed int v63; // eax
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  __int64 *v67; // rdx
  const char *v68; // rax
  signed int v69; // eax
  bool v70; // sf
  signed int v71; // eax
  wchar_t *v72; // rax
  int v73; // ecx
  int v74; // r8d
  int v75; // r9d
  wchar_t *v76; // rbx
  int v77; // eax
  WCHAR *v78; // rax
  WCHAR *v79; // rcx
  HMODULE LibraryW; // rax
  int v81; // ecx
  int v82; // r8d
  int v83; // r9d
  __int64 *v84; // rdi
  FARPROC ProcAddress; // rax
  int v86; // eax
  int v87; // r8d
  int v88; // r9d
  int v89; // ecx
  int v90; // r8d
  int v91; // r9d
  void *v92; // rax
  int v93; // r8d
  int v94; // r9d
  _QWORD *v95; // rax
  int v96; // r8d
  int v97; // r9d
  __int128 v98; // xmm0
  unsigned int i; // r13d
  __int64 v100; // rdi
  __int64 (__fastcall *v101)(__int64, __int64, __int64, _QWORD, __int128 *, __int64); // rbx
  __int64 v102; // rax
  __int64 v103; // r8
  __int64 v104; // rdx
  int v105; // ecx
  int v106; // r9d
  struct _GUID *v107; // rdx
  HMODULE v108; // rcx
  int v109; // r8d
  int v110; // r9d
  CFecEncoder *v112; // rax
  int v113; // r8d
  int v114; // r9d
  CFecEncoder *v115; // rax
  int v116; // ecx
  int v117; // r8d
  int v118; // r9d
  CFecDecoder *v119; // rax
  int v120; // r8d
  int v121; // r9d
  int v122; // ecx
  int v123; // r8d
  int v124; // r9d
  void *v125; // rax
  int v126; // r9d
  HMODULE *p_phModule; // [rsp+40h] [rbp-C8h]
  const char **v128; // [rsp+48h] [rbp-C0h]
  const char **v129; // [rsp+50h] [rbp-B8h]
  const char *v130; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v131; // [rsp+60h] [rbp-A8h] BYREF
  const char *v132; // [rsp+68h] [rbp-A0h] BYREF
  const char *v133; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v134[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v135; // [rsp+88h] [rbp-80h] BYREF
  HMODULE phModule; // [rsp+98h] [rbp-70h] BYREF
  const char *v137; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v138; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v139; // [rsp+ACh] [rbp-5Ch] BYREF
  unsigned int v140; // [rsp+B0h] [rbp-58h] BYREF
  CRdpUdpStream *v141; // [rsp+B4h] [rbp-54h] BYREF
  unsigned int v142; // [rsp+BCh] [rbp-4Ch] BYREF
  unsigned int v143; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v144; // [rsp+C4h] [rbp-44h] BYREF
  unsigned int v145; // [rsp+C8h] [rbp-40h] BYREF
  unsigned int v146; // [rsp+CCh] [rbp-3Ch] BYREF
  unsigned int v147; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int v148; // [rsp+D4h] [rbp-34h] BYREF
  unsigned int v149[4]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR Filename[264]; // [rsp+E8h] [rbp-20h] BYREF

  v137 = (const char *)a4;
  *(_QWORD *)&v135 = a3;
  if ( !a5 )
  {
    ClientEventLogCallback = -2147467261;
    if ( (unsigned int)CallbackContext <= 2 )
    {
LABEL_5:
      v11 = (char *)this - 64;
      goto LABEL_158;
    }
    LODWORD(phModule) = 516;
    v137 = "pSettings is NULL";
    v130 = "InitializeInstance";
    v132 = "Error condition failed";
    v129 = &v137;
    v9 = byte_1801CEDBB;
    v128 = &v130;
    p_phModule = &phModule;
    v10 = &v132;
LABEL_4:
    LODWORD(v131) = -2147467261;
    v134[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v9,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v10,
      (__int64)&v131,
      (__int64)v134,
      (__int64)p_phModule,
      (__int64)v128,
      (__int64)v129);
    goto LABEL_5;
  }
  if ( !*((_DWORD *)a5 + 2) )
  {
    if ( !a2 && (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v131) = *((_DWORD *)this + 32);
      v133 = "StreamWorker is invalid";
      v132 = "InitializeInstance";
      LODWORD(phModule) = 525;
      v134[0] = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v130) = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)byte_1801CF49B,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v133,
        (__int64)&v130,
        (__int64)v134,
        (__int64)&phModule,
        (__int64)&v132,
        (__int64)&v131);
    }
    if ( !a3 && (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v130) = *((_DWORD *)this + 32);
      v134[0] = "m_spEndpointInfo is invalid";
      v133 = "InitializeInstance";
      LODWORD(v131) = 529;
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(phModule) = -2147467261;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)&byte_1801CDFF7,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)v134,
        (__int64)&phModule,
        (__int64)&v132,
        (__int64)&v131,
        (__int64)&v133,
        (__int64)&v130);
    }
    v12 = v137;
    if ( !v137 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v130) = *((_DWORD *)this + 32);
        v134[0] = "m_spConnection is invalid";
        v133 = "InitializeInstance";
        LODWORD(v131) = 533;
        v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
        LODWORD(phModule) = -2147467261;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)this,
          (unsigned int)&word_1801CDCEE,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)v134,
          (__int64)&phModule,
          (__int64)&v132,
          (__int64)&v131,
          (__int64)&v133,
          (__int64)&v130);
      }
      v12 = v137;
    }
    if ( !a2 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_5;
      v132 = "InitializeInstance";
      v133 = "pWorker is NULL";
      v9 = (char *)word_1801CDA6A;
      LODWORD(v130) = 536;
      v137 = "Error condition failed";
      v129 = &v133;
      v128 = &v132;
      p_phModule = (HMODULE *)&v130;
      v10 = &v137;
      goto LABEL_4;
    }
    if ( !a3 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_5;
      v132 = "InitializeInstance";
      v133 = "pEndpointInfo is NULL";
      v9 = byte_1801CE1E3;
      LODWORD(v130) = 537;
      v137 = "Error condition failed";
      v129 = &v133;
      v128 = &v132;
      p_phModule = (HMODULE *)&v130;
      v10 = &v137;
      goto LABEL_4;
    }
    if ( !v12 )
    {
      ClientEventLogCallback = -2147467261;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_5;
      v132 = "InitializeInstance";
      v133 = "pSocket is NULL";
      v9 = byte_1801CF5C5;
      LODWORD(v130) = 538;
      v137 = "Error condition failed";
      v129 = &v133;
      v128 = &v132;
      p_phModule = (HMODULE *)&v130;
      v10 = &v137;
      goto LABEL_4;
    }
  }
  CTSReaderWriterLock::WriteLock((CRdpUdpStream *)((char *)this + 92));
  if ( a2 != *((struct IRDPENCCONStreamWorker **)this + 6) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 48);
    *((_QWORD *)this + 6) = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 48);
  }
  v13 = v135;
  if ( (_QWORD)v135 != *((_QWORD *)this + 8) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 64);
    *((_QWORD *)this + 8) = v13;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 64);
  }
  v14 = v137;
  if ( v137 != *((const char **)this + 9) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 72);
    *((_QWORD *)this + 9) = v14;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
  }
  CTSReaderWriterLock::WriteUnlock((CRdpUdpStream *)((char *)this + 92));
  v15 = a5;
  v16 = (CRdpUdpStream *)((char *)this - 64);
  if ( *((_DWORD *)a5 + 6) )
  {
    ClientEventLogCallback = CRdpUdpStream::CreateClientEventLogCallback(v16);
    if ( ClientEventLogCallback >= 0 )
      goto LABEL_41;
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_40;
    v20 = word_1801CF182;
    LODWORD(v130) = *((_DWORD *)this + 32);
    v21 = "UDP stream failed to create client state transition logger ";
    goto LABEL_39;
  }
  ClientEventLogCallback = CRdpUdpStream::CreateServerEventLogCallback(v16);
  if ( ClientEventLogCallback >= 0 )
    goto LABEL_41;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v20 = (__int16 *)byte_1801CDBC5;
    LODWORD(v130) = *((_DWORD *)this + 32);
    v21 = "UDP stream failed to create server state transition logger ";
LABEL_39:
    *(_QWORD *)&v135 = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (_DWORD)v20,
      v18,
      v19,
      (__int64)&v135,
      (__int64)&v130);
  }
LABEL_40:
  ClientEventLogCallback = 0;
LABEL_41:
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 48) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    ClientEventLogCallback = LastError;
    if ( LastError > 0 )
      ClientEventLogCallback = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v133 = "InitializeInstance";
      *(_QWORD *)&v135 = "Failed to create the stream event";
      LODWORD(v130) = 571;
      v134[0] = "Error condition failed";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v131) = ClientEventLogCallback;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)qword_1801CF688,
        v25,
        v26,
        (__int64)v134,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v133,
        (__int64)&v135);
    }
    goto LABEL_157;
  }
  v27 = FLOAT_0_25;
  v139 = 2;
  v138 = 875;
  v142 = 1;
  *(_QWORD *)v149 = 10000000;
  v141 = (CRdpUdpStream *)0x100000000LL;
  v140 = 0;
  v143 = 4;
  v144 = 3;
  v146 = 75000;
  v145 = 0;
  v147 = 15000;
  v148 = 0;
  CRdpUdpStream::ReadRegistryValue(0, L"ForceDisableUDPL", &v148);
  CRdpUdpStream::ReadRegistryValue(v28, L"UdpFecMode", &v139);
  if ( v139 == 1 )
    v140 = 9;
  CRdpUdpStream::ReadRegistryValue(v29, L"UdpDontTimeout", &v145);
  CRdpUdpStream::ReadRegistryValue(v30, L"UdpCongestionController", (unsigned int *)&v141 + 1);
  CRdpUdpStream::ReadRegistryValue(v31, L"UdpCWndMultiplier", &v142);
  CRdpUdpStream::ReadRegistryValue(v32, L"UdpCWndAlpha", &v143);
  CRdpUdpStream::ReadRegistryValue(v33, L"UdpCWndBeta", &v138);
  CRdpUdpStream::ReadRegistryValue(v34, L"DupAckThreshold", &v144);
  CRdpUdpStream::ReadRegistryValue(v35, L"OutOfOrderWaitTimeout", &v146);
  CRdpUdpStream::ReadRegistryValue(v36, L"UdpQLengthTraceInterval", &v147);
  if ( v138 > 0x3E8 )
  {
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v131) = v138;
      *(_QWORD *)&v135 = "Illegal value for CWndBeta was read from the registry - Resetting to default";
      LODWORD(v130) = 875;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v37,
        (unsigned int)word_1801CE3C2,
        v38,
        v39,
        (__int64)&v135,
        (__int64)&v131,
        (__int64)&v130);
    }
    v138 = 875;
  }
  CRdpUdpStream::ReadRegistryValue(v37, L"UdpFecAdaptiveIntervalNs", v149);
  CRdpUdpStream::ReadRegistryValue(v40, L"UdpFecAdaptiveRoundupPercent", (unsigned int *)&v141);
  if ( (unsigned int)((_DWORD)v141 - 1) <= 0x62 )
    v27 = (float)(int)v141 / 100.0;
  CRdpUdpStream::ReadRegistryValue((CRdpUdpStream *)(unsigned int)v141, L"UdpFecInitialBlockM", &v140);
  v42 = CRdpUdpStream::connId;
  v43 = (_DWORD *)((char *)this + 128);
  *((_DWORD *)this + 32) = CRdpUdpStream::connId;
  *((_DWORD *)this + 33) = 0;
  v44 = *(_DWORD *)a5;
  *((_DWORD *)this + 36) = 1045220557;
  CRdpUdpStream::connId = v42 + 1;
  v45 = v44 == 0;
  *((_DWORD *)this + 35) = v139;
  *((_DWORD *)this + 37) = HIDWORD(v141);
  *((_DWORD *)this + 38) = v142;
  *((_DWORD *)this + 39) = v143;
  v46 = v138;
  *((_DWORD *)this + 34) = v45;
  *((_DWORD *)this + 41) = v144;
  *((float *)this + 40) = (float)v46 / 1000.0;
  *((_DWORD *)this + 42) = *((_DWORD *)a5 + 5);
  *((_DWORD *)this + 43) = *((_DWORD *)a5 + 4);
  *((_QWORD *)this + 22) = *((unsigned int *)a5 + 3);
  *((_DWORD *)this + 46) = v45;
  v47 = *((_DWORD *)a5 + 2) == 0;
  *((float *)this + 52) = v27;
  *((_DWORD *)this + 47) = !v47;
  *((_QWORD *)this + 25) = *(_QWORD *)v149;
  *((_DWORD *)this + 53) = v140;
  *((_DWORD *)this + 54) = v145;
  *((_DWORD *)this + 57) = v146;
  *((_QWORD *)this + 30) = v147;
  *((_DWORD *)this + 48) = *((_DWORD *)a5 + 6);
  *((_DWORD *)this + 33) = *((unsigned __int16 *)a5 + 14);
  if ( v44 )
  {
    *((_DWORD *)this + 35) = 1;
    *((_DWORD *)this + 53) = 9;
  }
  if ( v148 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)&v135 = "Overriding UDP-Lossy Transport -- Please Note: Client and Server both must override UDP Lossy. "
                         "Else, the session *WILL* disconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)qword_1801CDAE8,
        0,
        v41,
        (__int64)&v135);
    }
    *((_DWORD *)this + 34) = 1;
  }
  v48 = *((_DWORD *)a5 + 6);
  LODWORD(phModule) = v48 != 0 ? 1024 : 200;
  v49 = (CRdpUdpStream *)(unsigned int)phModule;
  *((_WORD *)this + 111) = v48 != 0 ? 1024 : 200;
  LOWORD(v49) = v48 != 0 ? 2048 : 256;
  *((_WORD *)this + 112) = (_WORD)v49;
  *((_WORD *)this + 113) = v48 != 0 ? 4096 : 512;
  CRdpUdpStream::ReadRegistryValue(v49, L"ReceiverWindowSize", (unsigned int *)&phModule);
  *((_WORD *)this + 110) = (_WORD)phModule;
  CRdpUdpETWEvents_CreateInstance((CRdpUdpStream *)((char *)this + 128), v50, (void **)this + 14);
  v53 = (RdpUdpETWEvents *)*((_QWORD *)this + 14);
  if ( !v53 )
  {
    ClientEventLogCallback = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v133 = "InitializeInstance";
      *(_QWORD *)&v135 = "CRdpUdpETWEvents allocation";
      LODWORD(v130) = 705;
      v134[0] = "Error condition failed";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v131) = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)&dword_1801CDD7C,
        v51,
        v52,
        (__int64)v134,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v133,
        (__int64)&v135);
    }
    goto LABEL_5;
  }
  RdpUdpETWEvents::Enable(v53);
  v54 = (CRdpUdpTimer *)operator new(0x18u);
  if ( v54 )
  {
    *(_QWORD *)v54 = 0;
    *((_QWORD *)v54 + 1) = 1;
    *((_QWORD *)v54 + 2) = 0;
  }
  *((_QWORD *)this + 33) = v54;
  if ( !v54 )
  {
    ClientEventLogCallback = -2147024882;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v133 = "InitializeInstance";
      *(_QWORD *)&v135 = "CRdpUdpTimer allocation";
      LODWORD(v130) = 713;
      v134[0] = "Error condition failed";
      v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
      LODWORD(v131) = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024882,
        (unsigned int)&word_1801CF71E,
        v55,
        v56,
        (__int64)v134,
        (__int64)&v131,
        (__int64)&v132,
        (__int64)&v130,
        (__int64)&v133,
        (__int64)&v135);
    }
    goto LABEL_5;
  }
  CRdpUdpTimer::Initialize(v54);
  if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v130) = *((_DWORD *)this + 34) == 0;
    LODWORD(v131) = *((_DWORD *)this + 33);
    LODWORD(phModule) = *v43;
    *(_QWORD *)&v135 = "UDP Stream";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v57,
      (unsigned int)qword_1801CFB90,
      v25,
      v58,
      (__int64)&v135,
      (__int64)&phModule,
      (__int64)&v131,
      (__int64)&v130);
  }
  v59 = *((_DWORD *)this + 33);
  if ( v59 == 257 )
  {
    phModule = 0;
    memset_0(Filename, 0, 0x20Au);
    if ( GetModuleHandleExW(6u, (LPCWSTR)CRdpUdpStream::STATIC_GatewayWorkerThread, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW && ModuleFileNameW != 261 )
        goto LABEL_89;
      Filename[0] = 0;
      v61 = GetLastError();
      v62 = v61 < 0;
      if ( v61 > 0 )
        v62 = 1;
      if ( !v62 || (unsigned int)CallbackContext <= 3 )
        goto LABEL_89;
      *(_QWORD *)&v135 = "InitializeInstance";
      v63 = GetLastError();
      if ( v63 > 0 )
        v63 = (unsigned __int16)v63 | 0x80070000;
      LODWORD(v130) = v63;
      v67 = qword_1801CEA50;
      v68 = "Failed to get the module file name";
    }
    else
    {
      v69 = GetLastError();
      v70 = v69 < 0;
      if ( v69 > 0 )
        v70 = 1;
      if ( !v70 || (unsigned int)CallbackContext <= 3 )
        goto LABEL_89;
      *(_QWORD *)&v135 = "InitializeInstance";
      v71 = GetLastError();
      if ( v71 > 0 )
        v71 = (unsigned __int16)v71 | 0x80070000;
      LODWORD(v130) = v71;
      v67 = (__int64 *)byte_1801CF7EB;
      v68 = "Failed to get module handle to itself.";
    }
    v133 = v68;
    v132 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v64,
      (_DWORD)v67,
      v65,
      v66,
      (__int64)&v132,
      (__int64)&v133,
      (__int64)&v130,
      (__int64)&v135);
LABEL_89:
    v72 = wcsrchr(Filename, 0x5Cu);
    v76 = v72;
    if ( v72 )
    {
      v76 = v72 + 1;
      v72[1] = 0;
      v77 = StringCchCatW(Filename, 0x105u, L"rdpnanoTransport.dll");
      if ( v77 < 0 )
      {
        v73 = (int)CallbackContext;
        v76 = 0;
        if ( (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v130) = v77;
          *(_QWORD *)&v135 = "InitializeInstance";
          v133 = "StringCchCat of file path failed";
          v132 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)qword_1801CE2F8,
            v74,
            v75,
            (__int64)&v132,
            (__int64)&v133,
            (__int64)&v130,
            (__int64)&v135);
        }
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v78 = Filename;
      if ( !v76 )
        v78 = (WCHAR *)L"rdpnanoTransport.dll";
      *(_QWORD *)&v135 = v78;
      v133 = "Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v73,
        (unsigned int)&dword_1801CF3A4,
        v74,
        v75,
        (__int64)&v133,
        (__int64)&v135);
    }
    v79 = Filename;
    if ( !v76 )
      v79 = (WCHAR *)L"rdpnanoTransport.dll";
    LibraryW = LoadLibraryW(v79);
    *((_QWORD *)this + 76) = LibraryW;
    if ( LibraryW )
    {
      v84 = (__int64 *)((char *)this + 376);
      *((_QWORD *)this + 47) = 0;
      ProcAddress = GetProcAddress(LibraryW, "CreateRdpUdpStreamWrapper");
      if ( ProcAddress )
      {
        v86 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(11, (char *)this + 376);
        if ( v86 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LODWORD(v130) = v86;
          *(_QWORD *)&v135 = "InitializeInstance";
          v133 = "CreateRdpUdpStreamWrapper failed";
          v132 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_1801CE331,
            v87,
            v88,
            (__int64)&v132,
            (__int64)&v133,
            (__int64)&v130,
            (__int64)&v135);
        }
      }
      if ( *v84 )
      {
        if ( !*((_DWORD *)a5 + 6) )
          *((_DWORD *)this + 58) = 1;
        v92 = operator new(*((_QWORD *)this + 22) + 2050LL);
        *((_QWORD *)this + 69) = v92;
        if ( !v92 )
        {
          ClientEventLogCallback = -2147024882;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v133 = "InitializeInstance";
            *(_QWORD *)&v135 = "SendBuffer allocation";
            LODWORD(v130) = 812;
            v134[0] = "Error condition failed";
            v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v131) = -2147024882;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              -2147024882,
              (unsigned int)byte_1801CE94B,
              v93,
              v94,
              (__int64)v134,
              (__int64)&v131,
              (__int64)&v132,
              (__int64)&v130,
              (__int64)&v133,
              (__int64)&v135);
          }
          goto LABEL_5;
        }
        v95 = operator new(0x28u);
        if ( v95 )
        {
          v98 = *(_OWORD *)((char *)this + 564);
          v95[4] = 0;
          *v95 = &CRdpUdpStreamWrapperCallback::`vftable';
          v95[1] = (char *)this - 64;
          *((_OWORD *)v95 + 1) = v98;
        }
        else
        {
          v95 = 0;
        }
        v131 = 564;
        *((_QWORD *)this + 77) = v95;
        if ( !v95 )
        {
          ClientEventLogCallback = -2147024882;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v133 = "InitializeInstance";
            *(_QWORD *)&v135 = "CRdpUdpStreamWrapperCallback allocation";
            LODWORD(v130) = 815;
            v134[0] = "Error condition failed";
            v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v131) = -2147024882;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              -2147024882,
              (unsigned int)byte_1801CE455,
              v96,
              v97,
              (__int64)v134,
              (__int64)&v131,
              (__int64)&v132,
              (__int64)&v130,
              (__int64)&v133,
              (__int64)&v135);
          }
          goto LABEL_5;
        }
        v130 = 0;
        HIWORD(v130) = htons(1u);
        for ( i = 0; i < 8; ++i )
        {
          if ( *((_BYTE *)&v130 + i) == 1 )
            break;
        }
        v100 = *v84;
        v101 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int128 *, __int64))(*(_QWORD *)v100 + 32LL);
        v102 = (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v137 + 80LL))(v137);
        v103 = *((_QWORD *)this + 77);
        LOBYTE(v104) = *((_DWORD *)this + 48) != 0;
        v135 = *(_OWORD *)((char *)this + v131);
        ClientEventLogCallback = v101(v100, v104, v103, i, &v135, v102);
        if ( ClientEventLogCallback < 0 )
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            v133 = "InitializeInstance";
            *(_QWORD *)&v135 = "RdpUdpStreamWrapper Initialize failed";
            LODWORD(v130) = 831;
            v134[0] = "Error HResult failed";
            v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
            LODWORD(v131) = ClientEventLogCallback;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v105,
              (unsigned int)&byte_1801CE6FF,
              v25,
              v106,
              (__int64)v134,
              (__int64)&v131,
              (__int64)&v132,
              (__int64)&v130,
              (__int64)&v133,
              (__int64)&v135);
          }
          goto LABEL_5;
        }
        v11 = (char *)this - 64;
LABEL_128:
        v107 = (struct _GUID *)*((unsigned int *)v11 + 49);
        v135 = *(_OWORD *)((char *)this + 564);
        RDPTransportTraceLogging::LogRDPTransportUDPProfile((RDPTransportTraceLogging *)&v135, v107, v25);
        goto LABEL_129;
      }
      FreeLibrary(*((HMODULE *)this + 76));
      *((_QWORD *)this + 76) = 0;
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v131) = *v43;
        *(_QWORD *)&v135 = "Failed to get UDP-Nano wrapper with an expected interface version. Fall back to UDP v2";
        LODWORD(v130) = 11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v89,
          (unsigned int)word_1801CE7BA,
          v90,
          v91,
          (__int64)&v135,
          (__int64)&v131,
          (__int64)&v130);
      }
    }
    else if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v130) = *v43;
      *(_QWORD *)&v135 = "Failed to loadLibrary RdpNanoTransport.dll for URCP. Fall back to UDP v2";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v81,
        (unsigned int)word_1801CDBF2,
        v82,
        v83,
        (__int64)&v135,
        (__int64)&v130);
    }
    v15 = a5;
    goto LABEL_134;
  }
  if ( v59 < 0x101 )
  {
    if ( v59 < 0x100 )
    {
LABEL_135:
      v112 = (CFecEncoder *)operator new(0x1260u);
      if ( v112 )
        v115 = CFecEncoder::CFecEncoder(v112);
      else
        v115 = 0;
      *((_QWORD *)this + 31) = v115;
      if ( !v115 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v133 = "InitializeInstance";
          *(_QWORD *)&v135 = "CFecEncoder allocation";
          LODWORD(v130) = 847;
          v134[0] = "Error condition failed";
          v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v131) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)byte_1801CF63D,
            v113,
            v114,
            (__int64)v134,
            (__int64)&v131,
            (__int64)&v132,
            (__int64)&v130,
            (__int64)&v133,
            (__int64)&v135);
        }
        goto LABEL_5;
      }
      ClientEventLogCallback = CFecEncoder::Initialize(
                                 v115,
                                 (CRdpUdpStream *)((char *)this + 128),
                                 *((struct CRdpUdpTimer **)this + 33),
                                 *((struct IRdpUdpControlEvents **)this + 14));
      if ( ClientEventLogCallback < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v133 = "InitializeInstance";
          *(_QWORD *)&v135 = "FecEncoder initialization failed";
          LODWORD(v130) = 849;
          v134[0] = "Error HResult failed";
          v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v131) = ClientEventLogCallback;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v116,
            (unsigned int)&byte_1801CF227,
            v117,
            v118,
            (__int64)v134,
            (__int64)&v131,
            (__int64)&v132,
            (__int64)&v130,
            (__int64)&v133,
            (__int64)&v135);
        }
        goto LABEL_5;
      }
      v119 = (CFecDecoder *)operator new(0x190u);
      if ( v119 )
        v119 = CFecDecoder::CFecDecoder(v119);
      *((_QWORD *)this + 32) = v119;
      if ( !v119 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v133 = "InitializeInstance";
          *(_QWORD *)&v135 = "CFecDecoder allocation";
          LODWORD(v130) = 853;
          v134[0] = "Error condition failed";
          v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v131) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)byte_1801CDF8D,
            v120,
            v121,
            (__int64)v134,
            (__int64)&v131,
            (__int64)&v132,
            (__int64)&v130,
            (__int64)&v133,
            (__int64)&v135);
        }
        goto LABEL_5;
      }
      ClientEventLogCallback = CFecDecoder::Initialize(
                                 v119,
                                 (CRdpUdpStream *)((char *)this + 128),
                                 *((struct CRdpUdpTimer **)this + 33),
                                 *((struct IRdpUdpControlEvents **)this + 14));
      if ( ClientEventLogCallback < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v133 = "InitializeInstance";
          *(_QWORD *)&v135 = "FecDecoder initialization failed";
          LODWORD(v130) = 855;
          v134[0] = "Error HResult failed";
          v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v131) = ClientEventLogCallback;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v122,
            (unsigned int)byte_1801CF93B,
            v123,
            v124,
            (__int64)v134,
            (__int64)&v131,
            (__int64)&v132,
            (__int64)&v130,
            (__int64)&v133,
            (__int64)&v135);
        }
        goto LABEL_5;
      }
      v125 = operator new(*((_QWORD *)this + 22) + 2050LL);
      *((_QWORD *)this + 69) = v125;
      if ( !v125 )
      {
        ClientEventLogCallback = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v133 = "InitializeInstance";
          *(_QWORD *)&v135 = "SendBuffer allocation";
          LODWORD(v130) = 861;
          v134[0] = "Error condition failed";
          v132 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpstream.cpp";
          LODWORD(v131) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)qword_1801CDE50,
            v25,
            v126,
            (__int64)v134,
            (__int64)&v131,
            (__int64)&v132,
            (__int64)&v130,
            (__int64)&v133,
            (__int64)&v135);
        }
        goto LABEL_5;
      }
      goto LABEL_155;
    }
LABEL_134:
    *((_DWORD *)this + 33) = 2;
    goto LABEL_135;
  }
LABEL_155:
  if ( !*((_DWORD *)v15 + 6) )
    *((_DWORD *)this + 58) = 1;
LABEL_157:
  v11 = (char *)this - 64;
  if ( ClientEventLogCallback >= 0 )
    goto LABEL_128;
LABEL_158:
  if ( *((_DWORD *)v11 + 64) )
    CRdpUdpStream::LogUDPClientStateTransition(v11, 3);
  else
    CRdpUdpStream::LogUDPStateTransition(v11, 0, 8, 8, ClientEventLogCallback);
  v108 = (HMODULE)*((_QWORD *)this + 76);
  if ( v108 )
  {
    FreeLibrary(v108);
    *((_QWORD *)this + 76) = 0;
  }
LABEL_129:
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v131) = *((_DWORD *)this + 74);
    *(_QWORD *)&v135 = "UDP Stream Initialization done";
    LODWORD(v130) = ClientEventLogCallback;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v108,
      (unsigned int)&dword_1801CFA8C,
      v109,
      v110,
      (__int64)&v135,
      (__int64)&v131,
      (__int64)&v130);
  }
  return (unsigned int)ClientEventLogCallback;
}

```

## disassembly

```asm
0x180121af0  mov     rax, rsp
0x180121af3  mov     [rax+10h], rbx
0x180121af7  push    rbp
0x180121af8  push    rsi
0x180121af9  push    rdi
0x180121afa  push    r12
0x180121afc  push    r13
0x180121afe  push    r14
0x180121b00  push    r15
0x180121b02  lea     rbp, [rax-248h]
0x180121b09  sub     rsp, 310h
0x180121b10  movaps  xmmword ptr [rax-48h], xmm6
0x180121b14  mov     rax, cs:__security_cookie
0x180121b1b  xor     rax, rsp
0x180121b1e  mov     [rbp+240h+var_50], rax
0x180121b25  mov     rax, [rbp+240h+arg_20]
0x180121b2c  mov     rbx, r8
0x180121b2f  mov     [rbp+240h+var_2A8], r9
0x180121b33  mov     r13, rdx
0x180121b36  mov     qword ptr [rbp+240h+var_2C0], rbx
0x180121b3a  mov     rsi, rcx
0x180121b3d  mov     r14d, 2
0x180121b43  test    rax, rax
0x180121b46  jnz     loc_180121BEB
0x180121b4c  mov     eax, cs:CallbackContext
0x180121b52  mov     edi, 80004003h
0x180121b57  mov     ebx, edi
0x180121b59  cmp     eax, r14d
0x180121b5c  jbe     loc_180121BE2
0x180121b62  lea     rax, aPsettingsIsNul; "pSettings is NULL"
0x180121b69  mov     dword ptr [rbp+240h+phModule], 204h
0x180121b70  mov     [rbp+240h+var_2A8], rax
0x180121b74  lea     r15, aInitializeinst_1; "InitializeInstance"
0x180121b7b  lea     rax, aErrorCondition; "Error condition failed"
0x180121b82  mov     [rsp+340h+var_2F0], r15
0x180121b87  mov     [rsp+340h+var_2E0], rax
0x180121b8c  lea     r12, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180121b93  lea     rax, [rbp+240h+var_2A8]
0x180121b97  mov     [rsp+340h+var_2F8], rax
0x180121b9c  lea     rdx, byte_1801CEDBB
0x180121ba3  lea     rax, [rsp+340h+var_2F0]
0x180121ba8  mov     [rsp+340h+var_300], rax
0x180121bad  lea     rax, [rbp+240h+phModule]
0x180121bb1  mov     [rsp+340h+var_308], rax
0x180121bb6  lea     rax, [rsp+340h+var_2D0]
0x180121bbb  mov     [rsp+340h+var_310], rax
0x180121bc0  lea     rax, [rsp+340h+var_2E8]
0x180121bc5  mov     [rsp+340h+var_318], rax
0x180121bca  lea     rax, [rsp+340h+var_2E0]
0x180121bcf  mov     dword ptr [rsp+340h+var_2E8], edi
0x180121bd3  mov     [rsp+340h+var_2D0], r12
0x180121bd8  mov     [rsp+340h+var_320], rax
0x180121bdd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180121be2  lea     rax, [rsi-40h]
0x180121be6  jmp     loc_180123043
0x180121beb  cmp     dword ptr [rax+8], 0
0x180121bef  lea     r15, aInitializeinst_1; "InitializeInstance"
0x180121bf6  lea     r12, aOnecoreTermsrv_17; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180121bfd  jnz     loc_180121F0E
0x180121c03  mov     edi, 80004003h
0x180121c08  test    r13, r13
0x180121c0b  jnz     short loc_180121C8A
0x180121c0d  mov     eax, cs:CallbackContext
0x180121c13  cmp     eax, r14d
0x180121c16  jbe     short loc_180121C8A
0x180121c18  mov     eax, [rcx+80h]
0x180121c1e  lea     rdx, byte_1801CF49B
0x180121c25  mov     dword ptr [rsp+340h+var_2E8], eax
0x180121c29  lea     rax, aStreamworkerIs; "StreamWorker is invalid"
0x180121c30  mov     [rsp+340h+var_2D8], rax
0x180121c35  lea     rax, [rsp+340h+var_2E8]
0x180121c3a  mov     [rsp+340h+var_2F8], rax
0x180121c3f  lea     rax, [rsp+340h+var_2E0]
0x180121c44  mov     [rsp+340h+var_300], rax
0x180121c49  lea     rax, [rbp+240h+phModule]
0x180121c4d  mov     [rsp+340h+var_308], rax
0x180121c52  lea     rax, [rsp+340h+var_2D0]
0x180121c57  mov     [rsp+340h+var_310], rax
0x180121c5c  lea     rax, [rsp+340h+var_2F0]
0x180121c61  mov     [rsp+340h+var_318], rax
0x180121c66  lea     rax, [rsp+340h+var_2D8]
0x180121c6b  mov     [rsp+340h+var_320], rax
0x180121c70  mov     [rsp+340h+var_2E0], r15
0x180121c75  mov     dword ptr [rbp+240h+phModule], 20Dh
0x180121c7c  mov     [rsp+340h+var_2D0], r12
0x180121c81  mov     dword ptr [rsp+340h+var_2F0], edi
0x180121c85  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180121c8a  test    rbx, rbx
0x180121c8d  jnz     short loc_180121D0C
0x180121c8f  mov     eax, cs:CallbackContext
0x180121c95  cmp     eax, r14d
0x180121c98  jbe     short loc_180121D0C
0x180121c9a  mov     eax, [rsi+80h]
0x180121ca0  lea     rdx, byte_1801CDFF7
0x180121ca7  mov     dword ptr [rsp+340h+var_2F0], eax
0x180121cab  lea     rax, aMSpendpointinf; "m_spEndpointInfo is invalid"
0x180121cb2  mov     [rsp+340h+var_2D0], rax
0x180121cb7  lea     rax, [rsp+340h+var_2F0]
0x180121cbc  mov     [rsp+340h+var_2F8], rax
0x180121cc1  lea     rax, [rsp+340h+var_2D8]
0x180121cc6  mov     [rsp+340h+var_300], rax
0x180121ccb  lea     rax, [rsp+340h+var_2E8]
0x180121cd0  mov     [rsp+340h+var_308], rax
0x180121cd5  lea     rax, [rsp+340h+var_2E0]
0x180121cda  mov     [rsp+340h+var_310], rax
0x180121cdf  lea     rax, [rbp+240h+phModule]
0x180121ce3  mov     [rsp+340h+var_318], rax
0x180121ce8  lea     rax, [rsp+340h+var_2D0]
0x180121ced  mov     [rsp+340h+var_320], rax
0x180121cf2  mov     [rsp+340h+var_2D8], r15
0x180121cf7  mov     dword ptr [rsp+340h+var_2E8], 211h
0x180121cff  mov     [rsp+340h+var_2E0], r12
0x180121d04  mov     dword ptr [rbp+240h+phModule], edi
0x180121d07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180121d0c  mov     rax, [rbp+240h+var_2A8]
0x180121d10  test    rax, rax
0x180121d13  jnz     loc_180121D9A
0x180121d19  mov     eax, cs:CallbackContext
0x180121d1f  cmp     eax, r14d
0x180121d22  jbe     short loc_180121D96
0x180121d24  mov     eax, [rsi+80h]
0x180121d2a  lea     rdx, word_1801CDCEE
0x180121d31  mov     dword ptr [rsp+340h+var_2F0], eax
0x180121d35  lea     rax, aMSpconnectionI; "m_spConnection is invalid"
0x180121d3c  mov     [rsp+340h+var_2D0], rax
0x180121d41  lea     rax, [rsp+340h+var_2F0]
0x180121d46  mov     [rsp+340h+var_2F8], rax
0x180121d4b  lea     rax, [rsp+340h+var_2D8]
0x180121d50  mov     [rsp+340h+var_300], rax
0x180121d55  lea     rax, [rsp+340h+var_2E8]
0x180121d5a  mov     [rsp+340h+var_308], rax
0x180121d5f  lea     rax, [rsp+340h+var_2E0]
0x180121d64  mov     [rsp+340h+var_310], rax
0x180121d69  lea     rax, [rbp+240h+phModule]
0x180121d6d  mov     [rsp+340h+var_318], rax
0x180121d72  lea     rax, [rsp+340h+var_2D0]
0x180121d77  mov     [rsp+340h+var_320], rax
0x180121d7c  mov     [rsp+340h+var_2D8], r15
0x180121d81  mov     dword ptr [rsp+340h+var_2E8], 215h
0x180121d89  mov     [rsp+340h+var_2E0], r12
0x180121d8e  mov     dword ptr [rbp+240h+phModule], edi
0x180121d91  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180121d96  mov     rax, [rbp+240h+var_2A8]
0x180121d9a  test    r13, r13
0x180121d9d  jnz     short loc_180121E16
0x180121d9f  mov     eax, cs:CallbackContext
0x180121da5  mov     ebx, edi
0x180121da7  cmp     eax, r14d
0x180121daa  jbe     loc_180121BE2
0x180121db0  lea     rax, aPworkerIsNull; "pWorker is NULL"
0x180121db7  mov     [rsp+340h+var_2E0], r15
0x180121dbc  mov     [rsp+340h+var_2D8], rax
0x180121dc1  lea     rdx, word_1801CDA6A
0x180121dc8  lea     rax, aErrorCondition; "Error condition failed"
0x180121dcf  mov     dword ptr [rsp+340h+var_2F0], 218h
0x180121dd7  mov     [rbp+240h+var_2A8], rax
0x180121ddb  lea     rax, [rsp+340h+var_2D8]
0x180121de0  mov     [rsp+340h+var_2F8], rax
0x180121de5  lea     rax, [rsp+340h+var_2E0]
0x180121dea  mov     [rsp+340h+var_300], rax
0x180121def  lea     rax, [rsp+340h+var_2F0]
0x180121df4  mov     [rsp+340h+var_308], rax
0x180121df9  lea     rax, [rsp+340h+var_2D0]
0x180121dfe  mov     [rsp+340h+var_310], rax
0x180121e03  lea     rax, [rsp+340h+var_2E8]
0x180121e08  mov     [rsp+340h+var_318], rax
0x180121e0d  lea     rax, [rbp+240h+var_2A8]
0x180121e11  jmp     loc_180121BCF
0x180121e16  test    rbx, rbx
0x180121e19  jnz     short loc_180121E92
0x180121e1b  mov     eax, cs:CallbackContext
0x180121e21  mov     ebx, edi
0x180121e23  cmp     eax, r14d
0x180121e26  jbe     loc_180121BE2
0x180121e2c  lea     rax, aPendpointinfoI; "pEndpointInfo is NULL"
0x180121e33  mov     [rsp+340h+var_2E0], r15
0x180121e38  mov     [rsp+340h+var_2D8], rax
0x180121e3d  lea     rdx, byte_1801CE1E3
0x180121e44  lea     rax, aErrorCondition; "Error condition failed"
0x180121e4b  mov     dword ptr [rsp+340h+var_2F0], 219h
0x180121e53  mov     [rbp+240h+var_2A8], rax
0x180121e57  lea     rax, [rsp+340h+var_2D8]
0x180121e5c  mov     [rsp+340h+var_2F8], rax
0x180121e61  lea     rax, [rsp+340h+var_2E0]
0x180121e66  mov     [rsp+340h+var_300], rax
0x180121e6b  lea     rax, [rsp+340h+var_2F0]
0x180121e70  mov     [rsp+340h+var_308], rax
0x180121e75  lea     rax, [rsp+340h+var_2D0]
0x180121e7a  mov     [rsp+340h+var_310], rax
0x180121e7f  lea     rax, [rsp+340h+var_2E8]
0x180121e84  mov     [rsp+340h+var_318], rax
0x180121e89  lea     rax, [rbp+240h+var_2A8]
0x180121e8d  jmp     loc_180121BCF
0x180121e92  test    rax, rax
0x180121e95  jnz     short loc_180121F0E
0x180121e97  mov     eax, cs:CallbackContext
0x180121e9d  mov     ebx, edi
0x180121e9f  cmp     eax, r14d
0x180121ea2  jbe     loc_180121BE2
0x180121ea8  lea     rax, aPsocketIsNull; "pSocket is NULL"
0x180121eaf  mov     [rsp+340h+var_2E0], r15
0x180121eb4  mov     [rsp+340h+var_2D8], rax
0x180121eb9  lea     rdx, byte_1801CF5C5
0x180121ec0  lea     rax, aErrorCondition; "Error condition failed"
0x180121ec7  mov     dword ptr [rsp+340h+var_2F0], 21Ah
0x180121ecf  mov     [rbp+240h+var_2A8], rax
0x180121ed3  lea     rax, [rsp+340h+var_2D8]
0x180121ed8  mov     [rsp+340h+var_2F8], rax
0x180121edd  lea     rax, [rsp+340h+var_2E0]
0x180121ee2  mov     [rsp+340h+var_300], rax
0x180121ee7  lea     rax, [rsp+340h+var_2F0]
0x180121eec  mov     [rsp+340h+var_308], rax
0x180121ef1  lea     rax, [rsp+340h+var_2D0]
0x180121ef6  mov     [rsp+340h+var_310], rax
0x180121efb  lea     rax, [rsp+340h+var_2E8]
0x180121f00  mov     [rsp+340h+var_318], rax
0x180121f05  lea     rax, [rbp+240h+var_2A8]
0x180121f09  jmp     loc_180121BCF
0x180121f0e  lea     rcx, [rsi+5Ch]; this
0x180121f12  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180121f17  lea     rbx, [rsi+30h]
0x180121f1b  cmp     r13, [rbx]
0x180121f1e  jz      short loc_180121F33
0x180121f20  mov     rcx, rbx; void *
0x180121f23  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180121f28  mov     rcx, rbx
0x180121f2b  mov     [rbx], r13
0x180121f2e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180121f33  mov     rdi, qword ptr [rbp+240h+var_2C0]
0x180121f37  lea     rbx, [rsi+40h]
0x180121f3b  cmp     rdi, [rbx]
0x180121f3e  jz      short loc_180121F53
0x180121f40  mov     rcx, rbx; void *
0x180121f43  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180121f48  mov     rcx, rbx
0x180121f4b  mov     [rbx], rdi
0x180121f4e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180121f53  mov     rdi, [rbp+240h+var_2A8]
0x180121f57  lea     rbx, [rsi+48h]
0x180121f5b  cmp     rdi, [rbx]
0x180121f5e  jz      short loc_180121F73
0x180121f60  mov     rcx, rbx; void *
0x180121f63  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180121f68  mov     rcx, rbx
0x180121f6b  mov     [rbx], rdi
0x180121f6e  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180121f73  lea     rcx, [rsi+5Ch]; this
0x180121f77  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180121f7c  mov     rdi, [rbp+240h+arg_20]
0x180121f83  lea     rcx, [rsi-40h]; this
0x180121f87  cmp     dword ptr [rdi+18h], 0
0x180121f8b  jz      short loc_180121FBD
0x180121f8d  call    ?CreateClientEventLogCallback@CRdpUdpStream@@IEAAJXZ; CRdpUdpStream::CreateClientEventLogCallback(void)
0x180121f92  mov     ebx, eax
0x180121f94  test    eax, eax
0x180121f96  jns     short loc_180122009
0x180121f98  mov     eax, cs:CallbackContext
0x180121f9e  cmp     eax, 4
0x180121fa1  jbe     short loc_180122007
0x180121fa3  mov     eax, [rsi+80h]
0x180121fa9  lea     rdx, word_1801CF182
0x180121fb0  mov     dword ptr [rsp+340h+var_2F0], eax
0x180121fb4  lea     rax, aUdpStreamFaile; "UDP stream failed to create client stat"...
0x180121fbb  jmp     short loc_180121FEB
0x180121fbd  call    ?CreateServerEventLogCallback@CRdpUdpStream@@IEAAJXZ; CRdpUdpStream::CreateServerEventLogCallback(void)
0x180121fc2  mov     ebx, eax
0x180121fc4  test    eax, eax
0x180121fc6  jns     short loc_180122009
0x180121fc8  mov     eax, cs:CallbackContext
0x180121fce  cmp     eax, 4
0x180121fd1  jbe     short loc_180122007
0x180121fd3  mov     eax, [rsi+80h]
0x180121fd9  lea     rdx, byte_1801CDBC5
0x180121fe0  mov     dword ptr [rsp+340h+var_2F0], eax
0x180121fe4  lea     rax, aUdpStreamFaile_0; "UDP stream failed to create server stat"...
0x180121feb  mov     qword ptr [rbp+240h+var_2C0], rax
0x180121fef  lea     rax, [rsp+340h+var_2F0]
0x180121ff4  mov     [rsp+340h+var_318], rax
0x180121ff9  lea     rax, [rbp+240h+var_2C0]
0x180121ffd  mov     [rsp+340h+var_320], rax
0x180122002  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180122007  xor     ebx, ebx
0x180122009  xor     r9d, r9d; lpName
0x18012200c  xor     r8d, r8d; bInitialState
0x18012200f  xor     edx, edx; bManualReset
0x180122011  xor     ecx, ecx; lpEventAttributes
0x180122013  call    cs:__imp_CreateEventW
0x180122019  xor     ecx, ecx; this
0x18012201b  mov     [rsi+180h], rax
0x180122022  test    rax, rax
0x180122025  jnz     loc_1801220C8
0x18012202b  call    cs:__imp_GetLastError
0x180122031  mov     ebx, eax
0x180122033  test    eax, eax
0x180122035  jle     short loc_180122040
0x180122037  movzx   ebx, ax
0x18012203a  or      ebx, 80070000h
0x180122040  mov     eax, cs:CallbackContext
0x180122046  cmp     eax, r14d
0x180122049  jbe     loc_180123037
  ... truncated ...
```
