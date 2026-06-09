# SystemEventTriggerControllerSink::~SystemEventTriggerControllerSink(void)

- ea: `0x180014014`
- end: `0x180014147`
- name: `??1SystemEventTriggerControllerSink@@MEAA@XZ`
- size: `307`
- prototype: `void __fastcall(SystemEventTriggerControllerSink *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800142b0`
- `0x1800144c0`

## callees

- `0x1800056a0`
- `0x180014014`
- `0x1800146c0`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014140`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001407b`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18001407b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001408d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001408d`

## string_xrefs

- `0x180014058`: `onecoreuap\net\phone\phoneservice\service\lib\systemeventtriggercontrollersink.cpp`

## pseudocode

```c
void __fastcall SystemEventTriggerControllerSink::~SystemEventTriggerControllerSink(
        SystemEventTriggerControllerSink *this)
{
  bool v1; // zf
  void *v3; // rcx
  void *v4; // rcx
  __int64 **v5; // rdi
  __int64 *v6; // rcx
  __int64 *v7; // rdx
  __int64 v8; // rax
  void *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  v1 = *((_DWORD *)this + 12) == 0;
  *(_QWORD *)this = &SystemEventTriggerControllerSink::`vftable'{for `ICallsStateChangeSink'};
  *((_QWORD *)this + 1) = &SystemEventTriggerControllerSink::`vftable'{for `IPhoneLineCreationSink'};
  *((_QWORD *)this + 2) = &SystemEventTriggerControllerSink::`vftable'{for `ILinePropertiesChangeSink'};
  *((_QWORD *)this + 3) = &SystemEventTriggerControllerSink::`vftable'{for `IPhoneServiceUiSink'};
  if ( v1 )
  {
    Log_AssertionEvent_2(
      this,
      "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\systemeventtriggercontrollersink.cpp",
      32);
    if ( !*((_DWORD *)this + 12) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v3 = (void *)*((_QWORD *)this + 31);
  if ( v3 )
    PowerSettingUnregisterNotification(v3);
  if ( *((_QWORD *)this + 29) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  v4 = (void *)*((_QWORD *)this + 26);
  if ( v4 != (void *)-1LL )
  {
    *((_QWORD *)this + 27) = v4;
    operator delete(v4);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v5 = (__int64 **)((char *)this + 128);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == (__int64 *)v5 )
      break;
    v7 = (__int64 *)v6[1];
    v8 = *v6;
    *v7 = *v6;
    *(_QWORD *)(v8 + 8) = v7;
    operator delete(v6);
  }
  v9 = (void *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 19) = 0;
  if ( v9 )
    operator delete(v9);
  v10 = *((_QWORD *)this + 15);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = *((_QWORD *)this + 14);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
}

```

## disassembly

```asm
0x180014014  mov     [rsp+arg_8], rbx
0x180014019  push    rdi
0x18001401a  sub     rsp, 20h
0x18001401e  cmp     dword ptr [rcx+30h], 0
0x180014022  lea     rax, ??_7SystemEventTriggerControllerSink@@6BICallsStateChangeSink@@@; const SystemEventTriggerControllerSink::`vftable'{for `ICallsStateChangeSink'}
0x180014029  mov     [rcx], rax
0x18001402c  mov     rbx, rcx
0x18001402f  lea     rax, ??_7SystemEventTriggerControllerSink@@6BIPhoneLineCreationSink@@@; const SystemEventTriggerControllerSink::`vftable'{for `IPhoneLineCreationSink'}
0x180014036  mov     [rcx+8], rax
0x18001403a  lea     rax, ??_7SystemEventTriggerControllerSink@@6BILinePropertiesChangeSink@@@; const SystemEventTriggerControllerSink::`vftable'{for `ILinePropertiesChangeSink'}
0x180014041  mov     [rcx+10h], rax
0x180014045  lea     rax, ??_7SystemEventTriggerControllerSink@@6BIPhoneServiceUiSink@@@; const SystemEventTriggerControllerSink::`vftable'{for `IPhoneServiceUiSink'}
0x18001404c  mov     [rcx+18h], rax
0x180014050  jnz     short loc_18001406F
0x180014052  mov     r8d, 20h ; ' '
0x180014058  lea     rdx, aOnecoreuapNetP_13; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18001405f  call    Log_AssertionEvent_2
0x180014064  cmp     dword ptr [rbx+30h], 0
0x180014068  jnz     short loc_18001406F
0x18001406a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001406f  mov     rcx, [rbx+0F8h]; RegistrationHandle
0x180014076  test    rcx, rcx
0x180014079  jz      short loc_180014081
0x18001407b  call    cs:__imp_PowerSettingUnregisterNotification
0x180014081  mov     rcx, [rbx+0E8h]
0x180014088  test    rcx, rcx
0x18001408b  jz      short loc_180014093
0x18001408d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180014093  mov     rcx, [rbx+0D0h]; Block
0x18001409a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001409e  jz      short loc_1800140B3
0x1800140a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800140a7  mov     [rbx+0D8h], rcx
0x1800140ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800140b3  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x1800140ba  call    cs:__imp_DeleteCriticalSection
0x1800140c0  lea     rdi, [rbx+80h]
0x1800140c7  mov     rcx, [rdi]; Block
0x1800140ca  cmp     rcx, rdi
0x1800140cd  jz      short loc_1800140EB
0x1800140cf  mov     rdx, [rcx+8]
0x1800140d3  mov     rax, [rcx]
0x1800140d6  mov     [rdx], rax
0x1800140d9  mov     [rax+8], rdx
0x1800140dd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800140e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800140e9  jmp     short loc_1800140C7
0x1800140eb  mov     rcx, [rdi+10h]; Block
0x1800140ef  mov     qword ptr [rdi+18h], 0
0x1800140f7  test    rcx, rcx
0x1800140fa  jz      short loc_180014108
0x1800140fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014103  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014108  mov     rcx, [rbx+78h]
0x18001410c  test    rcx, rcx
0x18001410f  jz      short loc_18001411D
0x180014111  mov     rax, [rcx]
0x180014114  mov     rax, [rax+10h]
0x180014118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001411d  mov     rcx, [rbx+70h]
0x180014121  test    rcx, rcx
0x180014124  jz      short loc_180014132
0x180014126  mov     rax, [rcx]
0x180014129  mov     rax, [rax+10h]
0x18001412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014132  lea     rcx, [rbx+48h]
0x180014136  mov     rbx, [rsp+28h+arg_8]
0x18001413b  add     rsp, 20h
0x18001413f  pop     rdi
0x180014140  jmp     cs:__imp_DeleteCriticalSection
```
