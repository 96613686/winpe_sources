# FSService::Initialize(IFSEventLogger *,void *,ulong)

- ea: `0x1800102d0`
- end: `0x180010a16`
- name: `?Initialize@FSService@@UEAAJPEAUIFSEventLogger@@PEAXK@Z`
- size: `1862`
- prototype: `__int64 __fastcall(FSService *__hidden this, struct IFSEventLogger *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800014e0`
- `0x18000162c`
- `0x180003e20`
- `0x180009494`
- `0x180009608`
- `0x180009658`
- `0x18000a018`
- `0x18000a5b8`
- `0x18000a6b0`
- `0x18000a8e4`
- `0x180010268`
- `0x1800102d0`
- `0x180012b68`
- `0x1800148f4`
- `0x1800176b4`
- `0x1800185a4`
- `0x180018998`
- `0x180019044`
- `0x18002685c`
- `0x18002a3e4`
- `0x180050ee0`
- `0x180052fe8`
- `0x1800547bc`
- `0x180054840`
- `0x1800565d0`
- `0x180056944`
- `0x180063cac`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800105f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800105ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800105ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800104a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108a1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001088f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001088f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800108d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800108d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001045e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001045e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010467`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010495`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180010495`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001042f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001042f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180010363`
- `MFPlat!MFLockSharedWorkQueue` at `0x180010684`
- `MFPlat!MFLockSharedWorkQueue` at `0x180010684`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x1800106be`
- `MFPlat!MFAllocateSerialWorkQueue` at `0x1800106be`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x1800106fd`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x1800106fd`
- `MFPlat!MFSetMinimumMemoryAlignment` at `0x180010602`
- `MFPlat!MFSetMinimumMemoryAlignment` at `0x180010602`

## pseudocode

```c
__int64 __fastcall FSService::Initialize(FSService *this, struct IFSEventLogger *a2, void *a3, int a4)
{
  bool v4; // bl
  signed int v9; // edi
  __int64 v10; // rdx
  HRESULT Guid; // eax
  __int64 v12; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v14; // rax
  signed int LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int Instance; // eax
  __int64 v19; // rdx
  struct CallStackTracing *v20; // rdi
  __int64 v21; // rcx
  DWORD v22; // ecx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  struct _FILETIME v26; // rcx
  struct wil::details::wnf_subscription_state_base *v27; // rdx
  bool v28; // al
  RPC_BINDING_VECTOR *v29; // rdx
  const char *v30; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  const wchar_t *v36; // rax
  const wchar_t *v37; // rax
  bool v39; // [rsp+40h] [rbp-C0h]
  DWORD pID; // [rsp+44h] [rbp-BCh] BYREF
  struct _FILETIME pftDueTime; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwTaskId; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  char *v44; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v46[8]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v47[14]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  pdwTaskId = 0;
  v39 = 0;
  pID = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qqqD(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, a3, this, a2, a3, a4);
  InitializeWatchdogTimers();
  GetSystemInfo(&SystemInfo);
  if ( ((SystemInfo.dwPageSize - 1) & SystemInfo.dwPageSize) == 0 )
  {
    CFSLock::Lock((FSService *)((char *)this + 64), this, -1072875850, 0, 0);
    if ( !a3 )
    {
      v9 = -2147024809;
      if ( g_wppLevels )
      {
        v10 = 25;
LABEL_9:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v9);
        goto LABEL_86;
      }
      goto LABEL_86;
    }
    if ( *((_DWORD *)this + 244) )
    {
      v9 = -1072871856;
      if ( g_wppLevels )
      {
        v10 = 26;
        goto LABEL_9;
      }
LABEL_86:
      CFSLock::Unlock((FSService *)((char *)this + 64));
      goto LABEL_87;
    }
    Guid = CoCreateGuid((GUID *)((char *)this + 44));
    v9 = Guid;
    if ( Guid < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_86;
      v12 = 27;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, Guid);
      goto LABEL_86;
    }
    *(_QWORD *)((char *)this + 1052) = 0;
    CurrentProcess = GetCurrentProcess();
    v14 = GetCurrentProcess();
    if ( !DuplicateHandle(v14, a3, CurrentProcess, (LPHANDLE)this + 125, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_25:
          CFSLock::Unlock((FSService *)((char *)this + 64));
          v4 = v39;
          goto LABEL_87;
        }
        v16 = 28;
LABEL_24:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v9);
        goto LABEL_25;
      }
    }
    v17 = *((_QWORD *)this + 118);
    *((_QWORD *)this + 118) = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IFSEventLogger *))(*(_QWORD *)a2 + 8LL))(a2);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_DWORD *)this + 248) = a4;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraTelemetryTracking>::GetImpl'::`2'::impl)
      && (wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 1192),
          Instance = FSStatsFactory::CreateFSStatsFactory((struct IFSStatsFactory **)this + 149),
          v9 = Instance,
          Instance < 0) )
    {
      if ( !g_wppLevels )
        goto LABEL_25;
      v19 = 29;
    }
    else
    {
      v39 = IsProcessInContainer();
      v4 = v39;
      if ( !v39 )
        v9 = AutoMF::Initialize((FSService *)((char *)this + 1200));
      if ( v9 == -2147467263 || v39 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        ThreadpoolTimer = CreateThreadpoolTimer(FSService::TimerCallback, this, 0);
        *((_QWORD *)this + 136) = ThreadpoolTimer;
        if ( !ThreadpoolTimer )
        {
          v32 = GetLastError();
          v9 = v32;
          if ( v32 > 0 )
            v9 = (unsigned __int16)v32 | 0x80070000;
          if ( !g_wppLevels )
            goto LABEL_86;
          v10 = 30;
          goto LABEL_9;
        }
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
        v9 = 0;
        goto LABEL_86;
      }
      if ( v9 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 31;
          goto LABEL_9;
        }
        goto LABEL_86;
      }
      v20 = CallStackTracing::s_wpInstance;
      if ( CallStackTracing::s_wpInstance
        || (CallStackTracing::InitInstance(), (v20 = CallStackTracing::s_wpInstance) != 0) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v20 + 16));
        *((_BYTE *)v20 + 8) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v20 + 16));
      }
      Guid = MFSetMinimumMemoryAlignment(SystemInfo.dwPageSize);
      v9 = Guid;
      if ( Guid < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_86;
        v12 = 32;
        goto LABEL_17;
      }
      Guid = FSInitializeClientContext(SystemInfo.dwPageSize);
      v9 = Guid;
      if ( Guid < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_86;
        v12 = 33;
        goto LABEL_17;
      }
      Guid = FSVMInitialize(v21, SystemInfo.dwPageSize);
      v9 = Guid;
      if ( Guid < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_86;
        v12 = 34;
        goto LABEL_17;
      }
      Guid = MFLockSharedWorkQueue(L"Capture", 0, &pdwTaskId, &pID);
      v9 = Guid;
      if ( Guid < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_86;
        v12 = 35;
        goto LABEL_17;
      }
      v22 = pID;
      *((_DWORD *)this + 241) = pID;
      pID = 0;
      Guid = MFAllocateSerialWorkQueue(v22, &pID);
      v9 = Guid;
      if ( Guid < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_86;
        v12 = 36;
        goto LABEL_17;
      }
      *((_DWORD *)this + 242) = pID;
      if ( MFRegisterPlatformWithMMCSS(L"Audio", &pdwTaskId, -2) >= 0 )
      {
        *((_DWORD *)this + 243) = pdwTaskId;
        *((_BYTE *)this + 960) = 1;
      }
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 1096);
      Instance = FSPowerMonitor::CreateInstance((struct IFSPowerMonitor **)this + 137);
      v9 = Instance;
      if ( Instance >= 0 )
      {
        v47[1] = this;
        v47[0] = off_1800EB0D8;
        pftDueTime = 0;
        v47[13] = v47;
        v25 = wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v23, v46, v24, &pftDueTime);
        v26 = 0;
        if ( v25 >= 0 )
          v26 = pftDueTime;
        pftDueTime = v26;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
          (_QWORD *)this + 135,
          &pftDueTime);
        wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(
          (wil::details **)&pftDueTime,
          v27);
        wistd::function<void (void)>::~function<void (void)>(v46);
        if ( !*((_QWORD *)this + 135) )
        {
          v9 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_25;
          v16 = 39;
          goto LABEL_24;
        }
        v28 = FSIsStateSeparated();
        *((_BYTE *)this + 1050) = v28;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v30 = "state_separated_sku";
          if ( !v28 )
            v30 = "non_state_separated_sku";
          WPP_SF_qs(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            40,
            (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
            (_DWORD)this,
            (__int64)v30);
        }
        Instance = FSService::RegisterRpcInterface(this, v29);
        v9 = Instance;
        if ( Instance >= 0 )
        {
          *((_DWORD *)this + 244) = 1;
          Instance = FSService::InternalStartIdleTimer(this);
          v9 = Instance;
          if ( Instance >= 0 || !g_wppLevels )
            goto LABEL_25;
          v19 = 42;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_25;
          v19 = 41;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_25;
        v19 = 37;
      }
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
      this,
      Instance);
    goto LABEL_25;
  }
  v9 = -2147418113;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
      this,
      -2147418113);
LABEL_87:
  if ( dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
  {
    pftDueTime.dwLowDateTime = v9;
    v44 = (char *)this + 44;
    v43 = 50331648;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v33,
      (__int64)&byte_180102BC7,
      v34,
      v35,
      &v44,
      (__int64)&v43,
      (__int64)&pftDueTime);
  }
  if ( v9 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v37 = L"true";
      if ( !v4 )
        v37 = (const wchar_t *)L"false";
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        44,
        (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        (_DWORD)this,
        v9,
        (__int64)v37);
    }
  }
  else
  {
    if ( byte_18010EC4D )
    {
      v36 = L"true";
      if ( !v4 )
        v36 = (const wchar_t *)L"false";
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        43,
        (unsigned int)&WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        (_DWORD)this,
        v9,
        (__int64)v36);
    }
    (*(void (__fastcall **)(FSService *))(*(_QWORD *)this + 64LL))(this);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800102d0  mov     [rsp-8+arg_18], rbx
0x1800102d5  push    rbp
0x1800102d6  push    rsi
0x1800102d7  push    rdi
0x1800102d8  push    r12
0x1800102da  push    r13
0x1800102dc  push    r14
0x1800102de  push    r15
0x1800102e0  lea     rbp, [rsp-20h]
0x1800102e5  sub     rsp, 120h
0x1800102ec  mov     rax, cs:__security_cookie
0x1800102f3  xor     rax, rsp
0x1800102f6  mov     [rbp+50h+var_40], rax
0x1800102fa  xor     edi, edi
0x1800102fc  xorps   xmm0, xmm0
0x1800102ff  mov     bl, dil
0x180010302  mov     [rsp+150h+pdwTaskId], edi
0x180010306  mov     [rsp+150h+var_110], bl
0x18001030a  mov     r13d, r9d
0x18001030d  mov     r12, r8
0x180010310  mov     [rsp+150h+pID], edi
0x180010314  mov     r15, rdx
0x180010317  mov     rsi, rcx
0x18001031a  movups  xmmword ptr [rsp+150h+SystemInfo], xmm0
0x18001031f  movups  xmmword ptr [rsp+150h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180010324  movups  xmmword ptr [rbp+50h+SystemInfo.dwNumberOfProcessors], xmm0
0x180010328  cmp     cs:byte_18010EC4D, 8
0x18001032f  jb      short loc_180010359
0x180010331  mov     [rsp+150h+dwOptions], r9d
0x180010336  lea     edx, [rdi+17h]
0x180010339  mov     r9, rcx
0x18001033c  mov     qword ptr [rsp+150h+bInheritHandle], r8
0x180010341  mov     rcx, cs:WPP_GLOBAL_Control
0x180010348  mov     qword ptr [rsp+150h+dwDesiredAccess], r15
0x18001034d  mov     rcx, [rcx+0D8h]
0x180010354  call    WPP_SF_qqqD
0x180010359  call    ?InitializeWatchdogTimers@@YAXXZ; InitializeWatchdogTimers(void)
0x18001035e  lea     rcx, [rsp+150h+SystemInfo]; lpSystemInfo
0x180010363  call    cs:__imp_GetSystemInfo
0x180010369  mov     ecx, [rsp+150h+SystemInfo.dwPageSize]
0x18001036d  lea     eax, [rcx-1]
0x180010370  test    ecx, eax
0x180010372  jz      short loc_1800103AE
0x180010374  mov     edi, 8000FFFFh
0x180010379  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010380  jb      loc_1800108E4
0x180010386  mov     rcx, cs:WPP_GLOBAL_Control
0x18001038d  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180010394  mov     edx, 18h
0x180010399  mov     [rsp+150h+dwDesiredAccess], edi
0x18001039d  mov     r9, rsi
0x1800103a0  mov     rcx, [rcx+10h]
0x1800103a4  call    WPP_SF_qD
0x1800103a9  jmp     loc_1800108E4
0x1800103ae  lea     r14, [rsi+40h]
0x1800103b2  mov     qword ptr [rsp+150h+dwDesiredAccess], rdi; unsigned __int64 *
0x1800103b7  mov     rcx, r14; this
0x1800103ba  xor     r9d, r9d; unsigned int
0x1800103bd  mov     r8d, 0C00D36B6h; int
0x1800103c3  mov     rdx, rsi; void *
0x1800103c6  call    ?Lock@CFSLock@@QEAAXPEAXJKPEA_K@Z; CFSLock::Lock(void *,long,ulong,unsigned __int64 *)
0x1800103cb  test    r12, r12
0x1800103ce  jnz     short loc_18001040A
0x1800103d0  mov     edi, 80070057h
0x1800103d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800103dc  jb      loc_1800108DC
0x1800103e2  lea     edx, [r12+19h]
0x1800103e7  mov     [rsp+150h+dwDesiredAccess], edi
0x1800103eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103f2  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x1800103f9  mov     r9, rsi
0x1800103fc  mov     rcx, [rcx+10h]
0x180010400  call    WPP_SF_qD
0x180010405  jmp     loc_1800108DC
0x18001040a  cmp     [rsi+3D0h], edi
0x180010410  jz      short loc_18001042B
0x180010412  mov     edi, 0C00D4650h
0x180010417  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001041e  jb      loc_1800108DC
0x180010424  mov     edx, 1Ah
0x180010429  jmp     short loc_1800103E7
0x18001042b  lea     rcx, [rsi+2Ch]; pguid
0x18001042f  call    cs:__imp_CoCreateGuid
0x180010435  mov     edi, eax
0x180010437  test    eax, eax
0x180010439  jns     short loc_180010453
0x18001043b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010442  jb      loc_1800108DC
0x180010448  mov     edx, 1Bh
0x18001044d  mov     [rsp+150h+dwDesiredAccess], eax
0x180010451  jmp     short loc_1800103EB
0x180010453  mov     qword ptr [rsi+41Ch], 0
0x18001045e  call    cs:__imp_GetCurrentProcess
0x180010464  mov     rbx, rax
0x180010467  call    cs:__imp_GetCurrentProcess
0x18001046d  mov     [rsp+150h+dwOptions], 2; dwOptions
0x180010475  lea     r9, [rsi+3E8h]; lpTargetHandle
0x18001047c  mov     rcx, rax; hSourceProcessHandle
0x18001047f  mov     [rsp+150h+bInheritHandle], 0; bInheritHandle
0x180010487  mov     r8, rbx; hTargetProcessHandle
0x18001048a  mov     [rsp+150h+dwDesiredAccess], 0; dwDesiredAccess
0x180010492  mov     rdx, r12; hSourceHandle
0x180010495  call    cs:__imp_DuplicateHandle
0x18001049b  mov     r12d, 80070000h
0x1800104a1  test    eax, eax
0x1800104a3  jnz     short loc_1800104F8
0x1800104a5  call    cs:__imp_GetLastError
0x1800104ab  mov     edi, eax
0x1800104ad  test    eax, eax
0x1800104af  jle     short loc_1800104B7
0x1800104b1  movzx   edi, ax
0x1800104b4  or      edi, r12d
0x1800104b7  test    edi, edi
0x1800104b9  jns     short loc_1800104F8
0x1800104bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800104c2  jb      short loc_1800104E7
0x1800104c4  mov     edx, 1Ch
0x1800104c9  mov     [rsp+150h+dwDesiredAccess], edi
0x1800104cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800104d4  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x1800104db  mov     r9, rsi
0x1800104de  mov     rcx, [rcx+10h]
0x1800104e2  call    WPP_SF_qD
0x1800104e7  mov     rcx, r14; this
0x1800104ea  call    ?Unlock@CFSLock@@QEAAXXZ; CFSLock::Unlock(void)
0x1800104ef  mov     bl, [rsp+150h+var_110]
0x1800104f3  jmp     loc_1800108E4
0x1800104f8  mov     rbx, [rsi+3B0h]
0x1800104ff  mov     [rsi+3B0h], r15
0x180010506  test    r15, r15
0x180010509  jz      short loc_18001051A
0x18001050b  mov     rax, [r15]
0x18001050e  mov     rcx, r15
0x180010511  mov     rax, [rax+8]
0x180010515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001051a  test    rbx, rbx
0x18001051d  jz      short loc_18001052E
0x18001051f  mov     rax, [rbx]
0x180010522  mov     rcx, rbx
0x180010525  mov     rax, [rax+10h]
0x180010529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001052e  mov     [rsi+3E0h], r13d
0x180010535  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking> `wil::Feature<__WilFeatureTraits_Feature_CameraTelemetryTracking>::GetImpl(void)'::`2'::impl
0x18001053c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraTelemetryTracking@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking>::__private_IsEnabled(void)
0x180010541  test    al, al
0x180010543  jz      short loc_18001057D
0x180010545  lea     rbx, [rsi+4A8h]
0x18001054c  mov     rcx, rbx
0x18001054f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010554  mov     rcx, rbx; struct IFSStatsFactory **
0x180010557  call    ?CreateFSStatsFactory@FSStatsFactory@@SAJPEAPEAUIFSStatsFactory@@@Z; FSStatsFactory::CreateFSStatsFactory(IFSStatsFactory * *)
0x18001055c  mov     edi, eax
0x18001055e  test    eax, eax
0x180010560  jns     short loc_18001057D
0x180010562  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010569  jb      loc_1800104E7
0x18001056f  mov     edx, 1Dh
0x180010574  mov     [rsp+150h+dwDesiredAccess], eax
0x180010578  jmp     loc_1800104CD
0x18001057d  call    ?IsProcessInContainer@@YA_NXZ; IsProcessInContainer(void)
0x180010582  mov     [rsp+150h+var_110], al
0x180010586  mov     bl, al
0x180010588  test    al, al
0x18001058a  jnz     short loc_18001059A
0x18001058c  lea     rcx, [rsi+4B0h]; this
0x180010593  call    ?Initialize@AutoMF@@QEAAJXZ; AutoMF::Initialize(void)
0x180010598  mov     edi, eax
0x18001059a  cmp     edi, 80004001h
0x1800105a0  jz      loc_180010879
0x1800105a6  test    bl, bl
0x1800105a8  jnz     loc_180010879
0x1800105ae  test    edi, edi
0x1800105b0  jns     short loc_1800105C9
0x1800105b2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800105b9  jb      loc_1800108DC
0x1800105bf  mov     edx, 1Fh
0x1800105c4  jmp     loc_1800103E7
0x1800105c9  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800105d0  test    rdi, rdi
0x1800105d3  jnz     short loc_1800105E6
0x1800105d5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800105da  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800105e1  test    rdi, rdi
0x1800105e4  jz      short loc_1800105FE
0x1800105e6  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800105ea  call    cs:__imp_EnterCriticalSection
0x1800105f0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800105f4  mov     byte ptr [rdi+8], 0
0x1800105f8  call    cs:__imp_LeaveCriticalSection
0x1800105fe  mov     ecx, [rsp+150h+SystemInfo.dwPageSize]
0x180010602  call    cs:__imp_MFSetMinimumMemoryAlignment
0x180010608  mov     edi, eax
0x18001060a  test    eax, eax
0x18001060c  jns     short loc_180010625
0x18001060e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010615  jb      loc_1800108DC
0x18001061b  mov     edx, 20h ; ' '
0x180010620  jmp     loc_18001044D
0x180010625  mov     ecx, [rsp+150h+SystemInfo.dwPageSize]
0x180010629  call    FSInitializeClientContext
0x18001062e  mov     edi, eax
0x180010630  test    eax, eax
0x180010632  jns     short loc_18001064B
0x180010634  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001063b  jb      loc_1800108DC
0x180010641  mov     edx, 21h ; '!'
0x180010646  jmp     loc_18001044D
0x18001064b  mov     edx, [rsp+150h+SystemInfo.dwPageSize]
0x18001064f  call    FSVMInitialize
0x180010654  mov     edi, eax
0x180010656  test    eax, eax
0x180010658  jns     short loc_180010671
0x18001065a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010661  jb      loc_1800108DC
0x180010667  mov     edx, 22h ; '"'
0x18001066c  jmp     loc_18001044D
0x180010671  lea     r9, [rsp+150h+pID]; pID
0x180010676  xor     edx, edx; BasePriority
0x180010678  lea     r8, [rsp+150h+pdwTaskId]; pdwTaskId
0x18001067d  lea     rcx, wszClass; "Capture"
0x180010684  call    cs:__imp_MFLockSharedWorkQueue
0x18001068a  mov     edi, eax
0x18001068c  test    eax, eax
0x18001068e  jns     short loc_1800106A7
0x180010690  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010697  jb      loc_1800108DC
0x18001069d  mov     edx, 23h ; '#'
0x1800106a2  jmp     loc_18001044D
0x1800106a7  mov     ecx, [rsp+150h+pID]; dwWorkQueue
0x1800106ab  lea     rdx, [rsp+150h+pID]; pdwWorkQueue
0x1800106b0  mov     [rsi+3C4h], ecx
0x1800106b6  mov     [rsp+150h+pID], 0
0x1800106be  call    cs:__imp_MFAllocateSerialWorkQueue
0x1800106c4  mov     edi, eax
0x1800106c6  test    eax, eax
0x1800106c8  jns     short loc_1800106E1
0x1800106ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800106d1  jb      loc_1800108DC
0x1800106d7  mov     edx, 24h ; '$'
0x1800106dc  jmp     loc_18001044D
0x1800106e1  mov     eax, [rsp+150h+pID]
0x1800106e5  lea     rdx, [rsp+150h+pdwTaskId]; pdwTaskId
0x1800106ea  mov     r8d, 0FFFFFFFEh; lPriority
0x1800106f0  mov     [rsi+3C8h], eax
0x1800106f6  lea     rcx, aAudio; "Audio"
0x1800106fd  call    cs:__imp_MFRegisterPlatformWithMMCSS
0x180010703  test    eax, eax
0x180010705  js      short loc_180010718
0x180010707  mov     eax, [rsp+150h+pdwTaskId]
0x18001070b  mov     [rsi+3CCh], eax
0x180010711  mov     byte ptr [rsi+3C0h], 1
0x180010718  lea     rbx, [rsi+448h]
0x18001071f  mov     rcx, rbx
0x180010722  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180010727  mov     rcx, rbx; struct IFSPowerMonitor **
0x18001072a  call    ?CreateInstance@FSPowerMonitor@@SAJPEAPEAUIFSPowerMonitor@@@Z; FSPowerMonitor::CreateInstance(IFSPowerMonitor * *)
0x18001072f  mov     edi, eax
0x180010731  test    eax, eax
0x180010733  jns     short loc_18001074C
0x180010735  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001073c  jb      loc_1800104E7
0x180010742  mov     edx, 25h ; '%'
0x180010747  jmp     loc_180010574
0x18001074c  lea     rax, off_1800EB0D8
0x180010753  mov     [rbp+50h+var_A8], rsi
0x180010757  mov     [rbp+50h+var_B0], rax
0x18001075b  lea     r9, [rsp+150h+pftDueTime]
0x180010760  lea     rax, [rbp+50h+var_B0]
0x180010764  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], 0
0x18001076d  lea     rdx, [rbp+50h+var_B8]
0x180010771  mov     [rbp+50h+var_48], rax
0x180010775  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x18001077a  xor     ecx, ecx
0x18001077c  lea     rbx, [rsi+438h]
0x180010783  test    eax, eax
0x180010785  lea     rdx, [rsp+150h+pftDueTime]
0x18001078a  cmovns  rcx, qword ptr [rsp+150h+pftDueTime.dwLowDateTime]
0x180010790  mov     qword ptr [rsp+150h+pftDueTime.dwLowDateTime], rcx
0x180010795  mov     rcx, rbx
0x180010798  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x18001079d  lea     rcx, [rsp+150h+pftDueTime]
0x1800107a2  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800107a7  lea     rcx, [rbp+50h+var_B8]
0x1800107ab  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x1800107b0  cmp     qword ptr [rbx], 0
0x1800107b4  jnz     short loc_1800107D2
0x1800107b6  mov     edi, 8007000Eh
0x1800107bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800107c2  jb      loc_1800104E7
0x1800107c8  mov     edx, 27h ; '''
0x1800107cd  jmp     loc_1800104C9
0x1800107d2  call    ?FSIsStateSeparated@@YA_NXZ; FSIsStateSeparated(void)
0x1800107d7  mov     [rsi+41Ah], al
0x1800107dd  cmp     cs:byte_18010EC4D, 8
0x1800107e4  jb      short loc_180010821
0x1800107e6  lea     rdx, aNonStateSepara; "non_state_separated_sku"
0x1800107ed  test    al, al
0x1800107ef  lea     rcx, aStateSeparated; "state_separated_sku"
0x1800107f6  mov     r9, rsi
0x1800107f9  cmovz   rcx, rdx
  ... truncated ...
```
