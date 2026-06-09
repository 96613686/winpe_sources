# TsiInitialize(void)

- ea: `0x180015544`
- end: `0x1800159bb`
- name: `?TsiInitialize@@YAJXZ`
- size: `1143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016120`

## callees

- `0x180005c30`
- `0x180006870`
- `0x18000e970`
- `0x18000ea40`
- `0x18000eeb0`
- `0x180010094`
- `0x180015544`
- `0x180015c24`
- `0x180017308`
- `0x1800173c0`
- `0x18001939c`
- `0x180020530`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015829`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015847`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015866`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015885`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015829`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015847`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015866`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015885`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800158a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800158d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800158d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800158ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800158ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800158e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800158e8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800158b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800158b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015656`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015656`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015695`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015695`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015760`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800157d6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800157d6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800157bc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800157bc`

## string_xrefs

- `0x1800157cf`: `WptsExtensions.dll`
- `0x18001581b`: `WptsCreateAction`
- `0x180015858`: `WptsCopyActionData`
- `0x180015648`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\WP\TaskScheduler\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 TsiInitialize(void)
{
  __int64 v0; // rcx
  __int64 v1; // r8
  char v2; // al
  HKEY v3; // rax
  PdcManager *v4; // rcx
  PdcManager *v5; // rdi
  HKEY v6; // rbx
  signed int LastError; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v11; // ebx
  struct _ActionExtFunctions *v12; // rax
  struct _TP_POOL *Threadpool; // rax
  int v14; // edx
  CScheduleMgr *v15; // rcx
  int v16; // r8d
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  DWORD cbData; // [rsp+40h] [rbp-158h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-150h] BYREF
  _BYTE TimeZoneInformation[176]; // [rsp+60h] [rbp-138h] BYREF
  _BYTE v21[16]; // [rsp+170h] [rbp-28h] BYREF

  McGenEventRegister_EventRegister();
  v2 = Microsoft_WindowsPhone_TaskSchedulerEnableBits;
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 4) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(v0, ServiceInitializeStarted, v1, 1, v21);
    v2 = Microsoft_WindowsPhone_TaskSchedulerEnableBits;
  }
  if ( (v2 & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v0, ServiceInitializePhase1Started, v1, 1, v21);
  if ( (int)TsiValidateAndConfigureRegistry() < 0 )
    return 2147500037LL;
  v3 = (HKEY)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = (PdcManager *)v3;
  hKey[1] = v3;
  if ( v3 )
  {
    *(_QWORD *)v3 = 0;
    v6 = v3 + 2;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 1) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,PDC_ENTRY *>>>::_Buyheadnode();
    *((_BYTE *)v5 + 24) = 0;
    std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(v6);
  }
  else
  {
    v5 = 0;
  }
  g_PdcManager = v5;
  if ( !v5 )
    return 2147500037LL;
  PdcManager::Initialize(v4);
  hKey[0] = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_szTaskSchedulerParametersRegPath, 0, 0x2001Bu, hKey) )
    return 2147500037LL;
  cbData = 176;
  if ( !RegQueryValueExW(hKey[0], L"TimeZoneInfo", 0, 0, (LPBYTE)&g_CurrentTimeZoneInfo, &cbData) && cbData == 176 )
  {
LABEL_20:
    v11 = 0;
    RegCloseKey(hKey[0]);
    g_hModuleWptsExtensions = LoadLibraryW(L"WptsExtensions.dll");
    if ( g_hModuleWptsExtensions )
    {
      v12 = (struct _ActionExtFunctions *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      ActionExtensionFunctionTable = v12;
      if ( v12 )
      {
        *(_OWORD *)v12 = 0;
        *((_OWORD *)v12 + 1) = 0;
        *((_QWORD *)v12 + 4) = 0;
        *(_QWORD *)ActionExtensionFunctionTable = GetProcAddress(g_hModuleWptsExtensions, "WptsCreateAction");
        *((_QWORD *)ActionExtensionFunctionTable + 1) = GetProcAddress(g_hModuleWptsExtensions, "WptsDestroyAction");
        *((_QWORD *)ActionExtensionFunctionTable + 2) = GetProcAddress(g_hModuleWptsExtensions, "WptsCopyActionData");
        *((_QWORD *)ActionExtensionFunctionTable + 3) = GetProcAddress(g_hModuleWptsExtensions, "WptsFreeActionData");
        *((_QWORD *)ActionExtensionFunctionTable + 4) = GetProcAddress(g_hModuleWptsExtensions, "WptsLaunchAction");
      }
    }
    Threadpool = CreateThreadpool(0);
    ThreadPool = Threadpool;
    if ( Threadpool )
    {
      if ( SetThreadpoolThreadMinimum(Threadpool, 0) )
      {
        SetThreadpoolThreadMaximum(ThreadPool, 0xAu);
        ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
        ::ThreadpoolCleanupGroup = ThreadpoolCleanupGroup;
        if ( ThreadpoolCleanupGroup )
        {
          ThreadpoolCallBackEnvironment.Version = 3;
          *(_OWORD *)&ThreadpoolCallBackEnvironment.RaceDll = 0;
          ThreadpoolCallBackEnvironment.FinalizationCallback = 0;
          ThreadpoolCallBackEnvironment.u.Flags = 0;
          ThreadpoolCallBackEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
          ThreadpoolCallBackEnvironment.Size = 72;
          v15 = ThreadPool;
          ThreadpoolCallBackEnvironment.Pool = ThreadPool;
          ThreadpoolCallBackEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
          ThreadpoolCallBackEnvironment.CleanupGroupCancelCallback = 0;
          v11 = 1;
        }
      }
    }
    if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x40) != 0 )
      McTemplateU0qqqqq_EventWriteTransfer(
        (_DWORD)v15,
        v14,
        v16,
        dword_180030E9C,
        g_CurrentTimeZoneInfo.Bias,
        g_CurrentTimeZoneInfo.StandardBias,
        g_CurrentTimeZoneInfo.DaylightBias);
    if ( v11 )
      return CScheduleMgr::Initialize(v15);
    return 2147500037LL;
  }
  TimeInfo::TimeInfo((LPTIME_ZONE_INFORMATION)TimeZoneInformation);
  *(_OWORD *)&g_CurrentTimeZoneInfo.Bias = *(_OWORD *)TimeZoneInformation;
  *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[6] = *(_OWORD *)&TimeZoneInformation[16];
  *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[14] = *(_OWORD *)&TimeZoneInformation[32];
  *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[22] = *(_OWORD *)&TimeZoneInformation[48];
  *(_OWORD *)&g_CurrentTimeZoneInfo.StandardName[30] = *(_OWORD *)&TimeZoneInformation[64];
  *(_OWORD *)&g_CurrentTimeZoneInfo.StandardDate.wSecond = *(_OWORD *)&TimeZoneInformation[80];
  *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[4] = *(_OWORD *)&TimeZoneInformation[96];
  *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[12] = *(_OWORD *)&TimeZoneInformation[112];
  *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[20] = *(_OWORD *)&TimeZoneInformation[128];
  *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightName[28] = *(_OWORD *)&TimeZoneInformation[144];
  *(_OWORD *)&g_CurrentTimeZoneInfo.DaylightDate.wHour = *(_OWORD *)&TimeZoneInformation[160];
  if ( _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&TimeZoneInformation[160], 12)) != -1 )
  {
    RegSetKeyValueW(hKey[0], 0, L"TimeZoneInfo", 3u, &g_CurrentTimeZoneInfo, 0xB0u);
    goto LABEL_20;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v8, InvalidTZID);
  RegCloseKey(hKey[0]);
  return v9;
}

```

## disassembly

```asm
0x180015544  mov     [rsp+arg_0], rbx
0x180015549  push    rdi
0x18001554a  sub     rsp, 190h
0x180015551  mov     rax, cs:__security_cookie
0x180015558  xor     rax, rsp
0x18001555b  mov     [rsp+198h+var_18], rax
0x180015563  call    McGenEventRegister_EventRegister
0x180015568  mov     al, cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits
0x18001556e  test    al, 4
0x180015570  jz      short loc_180015597
0x180015572  lea     rax, [rsp+198h+var_28]
0x18001557a  mov     [rsp+198h+phkResult], rax
0x18001557f  mov     r9d, 1
0x180015585  lea     rdx, ServiceInitializeStarted
0x18001558c  call    McGenEventWrite_EventWriteTransfer
0x180015591  mov     al, cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits
0x180015597  test    al, 8
0x180015599  jz      short loc_1800155BA
0x18001559b  lea     rax, [rsp+198h+var_28]
0x1800155a3  mov     [rsp+198h+phkResult], rax
0x1800155a8  mov     r9d, 1
0x1800155ae  lea     rdx, ServiceInitializePhase1Started
0x1800155b5  call    McGenEventWrite_EventWriteTransfer
0x1800155ba  call    TsiValidateAndConfigureRegistry
0x1800155bf  test    eax, eax
0x1800155c1  js      loc_180015995
0x1800155c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800155ce  mov     ecx, 20h ; ' '; unsigned __int64
0x1800155d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800155d8  mov     rdi, rax
0x1800155db  mov     [rsp+198h+var_148], rax
0x1800155e0  test    rax, rax
0x1800155e3  jz      short loc_180015615
0x1800155e5  mov     qword ptr [rax], 0
0x1800155ec  lea     rbx, [rax+8]
0x1800155f0  mov     qword ptr [rbx], 0
0x1800155f7  mov     qword ptr [rbx+8], 0
0x1800155ff  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<_GUID const,PDC_ENTRY *>>>::_Buyheadnode(void)
0x180015604  mov     [rbx], rax
0x180015607  mov     byte ptr [rdi+18h], 0
0x18001560b  mov     rcx, rbx
0x18001560e  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(void)
0x180015613  jmp     short loc_180015617
0x180015615  xor     edi, edi
0x180015617  mov     cs:?g_PdcManager@@3PEAVPdcManager@@EA, rdi; PdcManager * g_PdcManager
0x18001561e  test    rdi, rdi
0x180015621  jz      loc_180015995
0x180015627  call    ?Initialize@PdcManager@@QEAAJXZ; PdcManager::Initialize(void)
0x18001562c  mov     [rsp+198h+hKey], 0
0x180015635  lea     rax, [rsp+198h+hKey]
0x18001563a  mov     [rsp+198h+phkResult], rax; phkResult
0x18001563f  mov     r9d, 2001Bh; samDesired
0x180015645  xor     r8d, r8d; ulOptions
0x180015648  lea     rdx, ?g_szTaskSchedulerParametersRegPath@@3PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001564f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015656  call    cs:__imp_RegOpenKeyExW
0x18001565c  test    eax, eax
0x18001565e  jnz     loc_180015995
0x180015664  mov     ebx, 0B0h
0x180015669  mov     [rsp+198h+cbData], ebx
0x18001566d  lea     rax, [rsp+198h+cbData]
0x180015672  mov     [rsp+198h+lpcbData], rax; lpcbData
0x180015677  lea     rdi, ?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A; _TIMEZONEINFO g_CurrentTimeZoneInfo
0x18001567e  mov     [rsp+198h+phkResult], rdi; lpData
0x180015683  xor     r9d, r9d; lpType
0x180015686  xor     r8d, r8d; lpReserved
0x180015689  lea     rdx, ValueName; "TimeZoneInfo"
0x180015690  mov     rcx, [rsp+198h+hKey]; hKey
0x180015695  call    cs:__imp_RegQueryValueExW
0x18001569b  test    eax, eax
0x18001569d  jnz     short loc_1800156A9
0x18001569f  cmp     [rsp+198h+cbData], ebx
0x1800156a3  jz      loc_1800157C2
0x1800156a9  lea     rcx, [rsp+198h+TimeZoneInformation]; lpTimeZoneInformation
0x1800156ae  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x1800156b3  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation]
0x1800156b8  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.Bias, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x1800156bf  movaps  xmm1, xmmword ptr [rsp+198h+TimeZoneInformation+10h]
0x1800156c4  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardName+0Ch, xmm1; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x1800156cb  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation+20h]
0x1800156d3  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardName+1Ch, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x1800156da  movaps  xmm1, xmmword ptr [rsp+198h+TimeZoneInformation+30h]
0x1800156e2  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardName+2Ch, xmm1; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x1800156e9  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation+40h]
0x1800156f1  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardName+3Ch, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x1800156f8  movaps  xmm1, xmmword ptr [rsp+198h+TimeZoneInformation+50h]
0x180015700  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardDate.wSecond, xmm1; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015707  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation+60h]
0x18001570f  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightName+8, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015716  movaps  xmm1, xmmword ptr [rsp+198h+TimeZoneInformation+70h]
0x18001571e  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightName+18h, xmm1; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015725  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation+80h]
0x18001572d  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightName+28h, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015734  movaps  xmm1, xmmword ptr [rsp+198h+TimeZoneInformation+90h]
0x18001573c  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightName+38h, xmm1; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015743  movaps  xmm0, xmmword ptr [rsp+198h+TimeZoneInformation+0A0h]
0x18001574b  movups  xmmword ptr cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightDate.wHour, xmm0; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015752  psrldq  xmm0, 0Ch
0x180015757  movd    eax, xmm0
0x18001575b  cmp     eax, 0FFFFFFFFh
0x18001575e  jnz     short loc_18001579F
0x180015760  call    cs:__imp_GetLastError
0x180015766  mov     ebx, eax
0x180015768  test    eax, eax
0x18001576a  jle     short loc_180015775
0x18001576c  movzx   ebx, ax
0x18001576f  or      ebx, 80070000h
0x180015775  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x18001577c  jz      short loc_18001578D
0x18001577e  mov     r8d, ebx
0x180015781  lea     rdx, InvalidTZID
0x180015788  call    McTemplateU0q_EventWriteTransfer
0x18001578d  mov     rcx, [rsp+198h+hKey]; hKey
0x180015792  call    cs:__imp_RegCloseKey
0x180015798  mov     eax, ebx
0x18001579a  jmp     loc_18001599A
0x18001579f  mov     dword ptr [rsp+198h+lpcbData], ebx; cbData
0x1800157a3  mov     [rsp+198h+phkResult], rdi; lpData
0x1800157a8  mov     r9d, 3; dwType
0x1800157ae  lea     r8, ValueName; "TimeZoneInfo"
0x1800157b5  xor     edx, edx; lpSubKey
0x1800157b7  mov     rcx, [rsp+198h+hKey]; hKey
0x1800157bc  call    cs:__imp_RegSetKeyValueW
0x1800157c2  xor     ebx, ebx
0x1800157c4  mov     rcx, [rsp+198h+hKey]; hKey
0x1800157c9  call    cs:__imp_RegCloseKey
0x1800157cf  lea     rcx, LibFileName; "WptsExtensions.dll"
0x1800157d6  call    cs:__imp_LoadLibraryW
0x1800157dc  mov     cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModuleWptsExtensions
0x1800157e3  test    rax, rax
0x1800157e6  jz      loc_1800158B5
0x1800157ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800157f3  lea     ecx, [rbx+28h]; unsigned __int64
0x1800157f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800157fb  mov     cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA, rax; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015802  test    rax, rax
0x180015805  jz      loc_1800158B5
0x18001580b  xorps   xmm0, xmm0
0x18001580e  xor     ecx, ecx
0x180015810  movups  xmmword ptr [rax], xmm0
0x180015813  movups  xmmword ptr [rax+10h], xmm0
0x180015817  mov     [rax+20h], rcx
0x18001581b  lea     rdx, aWptscreateacti; "WptsCreateAction"
0x180015822  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hModule
0x180015829  call    cs:__imp_GetProcAddress
0x18001582f  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015836  mov     [rcx], rax
0x180015839  lea     rdx, aWptsdestroyact; "WptsDestroyAction"
0x180015840  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hModule
0x180015847  call    cs:__imp_GetProcAddress
0x18001584d  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015854  mov     [rcx+8], rax
0x180015858  lea     rdx, aWptscopyaction; "WptsCopyActionData"
0x18001585f  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hModule
0x180015866  call    cs:__imp_GetProcAddress
0x18001586c  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015873  mov     [rcx+10h], rax
0x180015877  lea     rdx, aWptsfreeaction; "WptsFreeActionData"
0x18001587e  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hModule
0x180015885  call    cs:__imp_GetProcAddress
0x18001588b  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x180015892  mov     [rcx+18h], rax
0x180015896  lea     rdx, aWptslaunchacti; "WptsLaunchAction"
0x18001589d  mov     rcx, cs:?g_hModuleWptsExtensions@@3PEAUHINSTANCE__@@EA; hModule
0x1800158a4  call    cs:__imp_GetProcAddress
0x1800158aa  mov     rcx, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x1800158b1  mov     [rcx+20h], rax
0x1800158b5  xor     ecx, ecx; reserved
0x1800158b7  call    cs:__imp_CreateThreadpool
0x1800158bd  mov     cs:?ThreadPool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * ThreadPool
0x1800158c4  test    rax, rax
0x1800158c7  jz      loc_180015957
0x1800158cd  xor     edx, edx; cthrdMic
0x1800158cf  mov     rcx, rax; ptpp
0x1800158d2  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800158d8  test    eax, eax
0x1800158da  jz      short loc_180015957
0x1800158dc  mov     edx, 0Ah; cthrdMost
0x1800158e1  mov     rcx, cs:?ThreadPool@@3PEAU_TP_POOL@@EA; ptpp
0x1800158e8  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800158ee  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800158f4  mov     cs:?ThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * ThreadpoolCleanupGroup
0x1800158fb  test    rax, rax
0x1800158fe  jz      short loc_180015957
0x180015900  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x18001590a  xorps   xmm0, xmm0
0x18001590d  movdqa  xmmword ptr cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x180015915  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rbx; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x18001591c  mov     dword ptr cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, ebx; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x180015922  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x18001592c  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x180015936  mov     rcx, cs:?ThreadPool@@3PEAU_TP_POOL@@EA; _TP_POOL * ThreadPool
0x18001593d  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rcx; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x180015944  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x18001594b  mov     cs:?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rbx; _TP_CALLBACK_ENVIRON_V3 ThreadpoolCallBackEnvironment ...
0x180015952  mov     ebx, 1
0x180015957  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 40h
0x18001595e  jz      short loc_18001598A
0x180015960  mov     eax, cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.DaylightBias; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015966  mov     [rsp+198h+var_168], eax
0x18001596a  mov     eax, cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.StandardBias; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x180015970  mov     dword ptr [rsp+198h+lpcbData], eax
0x180015974  mov     eax, cs:?g_CurrentTimeZoneInfo@@3U_TIMEZONEINFO@@A.Bias; _TIMEZONEINFO g_CurrentTimeZoneInfo ...
0x18001597a  mov     dword ptr [rsp+198h+phkResult], eax
0x18001597e  mov     r9d, cs:dword_180030E9C
0x180015985  call    McTemplateU0qqqqq_EventWriteTransfer
0x18001598a  test    ebx, ebx
0x18001598c  jz      short loc_180015995
0x18001598e  call    ?Initialize@CScheduleMgr@@QEAAJXZ; CScheduleMgr::Initialize(void)
0x180015993  jmp     short loc_18001599A
0x180015995  mov     eax, 80004005h
0x18001599a  mov     rcx, [rsp+198h+var_18]
0x1800159a2  xor     rcx, rsp; StackCookie
0x1800159a5  call    __security_check_cookie
0x1800159aa  mov     rbx, [rsp+198h+arg_0]
0x1800159b2  add     rsp, 190h
0x1800159b9  pop     rdi
0x1800159ba  retn
```
