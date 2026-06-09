# ServiceMain(ulong,ushort * * const)

- ea: `0x18000c8e0`
- end: `0x18000cb6a`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `650`
- prototype: `void __fastcall(int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003a60`
- `0x18000c694`
- `0x18000c8e0`
- `0x18000cc20`
- `0x18000cd64`
- `0x18000cf28`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c9a9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c9a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cad7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cad7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ca1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ca1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000caf0`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000cb2c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000cb2c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c969`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000c969`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c94a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000c94a`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c97d`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c97d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000c9ea`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000c9ea`

## string_xrefs

- `0x18000c993`: `ServiceMain`
- `0x18000ca93`: `ServiceMain`
- `0x18000ca83`: `SmsRouter: Error while registering service callback for SmsRouter %d`

## pseudocode

```c
void __fastcall ServiceMain(int a1, unsigned __int16 **const a2)
{
  int v4; // ecx
  unsigned __int16 v5; // bx
  unsigned __int8 IsMultiSessionSku; // al
  unsigned __int16 **v7; // rdx
  unsigned int v8; // ecx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  REGHANDLE v13; // rcx
  GUID ProviderId; // [rsp+40h] [rbp-28h] BYREF

  McGenEventRegister_EventRegister();
  ProviderId = (GUID)*((_OWORD *)off_18008C080 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18008C0A0 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18008C078, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_18008C080, *(unsigned __int16 *)off_18008C080);
  if ( !a1 )
    goto LABEL_6;
  IsMultiSessionSku = RtlIsMultiSessionSku();
  LogSmsRouterInfo("ServiceMain", 0x15Au, "SmsRouterSvc starting (IsMultiSessionSku=%d)", IsMultiSessionSku);
  if ( (unsigned int)_o__wcsicmp(L"TestCallInitOnly", *a2) )
  {
    ServiceStatus.dwServiceType = 32;
    v9 = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
    hServiceStatus = RegisterServiceCtrlHandlerExW(L"SmsRouter", ServiceHandler, 0);
    if ( hServiceStatus )
    {
      UpdateServiceStatus(2u, 0, 0x64u);
      WaitHandle = 0;
      hObject = CreateEventW(0, 0, 0, 0);
      if ( !hObject )
      {
LABEL_6:
        v5 = -1;
        goto LABEL_17;
      }
      v10 = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18008CF88 + 192))(
              &WaitHandle,
              L"SmsRouter",
              hObject,
              StopService,
              0,
              8);
      if ( v10 )
      {
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        else
          v11 = v10;
        LogSmsRouterError(
          "ServiceMain",
          0x181u,
          v11,
          "SmsRouter: Error while registering service callback for SmsRouter %d",
          v10);
      }
    }
  }
  else
  {
    v9 = 1;
  }
  v12 = InitializeService(v8, v7);
  v5 = v12;
  if ( v12 < 0 )
  {
LABEL_17:
    if ( WaitHandle )
    {
      UpdateServiceStatus(3u, v5, 0x2710u);
      if ( hObject )
        SetEvent(hObject);
    }
    else
    {
      UninitializeService(v4);
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      UpdateServiceStatus(1u, v5, 0);
      v13 = RegHandle;
      dword_18008C078 = 0;
      RegHandle = 0;
      EventUnregister(v13);
    }
    return;
  }
  if ( !v9 )
  {
    ServiceStatus.dwControlsAccepted = 1;
    UpdateServiceStatus(4u, 0, 0);
  }
}

```

## disassembly

```asm
0x18000c8e0  mov     [rsp+arg_10], rbx
0x18000c8e5  push    rdi
0x18000c8e6  sub     rsp, 60h
0x18000c8ea  mov     rax, cs:__security_cookie
0x18000c8f1  xor     rax, rsp
0x18000c8f4  mov     [rsp+68h+var_18], rax
0x18000c8f9  mov     rdi, rdx
0x18000c8fc  mov     ebx, ecx
0x18000c8fe  call    McGenEventRegister_EventRegister
0x18000c903  cmp     cs:RegHandle, 0
0x18000c90b  mov     rax, cs:off_18008C080
0x18000c912  movups  xmm0, xmmword ptr [rax-10h]
0x18000c916  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000c91c  jz      short loc_18000C925
0x18000c91e  mov     ecx, 5
0x18000c923  int     29h; Win8: RtlFailFast(ecx)
0x18000c925  xorps   xmm0, xmm0
0x18000c928  lea     r9, RegHandle; RegHandle
0x18000c92f  lea     r8, dword_18008C078; CallbackContext
0x18000c936  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000c93d  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000c942  movdqu  cs:xmmword_18008C0A0, xmm0
0x18000c94a  call    cs:__imp_EventRegister
0x18000c950  test    eax, eax
0x18000c952  jnz     short loc_18000C96F
0x18000c954  mov     r8, cs:off_18008C080
0x18000c95b  lea     edx, [rax+2]
0x18000c95e  mov     rcx, cs:RegHandle
0x18000c965  movzx   r9d, word ptr [r8]
0x18000c969  call    cs:__imp_EventSetInformation
0x18000c96f  test    ebx, ebx
0x18000c971  jnz     short loc_18000C97D
0x18000c973  mov     ebx, 8000FFFFh
0x18000c978  jmp     loc_18000CAAE
0x18000c97d  call    cs:__imp_RtlIsMultiSessionSku
0x18000c983  movzx   r9d, al
0x18000c987  lea     r8, aSmsroutersvcSt_0; "SmsRouterSvc starting (IsMultiSessionSk"...
0x18000c98e  mov     edx, 15Ah; unsigned int
0x18000c993  lea     rcx, aServicemain_0; "ServiceMain"
0x18000c99a  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18000c99f  mov     rdx, [rdi]
0x18000c9a2  lea     rcx, aTestcalliniton; "TestCallInitOnly"
0x18000c9a9  call    cs:__imp__o__wcsicmp
0x18000c9af  test    eax, eax
0x18000c9b1  jnz     short loc_18000C9BB
0x18000c9b3  lea     edi, [rax+1]
0x18000c9b6  jmp     loc_18000CA9F
0x18000c9bb  xorps   xmm0, xmm0
0x18000c9be  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000c9c8  xor     edi, edi
0x18000c9ca  lea     rdx, ServiceHandler; lpHandlerProc
0x18000c9d1  xor     r8d, r8d; lpContext
0x18000c9d4  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rdi
0x18000c9db  lea     rcx, ?gc_szServiceName@@3QBGB; "SmsRouter"
0x18000c9e2  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x18000c9ea  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000c9f0  mov     cs:hServiceStatus, rax
0x18000c9f7  test    rax, rax
0x18000c9fa  jz      loc_18000CA9F
0x18000ca00  xor     edx, edx; unsigned int
0x18000ca02  lea     ecx, [rdi+2]; unsigned int
0x18000ca05  lea     r8d, [rdi+64h]; unsigned int
0x18000ca09  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18000ca0e  xor     r9d, r9d; lpName
0x18000ca11  mov     cs:WaitHandle, rdi
0x18000ca18  xor     r8d, r8d; bInitialState
0x18000ca1b  xor     edx, edx; bManualReset
0x18000ca1d  xor     ecx, ecx; lpEventAttributes
0x18000ca1f  call    cs:__imp_CreateEventW
0x18000ca25  mov     cs:hObject, rax
0x18000ca2c  mov     r8, rax
0x18000ca2f  test    rax, rax
0x18000ca32  jz      loc_18000C973
0x18000ca38  mov     rax, cs:qword_18008CF88
0x18000ca3f  lea     r9, StopService
0x18000ca46  mov     [rsp+68h+var_40], 8
0x18000ca4e  lea     rdx, ?gc_szServiceName@@3QBGB; "SmsRouter"
0x18000ca55  lea     rcx, WaitHandle
0x18000ca5c  mov     [rsp+68h+var_48], rdi
0x18000ca61  mov     rax, [rax+0C0h]
0x18000ca68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6d  test    eax, eax
0x18000ca6f  jz      short loc_18000CA9F
0x18000ca71  jg      short loc_18000CA78
0x18000ca73  mov     r8d, eax
0x18000ca76  jmp     short loc_18000CA83
0x18000ca78  movzx   r8d, ax
0x18000ca7c  or      r8d, 80070000h; int
0x18000ca83  lea     r9, aSmsrouterError; "SmsRouter: Error while registering serv"...
0x18000ca8a  mov     dword ptr [rsp+68h+var_48], eax
0x18000ca8e  mov     edx, 181h; unsigned int
0x18000ca93  lea     rcx, aServicemain_0; "ServiceMain"
0x18000ca9a  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18000ca9f  call    ?InitializeService@@YAJKQEAPEAG@Z; InitializeService(ulong,ushort * * const)
0x18000caa4  mov     ebx, eax
0x18000caa6  test    eax, eax
0x18000caa8  jns     loc_18000CB34
0x18000caae  cmp     cs:WaitHandle, 0
0x18000cab6  jz      short loc_18000CADF
0x18000cab8  movzx   edx, bx; unsigned int
0x18000cabb  mov     ecx, 3; unsigned int
0x18000cac0  mov     r8d, 2710h; unsigned int
0x18000cac6  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18000cacb  mov     rcx, cs:hObject; hEvent
0x18000cad2  test    rcx, rcx
0x18000cad5  jz      short loc_18000CB4F
0x18000cad7  call    cs:__imp_SetEvent
0x18000cadd  jmp     short loc_18000CB4F
0x18000cadf  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x18000cae4  mov     rcx, cs:hObject; hObject
0x18000caeb  test    rcx, rcx
0x18000caee  jz      short loc_18000CB01
0x18000caf0  call    cs:__imp_CloseHandle
0x18000caf6  mov     cs:hObject, 0
0x18000cb01  xor     r8d, r8d; unsigned int
0x18000cb04  movzx   edx, bx; unsigned int
0x18000cb07  lea     ecx, [r8+1]; unsigned int
0x18000cb0b  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18000cb10  mov     rcx, cs:RegHandle; RegHandle
0x18000cb17  mov     cs:dword_18008C078, 0
0x18000cb21  mov     cs:RegHandle, 0
0x18000cb2c  call    cs:__imp_EventUnregister
0x18000cb32  jmp     short loc_18000CB4F
0x18000cb34  test    edi, edi
0x18000cb36  jnz     short loc_18000CB4F
0x18000cb38  xor     r8d, r8d; unsigned int
0x18000cb3b  mov     cs:ServiceStatus.dwControlsAccepted, 1
0x18000cb45  xor     edx, edx; unsigned int
0x18000cb47  lea     ecx, [rdi+4]; unsigned int
0x18000cb4a  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x18000cb4f  mov     rcx, [rsp+68h+var_18]
0x18000cb54  xor     rcx, rsp; StackCookie
0x18000cb57  call    __security_check_cookie
0x18000cb5c  mov     rbx, [rsp+68h+arg_10]
0x18000cb64  add     rsp, 60h
0x18000cb68  pop     rdi
0x18000cb69  retn
```
