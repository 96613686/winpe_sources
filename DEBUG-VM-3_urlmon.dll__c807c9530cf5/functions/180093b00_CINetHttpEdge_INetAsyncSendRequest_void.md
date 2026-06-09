# CINetHttpEdge::INetAsyncSendRequest(void)

- ea: `0x180093b00`
- end: `0x180094624`
- name: `?INetAsyncSendRequest@CINetHttpEdge@@UEAAJXZ`
- size: `2852`
- prototype: `__int64 __fastcall(CINetHttpEdge *__hidden this)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007730`
- `0x1800080f4`
- `0x180009850`
- `0x18000a110`
- `0x18000a270`
- `0x18000c6f0`
- `0x18000cef0`
- `0x18000eb40`
- `0x18000f558`
- `0x1800214d0`
- `0x18002d510`
- `0x18002d5dc`
- `0x18002df78`
- `0x180046cb0`
- `0x1800573c0`
- `0x180057860`
- `0x18005c058`
- `0x1800627f0`
- `0x180073b18`
- `0x180078188`
- `0x1800786bc`
- `0x18007a42c`
- `0x18007c3b4`
- `0x18007d7ac`
- `0x18007e60c`
- `0x180083210`
- `0x180092990`
- `0x180093b00`
- `0x180095fa0`
- `0x1800b5db8`
- `0x1800e3484`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!_wtol` at `0x180094332`
- `msvcrt!_wtol` at `0x180094332`
- `iertutil!__imp_CoInternetFeatureValueInternal` at `0x1800944c7`
- `iertutil!__imp_CoInternetFeatureValueInternal` at `0x1800944c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093c1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094453`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093c1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180094453`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180093c05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009441a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180093c05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009441a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009428b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18009428b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093c5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800940fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093c5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093d77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800940fd`
- `WININET!InternetSetOptionW` at `0x180093f58`
- `WININET!InternetSetOptionW` at `0x180093f86`
- `WININET!InternetSetOptionW` at `0x180093fb4`
- `WININET!InternetSetOptionW` at `0x1800940ed`
- `WININET!InternetSetOptionW` at `0x180093f58`
- `WININET!InternetSetOptionW` at `0x180093f86`
- `WININET!InternetSetOptionW` at `0x180093fb4`
- `WININET!InternetSetOptionW` at `0x1800940ed`
- `WININET!InternetSetOptionA` at `0x180093dd6`
- `WININET!InternetSetOptionA` at `0x180093ead`
- `WININET!InternetSetOptionA` at `0x180093ed2`
- `WININET!InternetSetOptionA` at `0x180093f22`
- `WININET!InternetSetOptionA` at `0x180094019`
- `WININET!InternetSetOptionA` at `0x18009405b`
- `WININET!InternetSetOptionA` at `0x1800941f4`
- `WININET!InternetSetOptionA` at `0x180094218`
- `WININET!InternetSetOptionA` at `0x1800944a8`
- `WININET!InternetSetOptionA` at `0x180093dd6`
- `WININET!InternetSetOptionA` at `0x180093ead`
- `WININET!InternetSetOptionA` at `0x180093ed2`
- `WININET!InternetSetOptionA` at `0x180093f22`
- `WININET!InternetSetOptionA` at `0x180094019`
- `WININET!InternetSetOptionA` at `0x18009405b`
- `WININET!InternetSetOptionA` at `0x1800941f4`
- `WININET!InternetSetOptionA` at `0x180094218`
- `WININET!InternetSetOptionA` at `0x1800944a8`
- `WININET!HttpPushEnable` at `0x180094184`
- `WININET!HttpPushEnable` at `0x180094184`

## pseudocode

```c
__int64 __fastcall CINetHttpEdge::INetAsyncSendRequest(CINetHttpEdge *this)
{
  int NextSendBuffer; // edi
  unsigned int v3; // esi
  unsigned int v4; // r15d
  void *v5; // r13
  char v6; // dl
  char v7; // cl
  char v8; // r8
  struct IInternetBindInfo *RefCountedBindInfo; // rax
  struct IInternetBindInfo *v10; // r14
  struct IInternetBindInfoVtbl *v11; // rax
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  int IsDNTException; // eax
  void *v15; // rcx
  __int64 v16; // rsi
  BOOL v17; // edi
  void *v18; // rcx
  void *v19; // rcx
  int v20; // ecx
  int v21; // eax
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  struct IInternetBindInfoVtbl *lpVtbl; // rax
  int v27; // eax
  _WORD *v28; // rcx
  __int64 v29; // r9
  DWORD v30; // eax
  bool v31; // dl
  void *v32; // rcx
  struct IInternetBindInfo *v33; // rax
  struct IInternetBindInfo *v34; // r15
  struct IInternetBindInfoVtbl *v35; // rcx
  struct IInternetBindInfoVtbl *v36; // rax
  unsigned int v37; // r14d
  int v38; // esi
  const char *v39; // r9
  __int64 v40; // rcx
  struct IStream *RefCountedStream; // r14
  void *v42; // rcx
  unsigned int v43; // ebx
  unsigned int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  char v48; // [rsp+58h] [rbp-A8h]
  unsigned int v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  void *v51; // [rsp+70h] [rbp-90h] BYREF
  char v52; // [rsp+78h] [rbp-88h]
  CINetHttpEdge *v53; // [rsp+80h] [rbp-80h] BYREF
  char v54; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+90h] [rbp-70h] BYREF
  LPVOID *p_lpBuffer; // [rsp+B0h] [rbp-50h]
  __int64 v57; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v58[512]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( (unsigned int)dword_180159000 > 5 && (qword_180159010 & 0x20) != 0 && (qword_180159018 & 0x20) == qword_180159018 )
  {
    lpBuffer = this;
    p_lpBuffer = &lpBuffer;
    v57 = 8;
    tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180159000, byte_180144F6B, 0, 0, 3u, &v55);
  }
  v53 = this;
  v54 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 300);
  NextSendBuffer = 0;
  if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v53) )
  {
    v3 = 2;
    goto LABEL_124;
  }
  v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 14);
  if ( v3 != 1 )
    goto LABEL_124;
  v4 = 1223;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  *((_DWORD *)this + 32) = 5;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
  v5 = 0;
  v49 = 0;
  CINetHttpEdge::GetVerb(this);
  v7 = *((_BYTE *)this + 976);
  if ( ((v7 & 2) != 0 || *((_DWORD *)this + 108) + *((_DWORD *)this + 109)) && *((_QWORD *)this + 159) )
  {
    CoTaskMemFree(*((LPVOID *)this + 159));
    v7 = *((_BYTE *)this + 976);
    *((_QWORD *)this + 159) = 0;
  }
  if ( (v7 & 2) == 0 && !(*((_DWORD *)this + 108) + *((_DWORD *)this + 109)) )
    CINetHttpEdge::GetAdditionalHeader(this);
  v8 = *((_BYTE *)this + 976);
  if ( (v8 & 6) != 2 )
  {
    v6 = (_BYTE)this - 16;
    v49 = 0;
    if ( this != (CINetHttpEdge *)-752LL && *((_DWORD *)this + 199) && *((_DWORD *)this + 192) == 1 )
    {
      v5 = (void *)*((_QWORD *)this + 97);
      v49 = *((_DWORD *)this + 202);
    }
  }
  if ( !*((_DWORD *)this + 108) && !*((_DWORD *)this + 109) && (v8 & 2) == 0 )
  {
    NextSendBuffer = CINetHttpEdge::HttpNegBeginningTransaction(this);
    if ( NextSendBuffer == -2147467260 )
    {
LABEL_121:
      *((_DWORD *)this + 31) = NextSendBuffer;
      CINetEdge::SetBindResult(this, v4, NextSendBuffer);
      v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 17);
      if ( v3 != 1 )
        goto LABEL_124;
      goto LABEL_119;
    }
  }
  RefCountedBindInfo = CINetEdge::GetRefCountedBindInfo(this, v6);
  v10 = RefCountedBindInfo;
  if ( !RefCountedBindInfo )
  {
    NextSendBuffer = -2147467260;
    goto LABEL_121;
  }
  if ( (*((_BYTE *)this + 740) & 0x20) == 0 || *((_QWORD *)this + 160) )
  {
    if ( NextSendBuffer < 0 )
      goto LABEL_78;
LABEL_32:
    if ( g_fDoNotTrackAllowExceptions && g_fDoNotTrack )
    {
      IsDNTException = CINetEdge::IsDNTException(this, *((struct IUri **)this + 17));
      v15 = (void *)*((_QWORD *)this + 47);
      Buffer = IsDNTException;
      InternetSetOptionA(v15, 0x7Bu, &Buffer, 4u);
    }
    CINetHttpEdge::HttpNegGetRootSecurityId(this);
    v16 = *((_QWORD *)this + 17);
    lpBuffer = this;
    v48 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    v17 = 1;
    if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&lpBuffer)
      && *((_QWORD *)this + 162)
      && (int)EnsureSecurityManager() >= 0 )
    {
      if ( *((_QWORD *)this + 162) == -1 )
      {
        v17 = 0;
      }
      else
      {
        Buffer = 512;
        if ( (int)GetZoneAgnosticSecurityIdFromUri(
                    (_DWORD)g_pInternetSecurityManagerEx2,
                    v16,
                    (unsigned int)v58,
                    (unsigned int)&Buffer,
                    0) >= 0 )
          v17 = SecurityIdsMatch(v58, Buffer, *((unsigned __int8 **)this + 162), *((_DWORD *)this + 326)) == 0;
      }
    }
    CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&lpBuffer);
    v18 = (void *)*((_QWORD *)this + 47);
    LODWORD(v50) = v17;
    InternetSetOptionA(v18, 0x56u, &v50, 4u);
    v19 = (void *)*((_QWORD *)this + 47);
    LODWORD(pv) = 1;
    InternetSetOptionA(v19, 0x41u, &pv, 4u);
    v20 = *((_DWORD *)this + 185);
    Buffer = 0;
    if ( (v20 & 0x10001) != 0 )
    {
      v21 = 0;
      if ( (v20 & 1) != 0 )
      {
        Buffer = 4;
        v21 = 4;
      }
      if ( (v20 & 0x10000) != 0 )
        Buffer = v21 | 8;
      InternetSetOptionA(*((HINTERNET *)this + 47), 0x55u, &Buffer, 4u);
    }
    CINetEdge::EnableSingleSignOnIfNeeded(this);
    if ( (*((_BYTE *)this + 740) & 0x40) == 0 )
    {
      v22 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v22, 0x7Au, &Buffer, 4u);
    }
    if ( (*((_BYTE *)this + 744) & 2) != 0 )
    {
      v23 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v23, 0xAAu, &Buffer, 4u);
    }
    if ( (*((_BYTE *)this + 744) & 4) != 0 )
    {
      v24 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionW(v24, 0xACu, &Buffer, 4u);
    }
    v51 = 0;
    if ( (int)CINetEdge::QueryService(this, &GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b, &v51) >= 0 && v51 )
    {
      lpBuffer = 0;
      if ( !(*(unsigned int (__fastcall **)(void *, GUID *, LPVOID *))(*(_QWORD *)v51 + 24LL))(
              v51,
              &IID_IWindowForBindingUI,
              &lpBuffer) )
        InternetSetOptionA(*((HINTERNET *)this + 47), 0x70u, &lpBuffer, 8u);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
    }
    if ( (*((_DWORD *)this + 203) & 0x20000000) != 0 )
    {
      v25 = (void *)*((_QWORD *)this + 47);
      Buffer = 1;
      InternetSetOptionA(v25, 0x6Eu, &Buffer, 4u);
    }
    if ( *((_DWORD *)this + 199) == 1 && (*((_BYTE *)this + 1360) & 0x20) == 0 )
    {
      lpVtbl = v10->lpVtbl;
      Buffer = 0;
      lpBuffer = 0;
      v27 = ((__int64 (__fastcall *)(struct IInternetBindInfo *, __int64, LPVOID *, __int64, unsigned int *))lpVtbl->GetBindString)(
              v10,
              12,
              &lpBuffer,
              1,
              &Buffer);
      v28 = lpBuffer;
      if ( lpBuffer )
      {
        if ( !v27 )
        {
          *((_BYTE *)this + 1360) |= 0x20u;
          v29 = -1;
          do
            ++v29;
          while ( v28[v29] );
          InternetSetOptionW(*((HINTERNET *)this + 47), 0x35u, v28, v29 + 1);
          v28 = lpBuffer;
        }
        if ( v28 )
          CoTaskMemFree(v28);
      }
    }
    lpBuffer = this;
    v48 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&lpBuffer) )
    {
      NextSendBuffer = -2147467259;
      goto LABEL_77;
    }
    NextSendBuffer = 0;
    if ( !memcmp_0((char *)this + 1936, &GUID_NULL, 0x10u) || !memcmp_0((char *)this + 1952, &GUID_NULL, 0x10u) )
      goto LABEL_77;
    if ( *((_QWORD *)this + 241) )
    {
      v30 = 12019;
    }
    else
    {
      v30 = HttpPushEnable(
              *((HINTERNET *)this + 47),
              (HTTP_PUSH_TRANSPORT_SETTING *)((char *)this + 1936),
              (HTTP_PUSH_WAIT_HANDLE *)this + 241);
      if ( !v30 )
      {
LABEL_77:
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&lpBuffer);
        goto LABEL_78;
      }
    }
    v4 = v30;
    NextSendBuffer = -2147467260;
    goto LABEL_77;
  }
  v11 = RefCountedBindInfo->lpVtbl;
  Buffer = 0;
  pv = 0;
  NextSendBuffer = -2147024882;
  if ( ((int (__fastcall *)(struct IInternetBindInfo *, __int64, LPVOID *, __int64, unsigned int *))v11->GetBindString)(
         v10,
         19,
         &pv,
         1,
         &Buffer) >= 0 )
  {
    v12 = OLESTRDuplicate((const unsigned __int16 *)pv);
    v13 = pv;
    *((_QWORD *)this + 160) = v12;
    if ( v13 )
      CoTaskMemFree(v13);
    if ( *((_QWORD *)this + 160) )
    {
      CINetHttpEdge::SetWininetDownloadModeCore(this);
      goto LABEL_32;
    }
  }
LABEL_78:
  ((void (__fastcall *)(struct IInternetBindInfo *))v10->lpVtbl->Release)(v10);
  if ( NextSendBuffer == -2147467260 )
    goto LABEL_121;
  CINetHttpEdge::SetWininetPriority(this);
  if ( (*((_DWORD *)this + 130) & 0x4000010) == 0x10 )
  {
    v32 = (void *)*((_QWORD *)this + 47);
    LODWORD(pv) = 1;
    InternetSetOptionA(v32, 0x73u, &pv, 4u);
  }
  if ( (*((_DWORD *)this + 185) & 0x1000000) != 0 )
    InternetSetOptionA(*((HINTERNET *)this + 47), 0x7Cu, 0, 0);
  v33 = CINetEdge::GetRefCountedBindInfo(this, v31);
  v34 = v33;
  if ( v33 )
  {
    v35 = v33->lpVtbl;
    LODWORD(pv) = 0;
    if ( ((int (__fastcall *)(struct IInternetBindInfo *, __int64, char *, __int64, LPVOID *))v35->GetBindString)(
           v33,
           24,
           (char *)this + 1352,
           1,
           &pv) >= 0 )
      (*(void (__fastcall **)(CINetHttpEdge *))(*(_QWORD *)this + 408LL))(this);
    InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
    if ( byte_18015DE34 )
    {
      v51 = this;
      v52 = 0;
      _InterlockedIncrement((volatile signed __int32 *)this + 300);
      if ( CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v51) )
      {
        v36 = v34->lpVtbl;
        v50 = 0;
        v37 = 0;
        v38 = ((__int64 (__fastcall *)(struct IInternetBindInfo *, GUID *, __int64 *))v36->QueryInterface)(
                v34,
                &GUID_8fd4c3a8_e3e8_4b62_9f2f_483e5c09661d,
                &v50);
        if ( v38 >= 0 )
        {
          Buffer = 0;
          lpBuffer = 0;
          v38 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v50 + 32LL))(
                  v50,
                  2,
                  &lpBuffer,
                  &Buffer);
          if ( !v38 )
          {
            if ( !Buffer || !lpBuffer )
              wil::details::in1diag3::_FailFast_GetLastError(
                retaddr,
                (void *)0x24E9,
                (unsigned int)"onecoreuap\\inetcore\\urlmon\\iapp\\edge\\cnetedge.cxx",
                v39);
            v37 = _wtol((const wchar_t *)lpBuffer);
          }
        }
        v40 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        }
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v51);
        if ( v38 >= 0 && v37 )
          CINetEdge::s_SetTimeoutsOnHandle(*((HINTERNET *)this + 47), v37, 1, v37, 1, v37, 1);
      }
      else
      {
        CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v51);
      }
    }
    ((void (__fastcall *)(struct IInternetBindInfo *))v34->lpVtbl->Release)(v34);
  }
  CINetHttpEdge::ComputeSameSiteCookiePolicy(this, 0);
  CINetEdge::SetStatePending(this, 2147483658LL, 4);
  if ( !NextSendBuffer )
  {
    v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 15);
    if ( (unsigned int)CINetEdge::IsUpLoad(this) )
    {
      RefCountedStream = CINetHttpEdge::GetRefCountedStream(this);
      if ( RefCountedStream )
        goto LABEL_108;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( this != (CINetHttpEdge *)-752LL && *((_DWORD *)this + 192) == 4 )
      {
        RefCountedStream = (struct IStream *)*((_QWORD *)this + 97);
        ((void (__fastcall *)(struct IStream *))RefCountedStream->lpVtbl->AddRef)(RefCountedStream);
        *((_QWORD *)this + 238) = RefCountedStream;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 984));
      if ( RefCountedStream )
      {
LABEL_108:
        NextSendBuffer = CINetHttpEdge::GetNextSendBuffer(
                           this,
                           (struct _INTERNET_BUFFERSW *)((char *)this + 888),
                           RefCountedStream,
                           1);
        ((void (__fastcall *)(struct IStream *))RefCountedStream->lpVtbl->Release)(RefCountedStream);
      }
    }
    else
    {
      v42 = (void *)*((_QWORD *)this + 47);
      LODWORD(pv) = 11;
      InternetSetOptionA(v42, 0x3Eu, &pv, 4u);
    }
    if ( FCK::FEATURE_BROWSER_EMULATION )
    {
      Buffer = 0;
      if ( (int)CoInternetFeatureValueInternal(FCK::FEATURE_BROWSER_EMULATION, &Buffer) < 0 )
      {
LABEL_115:
        NextSendBuffer = CINetHttpEdge::DoSendRequest(this, NextSendBuffer, v5, v49);
        goto LABEL_124;
      }
      dword_180159E68 = Buffer;
      FCK::FEATURE_BROWSER_EMULATION = 0;
    }
    if ( dword_180159E68 != 7000 )
      CoInternetGetBrowserEmulationState((char *)this + 1416);
    goto LABEL_115;
  }
  CINetEdge::SetStatePending(this, 0, 4);
  v3 = CINetEdge::CheckAndSetINetEdgeState((__int64)this, 17);
  if ( v3 == 1 && NextSendBuffer != -2147483638 && *((_DWORD *)this + 31) )
LABEL_119:
    CINetHttpEdge::ReportResultAndStop(this, NextSendBuffer, 0, 0, 0);
LABEL_124:
  v43 = CINetEdge::CheckTransitionStatusAndDispatchAbort(this, v3, (unsigned int)NextSendBuffer);
  CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v53);
  return v43;
}

```

## disassembly

```asm
0x180093b00  push    rbp
0x180093b02  push    rbx
0x180093b03  lea     rbp, [rsp-1E8h]
0x180093b0b  sub     rsp, 2E8h
0x180093b12  mov     rax, cs:__security_cookie
0x180093b19  xor     rax, rsp
0x180093b1c  mov     [rbp+1F0h+var_30], rax
0x180093b23  mov     eax, cs:dword_180159000
0x180093b29  mov     rbx, rcx
0x180093b2c  cmp     eax, 5
0x180093b2f  jbe     short loc_180093B8E
0x180093b31  mov     rcx, cs:qword_180159018
0x180093b38  mov     rax, cs:qword_180159010
0x180093b3f  test    al, 20h
0x180093b41  jz      short loc_180093B8E
0x180093b43  mov     rax, rcx
0x180093b46  and     eax, 20h
0x180093b49  cmp     rax, rcx
0x180093b4c  jnz     short loc_180093B8E
0x180093b4e  lea     rax, [rsp+2F0h+lpBuffer]
0x180093b53  mov     [rsp+2F0h+lpBuffer], rbx
0x180093b58  mov     [rbp+1F0h+var_240], rax
0x180093b5c  lea     rdx, byte_180144F6B
0x180093b63  lea     rax, [rbp+1F0h+var_260]
0x180093b67  mov     [rbp+1F0h+var_238], 8
0x180093b6f  mov     qword ptr [rsp+2F0h+var_2C8], rax
0x180093b74  lea     rcx, dword_180159000
0x180093b7b  xor     r9d, r9d
0x180093b7e  mov     dword ptr [rsp+2F0h+var_2D0], 3
0x180093b86  xor     r8d, r8d
0x180093b89  call    _tlgWriteTransfer_BrowserWriteTransfer
0x180093b8e  mov     [rsp+2F0h+arg_8], rsi
0x180093b96  mov     [rsp+2F0h+arg_10], rdi
0x180093b9e  mov     [rsp+2F0h+arg_18], r12
0x180093ba6  mov     [rsp+2F0h+var_10], r13
0x180093bae  mov     [rsp+2F0h+var_18], r14
0x180093bb6  mov     [rsp+2F0h+var_20], r15
0x180093bbe  mov     [rbp+1F0h+var_270], rbx
0x180093bc2  mov     [rbp+1F0h+var_268], 0
0x180093bc6  lock inc dword ptr [rbx+4B0h]
0x180093bcd  lea     rcx, [rbp+1F0h+var_270]; this
0x180093bd1  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180093bd6  xor     edi, edi
0x180093bd8  test    al, al
0x180093bda  jz      loc_1800945A3
0x180093be0  mov     edx, 0Eh
0x180093be5  mov     rcx, rbx
0x180093be8  call    ?CheckAndSetINetEdgeState@CINetEdge@@IEAA?AW4INetEdgeStateTransition@@W4INetEdgeState@@@Z; CINetEdge::CheckAndSetINetEdgeState(INetEdgeState)
0x180093bed  mov     esi, eax
0x180093bef  cmp     eax, 1
0x180093bf2  jnz     loc_1800945A8
0x180093bf8  lea     rcx, [rbx+3D8h]; lpCriticalSection
0x180093bff  mov     r15d, 4C7h
0x180093c05  call    cs:__imp_EnterCriticalSection
0x180093c0b  lea     rcx, [rbx+3D8h]; lpCriticalSection
0x180093c12  mov     dword ptr [rbx+80h], 5
0x180093c1c  call    cs:__imp_LeaveCriticalSection
0x180093c22  xor     esi, esi
0x180093c24  mov     rcx, rbx; this
0x180093c27  mov     r13d, esi
0x180093c2a  mov     [rsp+2F0h+var_290], esi
0x180093c2e  call    ?GetVerb@CINetHttpEdge@@QEAAPEBGXZ; CINetHttpEdge::GetVerb(void)
0x180093c33  movzx   ecx, byte ptr [rbx+3D0h]
0x180093c3a  test    cl, 2
0x180093c3d  jnz     short loc_180093C4D
0x180093c3f  mov     eax, [rbx+1B4h]
0x180093c45  add     eax, [rbx+1B0h]
0x180093c4b  jz      short loc_180093C70
0x180093c4d  mov     rax, [rbx+4F8h]
0x180093c54  test    rax, rax
0x180093c57  jz      short loc_180093C70
0x180093c59  mov     rcx, rax; pv
0x180093c5c  call    cs:__imp_CoTaskMemFree
0x180093c62  movzx   ecx, byte ptr [rbx+3D0h]
0x180093c69  mov     [rbx+4F8h], rsi
0x180093c70  test    cl, 2
0x180093c73  jnz     short loc_180093C8B
0x180093c75  mov     eax, [rbx+1B4h]
0x180093c7b  add     eax, [rbx+1B0h]
0x180093c81  jnz     short loc_180093C8B
0x180093c83  mov     rcx, rbx; this
0x180093c86  call    ?GetAdditionalHeader@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::GetAdditionalHeader(void)
0x180093c8b  movzx   r8d, byte ptr [rbx+3D0h]
0x180093c93  movzx   eax, r8b
0x180093c97  and     al, 6
0x180093c99  cmp     al, 2
0x180093c9b  jz      short loc_180093CC8
0x180093c9d  lea     rdx, [rbx+2F0h]
0x180093ca4  mov     [rsp+2F0h+var_290], esi
0x180093ca8  test    rdx, rdx
0x180093cab  jz      short loc_180093CC8
0x180093cad  mov     ecx, [rdx+2Ch]
0x180093cb0  test    ecx, ecx
0x180093cb2  jz      short loc_180093CC8
0x180093cb4  sub     ecx, 1
0x180093cb7  cmp     dword ptr [rdx+10h], 1
0x180093cbb  jnz     short loc_180093CC8
0x180093cbd  mov     eax, [rdx+38h]
0x180093cc0  mov     r13, [rdx+18h]
0x180093cc4  mov     [rsp+2F0h+var_290], eax
0x180093cc8  cmp     [rbx+1B0h], esi
0x180093cce  jnz     short loc_180093CF3
0x180093cd0  cmp     [rbx+1B4h], esi
0x180093cd6  jnz     short loc_180093CF3
0x180093cd8  test    r8b, 2
0x180093cdc  jnz     short loc_180093CF3
0x180093cde  mov     rcx, rbx; this
0x180093ce1  call    ?HttpNegBeginningTransaction@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::HttpNegBeginningTransaction(void)
0x180093ce6  mov     edi, eax
0x180093ce8  cmp     eax, 80004004h
0x180093ced  jz      loc_180094563
0x180093cf3  mov     rcx, rbx; this
0x180093cf6  call    ?GetRefCountedBindInfo@CINetEdge@@IEAAPEAUIInternetBindInfo@@_N@Z; CINetEdge::GetRefCountedBindInfo(bool)
0x180093cfb  mov     r14, rax
0x180093cfe  test    rax, rax
0x180093d01  jz      loc_18009455E
0x180093d07  test    byte ptr [rbx+2E4h], 20h
0x180093d0e  jz      loc_180093D94
0x180093d14  cmp     [rbx+500h], rsi
0x180093d1b  jnz     short loc_180093D94
0x180093d1d  mov     rax, [rax]
0x180093d20  lea     rcx, [rsp+2F0h+Buffer]
0x180093d25  mov     [rsp+2F0h+var_2D0], rcx
0x180093d2a  lea     r8, [rsp+2F0h+pv]
0x180093d2f  mov     r9d, 1
0x180093d35  mov     [rsp+2F0h+Buffer], esi
0x180093d39  mov     edx, 13h
0x180093d3e  mov     [rsp+2F0h+pv], rsi
0x180093d43  mov     rax, [rax+20h]
0x180093d47  mov     rcx, r14
0x180093d4a  mov     edi, 8007000Eh
0x180093d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d54  test    eax, eax
0x180093d56  js      loc_1800941A2
0x180093d5c  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x180093d61  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x180093d66  mov     rcx, [rsp+2F0h+pv]; pv
0x180093d6b  mov     [rbx+500h], rax
0x180093d72  test    rcx, rcx
0x180093d75  jz      short loc_180093D7D
0x180093d77  call    cs:__imp_CoTaskMemFree
0x180093d7d  cmp     [rbx+500h], rsi
0x180093d84  jz      loc_1800941A2
0x180093d8a  mov     rcx, rbx; this
0x180093d8d  call    ?SetWininetDownloadModeCore@CINetHttpEdge@@IEAAJXZ; CINetHttpEdge::SetWininetDownloadModeCore(void)
0x180093d92  jmp     short loc_180093D9C
0x180093d94  test    edi, edi
0x180093d96  js      loc_1800941A2
0x180093d9c  cmp     cs:?g_fDoNotTrackAllowExceptions@@3HA, esi; int g_fDoNotTrackAllowExceptions
0x180093da2  jz      short loc_180093DDC
0x180093da4  cmp     cs:?g_fDoNotTrack@@3HA, esi; int g_fDoNotTrack
0x180093daa  jz      short loc_180093DDC
0x180093dac  mov     rdx, [rbx+88h]; struct IUri *
0x180093db3  mov     rcx, rbx; this
0x180093db6  call    ?IsDNTException@CINetEdge@@IEAAHPEAUIUri@@@Z; CINetEdge::IsDNTException(IUri *)
0x180093dbb  mov     rcx, [rbx+178h]; hInternet
0x180093dc2  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180093dc7  mov     r9d, 4; dwBufferLength
0x180093dcd  mov     [rsp+2F0h+Buffer], eax
0x180093dd1  mov     edx, 7Bh ; '{'; dwOption
0x180093dd6  call    cs:__imp_InternetSetOptionA
0x180093ddc  mov     rcx, rbx; this
0x180093ddf  call    ?HttpNegGetRootSecurityId@CINetHttpEdge@@QEAAJXZ; CINetHttpEdge::HttpNegGetRootSecurityId(void)
0x180093de4  mov     rsi, [rbx+88h]
0x180093deb  mov     [rsp+2F0h+lpBuffer], rbx
0x180093df0  mov     [rsp+2F0h+var_298], 0
0x180093df5  lock inc dword ptr [rbx+4B0h]
0x180093dfc  lea     rcx, [rsp+2F0h+lpBuffer]; this
0x180093e01  mov     edi, 1
0x180093e06  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x180093e0b  test    al, al
0x180093e0d  jz      short loc_180093E86
0x180093e0f  cmp     qword ptr [rbx+510h], 0
0x180093e17  jz      short loc_180093E86
0x180093e19  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x180093e1e  test    eax, eax
0x180093e20  js      short loc_180093E86
0x180093e22  cmp     qword ptr [rbx+510h], 0FFFFFFFFFFFFFFFFh
0x180093e2a  jnz     short loc_180093E32
0x180093e2c  xor     esi, esi
0x180093e2e  mov     edi, esi
0x180093e30  jmp     short loc_180093E88
0x180093e32  mov     rcx, cs:?g_pInternetSecurityManagerEx2@@3PEAUIInternetSecurityManagerEx2@@EA; IInternetSecurityManagerEx2 * g_pInternetSecurityManagerEx2
0x180093e39  lea     r9, [rsp+2F0h+Buffer]
0x180093e3e  lea     r8, [rbp+1F0h+var_230]
0x180093e42  mov     [rsp+2F0h+Buffer], 200h
0x180093e4a  mov     rdx, rsi
0x180093e4d  mov     [rsp+2F0h+var_2D0], 0
0x180093e56  call    GetZoneAgnosticSecurityIdFromUri
0x180093e5b  test    eax, eax
0x180093e5d  js      short loc_180093E86
0x180093e5f  mov     r9d, [rbx+518h]; unsigned int
0x180093e66  lea     rcx, [rbp+1F0h+var_230]; unsigned __int8 *
0x180093e6a  mov     r8, [rbx+510h]; unsigned __int8 *
0x180093e71  mov     edx, [rsp+2F0h+Buffer]; unsigned int
0x180093e75  call    ?SecurityIdsMatch@@YAHPEAEK0K@Z; SecurityIdsMatch(uchar *,ulong,uchar *,ulong)
0x180093e7a  xor     esi, esi
0x180093e7c  test    eax, eax
0x180093e7e  mov     edi, esi
0x180093e80  setz    dil
0x180093e84  jmp     short loc_180093E88
0x180093e86  xor     esi, esi
0x180093e88  lea     rcx, [rsp+2F0h+lpBuffer]; this
0x180093e8d  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x180093e92  mov     rcx, [rbx+178h]; hInternet
0x180093e99  lea     r8, [rsp+2F0h+var_288]; lpBuffer
0x180093e9e  mov     r9d, 4; dwBufferLength
0x180093ea4  mov     dword ptr [rsp+2F0h+var_288], edi
0x180093ea8  mov     edx, 56h ; 'V'; dwOption
0x180093ead  call    cs:__imp_InternetSetOptionA
0x180093eb3  mov     rcx, [rbx+178h]; hInternet
0x180093eba  lea     r8, [rsp+2F0h+pv]; lpBuffer
0x180093ebf  mov     r9d, 4; dwBufferLength
0x180093ec5  mov     dword ptr [rsp+2F0h+pv], 1
0x180093ecd  mov     edx, 41h ; 'A'; dwOption
0x180093ed2  call    cs:__imp_InternetSetOptionA
0x180093ed8  mov     ecx, [rbx+2E4h]
0x180093ede  mov     [rsp+2F0h+Buffer], esi
0x180093ee2  test    ecx, 10001h
0x180093ee8  jz      short loc_180093F28
0x180093eea  mov     eax, esi
0x180093eec  test    cl, 1
0x180093eef  jz      short loc_180093EFE
0x180093ef1  mov     [rsp+2F0h+Buffer], 4
0x180093ef9  mov     eax, 4
0x180093efe  bt      ecx, 10h
0x180093f02  jnb     short loc_180093F0B
0x180093f04  or      eax, 8
0x180093f07  mov     [rsp+2F0h+Buffer], eax
0x180093f0b  mov     rcx, [rbx+178h]; hInternet
0x180093f12  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180093f17  mov     r9d, 4; dwBufferLength
0x180093f1d  mov     edx, 55h ; 'U'; dwOption
0x180093f22  call    cs:__imp_InternetSetOptionA
0x180093f28  mov     rcx, rbx; this
0x180093f2b  call    ?EnableSingleSignOnIfNeeded@CINetEdge@@IEAAXXZ; CINetEdge::EnableSingleSignOnIfNeeded(void)
0x180093f30  test    byte ptr [rbx+2E4h], 40h
0x180093f37  jnz     short loc_180093F5E
0x180093f39  mov     rcx, [rbx+178h]; hInternet
0x180093f40  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180093f45  mov     r9d, 4; dwBufferLength
0x180093f4b  mov     [rsp+2F0h+Buffer], 1
0x180093f53  mov     edx, 7Ah ; 'z'; dwOption
0x180093f58  call    cs:__imp_InternetSetOptionW
0x180093f5e  test    byte ptr [rbx+2E8h], 2
0x180093f65  jz      short loc_180093F8C
0x180093f67  mov     rcx, [rbx+178h]; hInternet
0x180093f6e  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180093f73  mov     r9d, 4; dwBufferLength
0x180093f79  mov     [rsp+2F0h+Buffer], 1
0x180093f81  mov     edx, 0AAh; dwOption
0x180093f86  call    cs:__imp_InternetSetOptionW
0x180093f8c  test    byte ptr [rbx+2E8h], 4
0x180093f93  jz      short loc_180093FBA
0x180093f95  mov     rcx, [rbx+178h]; hInternet
0x180093f9c  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180093fa1  mov     r9d, 4; dwBufferLength
0x180093fa7  mov     [rsp+2F0h+Buffer], 1
0x180093faf  mov     edx, 0ACh; dwOption
0x180093fb4  call    cs:__imp_InternetSetOptionW
0x180093fba  lea     r8, [rsp+2F0h+var_280]; void **
0x180093fbf  mov     [rsp+2F0h+var_280], rsi
0x180093fc4  lea     rdx, _GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b; struct _GUID *
0x180093fcb  mov     rcx, rbx; this
0x180093fce  call    ?QueryService@CINetEdge@@IEAAJAEBU_GUID@@PEAPEAX@Z; CINetEdge::QueryService(_GUID const &,void * *)
0x180093fd3  test    eax, eax
0x180093fd5  js      short loc_180094030
0x180093fd7  mov     rcx, [rsp+2F0h+var_280]
0x180093fdc  test    rcx, rcx
0x180093fdf  jz      short loc_180094030
0x180093fe1  mov     [rsp+2F0h+lpBuffer], rsi
0x180093fe6  lea     r8, [rsp+2F0h+lpBuffer]
0x180093feb  mov     rax, [rcx]
0x180093fee  lea     rdx, IID_IWindowForBindingUI
0x180093ff5  mov     rax, [rax+18h]
0x180093ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ffe  test    eax, eax
0x180094000  jnz     short loc_18009401F
0x180094002  mov     rcx, [rbx+178h]; hInternet
0x180094009  lea     r8, [rsp+2F0h+lpBuffer]; lpBuffer
0x18009400e  mov     r9d, 8; dwBufferLength
0x180094014  mov     edx, 70h ; 'p'; dwOption
0x180094019  call    cs:__imp_InternetSetOptionA
0x18009401f  mov     rcx, [rsp+2F0h+var_280]
0x180094024  mov     rax, [rcx]
0x180094027  mov     rax, [rax+10h]
0x18009402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094030  test    dword ptr [rbx+32Ch], 20000000h
0x18009403a  jz      short loc_180094061
0x18009403c  mov     rcx, [rbx+178h]; hInternet
0x180094043  lea     r8, [rsp+2F0h+Buffer]; lpBuffer
0x180094048  mov     r9d, 4; dwBufferLength
0x18009404e  mov     [rsp+2F0h+Buffer], 1
0x180094056  mov     edx, 6Eh ; 'n'; dwOption
0x18009405b  call    cs:__imp_InternetSetOptionA
0x180094061  cmp     dword ptr [rbx+31Ch], 1
0x180094068  jnz     loc_180094103
0x18009406e  test    byte ptr [rbx+550h], 20h
0x180094075  jnz     loc_180094103
0x18009407b  mov     rax, [r14]
  ... truncated ...
```
