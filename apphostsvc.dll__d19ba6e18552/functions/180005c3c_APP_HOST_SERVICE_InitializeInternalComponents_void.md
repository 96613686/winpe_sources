# APP_HOST_SERVICE::InitializeInternalComponents(void)

- ea: `0x180005c3c`
- end: `0x180005eae`
- name: `?InitializeInternalComponents@APP_HOST_SERVICE@@AEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006274`

## callees

- `0x180002e20`
- `0x180005c3c`
- `0x1800076e0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005c75`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005c75`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180005ca1`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180005ca1`
- `ntdll!RtlCreateTimerQueue` at `0x180005d55`
- `ntdll!RtlCreateTimerQueue` at `0x180005d55`
- `iisutil!PuDbgPrintError` at `0x180005d39`
- `iisutil!PuDbgPrintError` at `0x180005d39`
- `iisutil!InitializeIISUtil` at `0x180005d81`
- `iisutil!InitializeIISUtil` at `0x180005d81`
- `nativerd!InitializeNativeConfiguration` at `0x180005dbf`
- `nativerd!InitializeNativeConfiguration` at `0x180005dbf`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005def`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005e3d`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005def`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180005e3d`

## string_xrefs

- `0x180005c5e`: `system.applicationHost/configHistory`
- `0x180005d2e`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\app_host_service.cxx`
- `0x180005d22`: `APP_HOST_SERVICE::InitializeInternalComponents`
- `0x180005cd9`: `Couldn't register service control handler\n`
- `0x180005d72`: `Could not create timer queue\n`
- `0x180005dd8`: `Could not initialize native config reader\n`

## pseudocode

```c
__int64 __fastcall APP_HOST_SERVICE::InitializeInternalComponents(APP_HOST_SERVICE *this)
{
  SERVICE_STATUS_HANDLE v2; // rax
  signed int v3; // eax
  int DefaultNativeConfigurationSystem; // ebx
  signed int v5; // eax
  NTSTATUS TimerQueue; // ebx
  signed int LastError; // eax
  unsigned int *v8; // rcx
  const wchar_t *v10; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-10h]
  struct INativeConfigurationSystem *v12; // [rsp+50h] [rbp+8h] BYREF
  struct INativeConfigurationSystem *v13; // [rsp+58h] [rbp+10h] BYREF

  v13 = 0;
  v10 = L"system.applicationHost/applicationPools";
  v11 = L"system.applicationHost/configHistory";
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 152), 0x800003E8) )
  {
    *((_DWORD *)this + 37) = 1;
LABEL_3:
    *((_DWORD *)this + 48) = 1;
    v2 = RegisterServiceCtrlHandlerW(L"apphostsvc", ServiceControlHandler);
    *((_QWORD *)this + 25) = v2;
    if ( v2 )
    {
      g_RegisterServiceCalled = 1;
      TimerQueue = RtlCreateTimerQueue((PHANDLE)this + 32);
      if ( TimerQueue >= 0 )
      {
        if ( (unsigned int)InitializeIISUtil() )
        {
          DefaultNativeConfigurationSystem = InitializeNativeConfiguration();
          if ( DefaultNativeConfigurationSystem >= 0 )
          {
            DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v13);
            if ( DefaultNativeConfigurationSystem >= 0 )
            {
              DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t **, __int64))(*(_QWORD *)v13 + 144LL))(
                                                   v13,
                                                   &v10,
                                                   2);
              if ( DefaultNativeConfigurationSystem >= 0 )
              {
                v12 = 0;
                DefaultNativeConfigurationSystem = AddDomainMapping(v8);
                if ( DefaultNativeConfigurationSystem >= 0 )
                {
                  DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v12);
                  if ( DefaultNativeConfigurationSystem >= 0 )
                    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, char *))(*(_QWORD *)v12 + 40LL))(
                                                         v12,
                                                         (char *)this + 272);
                }
                if ( v12 )
                  (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v12 + 16LL))(v12);
                if ( DefaultNativeConfigurationSystem >= 0 )
                  DefaultNativeConfigurationSystem = CONFIG_HISTORY::Initialize((APP_HOST_SERVICE *)((char *)this + 472));
              }
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
              922,
              "APP_HOST_SERVICE::InitializeInternalComponents",
              DefaultNativeConfigurationSystem,
              "Could not initialize native config reader\n",
              v10,
              v11);
          }
        }
        else
        {
          LastError = GetLastError();
          DefaultNativeConfigurationSystem = LastError;
          if ( LastError > 0 )
            DefaultNativeConfigurationSystem = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
              906,
              "APP_HOST_SERVICE::InitializeInternalComponents",
              DefaultNativeConfigurationSystem,
              "Could not initialize iisutil\n",
              v10,
              v11);
        }
      }
      else
      {
        DefaultNativeConfigurationSystem = TimerQueue | 0x10000000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
            888,
            "APP_HOST_SERVICE::InitializeInternalComponents",
            DefaultNativeConfigurationSystem,
            "Could not create timer queue\n",
            v10,
            v11);
      }
    }
    else
    {
      v3 = GetLastError();
      DefaultNativeConfigurationSystem = v3;
      if ( v3 > 0 )
        DefaultNativeConfigurationSystem = (unsigned __int16)v3 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
          867,
          "APP_HOST_SERVICE::InitializeInternalComponents",
          DefaultNativeConfigurationSystem,
          "Couldn't register service control handler\n",
          v10,
          v11);
    }
    goto LABEL_34;
  }
  v5 = GetLastError();
  DefaultNativeConfigurationSystem = v5;
  if ( v5 > 0 )
    DefaultNativeConfigurationSystem = (unsigned __int16)v5 | 0x80070000;
  if ( DefaultNativeConfigurationSystem >= 0 )
    goto LABEL_3;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\app_host_service.cxx",
      843,
      "APP_HOST_SERVICE::InitializeInternalComponents",
      DefaultNativeConfigurationSystem,
      "Lock initialization failed\n",
      v10,
      v11);
LABEL_34:
  if ( v13 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x180005c3c  mov     r11, rsp
0x180005c3f  mov     [r11+18h], rbx
0x180005c43  push    rdi
0x180005c44  sub     rsp, 40h
0x180005c48  lea     rax, aSystemApplicat_0; "system.applicationHost/applicationPools"
0x180005c4f  mov     qword ptr [r11+10h], 0
0x180005c57  mov     [r11-18h], rax
0x180005c5b  mov     rdi, rcx
0x180005c5e  lea     rax, aSystemApplicat; "system.applicationHost/configHistory"
0x180005c65  add     rcx, 98h; lpCriticalSection
0x180005c6c  mov     edx, 800003E8h; dwSpinCount
0x180005c71  mov     [r11-10h], rax
0x180005c75  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005c7b  test    eax, eax
0x180005c7d  jz      short loc_180005CE8
0x180005c7f  mov     dword ptr [rdi+94h], 1
0x180005c89  lea     rdx, ?ServiceControlHandler@@YAXK@Z; lpHandlerProc
0x180005c90  mov     dword ptr [rdi+0C0h], 1
0x180005c9a  lea     rcx, aApphostsvc_1; "apphostsvc"
0x180005ca1  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180005ca7  mov     [rdi+0C8h], rax
0x180005cae  test    rax, rax
0x180005cb1  jnz     loc_180005D44
0x180005cb7  call    cs:__imp_GetLastError
0x180005cbd  mov     ebx, eax
0x180005cbf  test    eax, eax
0x180005cc1  jle     short loc_180005CCC
0x180005cc3  movzx   ebx, ax
0x180005cc6  or      ebx, 80070000h
0x180005ccc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005cd3  jz      loc_180005E8B
0x180005cd9  lea     rax, aCouldnTRegiste; "Couldn't register service control handl"...
0x180005ce0  mov     r8d, 363h
0x180005ce6  jmp     short loc_180005D1B
0x180005ce8  call    cs:__imp_GetLastError
0x180005cee  mov     ebx, eax
0x180005cf0  test    eax, eax
0x180005cf2  jle     short loc_180005CFD
0x180005cf4  movzx   ebx, ax
0x180005cf7  or      ebx, 80070000h
0x180005cfd  test    ebx, ebx
0x180005cff  jns     short loc_180005C89
0x180005d01  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005d08  jz      loc_180005E8B
0x180005d0e  lea     rax, aLockInitializa; "Lock initialization failed\n"
0x180005d15  mov     r8d, 34Bh
0x180005d1b  mov     rcx, cs:g_pDebug
0x180005d22  lea     r9, aAppHostService_13; "APP_HOST_SERVICE::InitializeInternalCom"...
0x180005d29  mov     [rsp+48h+var_20], rax
0x180005d2e  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005d35  mov     [rsp+48h+var_28], ebx
0x180005d39  call    cs:__imp_PuDbgPrintError
0x180005d3f  jmp     loc_180005E8B
0x180005d44  lea     rcx, [rdi+100h]; TimerQueue
0x180005d4b  mov     cs:?g_RegisterServiceCalled@@3HA, 1; int g_RegisterServiceCalled
0x180005d55  call    cs:__imp_RtlCreateTimerQueue
0x180005d5b  mov     ebx, eax
0x180005d5d  test    eax, eax
0x180005d5f  jns     short loc_180005D81
0x180005d61  bts     ebx, 1Ch
0x180005d65  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005d6c  jz      loc_180005E8B
0x180005d72  lea     rax, aCouldNotCreate; "Could not create timer queue\n"
0x180005d79  mov     r8d, 378h
0x180005d7f  jmp     short loc_180005D1B
0x180005d81  call    cs:__imp_InitializeIISUtil
0x180005d87  test    eax, eax
0x180005d89  jnz     short loc_180005DBF
0x180005d8b  call    cs:__imp_GetLastError
0x180005d91  mov     ebx, eax
0x180005d93  test    eax, eax
0x180005d95  jle     short loc_180005DA0
0x180005d97  movzx   ebx, ax
0x180005d9a  or      ebx, 80070000h
0x180005da0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005da7  jz      loc_180005E8B
0x180005dad  lea     rax, aCouldNotInitia_0; "Could not initialize iisutil\n"
0x180005db4  mov     r8d, 38Ah
0x180005dba  jmp     loc_180005D1B
0x180005dbf  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x180005dc5  mov     ebx, eax
0x180005dc7  test    eax, eax
0x180005dc9  jns     short loc_180005DEA
0x180005dcb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005dd2  jz      loc_180005E8B
0x180005dd8  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x180005ddf  mov     r8d, 39Ah
0x180005de5  jmp     loc_180005D1B
0x180005dea  lea     rcx, [rsp+48h+arg_8]
0x180005def  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180005df5  mov     ebx, eax
0x180005df7  test    eax, eax
0x180005df9  js      loc_180005E8B
0x180005dff  mov     rcx, [rsp+48h+arg_8]
0x180005e04  lea     rdx, [rsp+48h+var_18]
0x180005e09  mov     r8d, 2
0x180005e0f  mov     rax, [rcx]
0x180005e12  mov     rax, [rax+90h]
0x180005e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1e  mov     ebx, eax
0x180005e20  test    eax, eax
0x180005e22  js      short loc_180005E8B
0x180005e24  mov     [rsp+48h+arg_0], 0
0x180005e2d  call    ?AddDomainMapping@@YAJPEAK@Z; AddDomainMapping(ulong *)
0x180005e32  mov     ebx, eax
0x180005e34  test    eax, eax
0x180005e36  js      short loc_180005E63
0x180005e38  lea     rcx, [rsp+48h+arg_0]
0x180005e3d  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180005e43  mov     ebx, eax
0x180005e45  test    eax, eax
0x180005e47  js      short loc_180005E63
0x180005e49  mov     rcx, [rsp+48h+arg_0]
0x180005e4e  lea     rdx, [rdi+110h]
0x180005e55  mov     rax, [rcx]
0x180005e58  mov     rax, [rax+28h]
0x180005e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e61  mov     ebx, eax
0x180005e63  mov     rcx, [rsp+48h+arg_0]
0x180005e68  test    rcx, rcx
0x180005e6b  jz      short loc_180005E79
0x180005e6d  mov     rax, [rcx]
0x180005e70  mov     rax, [rax+10h]
0x180005e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e79  test    ebx, ebx
0x180005e7b  js      short loc_180005E8B
0x180005e7d  lea     rcx, [rdi+1D8h]; this
0x180005e84  call    ?Initialize@CONFIG_HISTORY@@QEAAJXZ; CONFIG_HISTORY::Initialize(void)
0x180005e89  mov     ebx, eax
0x180005e8b  mov     rcx, [rsp+48h+arg_8]
0x180005e90  test    rcx, rcx
0x180005e93  jz      short loc_180005EA1
0x180005e95  mov     rax, [rcx]
0x180005e98  mov     rax, [rax+10h]
0x180005e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea1  mov     eax, ebx
0x180005ea3  mov     rbx, [rsp+48h+arg_10]
0x180005ea8  add     rsp, 40h
0x180005eac  pop     rdi
0x180005ead  retn
```
