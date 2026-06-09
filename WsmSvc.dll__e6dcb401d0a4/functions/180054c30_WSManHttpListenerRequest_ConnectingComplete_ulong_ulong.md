# WSManHttpListenerRequest::ConnectingComplete(ulong,ulong)

- ea: `0x180054c30`
- end: `0x180055ce7`
- name: `?ConnectingComplete@WSManHttpListenerRequest@@AEAAXKK@Z`
- size: `4279`
- prototype: `void __fastcall(WSManHttpListenerRequest *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054730`

## callees

- `0x180005d10`
- `0x1800121d0`
- `0x1800224f0`
- `0x180025d90`
- `0x180026310`
- `0x180026e80`
- `0x18002dd20`
- `0x180054494`
- `0x180054c30`
- `0x180055cf0`
- `0x180055d98`
- `0x180056000`
- `0x1800567e0`
- `0x180056878`
- `0x1800572e0`
- `0x180058e84`
- `0x180068b24`
- `0x180075434`
- `0x18008d16c`
- `0x18008e040`
- `0x1800fb570`
- `0x180103850`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x1801133b0`
- `0x18011a6d4`
- `0x1801236c8`
- `0x1801297b8`
- `0x18016de18`
- `0x18016f4cc`
- `0x1801701e4`
- `0x18017027c`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180054dd0`
- `msvcrt!_wcsicmp` at `0x180055235`
- `msvcrt!_wcsicmp` at `0x180054dd0`
- `msvcrt!_wcsicmp` at `0x180055235`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055247`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055247`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055013`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800550b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800550b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054e3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054e3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055319`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055319`

## string_xrefs

- `0x180055268`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18005551a`: `Failed to create new listener request`
- `0x180055a39`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180055b23`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180055b4b`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005569b`: `request data failed to read`
- `0x1800558ba`: `Getting service configuration`
- `0x1800559e0`: `Failed to create connection object`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall WSManHttpListenerRequest::ConnectingComplete(WSManHttpListenerRequest *this, unsigned int a2)
{
  unsigned int IsBusy; // eax
  __int64 v5; // r8
  __int64 v6; // rcx
  _WORD *v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // r9
  __int64 v10; // rdi
  __int64 v11; // rcx
  _WORD *v12; // rdx
  _WORD *v13; // rax
  const wchar_t *v14; // r12
  unsigned __int64 v15; // rcx
  __int64 v16; // r13
  _DWORD *v17; // rcx
  __int64 *v18; // r15
  __int64 *v19; // r14
  unsigned __int64 v20; // rax
  const wchar_t *v21; // rdx
  int v22; // r12d
  __int64 *v23; // r15
  __int64 v24; // r14
  __int64 v25; // r8
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int16 *v28; // rdx
  __int16 v29; // ax
  _WORD *v30; // rax
  __int64 v31; // r9
  _OWORD *v32; // rax
  PVOID *v33; // rcx
  __int64 v34; // r9
  _DWORD *v35; // r15
  __int64 v36; // rdx
  struct WSManHttpListenerConnection *ConnectionObject; // rax
  struct WSManHttpListenerConnection *v38; // rbx
  char *v39; // rdi
  DWORD v40; // ecx
  __int64 v41; // r13
  bool v42; // al
  __int64 v43; // rbx
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rdx
  unsigned int v47; // r8d
  int v48; // eax
  int v49; // eax
  _QWORD *v50; // rcx
  char *v51; // rcx
  __int64 v52; // rdx
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int ErrorCode; // eax
  unsigned int v56; // eax
  DWORD LastError; // eax
  const char *v58; // rdx
  unsigned int v59; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v60; // [rsp+30h] [rbp-D0h]
  _DWORD *v61; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  int v63; // [rsp+50h] [rbp-B0h]
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+60h] [rbp-A0h]
  void **v66; // [rsp+70h] [rbp-90h] BYREF
  signed __int32 v67; // [rsp+78h] [rbp-88h] BYREF
  int v68; // [rsp+80h] [rbp-80h]
  int v69; // [rsp+84h] [rbp-7Ch]
  char v70; // [rsp+88h] [rbp-78h]
  const wchar_t *v71; // [rsp+90h] [rbp-70h]
  const wchar_t *v72; // [rsp+98h] [rbp-68h]
  const wchar_t *v73; // [rsp+A0h] [rbp-60h]
  const wchar_t *v74; // [rsp+A8h] [rbp-58h]
  _OWORD v75[8]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v76[84]; // [rsp+130h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  IsBusy = WSManHttpListener::RequestIsBusy(*((WSManHttpListener **)this + 10), 1);
  if ( IsBusy )
  {
    v60 = L"Failed to create new listener request";
    v59 = IsBusy;
    goto LABEL_96;
  }
  if ( a2 == 234 || a2 == 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    v60 = L"Request headers too big";
    v59 = a2;
    goto LABEL_96;
  }
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    CRequestContext::CRequestContext((CRequestContext *)v76);
    v76[4] = L"request data failed to read";
    v76[5] = &Class;
    v76[6] = &Class;
    v76[7] = &Class;
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v76[0] + 64LL))(v76, a2, a2);
    SystemTimeAsFileTime = (struct _FILETIME)((char *)this + 5328);
    v63 = 0;
    CWSManCriticalSection::Acquire((WSManHttpListenerRequest *)((char *)this + 5328));
    *((_BYTE *)this + 4578) = 1;
    InCritSec::~InCritSec((InCritSec *)&SystemTimeAsFileTime);
    WSManHttpListenerRequest::Finished2(this, 0);
    CRequestContext::~CRequestContext((CRequestContext *)v76);
    return;
  }
  v6 = *((_QWORD *)this + 19);
  v7 = (_WORD *)((char *)this + 448);
  v8 = (unsigned __int64)*(unsigned __int16 *)(v6 + 68) >> 1;
  v9 = *(unsigned __int16 **)(v6 + 88);
  v10 = 2048;
  v11 = 2048;
  v12 = (_WORD *)((char *)this + 448);
  do
  {
    if ( !v8 )
      break;
    v5 = *v9;
    if ( !(_WORD)v5 )
      break;
    ++v9;
    *v12++ = v5;
    --v8;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  if ( !v11 )
  {
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_95;
    v52 = 169;
    goto LABEL_114;
  }
  v14 = (const wchar_t *)((char *)this + 448);
  v15 = *(unsigned __int16 *)(*((_QWORD *)this + 19) + 68LL);
  if ( (_WORD)v15 )
  {
    if ( *v7 == 47 )
      v14 = (const wchar_t *)((char *)this + 450);
    v51 = (char *)this + 2 * (v15 >> 1);
    if ( *((_WORD *)v51 + 223) == 47 )
      *((_WORD *)v51 + 223) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_Sdi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((_QWORD *)this + 19),
      v5,
      (_DWORD)this + 448,
      *(_DWORD *)(*((_QWORD *)this + 19) + 36LL),
      *(_QWORD *)(*((_QWORD *)this + 19) + 8LL));
  SystemTimeAsFileTime = (struct _FILETIME)*((_QWORD *)this + 10);
  v16 = *(_QWORD *)&SystemTimeAsFileTime + 376LL;
  v64 = *(_QWORD *)&SystemTimeAsFileTime + 376LL;
  (*(void (__fastcall **)(__int64, _WORD *, __int64, unsigned __int16 *))(*(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime
                                                                                    + 376LL)
                                                                        + 16LL))(
    *(_QWORD *)&SystemTimeAsFileTime + 376LL,
    v12,
    v5,
    v9);
  LOBYTE(v65) = 1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&SystemTimeAsFileTime + 376LL) + 16LL))(*(_QWORD *)&SystemTimeAsFileTime + 376LL);
  v17 = *(_DWORD **)(*(_QWORD *)&SystemTimeAsFileTime + 384LL);
  v61 = v17;
  v18 = *(__int64 **)v17;
  v19 = *(__int64 **)(*(_QWORD *)v17 + 8LL);
  if ( !*((_BYTE *)v19 + 25) )
  {
    while ( 1 )
    {
      v20 = v19[4];
      if ( v20 && v14 )
      {
        if ( _wcsicmp((const wchar_t *)v19[4], v14) >= 0 )
        {
LABEL_68:
          v18 = v19;
          v19 = (__int64 *)*v19;
          goto LABEL_19;
        }
      }
      else if ( v20 >= (unsigned __int64)v14 )
      {
        goto LABEL_68;
      }
      v19 = (__int64 *)v19[2];
LABEL_19:
      if ( *((_BYTE *)v19 + 25) )
      {
        v17 = v61;
        break;
      }
    }
  }
  if ( v18 == *(__int64 **)v17 )
    goto LABEL_28;
  if ( v14 && (v21 = (const wchar_t *)v18[4]) != 0 )
  {
    if ( _wcsicmp(v14, v21) < 0 )
    {
      v17 = v61;
LABEL_28:
      v18 = *(__int64 **)v17;
    }
  }
  else if ( (unsigned __int64)v14 < v18[4] )
  {
    goto LABEL_28;
  }
  if ( v18 == **(__int64 ***)(*(_QWORD *)&SystemTimeAsFileTime + 384LL) || *((_BYTE *)v18 + 56) )
  {
    v22 = 0;
    v23 = 0;
  }
  else
  {
    v23 = v18 + 5;
    v22 = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
  if ( !v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    goto LABEL_133;
  }
  v24 = v23[1];
  if ( v24 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v23[1]) )
  {
    SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>::~SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>(&v64);
LABEL_133:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        171,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        (char *)this + 448);
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x194u,
      1u,
      0,
      0,
      0x490u,
      L"HTTP request recieved for URL that we are not listening on",
      (unsigned __int16 *)this + 224);
    return;
  }
  *((_QWORD *)this + 55) = v24;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
  *((_QWORD *)this + 574) = GetTickCount64();
  v26 = *((_QWORD *)this + 19);
  v27 = (unsigned __int64)*(unsigned __int16 *)(v26 + 64) >> 1;
  v28 = *(__int16 **)(v26 + 72);
  do
  {
    if ( !v27 )
      break;
    v29 = *v28;
    if ( !*v28 )
      break;
    ++v28;
    *v7++ = v29;
    --v27;
    --v10;
  }
  while ( v10 );
  v30 = v7 - 1;
  if ( v10 )
    v30 = v7;
  *v30 = 0;
  if ( !v10 )
  {
    v50 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_95;
    v52 = 172;
LABEL_114:
    WPP_SF_(v50[2], v52, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
LABEL_95:
    v60 = L"HTTP URL is too long";
    v59 = 13;
LABEL_96:
    WSManHttpListenerRequest::SendHttpError(this, 0x190u, 1u, 0, 0, v59, v60, (unsigned __int16 *)&Class);
    return;
  }
  memset(v75, 0, sizeof(v75));
  v31 = *((_QWORD *)this + 19);
  v32 = *(_OWORD **)(v31 + 112);
  v75[0] = *v32;
  if ( LOWORD(v75[0]) == 2 )
  {
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        *(unsigned int *)(*(_QWORD *)(v31 + 112) + 4LL));
      goto LABEL_73;
    }
  }
  else
  {
    *(_OWORD *)((char *)v75 + 12) = *(_OWORD *)((char *)v32 + 12);
    v33 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF__IPV6_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, v25, *(_QWORD *)(v31 + 112) + 8LL);
LABEL_73:
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v34 = *(_QWORD *)(*((_QWORD *)this + 19) + 104LL);
  if ( *(_WORD *)v34 == 2 )
  {
    if ( v33 != &WPP_GLOBAL_Control && (*((_DWORD *)v33 + 7) & 0x400) != 0 )
      WPP_SF_d(v33[2], 175, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, *(unsigned int *)(v34 + 4));
  }
  else if ( v33 != &WPP_GLOBAL_Control && (*((_DWORD *)v33 + 7) & 0x400) != 0 )
  {
    WPP_SF__IPV6_(v33[2], 176, v25, v34 + 8);
  }
  v67 = 0;
  v66 = &CErrorContext::`vftable';
  v68 = 0;
  v69 = -1;
  v71 = &Class;
  v72 = &Class;
  v73 = &Class;
  v74 = &Class;
  v70 = 0;
  _InterlockedIncrement(&v67);
  v35 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10) + 16LL)
                                                                      + 112LL))(
                    *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
                    &v66,
                    *((_QWORD *)this + 55));
  v61 = v35;
  if ( !v35 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v66);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, ErrorCode);
    }
    v56 = CErrorContext::GetErrorCode((CErrorContext *)&v66);
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x1F4u,
      1u,
      0,
      0,
      v56,
      L"Getting service configuration",
      (unsigned __int16 *)&Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    return;
  }
  v68 = 0;
  v69 = -1;
  v71 = &Class;
  v72 = &Class;
  v73 = &Class;
  v74 = &Class;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, void ***, _OWORD *, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 10)
                                                                                            + 16LL)
                                                                              + 104LL))(
          *(_QWORD *)(*((_QWORD *)this + 10) + 16LL),
          &v66,
          v75,
          *((_QWORD *)this + 55)) )
  {
    if ( (v68 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v53 = CErrorContext::GetErrorCode((CErrorContext *)&v66);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v53);
      }
      v54 = CErrorContext::GetErrorCode((CErrorContext *)&v66);
      WSManHttpListenerRequest::SendHttpError(
        this,
        0x1F4u,
        1u,
        0,
        0,
        v54,
        L"Request failed to determine if we are listening on the inbound address",
        (unsigned __int16 *)&Class);
      AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      WSManHttpListenerRequest::SendHttpError(
        this,
        0x194u,
        1u,
        0,
        0,
        0x490u,
        L"Request was received on an address we are not accepting requests on",
        (unsigned __int16 *)&Class);
      AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    }
    return;
  }
  v36 = *((_QWORD *)this + 19);
  if ( *(_DWORD *)(v36 + 36) != 6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x195u,
      1u,
      0xAu,
      "POST",
      0xDu,
      L"Request was not a POST message",
      (unsigned __int16 *)&Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    return;
  }
  ConnectionObject = WSManHttpListener::GetConnectionObject(
                       *((WSManHttpListener **)this + 10),
                       (struct _HTTP_REQUEST_V2 *)v36);
  v38 = ConnectionObject;
  *((_QWORD *)this + 14) = ConnectionObject;
  if ( !ConnectionObject )
  {
    LastError = GetLastError();
    WSManHttpListenerRequest::SendHttpError(
      this,
      0x1F4u,
      1u,
      0,
      0,
      LastError,
      L"Failed to create connection object",
      (unsigned __int16 *)&Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    return;
  }
  v39 = (char *)ConnectionObject + 312;
  v64 = (__int64)ConnectionObject + 312;
  v65 = 0;
  v40 = *((_DWORD *)ConnectionObject + 78);
  if ( v40 )
  {
    SetLastError(v40);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)ConnectionObject + 8);
  }
  if ( *((_QWORD *)v38 + 45) )
  {
    if ( *((_QWORD *)v38 + 46) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 169, L"169", 0x54Fu, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        v38,
        *((_QWORD *)v38 + 45),
        this);
    *((_QWORD *)v38 + 45) = this;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        v38,
        this,
        *((_QWORD *)v38 + 46));
    *((_QWORD *)v38 + 45) = this;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qLq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
        v38,
        0,
        *((_QWORD *)v38 + 46));
    v41 = *((_QWORD *)v38 + 46);
    if ( v41 )
    {
      *((_QWORD *)v38 + 46) = 0;
      CWSManCriticalSection::Release((CWSManCriticalSection *)v39);
      v22 = 1;
      v65 = 1;
      v42 = IsErrorRecoverable(0);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v41 + 16LL))(v41, 2 * !v42, 0, 0);
    }
  }
  if ( !v22 )
  {
    if ( *(_DWORD *)v39 )
      SetLastError(*(_DWORD *)v39);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)(v39 + 8));
  }
  if ( *(_WORD *)(*((_QWORD *)this + 19) + 536LL)
    || (unsigned int)WSManHttpListenerRequest::AuthorizationRequired(
                       this,
                       *((struct WSManHttpListenerConnection **)this + 14)) )
  {
    v46 = *((_QWORD *)this + 19);
    v47 = *(unsigned __int16 *)(v46 + 536);
    if ( (_WORD)v47 )
    {
      if ( v47 > *(_DWORD *)(*((_QWORD *)this + 10) + 928LL) )
      {
        WSManHttpListenerRequest::SendHttpError(
          this,
          0x1F4u,
          1u,
          0,
          0,
          0xDu,
          L"Requests authorization header too long",
          (unsigned __int16 *)&Class);
        AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
        return;
      }
      v58 = *(const char **)(v46 + 544);
      if ( v58 )
        WSManHttpListenerRequest::ProcessAuthorization(
          this,
          v58,
          v47,
          *((struct WSManHttpListenerConnection **)this + 14));
      else
        WSManHttpListenerRequest::SendHttpError(
          this,
          0x1F4u,
          1u,
          0,
          0,
          0xDu,
          L"Requests authorization header is invalid",
          (unsigned __int16 *)&Class);
    }
    else
    {
      if ( (unsigned int)WSManHttpListenerRequest::IsIdentifyHeaderPresent(this) )
      {
        WSManHttpListenerRequest::SendIdentifyResponse(this);
        AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
        return;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      if ( WSManHttpListenerRequest::s_limitedAccess && v35[93] )
        WSManHttpListenerRequest::ProcessAuthorizationAnonymousLimitedAccessAuth(
          this,
          *((struct WSManHttpListenerConnection **)this + 14));
      else
        WSManHttpListenerRequest::Send401(this, 0, 0);
    }
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
    return;
  }
  v43 = *((_QWORD *)this + 14);
  if ( !*(_BYTE *)(v43 + 176) )
    goto LABEL_61;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 405, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
  if ( !v43 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 7841, L"7841", 0x54Fu, 0);
    goto LABEL_85;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (SystemTimeAsFileTime.dwLowDateTime
      + (*(_QWORD *)&SystemTimeAsFileTime & 0xFFFFFFFF00000000uLL)
      - (*(_QWORD *)(v43 + 156) & 0xFFFFFFFF00000000uLL)
      - (unsigned int)*(_QWORD *)(v43 + 156))
     / 0x2710 >= *(_QWORD *)(v43 + 168) )
  {
LABEL_85:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    goto LABEL_171;
  }
LABEL_61:
  v44 = 120LL * *(int *)(*((_QWORD *)this + 14) + 180LL);
  v45 = IsEncryptHeader(
          *(const char **)(*((_QWORD *)this + 19) + 352LL),
          *(unsigned __int16 *)(*((_QWORD *)this + 19) + 344LL),
          *(const char **)((char *)&g_authStrings + v44 + 8),
          *(_DWORD *)((char *)&g_authStrings + v44 + 16),
          (const char **)this + 568,
          (unsigned int *)this + 1138,
          (bool *)this + 4556);
  *((_DWORD *)this + 69) = v45;
  if ( !*(_QWORD *)(*((_QWORD *)this + 19) + 840LL) )
  {
    if ( v45 )
    {
      v48 = *((_DWORD *)this + 70);
      if ( (v48 & 0x10) != 0 && (v48 & 4) == 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
        goto LABEL_171;
      }
    }
    else if ( !(*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)v35 + 96LL))(v35) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
LABEL_171:
      WSManHttpListenerRequest::Send401(this, 0, 0);
      AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v61);
      return;
    }
  }
  WSManHttpListenerRequest::GetData(this);
  v49 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v35 + 144LL))(v35);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids, v35, v49);
}

```

## disassembly

```asm
0x180054c30  mov     [rsp-8+arg_10], rbx
0x180054c35  push    rbp
0x180054c36  push    rsi
0x180054c37  push    rdi
0x180054c38  push    r12
0x180054c3a  push    r13
0x180054c3c  push    r14
0x180054c3e  push    r15
0x180054c40  lea     rbp, [rsp-2E0h]
0x180054c48  sub     rsp, 3E0h
0x180054c4f  mov     rax, cs:__security_cookie
0x180054c56  xor     rax, rsp
0x180054c59  mov     [rbp+310h+var_40], rax
0x180054c60  mov     edi, r8d
0x180054c63  mov     ebx, edx
0x180054c65  mov     rsi, rcx
0x180054c68  lea     r14, WPP_GLOBAL_Control
0x180054c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c76  cmp     rcx, r14
0x180054c79  jnz     loc_180055636
0x180054c7f  mov     dl, 1; bool
0x180054c81  mov     rcx, [rsi+50h]; this
0x180054c85  call    ?RequestIsBusy@WSManHttpListener@@QEAAK_N@Z; WSManHttpListener::RequestIsBusy(bool)
0x180054c8a  test    eax, eax
0x180054c8c  jnz     loc_18005550E
0x180054c92  cmp     ebx, 0EAh
0x180054c98  jz      loc_180055C95
0x180054c9e  cmp     ebx, 7Ah ; 'z'
0x180054ca1  jz      loc_180055C95
0x180054ca7  test    ebx, ebx
0x180054ca9  jnz     loc_180055660
0x180054caf  mov     rcx, [rsi+98h]
0x180054cb6  lea     rbx, [rsi+1C0h]
0x180054cbd  movzx   eax, word ptr [rcx+44h]
0x180054cc1  shr     rax, 1
0x180054cc4  mov     r9, [rcx+58h]
0x180054cc8  mov     edi, 800h
0x180054ccd  mov     ecx, edi
0x180054ccf  mov     rdx, rbx
0x180054cd2  test    rax, rax
0x180054cd5  jz      short loc_180054CF6
0x180054cd7  movzx   r8d, word ptr [r9]
0x180054cdb  test    r8w, r8w
0x180054cdf  jz      short loc_180054CF6
0x180054ce1  add     r9, 2
0x180054ce5  mov     [rdx], r8w
0x180054ce9  add     rdx, 2
0x180054ced  dec     rax
0x180054cf0  sub     rcx, 1
0x180054cf4  jnz     short loc_180054CD2
0x180054cf6  lea     rax, [rdx-2]
0x180054cfa  test    rcx, rcx
0x180054cfd  cmovnz  rax, rdx
0x180054d01  xor     r12d, r12d
0x180054d04  mov     [rax], r12w
0x180054d08  test    rcx, rcx
0x180054d0b  jz      loc_18005542B
0x180054d11  mov     r12, rbx
0x180054d14  mov     rax, [rsi+98h]
0x180054d1b  movzx   ecx, word ptr [rax+44h]
0x180054d1f  test    cx, cx
0x180054d22  jnz     loc_180055538
0x180054d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d2f  cmp     rcx, r14
0x180054d32  jnz     loc_180055729
0x180054d38  mov     r14, [rsi+50h]
0x180054d3c  mov     qword ptr [rsp+410h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180054d41  lea     r13, [r14+178h]
0x180054d48  mov     [rsp+410h+var_3B8], r13
0x180054d4d  mov     rax, [r13+0]
0x180054d51  mov     rcx, r13
0x180054d54  mov     rax, [rax+10h]
0x180054d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d5d  mov     byte ptr [rsp+410h+var_3B0], 1
0x180054d62  mov     rax, [r13+0]
0x180054d66  mov     rcx, r13
0x180054d69  mov     rax, [rax+10h]
0x180054d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d72  mov     rcx, [r14+180h]
0x180054d79  mov     [rsp+410h+var_3D0], rcx
0x180054d7e  mov     r15, [rcx]
0x180054d81  mov     r14, [r15+8]
0x180054d85  cmp     byte ptr [r14+19h], 0
0x180054d8a  jnz     short loc_180054DB2
0x180054d8c  mov     rax, [r14+20h]
0x180054d90  test    rax, rax
0x180054d93  jnz     loc_180055226
0x180054d99  cmp     rax, r12
0x180054d9c  jnb     loc_1800551D5
0x180054da2  mov     r14, [r14+10h]
0x180054da6  cmp     byte ptr [r14+19h], 0
0x180054dab  jz      short loc_180054D8C
0x180054dad  mov     rcx, [rsp+410h+var_3D0]
0x180054db2  cmp     r15, [rcx]
0x180054db5  jz      short loc_180054DE2
0x180054db7  test    r12, r12
0x180054dba  jnz     short loc_180054DC4
0x180054dbc  cmp     r12, [r15+20h]
0x180054dc0  jnb     short loc_180054DE5
0x180054dc2  jmp     short loc_180054DE2
0x180054dc4  mov     rdx, [r15+20h]; String2
0x180054dc8  test    rdx, rdx
0x180054dcb  jz      short loc_180054DBC
0x180054dcd  mov     rcx, r12; String1
0x180054dd0  call    cs:__imp__wcsicmp
0x180054dd6  shr     eax, 1Fh
0x180054dd9  test    al, al
0x180054ddb  jz      short loc_180054DE5
0x180054ddd  mov     rcx, [rsp+410h+var_3D0]
0x180054de2  mov     r15, [rcx]
0x180054de5  mov     rax, qword ptr [rsp+410h+SystemTimeAsFileTime.dwLowDateTime]
0x180054dea  mov     rax, [rax+180h]
0x180054df1  cmp     r15, [rax]
0x180054df4  jnz     loc_1800551E0
0x180054dfa  xor     r12d, r12d
0x180054dfd  mov     r15d, r12d
0x180054e00  mov     rax, [r13+0]
0x180054e04  mov     rcx, r13
0x180054e07  mov     rax, [rax+18h]
0x180054e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e10  nop
0x180054e11  test    r15, r15
0x180054e14  jz      loc_18005575E
0x180054e1a  mov     r14, [r15+8]
0x180054e1e  test    r14, r14
0x180054e21  jnz     loc_180055771
0x180054e27  mov     [rsi+1B8h], r14
0x180054e2e  mov     rax, [r13+0]
0x180054e32  mov     rcx, r13
0x180054e35  mov     rax, [rax+18h]
0x180054e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e3e  nop
0x180054e3f  call    cs:__imp_GetTickCount64
0x180054e45  mov     [rsi+11F0h], rax
0x180054e4c  mov     rax, [rsi+98h]
0x180054e53  movzx   ecx, word ptr [rax+40h]
0x180054e57  shr     rcx, 1
0x180054e5a  mov     rdx, [rax+48h]
0x180054e5e  xchg    ax, ax
0x180054e60  test    rcx, rcx
0x180054e63  jz      short loc_180054E81
0x180054e65  movzx   eax, word ptr [rdx]
0x180054e68  test    ax, ax
0x180054e6b  jz      short loc_180054E81
0x180054e6d  add     rdx, 2
0x180054e71  mov     [rbx], ax
0x180054e74  add     rbx, 2
0x180054e78  dec     rcx
0x180054e7b  sub     rdi, 1
0x180054e7f  jnz     short loc_180054E60
0x180054e81  lea     rax, [rbx-2]
0x180054e85  test    rdi, rdi
0x180054e88  cmovnz  rax, rbx
0x180054e8c  mov     [rax], r12w
0x180054e90  jz      loc_180055568
0x180054e96  xorps   xmm0, xmm0
0x180054e99  movups  [rbp+310h+var_360], xmm0
0x180054e9d  movups  [rbp+310h+var_350], xmm0
0x180054ea1  movups  [rbp+310h+var_340], xmm0
0x180054ea5  movups  [rbp+310h+var_330], xmm0
0x180054ea9  movups  [rbp+310h+var_320], xmm0
0x180054ead  movups  [rbp+310h+var_310], xmm0
0x180054eb1  movups  [rbp+310h+var_300], xmm0
0x180054eb5  movups  [rbp+310h+var_2F0], xmm0
0x180054eb9  mov     r9, [rsi+98h]
0x180054ec0  mov     rax, [r9+70h]
0x180054ec4  mov     ebx, 2
0x180054ec9  movups  xmm0, xmmword ptr [rax]
0x180054ecc  cmp     bx, [rax]
0x180054ecf  movaps  [rbp+310h+var_360], xmm0
0x180054ed3  jz      loc_1800557EE
0x180054ed9  movups  xmm1, xmmword ptr [rax+0Ch]
0x180054edd  movups  [rbp+310h+var_360+0Ch], xmm1
0x180054ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ee8  lea     r13, WPP_GLOBAL_Control
0x180054eef  cmp     rcx, r13
0x180054ef2  jnz     loc_1800551F7
0x180054ef8  mov     rax, [rsi+98h]
0x180054eff  mov     r9, [rax+68h]
0x180054f03  cmp     bx, [r9]
0x180054f07  jz      loc_180055834
0x180054f0d  cmp     rcx, r13
0x180054f10  jnz     loc_180055475
0x180054f16  mov     [rsp+410h+var_398], r12d
0x180054f1b  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180054f22  mov     [rsp+410h+var_3A0], rax
0x180054f27  mov     [rbp+310h+var_390], r12d
0x180054f2b  mov     [rbp+310h+var_38C], 0FFFFFFFFh
0x180054f32  lea     r14, Class
0x180054f39  mov     [rbp+310h+var_380], r14
0x180054f3d  mov     [rbp+310h+var_378], r14
0x180054f41  mov     [rbp+310h+var_370], r14
0x180054f45  mov     [rbp+310h+var_368], r14
0x180054f49  mov     [rbp+310h+var_388], 0
0x180054f4d  lock inc [rsp+410h+var_398]
0x180054f52  mov     rax, [rsi+50h]
0x180054f56  mov     rcx, [rax+10h]
0x180054f5a  mov     rax, [rcx]
0x180054f5d  mov     r8, [rsi+1B8h]
0x180054f64  lea     rdx, [rsp+410h+var_3A0]
0x180054f69  mov     rax, [rax+70h]
0x180054f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f72  mov     r15, rax
0x180054f75  mov     [rsp+410h+var_3D0], rax
0x180054f7a  test    rax, rax
0x180054f7d  jz      loc_180055868
0x180054f83  mov     [rbp+310h+var_390], r12d
0x180054f87  mov     [rbp+310h+var_38C], 0FFFFFFFFh
0x180054f8e  mov     [rbp+310h+var_380], r14
0x180054f92  mov     [rbp+310h+var_378], r14
0x180054f96  mov     [rbp+310h+var_370], r14
0x180054f9a  mov     [rbp+310h+var_368], r14
0x180054f9e  mov     rax, [rsi+50h]
0x180054fa2  mov     rcx, [rax+10h]
0x180054fa6  mov     rax, [rcx]
0x180054fa9  mov     r9, [rsi+1B8h]
0x180054fb0  lea     r8, [rbp+310h+var_360]
0x180054fb4  lea     rdx, [rsp+410h+var_3A0]
0x180054fb9  mov     rax, [rax+68h]
0x180054fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fc2  test    al, al
0x180054fc4  jz      loc_1800555A6
0x180054fca  mov     rdx, [rsi+98h]; struct _HTTP_REQUEST_V2 *
0x180054fd1  cmp     dword ptr [rdx+24h], 6
0x180054fd5  jnz     loc_18005595A
0x180054fdb  mov     rcx, [rsi+50h]; this
0x180054fdf  call    ?GetConnectionObject@WSManHttpListener@@QEAAPEAVWSManHttpListenerConnection@@PEAU_HTTP_REQUEST_V2@@@Z; WSManHttpListener::GetConnectionObject(_HTTP_REQUEST_V2 *)
0x180054fe4  mov     rbx, rax
0x180054fe7  mov     [rsi+70h], rax
0x180054feb  test    rax, rax
0x180054fee  jz      loc_1800559D0
0x180054ff4  lea     rdi, [rax+138h]
0x180054ffb  mov     [rsp+410h+var_3B8], rdi
0x180055000  mov     [rsp+410h+var_3B0], r12d
0x180055005  mov     ecx, [rdi]; dwErrCode
0x180055007  test    ecx, ecx
0x180055009  jnz     loc_180055247
0x18005500f  lea     rcx, [rdi+8]; lpCriticalSection
0x180055013  call    cs:__imp_EnterCriticalSection
0x180055019  nop
0x18005501a  cmp     qword ptr [rbx+168h], 0
0x180055022  jnz     loc_180055A14
0x180055028  mov     rcx, cs:WPP_GLOBAL_Control
0x18005502f  cmp     rcx, r13
0x180055032  jnz     loc_180055A8F
0x180055038  mov     [rbx+168h], rsi
0x18005503f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055046  cmp     rcx, r13
0x180055049  jnz     loc_180055ACA
0x18005504f  mov     r13, [rbx+170h]
0x180055056  test    r13, r13
0x180055059  jz      short loc_18005509C
0x18005505b  xor     eax, eax
0x18005505d  mov     [rbx+170h], rax
0x180055064  mov     rcx, rdi; this
0x180055067  call    ?Release@CWSManCriticalSection@@QEAAXXZ; CWSManCriticalSection::Release(void)
0x18005506c  mov     r12d, 1
0x180055072  mov     [rsp+410h+var_3B0], r12d
0x180055077  xor     ecx, ecx; unsigned int
0x180055079  call    ?IsErrorRecoverable@@YA_NK@Z; IsErrorRecoverable(ulong)
0x18005507e  movzx   edx, al
0x180055081  xor     edx, r12d
0x180055084  add     edx, edx
0x180055086  mov     rax, [r13+0]
0x18005508a  xor     r9d, r9d
0x18005508d  xor     r8d, r8d
0x180055090  mov     rcx, r13
0x180055093  mov     rax, [rax+10h]
0x180055097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005509c  lea     r13, WPP_GLOBAL_Control
0x1800550a3  test    r12d, r12d
0x1800550a6  jnz     short loc_1800550BC
0x1800550a8  mov     ecx, [rdi]; dwErrCode
0x1800550aa  test    ecx, ecx
0x1800550ac  jnz     loc_180055279
0x1800550b2  lea     rcx, [rdi+8]; lpCriticalSection
0x1800550b6  call    cs:__imp_LeaveCriticalSection
0x1800550bc  mov     rax, [rsi+98h]
0x1800550c3  cmp     word ptr [rax+218h], 0
0x1800550cb  jnz     loc_180055284
0x1800550d1  mov     rdx, [rsi+70h]; struct WSManHttpListenerConnection *
0x1800550d5  mov     rcx, rsi; this
0x1800550d8  call    ?AuthorizationRequired@WSManHttpListenerRequest@@AEAAHPEAVWSManHttpListenerConnection@@@Z; WSManHttpListenerRequest::AuthorizationRequired(WSManHttpListenerConnection *)
0x1800550dd  test    eax, eax
0x1800550df  jnz     loc_180055284
0x1800550e5  mov     rbx, [rsi+70h]
0x1800550e9  cmp     [rbx+0B0h], al
0x1800550ef  jnz     loc_1800552F4
0x1800550f5  mov     rax, [rsi+70h]
0x1800550f9  movsxd  rcx, dword ptr [rax+0B4h]
0x180055100  imul    r8, rcx, 78h ; 'x'
0x180055104  mov     rcx, [rsi+98h]
0x18005510b  lea     rax, [rsi+11CCh]
0x180055112  lea     r9, [rsi+11C8h]
0x180055119  lea     r10, [rsi+11C0h]
0x180055120  lea     r11, ?g_authStrings@@3PAU_AUTHENTICATION_STRINGS@@A; _AUTHENTICATION_STRINGS near * g_authStrings
0x180055127  movzx   edx, word ptr [rcx+158h]; unsigned int
0x18005512e  mov     [rsp+410h+var_3E0], rax; bool *
0x180055133  mov     [rsp+410h+var_3E8], r9; unsigned int *
0x180055138  mov     [rsp+410h+var_3F0], r10; char **
  ... truncated ...
```
