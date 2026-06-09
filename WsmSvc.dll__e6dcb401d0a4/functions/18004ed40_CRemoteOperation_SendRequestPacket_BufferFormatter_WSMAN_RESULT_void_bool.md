# CRemoteOperation::SendRequestPacket(BufferFormatter &,_WSMAN_RESULT *,void *,bool)

- ea: `0x18004ed40`
- end: `0x18004f966`
- name: `?SendRequestPacket@CRemoteOperation@@QEAAHAEAVBufferFormatter@@PEAU_WSMAN_RESULT@@PEAX_N@Z`
- size: `3110`
- prototype: `__int64 __fastcall(CRemoteOperation *__hidden this, struct BufferFormatter *, struct _WSMAN_RESULT *, void *, bool)`
- caller_count: `10`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180030be4`
- `0x180050680`
- `0x1800d2568`
- `0x1800fa540`
- `0x180142e1c`
- `0x180143a80`
- `0x180144110`
- `0x180144770`
- `0x18014762c`
- `0x180148564`

## callees

- `0x180005d10`
- `0x180019950`
- `0x18002c580`
- `0x18004a900`
- `0x18004e0d0`
- `0x18004ed40`
- `0x18004f96c`
- `0x18004fa5c`
- `0x18004fbc0`
- `0x18005d800`
- `0x18005df20`
- `0x180071cdc`
- `0x18007ec20`
- `0x180080470`
- `0x180080810`
- `0x1800a38d0`
- `0x18010d8c6`
- `0x180112380`
- `0x180112460`
- `0x18011349c`
- `0x18011a6d4`
- `0x180123604`
- `0x180134238`
- `0x1801a403c`
- `0x1801a4220`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004edfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f19e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f308`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f33c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f43d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f4a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004edfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f19e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f2d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f308`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f33c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f43d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f404`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004eef5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004eef5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f27e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f27e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ef9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f004`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ef9c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004f004`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004f1b7`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18004f1b7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004f13a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004f13a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f38d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f936`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f38d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f936`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004ef5f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004ef5f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004f466`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004f466`
- `ntdll!EtwEventEnabled` at `0x18004ee77`
- `ntdll!EtwEventEnabled` at `0x18004ee77`

## string_xrefs

- `0x18004f2f5`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18004f329`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18004f761`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18004f790`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall CRemoteOperation::SendRequestPacket(
        CRemoteOperation *this,
        struct BufferFormatter *a2,
        struct _WSMAN_RESULT *a3,
        void *a4,
        bool a5)
{
  struct _WSMAN_RESULT *v6; // rdi
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(struct BufferFormatter *); // rax
  unsigned int v11; // edi
  __int64 v12; // rsi
  __int64 v13; // rdx
  DWORD v14; // r15d
  DWORD v15; // edi
  bool v16; // si
  DWORD v17; // eax
  __int64 v18; // rsi
  SIZE_T v19; // r13
  PSLIST_ENTRY v20; // rax
  CHeap *v21; // rcx
  struct Packet *v22; // rdi
  struct Packet *v23; // r15
  CHeap *v24; // rcx
  void *Handle; // rax
  const void *v26; // rsi
  CHeap *v27; // rcx
  void *v28; // rax
  LPVOID v29; // rsi
  void *v30; // rcx
  CHAR *v31; // rsi
  unsigned int v32; // edi
  const void *v33; // rax
  char *v34; // rdx
  __int64 v35; // r14
  void *Heap; // rax
  bool v38; // di
  PVOID *v39; // rcx
  int v40; // eax
  struct IChannel *inited; // rsi
  unsigned int v42; // esi
  __int64 v43; // r15
  DWORD LastError; // eax
  unsigned int v45; // edi
  const unsigned __int16 *v46; // rax
  unsigned int v47; // edi
  const char *v48; // rax
  int v49; // [rsp+20h] [rbp-71h]
  struct Packet *v50; // [rsp+50h] [rbp-41h] BYREF
  CWSManCriticalSectionWithConditionVar *v51; // [rsp+58h] [rbp-39h] BYREF
  int v52; // [rsp+60h] [rbp-31h]
  void **v53; // [rsp+70h] [rbp-21h] BYREF
  signed __int32 v54[4]; // [rsp+78h] [rbp-19h] BYREF
  char v55; // [rsp+88h] [rbp-9h]
  const wchar_t *v56; // [rsp+90h] [rbp-1h]
  const wchar_t *v57; // [rsp+98h] [rbp+7h]
  const wchar_t *v58; // [rsp+A0h] [rbp+Fh]
  const wchar_t *v59; // [rsp+A8h] [rbp+17h]
  LARGE_INTEGER PerformanceCount; // [rsp+F0h] [rbp+5Fh] BYREF
  struct _WSMAN_RESULT *v61; // [rsp+100h] [rbp+6Fh]

  v61 = a3;
  v6 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
      this,
      *((_DWORD *)this + 13531));
  v9 = *((_QWORD *)this + 6776);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 88LL))(v9);
  v10 = *(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 72LL);
  if ( *((_BYTE *)this + 424) )
  {
    v42 = v10(a2);
    v43 = (*(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 56LL))(a2);
    LastError = GetLastError();
    PerformanceCount.LowPart = LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 3) != 0 )
    {
      LOBYTE(v49) = 0;
      TraceSoapMessageW(1, 1, v43, v42 >> 1, v49);
      LastError = PerformanceCount.LowPart;
    }
    SetLastError(LastError);
    if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_SOAP_CLIENT_SENDING) )
    {
      v45 = (*(unsigned int (__fastcall **)(struct BufferFormatter *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, 0) >> 1;
      v46 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 56LL))(a2);
      WSMan::EventHandler::WriteSoapW(&LOG_WSMAN_AN_SOAP_CLIENT_SENDING, v46, v45);
      v6 = v61;
    }
  }
  else
  {
    v11 = v10(a2);
    v12 = (*(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 56LL))(a2);
    v14 = GetLastError();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 3) != 0 )
      TraceSoapMessageA(1, v13, v12, v11);
    SetLastError(v14);
    v15 = GetLastError();
    v54[0] = 0;
    v53 = &CErrorContext::`vftable';
    v54[2] = 0;
    v54[3] = -1;
    v56 = &Class;
    v57 = &Class;
    v58 = &Class;
    v59 = &Class;
    v55 = 0;
    _InterlockedIncrement(v54);
    if ( !g_eventHandler )
      ILoader<WSMan::EventHandler>::CreateInstance(&g_eventHandler, &v53);
    if ( g_eventHandler )
    {
      if ( *(_QWORD *)g_eventHandler )
      {
        v16 = (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_eventHandler, &LOG_WSMAN_AN_SOAP_CLIENT_SENDING_UTF8) != 0;
      }
      else
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmaneventhandler.cpp", 644, L"644", 0x54Fu, 0);
        v16 = 0;
      }
      SetLastError(v15);
      if ( v16 )
      {
        v47 = (*(__int64 (__fastcall **)(struct BufferFormatter *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, 0);
        v48 = (const char *)(*(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 56LL))(a2);
        WSMan::EventHandler::WriteSoapA(&LOG_WSMAN_AN_SOAP_CLIENT_SENDING_UTF8, v48, v47);
      }
    }
    else
    {
      SetLastError(v15);
    }
    v6 = v61;
  }
  if ( !*((_QWORD *)this + 75) )
  {
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\cremoteoperation.cpp",
      2057,
      L"2057",
      0x54Fu,
      *((struct IRequestContext **)this + 76));
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
      (LARGE_INTEGER)PerformanceCount.QuadPart,
      this);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(CRemoteOperation *))(*(_QWORD *)this + 312LL))(this) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 76) + 24LL))(*((_QWORD *)this + 76));
    return 0;
  }
  v51 = (CRemoteOperation *)((char *)this + 328);
  v52 = 0;
  v17 = *((_DWORD *)this + 82);
  if ( v17 )
  {
    SetLastError(v17);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  }
  if ( (*(unsigned __int8 (__fastcall **)(CRemoteOperation *, CWSManCriticalSectionWithConditionVar **))(*(_QWORD *)this + 80LL))(
         this,
         &v51) )
  {
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v51);
    return 1;
  }
  if ( *((_BYTE *)this + 54120) )
  {
    if ( !*((_BYTE *)this + 54121) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          91,
          WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
          this,
          *((_QWORD *)this + 17));
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 76) + 72LL))(*((_QWORD *)this + 76), 995);
      goto LABEL_115;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
        this,
        *((_QWORD *)this + 17));
    *((_BYTE *)this + 54121) = 0;
  }
  *((_QWORD *)this + 48) = v6;
  *((_QWORD *)this + 52) = a4;
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 96LL))(*((_QWORD *)this + 75));
  v19 = (*(unsigned int (__fastcall **)(struct BufferFormatter *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, 0);
  v20 = InterlockedPopEntrySList((PSLIST_HEADER)(v18 + 16));
  v22 = (struct Packet *)&v20[-1];
  if ( !v20 )
    v22 = 0;
  if ( v22 )
  {
    v23 = v22;
    v50 = v22;
    goto LABEL_30;
  }
  if ( CHeap::GetHandle(v21) )
  {
    Handle = CHeap::GetHandle(v24);
    v22 = (struct Packet *)HeapAlloc(Handle, 0, 0x40u);
    if ( v22 )
    {
      *(_QWORD *)v22 = &Packet::`vftable';
      *((_QWORD *)v22 + 4) = 0;
      *((_QWORD *)v22 + 5) = 0;
      *((_DWORD *)v22 + 12) = 0;
      *((_QWORD *)v22 + 3) = v18;
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 32));
      goto LABEL_29;
    }
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
  }
  v22 = 0;
LABEL_29:
  v23 = v22;
  v50 = v22;
  if ( !v22 )
  {
LABEL_102:
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 76) + 72LL))(*((_QWORD *)this + 76), 14);
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v51);
    return 0;
  }
LABEL_30:
  v26 = (const void *)*((_QWORD *)v22 + 4);
  if ( v26 )
  {
    Heap = WSManMemory::GetHeap();
    if ( HeapSize(Heap, 0, v26) >= v19 )
    {
      v29 = (LPVOID)*((_QWORD *)v22 + 4);
      goto LABEL_36;
    }
  }
  if ( !CHeap::GetHandle(v21) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
    goto LABEL_119;
  }
  v28 = CHeap::GetHandle(v27);
  v29 = HeapAlloc(v28, 0, v19);
  if ( !v29 )
  {
LABEL_119:
    Packet::Recycle(v22);
    goto LABEL_102;
  }
  v30 = (void *)*((_QWORD *)v22 + 4);
  if ( v30 )
    WSManMemory::Free(v30, 0);
  *((_QWORD *)v22 + 4) = v29;
LABEL_36:
  *((_QWORD *)v22 + 5) = v29;
  *((_DWORD *)v22 + 12) = v19;
  v31 = (CHAR *)Buf1;
  if ( *((_QWORD *)v23 + 5) )
    v31 = (CHAR *)*((_QWORD *)v23 + 5);
  v32 = (*(__int64 (__fastcall **)(struct BufferFormatter *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, 0);
  v33 = (const void *)(*(__int64 (__fastcall **)(struct BufferFormatter *))(*(_QWORD *)a2 + 56LL))(a2);
  memcpy_0(v31, v33, v32);
  if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 72LL))(*((_QWORD *)this + 75)) & 0x1000) == 0 )
    goto LABEL_39;
  if ( !(unsigned int)CRemoteOperation::CompressOutboundPacket(this, &v50) )
  {
    if ( v50 )
      (**(void (__fastcall ***)(struct Packet *, __int64))v50)(v50, 1);
LABEL_115:
    InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v51);
    return 0;
  }
  v23 = v50;
LABEL_39:
  (**(void (__fastcall ***)(CRemoteOperation *))this)(this);
  if ( *((_QWORD *)this + 17) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\cremoteoperation.cpp", 2123, L"2123", 0x54Fu, 0);
  LOBYTE(PerformanceCount.LowPart) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
      *((_QWORD *)this + 76));
  v34 = (char *)this + 128;
  if ( !this )
    v34 = 0;
  LOBYTE(v49) = 1;
  v35 = (*(__int64 (__fastcall **)(void ***, char *, _QWORD, CRemoteOperation *, int, _BYTE, _DWORD, LARGE_INTEGER *))g_RobustConnectionChannelFactory[0])(
          g_RobustConnectionChannelFactory,
          v34,
          *((_QWORD *)this + 76),
          this,
          v49,
          *((_BYTE *)this + 54108),
          0,
          &PerformanceCount);
  if ( v35 )
  {
    if ( !*((_QWORD *)this + 6799) )
      *((_QWORD *)this + 6799) = v23;
    (**(void (__fastcall ***)(CRemoteOperation *))this)(this);
    if ( v35 != *((_QWORD *)this + 17) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\cremoteoperation.cpp", 2151, L"2151", 0x54Fu, 0);
    CRemoteOperation::ReleasePreviousChannelData(this);
    v38 = 0;
    if ( a5 )
      v38 = LOBYTE(PerformanceCount.LowPart) == 0;
    v39 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_qdddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
        this,
        1,
        *((_DWORD *)this + 13604),
        *((_DWORD *)this + 80),
        v38);
      goto LABEL_123;
    }
    while ( 1 )
    {
      v40 = *((unsigned __int8 *)this + 54444);
      if ( !(_BYTE)v40 && *((_QWORD *)this + 6802) == 1 )
        break;
      if ( *((_BYTE *)this + 54445) )
        break;
      if ( v39 != &WPP_GLOBAL_Control && (*((_DWORD *)v39 + 7) & 0x400) != 0 )
        WPP_SF_qLd(v39[2], 121, WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids, this, v40, 0);
      if ( CWSManCriticalSectionWithConditionVar::WaitForConditionVar(v51, 0xFFFFFFFF) )
      {
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\cremoteoperation.cpp",
          3154,
          L"3154",
          0x54Fu,
          0);
        break;
      }
LABEL_123:
      v39 = (PVOID *)WPP_GLOBAL_Control;
    }
    inited = CRemoteOperation::InitSend(this);
    if ( v38 )
    {
      if ( *((_DWORD *)this + 13534) )
        WSManError(
          (wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\cremoteoperation.cpp",
          3166,
          L"3166",
          0x54Fu,
          0);
      *((_DWORD *)this + 13534) = 1;
      *((_QWORD *)this + 6768) = inited;
      *((_QWORD *)this + 6769) = v23;
      *((_DWORD *)this + 13540) = 4;
    }
    CWSManCriticalSectionWithConditionVar::WakeAllWaitingForConditionVar(v51);
    if ( *(_DWORD *)v51 )
      SetLastError(*(_DWORD *)v51);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v51 + 8));
    v52 = 1;
    if ( v38 )
    {
      SubmitThreadpoolWork(*((PTP_WORK *)this + 6766));
    }
    else if ( inited )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids, this, v23);
      (*(void (__fastcall **)(struct IChannel *, struct Packet *, __int64))(*(_QWORD *)inited + 16LL))(inited, v23, 4);
    }
    else
    {
      (*(void (__fastcall **)(char *, __int64, _QWORD, _QWORD))(*((_QWORD *)this + 16) + 16LL))(
        (char *)this + 128,
        3,
        0,
        0);
    }
  }
  if ( !v52 )
  {
    if ( *(_DWORD *)v51 )
    {
      SetLastError(*(_DWORD *)v51);
      WSManError(
        (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
        102,
        L"102",
        0x54Fu,
        0);
    }
    else
    {
      WakeAllConditionVariable((PCONDITION_VARIABLE)v51 + 6);
    }
    if ( *(_DWORD *)v51 )
      SetLastError(*(_DWORD *)v51);
    else
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v51 + 8));
  }
  if ( !v35 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids);
    Packet::Recycle(v23);
    (*(void (__fastcall **)(CRemoteOperation *, _QWORD, _QWORD))(*(_QWORD *)this + 8LL))(this, 0, 0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      WPP_1f9f6943463233aa4758943dc4921c1f_Traceguids,
      (LARGE_INTEGER)PerformanceCount.QuadPart,
      this);
  }
  return v35 != 0;
}

```

## disassembly

```asm
0x18004ed40  mov     [rsp-8+arg_8], rbx
0x18004ed45  mov     [rsp-8+arg_10], r8
0x18004ed4a  push    rbp
0x18004ed4b  push    rsi
0x18004ed4c  push    rdi
0x18004ed4d  push    r12
0x18004ed4f  push    r13
0x18004ed51  push    r14
0x18004ed53  push    r15
0x18004ed55  lea     rbp, [rsp-1Fh]
0x18004ed5a  sub     rsp, 0B0h
0x18004ed61  mov     r13, r9
0x18004ed64  mov     rdi, r8
0x18004ed67  mov     r14, rdx
0x18004ed6a  mov     rbx, rcx
0x18004ed6d  lea     rax, WPP_GLOBAL_Control
0x18004ed74  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed7b  cmp     rcx, rax
0x18004ed7e  jnz     loc_18004F347
0x18004ed84  mov     rcx, [rbx+0D3C0h]
0x18004ed8b  test    rcx, rcx
0x18004ed8e  jz      short loc_18004ED9C
0x18004ed90  mov     rax, [rcx]
0x18004ed93  mov     rax, [rax+58h]
0x18004ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed9c  mov     rax, [r14]
0x18004ed9f  mov     rax, [rax+48h]
0x18004eda3  xor     edx, edx
0x18004eda5  mov     rcx, r14
0x18004eda8  cmp     [rbx+1A8h], dl
0x18004edae  jnz     loc_18004F3EB
0x18004edb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edb9  mov     edi, eax
0x18004edbb  mov     rcx, [r14]
0x18004edbe  mov     rax, [rcx+38h]
0x18004edc2  mov     rcx, r14
0x18004edc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edca  mov     rsi, rax
0x18004edcd  call    cs:__imp_GetLastError
0x18004edd3  mov     r15d, eax
0x18004edd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eddd  mov     r12d, 1
0x18004ede3  test    byte ptr [rcx+1Ch], 3
0x18004ede7  jz      short loc_18004EDF7
0x18004ede9  mov     r9d, edi
0x18004edec  mov     r8, rsi
0x18004edef  mov     ecx, r12d
0x18004edf2  call    ?TraceSoapMessageA@@YAXW4TraceRole@@W4TraceDirection@@PEBDK@Z; TraceSoapMessageA(TraceRole,TraceDirection,char const *,ulong)
0x18004edf7  mov     ecx, r15d; dwErrCode
0x18004edfa  call    cs:__imp_SetLastError
0x18004ee00  call    cs:__imp_GetLastError
0x18004ee06  mov     edi, eax
0x18004ee08  xor     r15d, r15d
0x18004ee0b  mov     [rbp+4Fh+var_68], r15d
0x18004ee0f  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x18004ee16  mov     [rbp+4Fh+var_70], rax
0x18004ee1a  mov     [rbp+4Fh+var_60], r15d
0x18004ee1e  mov     [rbp+4Fh+var_5C], 0FFFFFFFFh
0x18004ee25  lea     rax, Class
0x18004ee2c  mov     [rbp+4Fh+var_50], rax
0x18004ee30  mov     [rbp+4Fh+var_48], rax
0x18004ee34  mov     [rbp+4Fh+var_40], rax
0x18004ee38  mov     [rbp+4Fh+var_38], rax
0x18004ee3c  mov     [rbp+4Fh+var_58], r15b
0x18004ee40  lock inc [rbp+4Fh+var_68]
0x18004ee44  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18004ee4b  test    rax, rax
0x18004ee4e  jz      loc_18004F5A6
0x18004ee54  mov     rax, cs:?g_eventHandler@@3V?$Loader@VEventHandler@WSMan@@$00@@A; Loader<WSMan::EventHandler,1> g_eventHandler
0x18004ee5b  test    rax, rax
0x18004ee5e  jz      loc_18004F19C
0x18004ee64  mov     rcx, [rax]
0x18004ee67  test    rcx, rcx
0x18004ee6a  jz      loc_18004F552
0x18004ee70  lea     rdx, LOG_WSMAN_AN_SOAP_CLIENT_SENDING_UTF8
0x18004ee77  call    cs:__imp_EtwEventEnabled
0x18004ee7d  test    al, al
0x18004ee7f  setnz   sil
0x18004ee83  mov     ecx, edi; dwErrCode
0x18004ee85  call    cs:__imp_SetLastError
0x18004ee8b  nop
0x18004ee8c  test    sil, sil
0x18004ee8f  jnz     loc_18004F5FA
0x18004ee95  mov     rdi, [rbp+4Fh+arg_10]
0x18004ee99  cmp     qword ptr [rbx+258h], 0
0x18004eea1  jz      loc_18004F633
0x18004eea7  mov     rax, cs:WPP_GLOBAL_Control
0x18004eeae  lea     rsi, WPP_GLOBAL_Control
0x18004eeb5  cmp     rax, rsi
0x18004eeb8  jnz     loc_18004F37B
0x18004eebe  mov     rax, [rbx]
0x18004eec1  mov     rcx, rbx
0x18004eec4  mov     rax, [rax+138h]
0x18004eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eed0  test    al, al
0x18004eed2  jz      loc_18004F664
0x18004eed8  lea     rcx, [rbx+148h]
0x18004eedf  mov     [rbp+4Fh+var_88], rcx
0x18004eee3  mov     [rbp+4Fh+var_80], r15d
0x18004eee7  mov     eax, [rcx]
0x18004eee9  test    eax, eax
0x18004eeeb  jnz     loc_18004F2D6
0x18004eef1  add     rcx, 8; lpCriticalSection
0x18004eef5  call    cs:__imp_EnterCriticalSection
0x18004eefb  nop
0x18004eefc  mov     rcx, [rbx]
0x18004eeff  mov     rax, [rcx+50h]
0x18004ef03  lea     rdx, [rbp+4Fh+var_88]
0x18004ef07  mov     rcx, rbx
0x18004ef0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef0f  test    al, al
0x18004ef11  jnz     loc_18004F67E
0x18004ef17  cmp     [rbx+0D368h], al
0x18004ef1d  jnz     loc_18004F68F
0x18004ef23  mov     [rbx+180h], rdi
0x18004ef2a  mov     [rbx+1A0h], r13
0x18004ef31  mov     rcx, [rbx+258h]
0x18004ef38  mov     rax, [rcx]
0x18004ef3b  mov     rax, [rax+60h]
0x18004ef3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef44  mov     rsi, rax
0x18004ef47  mov     rcx, [r14]
0x18004ef4a  mov     rax, [rcx+48h]
0x18004ef4e  xor     edx, edx
0x18004ef50  mov     rcx, r14
0x18004ef53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef58  mov     r13d, eax
0x18004ef5b  lea     rcx, [rsi+10h]; ListHead
0x18004ef5f  call    cs:__imp_InterlockedPopEntrySList
0x18004ef65  lea     rdi, [rax-10h]
0x18004ef69  test    rax, rax
0x18004ef6c  cmovz   rdi, r15
0x18004ef70  test    rdi, rdi
0x18004ef73  jz      short loc_18004EF7E
0x18004ef75  mov     r15, rdi
0x18004ef78  mov     [rbp+4Fh+var_90], rdi
0x18004ef7c  jmp     short loc_18004EFDC
0x18004ef7e  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004ef83  test    rax, rax
0x18004ef86  jz      loc_18004F74A
0x18004ef8c  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004ef91  xor     edx, edx; dwFlags
0x18004ef93  mov     r8d, 40h ; '@'; dwBytes
0x18004ef99  mov     rcx, rax; hHeap
0x18004ef9c  call    cs:__imp_HeapAlloc
0x18004efa2  mov     rdi, rax
0x18004efa5  test    rax, rax
0x18004efa8  jz      loc_18004F76D
0x18004efae  lea     rax, ??_7Packet@@6B@; const Packet::`vftable'
0x18004efb5  mov     [rdi], rax
0x18004efb8  mov     [rdi+20h], r15
0x18004efbc  mov     [rdi+28h], r15
0x18004efc0  mov     [rdi+30h], r15d
0x18004efc4  mov     [rdi+18h], rsi
0x18004efc8  lock inc dword ptr [rsi+20h]
0x18004efcc  mov     r15, rdi
0x18004efcf  mov     [rbp+4Fh+var_90], rdi
0x18004efd3  test    rdi, rdi
0x18004efd6  jz      loc_18004F57D
0x18004efdc  mov     rsi, [rdi+20h]
0x18004efe0  test    rsi, rsi
0x18004efe3  jnz     loc_18004F1AA
0x18004efe9  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004efee  test    rax, rax
0x18004eff1  jz      loc_18004F775
0x18004eff7  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18004effc  mov     r8, r13; dwBytes
0x18004efff  xor     edx, edx; dwFlags
0x18004f001  mov     rcx, rax; hHeap
0x18004f004  call    cs:__imp_HeapAlloc
0x18004f00a  mov     rsi, rax
0x18004f00d  test    rax, rax
0x18004f010  jz      loc_18004F79C
0x18004f016  mov     rcx, [rdi+20h]; void *
0x18004f01a  test    rcx, rcx
0x18004f01d  jnz     loc_18004F7A9
0x18004f023  mov     [rdi+20h], rsi
0x18004f027  mov     [rdi+28h], rsi
0x18004f02b  mov     [rdi+30h], r13d
0x18004f02f  mov     rax, [r15+28h]
0x18004f033  lea     rsi, Buf1
0x18004f03a  test    rax, rax
0x18004f03d  cmovnz  rsi, rax
0x18004f041  mov     rax, [r14]
0x18004f044  xor     edx, edx
0x18004f046  mov     rcx, r14
0x18004f049  mov     rax, [rax+48h]
0x18004f04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f052  mov     edi, eax
0x18004f054  mov     rax, [r14]
0x18004f057  mov     rcx, r14
0x18004f05a  mov     rax, [rax+38h]
0x18004f05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f063  mov     rdx, rax; Src
0x18004f066  mov     r8d, edi; Size
0x18004f069  mov     rcx, rsi; void *
0x18004f06c  call    memcpy_0
0x18004f071  mov     rcx, [rbx+258h]
0x18004f078  mov     rax, [rcx]
0x18004f07b  mov     rax, [rax+48h]
0x18004f07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f084  bt      eax, 0Ch
0x18004f088  jb      loc_18004F535
0x18004f08e  mov     rax, [rbx]
0x18004f091  mov     rcx, rbx
0x18004f094  mov     rax, [rax]
0x18004f097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f09c  cmp     qword ptr [rbx+88h], 0
0x18004f0a4  jnz     loc_18004F7C7
0x18004f0aa  mov     byte ptr [rbp+4Fh+PerformanceCount], 0
0x18004f0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0b5  lea     rsi, WPP_GLOBAL_Control
0x18004f0bc  cmp     rcx, rsi
0x18004f0bf  jnz     loc_18004F3BD
0x18004f0c5  lea     rdx, [rbx+80h]
0x18004f0cc  xor     eax, eax
0x18004f0ce  test    rbx, rbx
0x18004f0d1  cmovz   rdx, rax
0x18004f0d5  mov     rax, cs:?g_RobustConnectionChannelFactory@@3VRobustConnectionChannelFactory@@A; RobustConnectionChannelFactory g_RobustConnectionChannelFactory
0x18004f0dc  lea     rcx, [rbp+4Fh+PerformanceCount]
0x18004f0e0  mov     [rsp+0E0h+var_A8], rcx
0x18004f0e5  mov     [rsp+0E0h+var_B0], 0
0x18004f0ed  movzx   ecx, byte ptr [rbx+0D35Ch]
0x18004f0f4  mov     byte ptr [rsp+0E0h+var_B8], cl
0x18004f0f8  mov     byte ptr [rsp+0E0h+var_C0], 1
0x18004f0fd  mov     r9, rbx
0x18004f100  mov     r8, [rbx+260h]
0x18004f107  lea     rcx, ?g_RobustConnectionChannelFactory@@3VRobustConnectionChannelFactory@@A; RobustConnectionChannelFactory g_RobustConnectionChannelFactory
0x18004f10e  mov     rax, [rax]
0x18004f111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f116  mov     r14, rax
0x18004f119  test    rax, rax
0x18004f11c  jnz     loc_18004F1CF
0x18004f122  cmp     [rbp+4Fh+var_80], 0
0x18004f126  jnz     short loc_18004F159
0x18004f128  mov     rcx, [rbp+4Fh+var_88]
0x18004f12c  mov     eax, [rcx]
0x18004f12e  test    eax, eax
0x18004f130  jnz     loc_18004F306
0x18004f136  add     rcx, 30h ; '0'; ConditionVariable
0x18004f13a  call    cs:__imp_WakeAllConditionVariable
0x18004f140  mov     rcx, [rbp+4Fh+var_88]
0x18004f144  mov     eax, [rcx]
0x18004f146  test    eax, eax
0x18004f148  jnz     loc_18004F33A
0x18004f14e  add     rcx, 8; lpCriticalSection
0x18004f152  call    cs:__imp_LeaveCriticalSection
0x18004f158  nop
0x18004f159  test    r14, r14
0x18004f15c  jz      loc_18004F8DF
0x18004f162  mov     rax, cs:WPP_GLOBAL_Control
0x18004f169  cmp     rax, rsi
0x18004f16c  jz      short loc_18004F178
0x18004f16e  test    byte ptr [rax+1Ch], 40h
0x18004f172  jnz     loc_18004F92A
0x18004f178  xor     eax, eax
0x18004f17a  test    r14, r14
0x18004f17d  cmovnz  eax, r12d
0x18004f181  mov     rbx, [rsp+0E0h+arg_8]
0x18004f189  add     rsp, 0B0h
0x18004f190  pop     r15
0x18004f192  pop     r14
0x18004f194  pop     r13
0x18004f196  pop     r12
0x18004f198  pop     rdi
0x18004f199  pop     rsi
0x18004f19a  pop     rbp
0x18004f19b  retn
0x18004f19c  mov     ecx, edi; dwErrCode
0x18004f19e  call    cs:__imp_SetLastError
0x18004f1a4  nop
0x18004f1a5  jmp     loc_18004EE95
0x18004f1aa  call    ?GetHeap@WSManMemory@@SAPEAXXZ; WSManMemory::GetHeap(void)
0x18004f1af  mov     r8, rsi; lpMem
0x18004f1b2  xor     edx, edx; dwFlags
0x18004f1b4  mov     rcx, rax; hHeap
0x18004f1b7  call    cs:__imp_HeapSize
0x18004f1bd  cmp     rax, r13
0x18004f1c0  jb      loc_18004EFE9
0x18004f1c6  mov     rsi, [rdi+20h]
0x18004f1ca  jmp     loc_18004F027
0x18004f1cf  cmp     qword ptr [rbx+0D478h], 0
0x18004f1d7  jnz     short loc_18004F1E0
0x18004f1d9  mov     [rbx+0D478h], r15
0x18004f1e0  mov     rcx, [rbx]
0x18004f1e3  mov     rax, [rcx]
0x18004f1e6  mov     rcx, rbx
0x18004f1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1ee  cmp     r14, [rbx+88h]
0x18004f1f5  jnz     loc_18004F7F3
0x18004f1fb  mov     rcx, rbx; this
0x18004f1fe  call    ?ReleasePreviousChannelData@CRemoteOperation@@AEAAXXZ; CRemoteOperation::ReleasePreviousChannelData(void)
0x18004f203  xor     dil, dil
0x18004f206  cmp     [rbp+4Fh+arg_20], 1
0x18004f20a  jnz     short loc_18004F218
0x18004f20c  movzx   edi, dil
0x18004f210  cmp     byte ptr [rbp+4Fh+PerformanceCount], 0
0x18004f214  cmovz   edi, r12d
0x18004f218  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f21f  cmp     rcx, rsi
  ... truncated ...
```
