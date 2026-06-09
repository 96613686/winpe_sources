# CSessionEnvService::ServiceStart(ulong,ushort * *)

- ea: `0x18001d7f4`
- end: `0x18001d9cd`
- name: `?ServiceStart@CSessionEnvService@@QEAAJKPEAPEAG@Z`
- size: `473`
- prototype: `__int64 __fastcall(CSessionEnvService *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d240`

## callees

- `0x180003f30`
- `0x180005120`
- `0x1800141f4`
- `0x18001d3bc`
- `0x18001d3e8`
- `0x18001d7f4`
- `0x18001dc44`
- `0x18001ed5c`
- `0x18001fc10`
- `0x180020acc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d8b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d8b3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001d831`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001d831`

## string_xrefs

- `0x18001d862`: `CSessionEnvService::ServiceStart`
- `0x18001d858`: `RegisterServiceCtrlHandlerEx failed: 0x%x in %s`
- `0x18001d8db`: `CreateEvent failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CSessionEnvService::ServiceStart(struct IWLNotificationManager **this, int a2, LPCWSTR *a3)
{
  unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // ebx
  SERVICE_STATUS_HANDLE v9; // rax
  signed int LastError; // eax
  int v11; // eax
  struct IWLNotificationManager *EventW; // rax
  signed int v13; // eax
  int InstanceOfNotificationManager; // eax
  int v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-28h]

  RegisterTraceLoggingProvider();
  if ( a2 )
  {
    CUtils::DebugBreakIfAskedEx(v7, v6);
    v9 = RegisterServiceCtrlHandlerExW(*a3, CSessionEnvService::staticControlHandlerEx, this);
    *this = (struct IWLNotificationManager *)v9;
    if ( v9 )
      goto LABEL_8;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_8:
      CSessionEnvService::UpdateServiceStatus((CSessionEnvService *)this, 2u, 0, 0, v17, 0x2710u);
      v11 = CUtils::Initialize();
      v8 = v11;
      if ( v11 >= 0 )
      {
        EventW = (struct IWLNotificationManager *)CreateEventW(0, 0, 0, 0);
        this[5] = EventW;
        if ( EventW )
          goto LABEL_31;
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
        if ( (v8 & 0x80000000) == 0 )
        {
LABEL_31:
          if ( g_pSvchostData && *((_QWORD *)g_pSvchostData + 24) )
          {
            LicensingModeIntegrityCheck();
            InstanceOfNotificationManager = IWLNotificationManager::GetInstanceOfNotificationManager(this + 9);
            v8 = InstanceOfNotificationManager;
            if ( InstanceOfNotificationManager >= 0 )
            {
              v15 = (*((__int64 (__fastcall **)(char *, LPCWSTR, struct IWLNotificationManager *, void (__fastcall *)(CSessionEnvService *, unsigned __int8)))g_pSvchostData
                     + 24))(
                      (char *)this + 48,
                      *a3,
                      this[5],
                      CSessionEnvService::staticStopCallback);
              if ( !v15 )
              {
                CSessionEnvService::UpdateServiceStatus((CSessionEnvService *)this, 4u, 0, 0, (unsigned int)this, 0);
                return v8;
              }
              if ( v15 > 0 )
                v8 = (unsigned __int16)v15 | 0x80070000;
              else
                v8 = v15;
              _DbgPrintMessage(8, "RegisterStopCallback failed: 0x%x in %s", v8, "CSessionEnvService::ServiceStart");
            }
            else
            {
              _DbgPrintMessage(
                8,
                "IWLNotificationManager::GetInstanceOfNotificationManager failed: 0x%x in %s",
                (unsigned int)InstanceOfNotificationManager,
                "CSessionEnvService::ServiceStart");
            }
          }
          else
          {
            v8 = -2147024883;
          }
        }
        else
        {
          _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", v8, "CSessionEnvService::ServiceStart");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "CUtils::Initialize failed: 0x%x in %s",
          (unsigned int)v11,
          "CSessionEnvService::ServiceStart");
      }
    }
    else
    {
      _DbgPrintMessage(8, "RegisterServiceCtrlHandlerEx failed: 0x%x in %s", v8, "CSessionEnvService::ServiceStart");
    }
  }
  else
  {
    v8 = -2147024809;
  }
  CSessionEnvService::ServiceStop((CSessionEnvService *)this, 0x42Au, v8);
  if ( this )
    CSessionEnvService::`scalar deleting destructor'((CSessionEnvService *)this);
  return v8;
}

```

## disassembly

```asm
0x18001d7f4  mov     [rsp+arg_0], rbx
0x18001d7f9  mov     [rsp+arg_8], rsi
0x18001d7fe  push    rdi
0x18001d7ff  sub     rsp, 40h
0x18001d803  mov     rsi, r8
0x18001d806  mov     ebx, edx
0x18001d808  mov     rdi, rcx
0x18001d80b  call    ?RegisterTraceLoggingProvider@@YAXXZ; RegisterTraceLoggingProvider(void)
0x18001d810  cmp     ebx, 1
0x18001d813  jnb     short loc_18001D81F
0x18001d815  mov     ebx, 80070057h
0x18001d81a  jmp     loc_18001D99E
0x18001d81f  call    ?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z; CUtils::DebugBreakIfAskedEx(ushort *,ushort *)
0x18001d824  mov     rcx, [rsi]; lpServiceName
0x18001d827  lea     rdx, ?staticControlHandlerEx@CSessionEnvService@@CAKKKPEAX0@Z; lpHandlerProc
0x18001d82e  mov     r8, rdi; lpContext
0x18001d831  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001d837  mov     [rdi], rax
0x18001d83a  test    rax, rax
0x18001d83d  jnz     short loc_18001D878
0x18001d83f  call    cs:__imp_GetLastError
0x18001d845  mov     ebx, eax
0x18001d847  test    eax, eax
0x18001d849  jle     short loc_18001D854
0x18001d84b  movzx   ebx, ax
0x18001d84e  or      ebx, 80070000h
0x18001d854  test    ebx, ebx
0x18001d856  jns     short loc_18001D878
0x18001d858  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed: 0x"...
0x18001d85f  mov     r8d, ebx
0x18001d862  lea     r9, aCsessionenvser; "CSessionEnvService::ServiceStart"
0x18001d869  mov     ecx, 8; int
0x18001d86e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001d873  jmp     loc_18001D99E
0x18001d878  xor     r9d, r9d; unsigned int
0x18001d87b  mov     [rsp+48h+var_20], 2710h; unsigned int
0x18001d883  xor     r8d, r8d; unsigned int
0x18001d886  mov     rcx, rdi; this
0x18001d889  lea     edx, [r9+2]; unsigned int
0x18001d88d  call    ?UpdateServiceStatus@CSessionEnvService@@AEAAHKKKKK@Z; CSessionEnvService::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d892  call    ?Initialize@CUtils@@SAJXZ; CUtils::Initialize(void)
0x18001d897  mov     ebx, eax
0x18001d899  test    eax, eax
0x18001d89b  jns     short loc_18001D8A9
0x18001d89d  mov     r8d, eax
0x18001d8a0  lea     rdx, aCutilsInitiali_0; "CUtils::Initialize failed: 0x%x in %s"
0x18001d8a7  jmp     short loc_18001D862
0x18001d8a9  xor     r9d, r9d; lpName
0x18001d8ac  xor     r8d, r8d; bInitialState
0x18001d8af  xor     edx, edx; bManualReset
0x18001d8b1  xor     ecx, ecx; lpEventAttributes
0x18001d8b3  call    cs:__imp_CreateEventW
0x18001d8b9  mov     [rdi+28h], rax
0x18001d8bd  test    rax, rax
0x18001d8c0  jnz     short loc_18001D8E7
0x18001d8c2  call    cs:__imp_GetLastError
0x18001d8c8  mov     ebx, eax
0x18001d8ca  test    eax, eax
0x18001d8cc  jle     short loc_18001D8D7
0x18001d8ce  movzx   ebx, ax
0x18001d8d1  or      ebx, 80070000h
0x18001d8d7  test    ebx, ebx
0x18001d8d9  jns     short loc_18001D8E7
0x18001d8db  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18001d8e2  jmp     loc_18001D85F
0x18001d8e7  mov     rax, cs:?g_pSvchostData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostData
0x18001d8ee  test    rax, rax
0x18001d8f1  jz      loc_18001D999
0x18001d8f7  cmp     qword ptr [rax+0C0h], 0
0x18001d8ff  jz      loc_18001D999
0x18001d905  call    ?LicensingModeIntegrityCheck@@YAXXZ; LicensingModeIntegrityCheck(void)
0x18001d90a  lea     rcx, [rdi+48h]; struct IWLNotificationManager **
0x18001d90e  call    ?GetInstanceOfNotificationManager@IWLNotificationManager@@SAJPEAPEAV1@@Z; IWLNotificationManager::GetInstanceOfNotificationManager(IWLNotificationManager * *)
0x18001d913  mov     ebx, eax
0x18001d915  test    eax, eax
0x18001d917  jns     short loc_18001D928
0x18001d919  mov     r8d, eax
0x18001d91c  lea     rdx, aIwlnotificatio_0; "IWLNotificationManager::GetInstanceOfNo"...
0x18001d923  jmp     loc_18001D862
0x18001d928  mov     rax, cs:?g_pSvchostData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostData
0x18001d92f  lea     rcx, [rdi+30h]
0x18001d933  mov     r8, [rdi+28h]
0x18001d937  lea     r9, ?staticStopCallback@CSessionEnvService@@CAXPEAXE@Z; CSessionEnvService::staticStopCallback(void *,uchar)
0x18001d93e  mov     rdx, [rsi]
0x18001d941  mov     [rsp+48h+var_20], 0
0x18001d949  mov     rax, [rax+0C0h]
0x18001d950  mov     qword ptr [rsp+48h+var_28], rdi; unsigned int
0x18001d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d95a  test    eax, eax
0x18001d95c  jz      short loc_18001D97D
0x18001d95e  jg      short loc_18001D964
0x18001d960  mov     ebx, eax
0x18001d962  jmp     short loc_18001D96D
0x18001d964  movzx   ebx, ax
0x18001d967  or      ebx, 80070000h
0x18001d96d  test    ebx, ebx
0x18001d96f  jns     short loc_18001D97D
0x18001d971  lea     rdx, aRegisterstopca; "RegisterStopCallback failed: 0x%x in %s"
0x18001d978  jmp     loc_18001D85F
0x18001d97d  xor     r9d, r9d; unsigned int
0x18001d980  mov     [rsp+48h+var_20], 0; unsigned int
0x18001d988  xor     r8d, r8d; unsigned int
0x18001d98b  mov     rcx, rdi; this
0x18001d98e  lea     edx, [r9+4]; unsigned int
0x18001d992  call    ?UpdateServiceStatus@CSessionEnvService@@AEAAHKKKKK@Z; CSessionEnvService::UpdateServiceStatus(ulong,ulong,ulong,ulong,ulong)
0x18001d997  jmp     short loc_18001D9BB
0x18001d999  mov     ebx, 8007000Dh
0x18001d99e  mov     r8d, ebx; unsigned int
0x18001d9a1  mov     edx, 42Ah; unsigned int
0x18001d9a6  mov     rcx, rdi; this
0x18001d9a9  call    ?ServiceStop@CSessionEnvService@@AEAAXKK@Z; CSessionEnvService::ServiceStop(ulong,ulong)
0x18001d9ae  test    rdi, rdi
0x18001d9b1  jz      short loc_18001D9BB
0x18001d9b3  mov     rcx, rdi; this
0x18001d9b6  call    ??_GCSessionEnvService@@QEAAPEAXI@Z; CSessionEnvService::`scalar deleting destructor'(uint)
0x18001d9bb  mov     rsi, [rsp+48h+arg_8]
0x18001d9c0  mov     eax, ebx
0x18001d9c2  mov     rbx, [rsp+48h+arg_0]
0x18001d9c7  add     rsp, 40h
0x18001d9cb  pop     rdi
0x18001d9cc  retn
```
