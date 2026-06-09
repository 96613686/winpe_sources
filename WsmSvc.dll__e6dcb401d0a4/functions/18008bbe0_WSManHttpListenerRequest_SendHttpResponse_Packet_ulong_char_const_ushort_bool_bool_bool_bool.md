# WSManHttpListenerRequest::SendHttpResponse(Packet *,ulong,char const *,ushort,bool,bool,bool,bool)

- ea: `0x18008bbe0`
- end: `0x18008d166`
- name: `?SendHttpResponse@WSManHttpListenerRequest@@IEAAKPEAVPacket@@KPEBDG_N222@Z`
- size: `5510`
- prototype: `unsigned int __fastcall(WSManHttpListenerRequest *this, struct Packet *, __int64, const char *, unsigned __int16, bool, bool, char, bool)`
- caller_count: `3`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008a000`
- `0x18008a6b0`
- `0x18016f4cc`

## callees

- `0x180005d10`
- `0x18004d280`
- `0x18004e188`
- `0x18004e7e4`
- `0x18005c09c`
- `0x180071cdc`
- `0x180075e00`
- `0x180077514`
- `0x18007ec20`
- `0x180080470`
- `0x18008bbe0`
- `0x18008d16c`
- `0x18008db80`
- `0x18008ddb0`
- `0x1800b8294`
- `0x1800b850c`
- `0x1800c9420`
- `0x1800e43f4`
- `0x1800fb3e0`
- `0x180100448`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x180153858`
- `0x180170180`
- `0x1801ba152`
- `0x1801ba1b0`

## import_xrefs

- `msvcrt!_scprintf` at `0x18008c275`
- `msvcrt!_scprintf` at `0x18008c275`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008bdae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008bf87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c04c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c07e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008bdae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008bf87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c04c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008c07e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bc47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008bc47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bc69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008bc69`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008c2df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008ccb5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008c2df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008ccb5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18008c920`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18008d110`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18008c920`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18008d110`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008be04`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008c772`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008be04`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18008c772`
- `ntdll!EtwEventEnabled` at `0x18008bd9f`
- `ntdll!EtwEventEnabled` at `0x18008bd9f`
- `SspiCli!QueryContextAttributesW` at `0x18008c24f`
- `SspiCli!QueryContextAttributesW` at `0x18008c24f`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18008c7e8`
- `HTTPAPI!HttpSendResponseEntityBody` at `0x18008c7e8`
- `HTTPAPI!HttpSendHttpResponse` at `0x18008c0cb`
- `HTTPAPI!HttpSendHttpResponse` at `0x18008c0cb`

## string_xrefs

- `0x18008c06d`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18008c26e`: `OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\n`
- `0x18008bf13`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008c391`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008ca3f`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008caaf`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008cba4`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008cd92`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18008bfbd`: `application/soap+xml;charset=UTF-8`
- `0x18008cd44`: `application/soap+xml;charset=UTF-16`
- `0x18008cd6e`: `application/soap+xml;charset=UTF-16LE`
- `0x18008cd59`: `application/soap+xml;charset=UTF-16BE`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned int __fastcall WSManHttpListenerRequest::SendHttpResponse(
        WSManHttpListenerRequest *this,
        struct Packet *a2,
        __int64 a3,
        const char *a4,
        unsigned __int16 a5,
        bool a6,
        bool a7,
        char a8,
        bool a9)
{
  DWORD v11; // ecx
  DWORD v12; // ecx
  struct _HTTP_DATA_CHUNK *v13; // rsi
  __int64 v14; // rdi
  int v15; // r12d
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD LastError; // r14d
  bool v19; // r15
  __int64 v20; // rax
  int v21; // r14d
  __int64 v22; // rsi
  signed __int32 v23; // eax
  const wchar_t *v24; // r13
  int v25; // r9d
  volatile signed __int32 *v26; // rsi
  void *v27; // rcx
  ULONG v28; // edi
  int v29; // ecx
  int v31; // ecx
  const char *v32; // rax
  __int64 v33; // rcx
  int v34; // edx
  __int64 v35; // rcx
  const CHAR *v36; // rax
  int v37; // r8d
  const wchar_t *v38; // r8
  Packet *v39; // rcx
  int v40; // r15d
  __int64 v41; // rdx
  struct _SecHandle *v42; // r10
  const char *v43; // r9
  __int64 v44; // rdx
  LARGE_INTEGER v45; // rax
  unsigned int v46; // r15d
  unsigned int v47; // eax
  EncryptDecryptHelper *v48; // rcx
  char v49; // r8
  SECURITY_STATUS v50; // eax
  unsigned int v51; // ecx
  unsigned int v52; // edx
  int TotalEncryptedSizeInternalSsl; // eax
  PVOID *v54; // r9
  __int64 v55; // rcx
  const wchar_t *v56; // rax
  unsigned int v57; // edx
  LARGE_INTEGER v58; // r15
  _BYTE *v59; // r11
  unsigned __int8 *v60; // r8
  unsigned int v61; // r10d
  const CHAR *v62; // rdx
  unsigned int v63; // r9d
  unsigned int v64; // edx
  __int64 v65; // rax
  int v66; // ecx
  __int64 v67; // rdx
  int v68; // r8d
  __int64 v69; // rdx
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // edi
  __int64 v73; // rax
  const CHAR *v74; // r13
  Spinlock *v75; // r14
  void *v76; // rcx
  ULONG v77; // r8d
  unsigned int v78; // ecx
  char v79; // al
  _QWORD *v80; // rcx
  __int64 v81; // rdx
  int v82; // r9d
  const wchar_t *v83; // r8
  struct Packet *v84; // rax
  _QWORD *v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rdx
  __int64 v88; // r8
  int v89; // ecx
  struct Packet *v90; // rax
  unsigned int v91; // r15d
  signed __int64 v92; // rax
  int v93; // r15d
  unsigned int BytesSent; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *Reserved1; // [rsp+30h] [rbp-D0h]
  char v96[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v97; // [rsp+64h] [rbp-9Ch] BYREF
  char v98; // [rsp+68h] [rbp-98h]
  unsigned int v99; // [rsp+6Ch] [rbp-94h]
  unsigned int v100; // [rsp+70h] [rbp-90h] BYREF
  SECURITY_STATUS v101; // [rsp+74h] [rbp-8Ch] BYREF
  LARGE_INTEGER v102; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v103; // [rsp+80h] [rbp-80h] BYREF
  int v104; // [rsp+84h] [rbp-7Ch]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-78h] BYREF
  signed __int64 v106; // [rsp+90h] [rbp-70h]
  const CHAR *v107; // [rsp+98h] [rbp-68h]
  const CHAR *v108; // [rsp+A0h] [rbp-60h]
  char *v109; // [rsp+A8h] [rbp-58h]
  struct _SecHandle *v110; // [rsp+B0h] [rbp-50h]
  void **v111; // [rsp+C0h] [rbp-40h] BYREF
  signed __int32 v112[4]; // [rsp+C8h] [rbp-38h] BYREF
  char v113; // [rsp+D8h] [rbp-28h]
  const wchar_t *v114; // [rsp+E0h] [rbp-20h]
  const wchar_t *v115; // [rsp+E8h] [rbp-18h]
  const wchar_t *v116; // [rsp+F0h] [rbp-10h]
  const wchar_t *v117; // [rsp+F8h] [rbp-8h]
  __int128 pBuffer; // [rsp+100h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 350, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  if ( !*((_QWORD *)this + 27) )
  {
    WSManHttpListenerRequest::NotifyReplySentCallback(this, 0xEu);
    return 14;
  }
  v11 = *((_DWORD *)this + 1332);
  if ( v11 )
  {
    SetLastError(v11);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      0x3Bu,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 5336));
  }
  *((_BYTE *)this + 5315) = 1;
  v12 = *((_DWORD *)this + 1332);
  if ( v12 )
    SetLastError(v12);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5336));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 351, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, a5);
  if ( *((_BYTE *)this + 24) )
  {
    *((_BYTE *)this + 24) = 0;
    v39 = (Packet *)*((_QWORD *)this + 2);
    if ( v39 )
      Packet::Recycle(v39);
  }
  *((_QWORD *)this + 2) = a2;
  *((_BYTE *)this + 24) = a9;
  if ( *((_BYTE *)this + 4600) != a7 && !*((_BYTE *)this + 4601) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1AB6u, L"6838", 0x54Fu, 0);
  *((_BYTE *)this + 4600) = a7;
  *((_BYTE *)this + 4602) = a8;
  v13 = (struct _HTTP_DATA_CHUNK *)((char *)this + 224);
  v14 = *((_QWORD *)this + 27);
  memset_0((void *)v14, 0, 0x238u);
  v15 = 1;
  *(_DWORD *)(v14 + 4) = 65537;
  *(_WORD *)(v14 + 8) = a5;
  if ( !*((_BYTE *)this + 4600) )
  {
LABEL_11:
    v16 = *((_QWORD *)this + 33);
    if ( v16 && a5 == 200 )
    {
      *(_QWORD *)(v14 + 528) = v16;
      *(_WORD *)(v14 + 520) = *((_WORD *)this + 136);
    }
    v17 = *((_QWORD *)this + 2);
    if ( !v17 )
    {
      LastError = GetLastError();
      v112[0] = 0;
      v111 = &CErrorContext::`vftable';
      v112[2] = 0;
      v112[3] = -1;
      v114 = &Class;
      v115 = &Class;
      v116 = &Class;
      v117 = &Class;
      v113 = 0;
      _InterlockedIncrement(v112);
      if ( !g_eventHandler )
        ILoader<WSMan::EventHandler>::CreateInstance(&g_eventHandler, &v111);
      if ( g_eventHandler )
      {
        if ( *(_QWORD *)g_eventHandler )
        {
          v19 = (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_eventHandler, &LOG_WSMAN_AN_SOAP_LISTENER_SENDING) != 0;
        }
        else
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmaneventhandler.cpp", 0x284u, L"644", 0x54Fu, 0);
          v19 = 0;
        }
        SetLastError(LastError);
        v111 = &ILifeTimeMgmt::`vftable';
        if ( v19 )
          WSMan::EventHandler::WriteSoapW(&LOG_WSMAN_AN_SOAP_LISTENER_SENDING, &Class, 0);
      }
      else
      {
        SetLastError(LastError);
        v111 = &ILifeTimeMgmt::`vftable';
      }
LABEL_20:
      if ( *((_BYTE *)this + 4600) && *((_BYTE *)this + 4601) )
      {
        *(_QWORD *)(v14 + 160) = "chunked";
        *(_WORD *)(v14 + 152) = 7;
        *(_WORD *)(v14 + 536) = 0;
        *(_QWORD *)(v14 + 544) = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          365,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          (LARGE_INTEGER)PerformanceCount.QuadPart,
          this);
      }
      v20 = *((_QWORD *)this + 14);
      if ( !v20 || (v21 = 1, !*(_BYTE *)(v20 + 289)) )
        v21 = 0;
      StartThreadpoolIo(*((PTP_IO *)this + 13));
      v22 = *((_QWORD *)this + 11);
      v101 = 0;
      while ( 1 )
      {
        v23 = *(_DWORD *)v22;
        v24 = L"true";
        if ( *(_DWORD *)(v22 + 8) != *(_DWORD *)(v22 + 4) || v23 < 0 )
          break;
        v25 = v23 + 1;
        if ( v23 == _InterlockedCompareExchange((volatile signed __int32 *)v22, v23 + 1, v23) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
          {
            v38 = L"true";
            if ( v25 >= 0 )
              v38 = L"false";
            WPP_SF_qLS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)WPP_9896aa7138543c0bf89dc30a450bb385_Traceguids,
              v22,
              v25,
              (__int64)v38);
          }
          goto LABEL_29;
        }
      }
      v102.QuadPart = 0;
      do
      {
        v106 = *(_QWORD *)(v22 + 8);
        v102.LowPart = v106 + 1;
        v102.HighPart = HIDWORD(v106);
        v92 = _InterlockedCompareExchange64((volatile signed __int64 *)(v22 + 8), v102.QuadPart, v106);
      }
      while ( v92 != v106 );
      v93 = HIDWORD(v106);
      while ( *(_DWORD *)(v22 + 4) - v93 < 0 || *(int *)v22 < 0 )
        Wait(&v101);
      v82 = _InterlockedIncrement((volatile signed __int32 *)v22);
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 4));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      {
        v83 = L"true";
        if ( v82 >= 0 )
          v83 = L"false";
        WPP_SF_qLS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_9896aa7138543c0bf89dc30a450bb385_Traceguids,
          v22,
          v82,
          (__int64)v83);
      }
LABEL_29:
      v26 = (volatile signed __int32 *)*((_QWORD *)this + 11);
      v27 = (void *)**((_QWORD **)this + 12);
      if ( v27 )
      {
        if ( !v21 )
          v15 = *((_BYTE *)this + 4600) != 0 ? 2 : 0;
        v28 = HttpSendHttpResponse(
                v27,
                *(_QWORD *)(*((_QWORD *)this + 19) + 16LL),
                v15,
                (PHTTP_RESPONSE)v14,
                0,
                0,
                0,
                0,
                (LPOVERLAPPED)((char *)this + 40),
                0);
      }
      else
      {
        v28 = 1115;
      }
      if ( (*v26 & 0x7FFFFFFF) != 0 )
      {
        if ( *v26 == -2147483647 || (v29 = _InterlockedDecrement(v26), v29 == 0x80000000) )
        {
          *v26 = 0;
          v29 = 0;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
        {
          if ( v29 >= 0 )
            v24 = L"false";
          WPP_SF_qLS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_9896aa7138543c0bf89dc30a450bb385_Traceguids,
            (_DWORD)v26,
            v29,
            (__int64)v24);
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\pool.cpp", 0x73u, L"115", 0x54Fu, 0);
      }
      if ( v28 == 997 )
        return 0;
      if ( !v28 )
        return v28;
      CancelThreadpoolIo(*((PTP_IO *)this + 13));
      v80 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v81 = 366;
        goto LABEL_249;
      }
      goto LABEL_250;
    }
    if ( !*(_QWORD *)(v17 + 40) || *(_DWORD *)(v17 + 48) <= 1u )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1B74u, L"7028", 0x54Fu, 0);
      return WSManHttpListenerRequest::SendHttpError(
               this,
               0x1F4u,
               0,
               0,
               0,
               0xDu,
               L"Response packet size is too small",
               &Class);
    }
    v31 = *((_DWORD *)this + 30);
    if ( v31 == 3 )
    {
      *(_WORD *)(v14 + 248) = 34;
      v32 = "application/soap+xml;charset=UTF-8";
      goto LABEL_47;
    }
    if ( v31 )
    {
      v89 = v31 - 1;
      if ( v89 )
      {
        if ( v89 != 1 )
        {
          v56 = L"Cannot send a response in ISO_8859_1 format";
          goto LABEL_95;
        }
        *(_WORD *)(v14 + 248) = 35;
        v32 = "application/soap+xml;charset=UTF-16";
      }
      else
      {
        *(_WORD *)(v14 + 248) = 37;
        v32 = "application/soap+xml;charset=UTF-16BE";
      }
    }
    else
    {
      *(_WORD *)(v14 + 248) = 37;
      v32 = "application/soap+xml;charset=UTF-16LE";
    }
LABEL_47:
    *(_QWORD *)(v14 + 256) = v32;
    v33 = *((_QWORD *)this + 14);
    if ( !v33
      || ((v34 = *(_DWORD *)(v33 + 72), (unsigned int)(v34 - 3) > 1) || (*(_BYTE *)(v33 + 100) & 0x10) == 0) && v34 != 6
      || !*((_BYTE *)this + 256) )
    {
LABEL_50:
      if ( !*((_BYTE *)this + 4600) )
      {
LABEL_51:
        v13->DataChunkType = HttpDataChunkFromMemory;
        v35 = *((_QWORD *)this + 2);
        v36 = *(const CHAR **)(v35 + 40);
        if ( v36 )
        {
          v37 = *(_DWORD *)(v35 + 48);
        }
        else
        {
          v36 = Buf1;
          v37 = 0;
        }
        *((_QWORD *)this + 29) = v36;
        *((_DWORD *)this + 60) = v37;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            363,
            &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
            this,
            v37);
        *(_WORD *)(v14 + 536) = 1;
        *(_QWORD *)(v14 + 544) = v13;
        goto LABEL_20;
      }
      if ( !*((_BYTE *)this + 24) )
      {
        v90 = Packet::Clone(*((Packet **)this + 2), 0);
        *((_QWORD *)this + 2) = v90;
        if ( !v90 )
        {
          v85 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
            goto LABEL_186;
          v86 = 361;
LABEL_185:
          WPP_SF_(v85[2], v86, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
LABEL_186:
          Reserved1 = L"Failed to clone the response packet";
          BytesSent = 14;
          return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
        }
        *((_BYTE *)this + 24) = 1;
      }
      v91 = PrepareChunk(a8, (struct Packet **)this + 2);
      if ( !v91 )
        goto LABEL_51;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 362, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v91);
      Reserved1 = L"Failed to prepare the chunk from the response packet";
      BytesSent = v91;
      return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
    }
    v40 = 1359;
    if ( *(_DWORD *)(v33 + 180) == 3 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1BA6u, L"7078", 0x54Fu, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 360, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    v41 = *((_QWORD *)this + 14);
    v42 = (struct _SecHandle *)(v41 + 80);
    v110 = (struct _SecHandle *)(v41 + 80);
    if ( v41 == -80 )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x1305u, L"4869", 0x54Fu, 0);
    }
    else
    {
      v43 = (const char *)*((_QWORD *)&PacketFormatter::CHARSETS + 3 * *((int *)this + 30));
      v102.QuadPart = (LONGLONG)v43;
      if ( v43 )
      {
        v44 = *(int *)(v41 + 180);
        v103 = v44;
        v109 = (&off_18027B0B8)[15 * v44];
        if ( v109 )
        {
          v45 = *(LARGE_INTEGER *)((char *)this + 16);
          PerformanceCount = v45;
          v46 = 0;
          v100 = 0;
          if ( *(_QWORD *)(v45.QuadPart + 40) )
            v47 = *(_DWORD *)(v45.QuadPart + 48);
          else
            v47 = 0;
          v99 = v47;
          if ( (int)v44 >= 3 )
          {
            WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x12ECu, L"4844", 0x54Fu, 0);
            TotalEncryptedSizeInternalSsl = 1359;
          }
          else
          {
            v48 = (EncryptDecryptHelper *)LODWORD(qword_18027B0C0[15 * v44]);
            v104 = qword_18027B0C0[15 * v44];
            v49 = *((_BYTE *)this + 4600);
            v96[0] = v49;
            if ( (_DWORD)v44 == 2 )
            {
              TotalEncryptedSizeInternalSsl = EncryptDecryptHelper::GetTotalEncryptedSizeInternalSsl(
                                                v48,
                                                v42,
                                                v47,
                                                v43,
                                                v49,
                                                (unsigned int)v48,
                                                0x12u,
                                                &v100);
              v46 = v100;
            }
            else
            {
              pBuffer = 0;
              v50 = QueryContextAttributesW(v42, 0, &pBuffer);
              v101 = v50;
              if ( v50 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    124,
                    &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
                    (unsigned int)v50);
                  v50 = v101;
                }
                TotalEncryptedSizeInternalSsl = SecurityStatusToWin32(v50);
              }
              else
              {
                v51 = _scprintf(
                        "OriginalContent: type=application/soap+xml;charset=%s;Length=%lu\r\n",
                        (const char *)v102.QuadPart,
                        v99)
                    + v104
                    + 135;
                v52 = v51 + HIDWORD(pBuffer);
                if ( v51 + HIDWORD(pBuffer) >= v51 )
                {
                  v46 = -1;
                  if ( v99 + v52 >= v52 )
                    v46 = v99 + v52;
                  TotalEncryptedSizeInternalSsl = v99 + v52 < v52 ? 0x216 : 0;
                }
                else
                {
                  TotalEncryptedSizeInternalSsl = 534;
                  v46 = -1;
                }
              }
            }
            if ( !TotalEncryptedSizeInternalSsl )
            {
              *(_QWORD *)&pBuffer = 0;
              v57 = v46;
              v58 = PerformanceCount;
              TotalEncryptedSizeInternalSsl = PacketPool::GetPacket(
                                                *(PacketPool **)(PerformanceCount.QuadPart + 24),
                                                v57,
                                                (struct Packet **)&pBuffer);
              if ( !TotalEncryptedSizeInternalSsl )
              {
                v59 = (char *)this + 4560;
                v60 = *(unsigned __int8 **)(v58.QuadPart + 40);
                v107 = (const CHAR *)v60;
                if ( v60 )
                {
                  v61 = *(_DWORD *)(v58.QuadPart + 48);
                }
                else
                {
                  v60 = (unsigned __int8 *)Buf1;
                  v107 = Buf1;
                  v61 = 0;
                }
                v100 = v61;
                PerformanceCount.QuadPart = pBuffer;
                v62 = *(const CHAR **)(pBuffer + 40);
                v108 = v62;
                if ( v62 )
                {
                  v63 = *(_DWORD *)(pBuffer + 48);
                }
                else
                {
                  v62 = Buf1;
                  v108 = Buf1;
                  v63 = 0;
                }
                v99 = v63;
                v97 = 0;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                {
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    134,
                    &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
                    (char *)this + 4560);
                  v62 = v108;
                  v60 = (unsigned __int8 *)v107;
                  v63 = v99;
                  v61 = v100;
                  v59 = (char *)this + 4560;
                }
                if ( v103 == 2 && (v96[0] || v61 > 0x4000) )
                {
                  v96[0] = 1;
                  v97 = 0;
                  v103 = 0;
                  while ( 1 )
                  {
                    if ( v61 >= 0x4000 )
                    {
                      v78 = 0x4000;
                      v100 = v61 - 0x4000;
                      v79 = v61 == 0x4000;
                    }
                    else
                    {
                      v78 = v61;
                      v79 = 1;
                    }
                    v98 = v79;
                    v101 = v78;
                    v40 = EncryptDecryptHelper::DoPartEncryption(
                            v59,
                            v110,
                            v78,
                            v60,
                            (LARGE_INTEGER)v102.QuadPart,
                            v109,
                            v104,
                            2,
                            v79,
                            v63,
                            v62,
                            &v103);
                    if ( v40 )
                      break;
                    v64 = v103 + v97;
                    v97 += v103;
                    if ( v98 )
                      goto LABEL_111;
                    v60 = (unsigned __int8 *)&v107[v101];
                    v107 = (const CHAR *)v60;
                    v63 = v99 - v103;
                    v99 -= v103;
                    v62 = &v108[v103];
                    v108 = v62;
                    v61 = v100;
                    v59 = (char *)this + 4560;
                  }
                }
                else
                {
                  v40 = EncryptDecryptHelper::DoPartEncryption(
                          v59,
                          v110,
                          v61,
                          v60,
                          (LARGE_INTEGER)v102.QuadPart,
                          v109,
                          v104,
                          v103,
                          1,
                          v63,
                          v62,
                          &v97);
                  v96[0] = 0;
                  if ( !v40 )
                  {
                    v64 = v97;
LABEL_111:
                    v40 = Packet::Reallocate((Packet *)pBuffer, v64, 0);
                    if ( !v40 )
                    {
LABEL_112:
                      if ( !v40 )
                      {
                        CRemoteListenerRequest::RemoveResponsePacket(this);
                        *((_BYTE *)this + 24) = 1;
                        *((LARGE_INTEGER *)this + 2) = PerformanceCount;
                        v65 = 15LL * *(int *)(*((_QWORD *)this + 14) + 180LL);
                        if ( v96[0] )
                        {
                          *(_QWORD *)(v14 + 256) = qword_18027B100[v65 + 1];
                          v66 = qword_18027B100[15 * *(int *)(*((_QWORD *)this + 14) + 180LL) + 2];
                        }
                        else
                        {
                          *(_QWORD *)(v14 + 256) = (&off_18027B0E8)[v65];
                          v66 = qword_18027B0F0[15 * *(int *)(*((_QWORD *)this + 14) + 180LL)];
                        }
                        *(_WORD *)(v14 + 248) = v66;
                        goto LABEL_50;
                      }
                      goto LABEL_121;
                    }
                  }
                }
                Packet::Recycle((Packet *)pBuffer);
                PerformanceCount.QuadPart = 0;
                goto LABEL_112;
              }
            }
          }
          v40 = TotalEncryptedSizeInternalSsl;
        }
        else
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x1307u, L"4871", 0x54Fu, 0);
          v40 = 1359;
        }
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x1306u, L"4870", 0x54Fu, 0);
        v40 = 1359;
      }
    }
LABEL_121:
    Reserved1 = L"Failed to encrypt response packet";
    BytesSent = v40;
    return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
  }
  if ( a5 != 200 )
  {
    v54 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_89;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 353, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  }
  v54 = (PVOID *)WPP_GLOBAL_Control;
LABEL_89:
  if ( *((_BYTE *)this + 4601) )
    goto LABEL_11;
  if ( *((_DWORD *)this + 71) != 8 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1ADCu, L"6876", 0x54Fu, 0);
    v54 = (PVOID *)WPP_GLOBAL_Control;
  }
  v55 = *((_QWORD *)this + 2);
  if ( v55 )
  {
    if ( !*(_QWORD *)(v55 + 40) || *(_DWORD *)(v55 + 48) <= 1u )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1AE7u, L"6887", 0x54Fu, 0);
      v56 = L"Response packet size is too small";
LABEL_95:
      Reserved1 = v56;
      BytesSent = 13;
      return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
    }
    v67 = *((_QWORD *)this + 14);
    if ( v67
      && ((v68 = *(_DWORD *)(v67 + 72), (unsigned int)(v68 - 3) <= 1) && (*(_BYTE *)(v67 + 100) & 0x10) != 0 || v68 == 6)
      && *((_BYTE *)this + 256) )
    {
      if ( *(_DWORD *)(v67 + 180) == 3 )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1AF5u, L"6901", 0x54Fu, 0);
        v54 = (PVOID *)WPP_GLOBAL_Control;
      }
      v96[0] = 0;
      v102.QuadPart = 0;
      if ( v54 != &WPP_GLOBAL_Control && (*((_DWORD *)v54 + 7) & 0x400) != 0 )
        WPP_SF_(v54[2], 354, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      v69 = *((_QWORD *)this + 14);
      v70 = EncryptDecryptHelper::DoEncryption(
              (char *)this + 4560,
              v69 + 80,
              *((_QWORD *)this + 2),
              &v102,
              *((_QWORD *)&PacketFormatter::CHARSETS + 3 * *((int *)this + 30)),
              *((_BYTE *)this + 4600),
              (&off_18027B0B8)[15 * *(int *)(v69 + 180)],
              qword_18027B0C0[15 * *(int *)(v69 + 180)],
              *(_DWORD *)(v69 + 180),
              v96);
      if ( v70 )
      {
        Reserved1 = L"Failed to encrypt response packet";
        BytesSent = v70;
        return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
      }
      CRemoteListenerRequest::RemoveResponsePacket(this);
      *((_BYTE *)this + 24) = 1;
      *((LARGE_INTEGER *)this + 2) = v102;
    }
    else if ( !*((_BYTE *)this + 24) )
    {
      v84 = Packet::Clone((Packet *)v55, 0);
      *((_QWORD *)this + 2) = v84;
      if ( !v84 )
      {
        v85 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_186;
        v86 = 355;
        goto LABEL_185;
      }
      *((_BYTE *)this + 24) = 1;
    }
    v71 = PrepareChunk(a8, (struct Packet **)this + 2);
    v72 = v71;
    if ( v71 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 356, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v71);
      Reserved1 = L"Failed to prepare the chunk from the response packet";
      BytesSent = v72;
      return WSManHttpListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0, BytesSent, Reserved1, &Class);
    }
    v13->DataChunkType = HttpDataChunkFromMemory;
    v73 = *((_QWORD *)this + 2);
    v74 = *(const CHAR **)(v73 + 40);
    if ( v74 )
      v72 = *(_DWORD *)(v73 + 48);
    else
      v74 = Buf1;
    *((_QWORD *)this + 29) = v74;
    *((_DWORD *)this + 60) = v72;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v102.QuadPart = 0;
      QueryPerformanceCounter(&v102);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_Iqd)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v87,
        v88,
        (LARGE_INTEGER)v102.QuadPart,
        this,
        v72);
    }
LABEL_138:
    StartThreadpoolIo(*((PTP_IO *)this + 13));
    Spinlock::SharedAcquire(*((Spinlock **)this + 11));
    v75 = (Spinlock *)*((_QWORD *)this + 11);
    v76 = (void *)**((_QWORD **)this + 12);
    if ( v76 )
    {
      v77 = 0;
      if ( !*((_BYTE *)this + 4602) )
        v77 = 2;
      v28 = HttpSendResponseEntityBody(
              v76,
              *(_QWORD *)(*((_QWORD *)this + 19) + 16LL),
              v77,
              v15,
              v13,
              0,
              0,
              0,
              (LPOVERLAPPED)((char *)this + 40),
              0);
      Spinlock::Release(v75);
      if ( v28 == 997 )
        return 0;
      if ( !v28 )
        return v28;
    }
    else
    {
      v28 = 1115;
      Spinlock::Release(*((Spinlock **)this + 11));
    }
    CancelThreadpoolIo(*((PTP_IO *)this + 13));
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v81 = 358;
LABEL_249:
      WPP_SF_d(v80[2], v81, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v28);
    }
LABEL_250:
    WSManHttpListenerRequest::NotifyReplySentCallback(this, v28);
    WSManHttpListenerRequest::Finished(this, 0, 0);
    return v28;
  }
  if ( *((_BYTE *)this + 4602) )
  {
    v13 = 0;
    LOWORD(v15) = 0;
    goto LABEL_138;
  }
  if ( v54 != &WPP_GLOBAL_Control && (*((_DWORD *)v54 + 7) & 0x400) != 0 )
    WPP_SF_(v54[2], 359, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  WSManHttpListenerRequest::NotifyReplySentCallback(this, 0x57u);
  WSManHttpListenerRequest::Finished(this, 0x57u, 0);
  return 87;
}

```

## disassembly

```asm
0x18008bbe0  push    rbp
0x18008bbe2  push    rbx
0x18008bbe3  push    rsi
0x18008bbe4  push    rdi
0x18008bbe5  push    r12
0x18008bbe7  push    r13
0x18008bbe9  push    r14
0x18008bbeb  push    r15
0x18008bbed  lea     rbp, [rsp-28h]
0x18008bbf2  sub     rsp, 128h
0x18008bbf9  mov     rax, cs:__security_cookie
0x18008bc00  xor     rax, rsp
0x18008bc03  mov     [rbp+60h+var_50], rax
0x18008bc07  mov     rsi, rdx
0x18008bc0a  mov     rbx, rcx
0x18008bc0d  lea     r14, WPP_GLOBAL_Control
0x18008bc14  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc1b  cmp     rcx, r14
0x18008bc1e  jnz     loc_18008C2A3
0x18008bc24  cmp     qword ptr [rbx+0D8h], 0
0x18008bc2c  jz      loc_18008C9D6
0x18008bc32  mov     ecx, [rbx+14D0h]; dwErrCode
0x18008bc38  test    ecx, ecx
0x18008bc3a  jnz     loc_18008C04C
0x18008bc40  lea     rcx, [rbx+14D8h]; lpCriticalSection
0x18008bc47  call    cs:__imp_EnterCriticalSection
0x18008bc4d  mov     byte ptr [rbx+14C3h], 1
0x18008bc54  mov     ecx, [rbx+14D0h]; dwErrCode
0x18008bc5a  test    ecx, ecx
0x18008bc5c  jnz     loc_18008C07E
0x18008bc62  lea     rcx, [rbx+14D8h]; lpCriticalSection
0x18008bc69  call    cs:__imp_LeaveCriticalSection
0x18008bc6f  movzx   r15d, [rbp+60h+arg_20]
0x18008bc77  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc7e  cmp     rcx, r14
0x18008bc81  jnz     loc_18008C9ED
0x18008bc87  cmp     byte ptr [rbx+18h], 0
0x18008bc8b  jnz     loc_18008C13C
0x18008bc91  mov     [rbx+10h], rsi
0x18008bc95  movzx   eax, [rbp+60h+arg_40]
0x18008bc9c  mov     [rbx+18h], al
0x18008bc9f  movzx   edi, [rbp+60h+arg_30]
0x18008bca6  cmp     [rbx+11F8h], dil
0x18008bcad  jnz     loc_18008CA17
0x18008bcb3  mov     [rbx+11F8h], dil
0x18008bcba  movzx   r13d, [rbp+60h+arg_38]
0x18008bcc2  mov     [rbx+11FAh], r13b
0x18008bcc9  lea     rsi, [rbx+0E0h]
0x18008bcd0  mov     rdi, [rbx+0D8h]
0x18008bcd7  xor     edx, edx; Val
0x18008bcd9  mov     r8d, 238h; Size
0x18008bcdf  mov     rcx, rdi; void *
0x18008bce2  call    memset_0
0x18008bce7  mov     r12d, 1
0x18008bced  mov     dword ptr [rdi+4], 10001h
0x18008bcf4  mov     [rdi+8], r15w
0x18008bcf9  mov     ecx, 0C8h
0x18008bcfe  cmp     byte ptr [rbx+11F8h], 0
0x18008bd05  jnz     loc_18008C32C
0x18008bd0b  mov     rax, [rbx+108h]
0x18008bd12  test    rax, rax
0x18008bd15  jnz     loc_18008CCFD
0x18008bd1b  mov     rax, [rbx+10h]
0x18008bd1f  test    rax, rax
0x18008bd22  jnz     loc_18008BEEF
0x18008bd28  call    cs:__imp_GetLastError
0x18008bd2e  mov     r14d, eax
0x18008bd31  xor     edx, edx
0x18008bd33  mov     [rbp+60h+var_98], edx
0x18008bd36  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x18008bd3d  mov     [rbp+60h+var_A0], rax
0x18008bd41  mov     [rbp+60h+var_90], edx
0x18008bd44  mov     r15d, 0FFFFFFFFh
0x18008bd4a  mov     [rbp+60h+var_8C], r15d
0x18008bd4e  lea     rsi, Class
0x18008bd55  mov     [rbp+60h+var_80], rsi
0x18008bd59  mov     [rbp+60h+var_78], rsi
0x18008bd5d  mov     [rbp+60h+var_70], rsi
0x18008bd61  mov     [rbp+60h+var_68], rsi
0x18008bd65  mov     [rbp+60h+var_88], dl
0x18008bd68  lock inc [rbp+60h+var_98]
0x18008bd6c  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18008bd73  test    rax, rax
0x18008bd76  jz      loc_18008C905
0x18008bd7c  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18008bd83  test    rax, rax
0x18008bd86  jz      loc_18008BF84
0x18008bd8c  mov     rcx, [rax]
0x18008bd8f  test    rcx, rcx
0x18008bd92  jz      loc_18008C5F7
0x18008bd98  lea     rdx, LOG_WSMAN_AN_SOAP_LISTENER_SENDING
0x18008bd9f  call    cs:__imp_EtwEventEnabled
0x18008bda5  test    al, al
0x18008bda7  setnz   r15b
0x18008bdab  mov     ecx, r14d; dwErrCode
0x18008bdae  call    cs:__imp_SetLastError
0x18008bdb4  nop
0x18008bdb5  lea     rax, ??_7ILifeTimeMgmt@@6B@; const ILifeTimeMgmt::`vftable'
0x18008bdbc  mov     [rbp+60h+var_A0], rax
0x18008bdc0  test    r15b, r15b
0x18008bdc3  jnz     loc_18008D018
0x18008bdc9  xor     r15d, r15d
0x18008bdcc  lea     rdx, WPP_GLOBAL_Control
0x18008bdd3  cmp     byte ptr [rbx+11F8h], 0
0x18008bdda  jnz     loc_18008D02F
0x18008bde0  mov     rax, cs:WPP_GLOBAL_Control
0x18008bde7  cmp     rax, rdx
0x18008bdea  jnz     loc_18008C2CD
0x18008bdf0  mov     rax, [rbx+70h]
0x18008bdf4  test    rax, rax
0x18008bdf7  jnz     loc_18008D067
0x18008bdfd  mov     r14d, r15d
0x18008be00  mov     rcx, [rbx+68h]; pio
0x18008be04  call    cs:__imp_StartThreadpoolIo
0x18008be0a  mov     rsi, [rbx+58h]
0x18008be0e  mov     [rsp+160h+var_EC], r15d
0x18008be13  mov     eax, [rsi]
0x18008be15  mov     edx, [rsi+4]
0x18008be18  mov     ecx, [rsi+8]
0x18008be1b  lea     r11, aFalse; "false"
0x18008be22  lea     r13, aTrue; "true"
0x18008be29  cmp     ecx, edx
0x18008be2b  jnz     loc_18008D07C
0x18008be31  test    eax, eax
0x18008be33  js      loc_18008D07C
0x18008be39  lea     r9d, [rax+1]
0x18008be3d  lock cmpxchg [rsi], r9d
0x18008be42  jnz     short loc_18008BE13
0x18008be44  mov     rcx, cs:WPP_GLOBAL_Control
0x18008be4b  lea     rdx, WPP_GLOBAL_Control
0x18008be52  cmp     rcx, rdx
0x18008be55  jnz     loc_18008C0E6
0x18008be5b  mov     rsi, [rbx+58h]
0x18008be5f  mov     rax, [rbx+60h]
0x18008be63  mov     rcx, [rax]; RequestQueueHandle
0x18008be66  test    rcx, rcx
0x18008be69  jnz     loc_18008C08F
0x18008be6f  mov     edi, 45Bh
0x18008be74  mov     ecx, [rsi]
0x18008be76  test    ecx, 7FFFFFFFh
0x18008be7c  jbe     loc_18008BF5C
0x18008be82  mov     eax, [rsi]
0x18008be84  cmp     eax, 80000001h
0x18008be89  jz      short loc_18008BE9E
0x18008be8b  mov     ecx, 0FFFFFFFFh
0x18008be90  lock xadd [rsi], ecx
0x18008be94  dec     ecx
0x18008be96  cmp     ecx, 80000000h
0x18008be9c  jnz     short loc_18008BEA4
0x18008be9e  mov     [rsi], r15d
0x18008bea1  mov     ecx, r15d
0x18008bea4  mov     r10, cs:WPP_GLOBAL_Control
0x18008beab  cmp     r10, rdx
0x18008beae  jz      short loc_18008BEBE
0x18008beb0  test    dword ptr [r10+1Ch], 1000000h
0x18008beb8  jnz     loc_18008D0CF
0x18008bebe  cmp     edi, 3E5h
0x18008bec4  jnz     loc_18008D104
0x18008beca  mov     edi, r15d
0x18008becd  mov     eax, edi
0x18008becf  mov     rcx, [rbp+60h+var_50]
0x18008bed3  xor     rcx, rsp; StackCookie
0x18008bed6  call    __security_check_cookie
0x18008bedb  add     rsp, 128h
0x18008bee2  pop     r15
0x18008bee4  pop     r14
0x18008bee6  pop     r13
0x18008bee8  pop     r12
0x18008beea  pop     rdi
0x18008beeb  pop     rsi
0x18008beec  pop     rbx
0x18008beed  pop     rbp
0x18008beee  retn
0x18008beef  cmp     qword ptr [rax+28h], 0
0x18008bef4  jnz     loc_18008BF9E
0x18008befa  xor     edi, edi
0x18008befc  mov     [rsp+160h+CachePolicy], rdi; struct IRequestContext *
0x18008bf01  mov     r9d, 54Fh; unsigned int
0x18008bf07  lea     r8, a7028; "7028"
0x18008bf0e  mov     edx, 1B74h; unsigned int
0x18008bf13  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18008bf1a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18008bf1f  lea     rsi, Class
0x18008bf26  mov     qword ptr [rsp+160h+Reserved2], rsi; unsigned __int16 *
0x18008bf2b  lea     rax, aResponsePacket; "Response packet size is too small"
0x18008bf32  mov     [rsp+160h+Reserved1], rax; unsigned __int16 *
0x18008bf37  mov     dword ptr [rsp+160h+BytesSent], 0Dh; unsigned int
0x18008bf3f  mov     [rsp+160h+CachePolicy], rdi; char *
0x18008bf44  mov     edx, 1F4h; unsigned __int16
0x18008bf49  xor     r9d, r9d; unsigned int
0x18008bf4c  xor     r8d, r8d; bool
0x18008bf4f  mov     rcx, rbx; this
0x18008bf52  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x18008bf57  jmp     loc_18008BECF
0x18008bf5c  mov     [rsp+160h+CachePolicy], r15; struct IRequestContext *
0x18008bf61  mov     r9d, 54Fh; unsigned int
0x18008bf67  lea     r8, a115; "115"
0x18008bf6e  mov     edx, 73h ; 's'; unsigned int
0x18008bf73  lea     rcx, aOnecoreAdminWm_130; "onecore\\admin\\wmi\\wmx\\stdlib\\pool."...
0x18008bf7a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18008bf7f  jmp     loc_18008BEBE
0x18008bf84  mov     ecx, r14d; dwErrCode
0x18008bf87  call    cs:__imp_SetLastError
0x18008bf8d  nop
0x18008bf8e  lea     rax, ??_7ILifeTimeMgmt@@6B@; const ILifeTimeMgmt::`vftable'
0x18008bf95  mov     [rbp+60h+var_A0], rax
0x18008bf99  jmp     loc_18008BDC9
0x18008bf9e  cmp     [rax+30h], r12d
0x18008bfa2  jbe     loc_18008BEFA
0x18008bfa8  mov     ecx, [rbx+78h]
0x18008bfab  cmp     ecx, 3
0x18008bfae  jnz     loc_18008CD21
0x18008bfb4  mov     word ptr [rdi+0F8h], 22h ; '"'
0x18008bfbd  lea     rax, aApplicationSoa; "application/soap+xml;charset=UTF-8"
0x18008bfc4  mov     [rdi+100h], rax
0x18008bfcb  mov     rcx, [rbx+70h]
0x18008bfcf  lea     r13, Buf1
0x18008bfd6  test    rcx, rcx
0x18008bfd9  jz      short loc_18008BFF3
0x18008bfdb  mov     edx, [rcx+48h]
0x18008bfde  lea     eax, [rdx-3]
0x18008bfe1  cmp     eax, r12d
0x18008bfe4  jbe     loc_18008C157
0x18008bfea  cmp     edx, 6
0x18008bfed  jz      loc_18008C161
0x18008bff3  cmp     byte ptr [rbx+11F8h], 0
0x18008bffa  jnz     loc_18008CF2A
0x18008c000  xor     r15d, r15d
0x18008c003  mov     [rsi], r15d
0x18008c006  mov     rcx, [rbx+10h]
0x18008c00a  mov     rax, [rcx+28h]
0x18008c00e  test    rax, rax
0x18008c011  jnz     short loc_18008C089
0x18008c013  mov     rax, r13
0x18008c016  mov     r8d, r15d
0x18008c019  mov     [rsi+8], rax
0x18008c01d  mov     [rsi+10h], r8d
0x18008c021  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c028  lea     rdx, WPP_GLOBAL_Control
0x18008c02f  cmp     rcx, rdx
0x18008c032  jnz     loc_18008CFE2
0x18008c038  mov     [rdi+218h], r12w
0x18008c040  mov     [rdi+220h], rsi
0x18008c047  jmp     loc_18008BDD3
0x18008c04c  call    cs:__imp_SetLastError
0x18008c052  mov     [rsp+160h+CachePolicy], 0; struct IRequestContext *
0x18008c05b  mov     r9d, 54Fh; unsigned int
0x18008c061  lea     r8, a59; "59"
0x18008c068  mov     edx, 3Bh ; ';'; unsigned int
0x18008c06d  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18008c074  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18008c079  jmp     loc_18008BC4D
0x18008c07e  call    cs:__imp_SetLastError
0x18008c084  jmp     loc_18008BC6F
0x18008c089  mov     r8d, [rcx+30h]
0x18008c08d  jmp     short loc_18008C019
0x18008c08f  lea     r8, [rbx+28h]
0x18008c093  test    r14d, r14d
0x18008c096  jz      loc_18008C30F
0x18008c09c  mov     rdx, [rbx+98h]
0x18008c0a3  mov     [rsp+160h+LogData], r15; LogData
0x18008c0a8  mov     [rsp+160h+Overlapped], r8; Overlapped
0x18008c0ad  mov     [rsp+160h+Reserved2], r15d; Reserved2
0x18008c0b2  mov     [rsp+160h+Reserved1], r15; Reserved1
0x18008c0b7  mov     [rsp+160h+BytesSent], r15; BytesSent
0x18008c0bc  mov     [rsp+160h+CachePolicy], r15; CachePolicy
0x18008c0c1  mov     r9, rdi; HttpResponse
0x18008c0c4  mov     r8d, r12d; Flags
0x18008c0c7  mov     rdx, [rdx+10h]; RequestId
0x18008c0cb  call    cs:__imp_HttpSendHttpResponse
0x18008c0d1  mov     edi, eax
0x18008c0d3  lea     rdx, WPP_GLOBAL_Control
0x18008c0da  lea     r11, aFalse; "false"
0x18008c0e1  jmp     loc_18008BE74
0x18008c0e6  test    dword ptr [rcx+1Ch], 1000000h
0x18008c0ed  jz      loc_18008BE5B
0x18008c0f3  mov     eax, r9d
0x18008c0f6  shr     eax, 1Fh
0x18008c0f9  mov     r8, r13
0x18008c0fc  test    al, al
0x18008c0fe  cmovz   r8, r11
0x18008c102  btr     r9d, 1Fh
0x18008c107  mov     edx, 0Ch
0x18008c10c  mov     [rsp+160h+BytesSent], r8
0x18008c111  mov     dword ptr [rsp+160h+CachePolicy], r9d
0x18008c116  mov     r9, rsi
0x18008c119  lea     r8, WPP_9896aa7138543c0bf89dc30a450bb385_Traceguids
0x18008c120  mov     rcx, [rcx+10h]
0x18008c124  call    WPP_SF_qLS
0x18008c129  lea     rdx, WPP_GLOBAL_Control
0x18008c130  lea     r11, aFalse; "false"
0x18008c137  jmp     loc_18008BE5B
0x18008c13c  mov     byte ptr [rbx+18h], 0
0x18008c140  mov     rcx, [rbx+10h]; this
0x18008c144  test    rcx, rcx
0x18008c147  jz      loc_18008BC91
0x18008c14d  call    ?Recycle@Packet@@QEAAXXZ; Packet::Recycle(void)
0x18008c152  jmp     loc_18008BC91
0x18008c157  test    byte ptr [rcx+64h], 10h
0x18008c15b  jz      loc_18008BFEA
  ... truncated ...
```
