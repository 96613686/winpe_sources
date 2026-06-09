# WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::Invoke(__MIDL___MIDL_itf_wpnplatform_0000_0007_0001,long,ushort const *)

- ea: `0x180015dc0`
- end: `0x180015f5d`
- name: `?Invoke@IncomingCallToastFeedback@Calls@ApplicationModel@WindowsInternal@@UEAAJW4__MIDL___MIDL_itf_wpnplatform_0000_0007_0001@@JPEBG@Z`
- size: `413`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x18000cf20`
- `0x18000cf2c`
- `0x180015dc0`
- `0x180015f64`
- `0x1800164d4`
- `0x1800165c4`

## import_xrefs

- `PhoneOm!PhoneRejectIncoming` at `0x180015e92`
- `PhoneOm!PhoneRejectIncoming` at `0x180015e92`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015eaf`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015f22`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015eaf`
- `PhoneOm!PhoneAPIUninitialize` at `0x180015f22`
- `PhoneOm!PhoneAPIInitialize` at `0x180015de4`
- `PhoneOm!PhoneAPIInitialize` at `0x180015de4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180015ef2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180015ef2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f10`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x180015f1c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x180015f1c`

## string_xrefs

- `0x180015e5d`: `IncomingCallToastFeedback: Invoked, callId`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastFeedback::Invoke(__int64 a1, int a2)
{
  int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // rcx
  DWORD ProcessId; // ebx
  int CallingProcessHandle; // edi
  char *v18; // rcx
  __int64 v19; // rcx
  HANDLE Process; // [rsp+30h] [rbp-39h] BYREF
  int v21; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+40h] [rbp-29h] BYREF
  const char *v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  HANDLE *p_Process; // [rsp+70h] [rbp+7h]
  __int64 v26; // [rsp+78h] [rbp+Fh]
  int *v27; // [rsp+80h] [rbp+17h]
  __int64 v28; // [rsp+88h] [rbp+1Fh]

  v4 = PhoneAPIInitialize();
  v6 = v4;
  if ( v4 < 0 )
  {
    Log_HREvent_0((unsigned int)v4, 1, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h");
    Log_HREvent_2(v6, v7, v8, 25);
    return v6;
  }
  v10 = 4;
  if ( (unsigned int)dword_180025038 > 4 )
  {
    LODWORD(Process) = *(_DWORD *)(a1 + 32);
    v28 = 4;
    v27 = &v21;
    v26 = 4;
    p_Process = &Process;
    v21 = a2;
    v23 = "IncomingCallToastFeedback: Invoked, callId";
    v24 = 43;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180025038, (int)&dword_1800211B4, 0, 0, 5u, &v22);
  }
  if ( a2 == 2 )
  {
    v11 = PhoneRejectIncoming(a1 + 32);
    v14 = v11;
    if ( v11 < 0 )
    {
      Log_HREvent_2((unsigned int)v11, v12, v13, 37);
      if ( (int)PhoneAPIUninitialize() < 0 )
      {
        Log_AssertionEvent_1(v15, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      return v14;
    }
  }
  else if ( a2 == 1 )
  {
    ProcessId = 0;
    Process = 0;
    CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(v10, v5, &Process);
    if ( CallingProcessHandle >= 0 )
      ProcessId = GetProcessId(Process);
    v18 = (char *)Process;
    Process = 0;
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v18);
    if ( CallingProcessHandle >= 0 )
      AllowSetForegroundWindow(ProcessId);
  }
  if ( (int)PhoneAPIUninitialize() < 0 )
  {
    Log_AssertionEvent_1(v19, "OnecoreUAP\\internal\\Net\\inc\\phsmartpointers.h", 62);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  return 0;
}

```

## disassembly

```asm
0x180015dc0  push    rbp
0x180015dc2  push    rbx
0x180015dc3  push    rsi
0x180015dc4  push    rdi
0x180015dc5  lea     rbp, [rsp-3Fh]
0x180015dca  sub     rsp, 0A8h
0x180015dd1  mov     rax, cs:__security_cookie
0x180015dd8  xor     rax, rsp
0x180015ddb  mov     [rbp+57h+var_30], rax
0x180015ddf  mov     ebx, edx
0x180015de1  mov     rsi, rcx
0x180015de4  call    cs:__imp_PhoneAPIInitialize
0x180015dea  mov     edi, eax
0x180015dec  test    eax, eax
0x180015dee  jns     short loc_180015E1C
0x180015df0  mov     r9d, 33h ; '3'
0x180015df6  lea     r8, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015dfd  mov     ecx, eax
0x180015dff  lea     edx, [r9-32h]
0x180015e03  call    Log_HREvent_0
0x180015e08  mov     r9d, 19h
0x180015e0e  mov     ecx, edi
0x180015e10  call    Log_HREvent_2
0x180015e15  mov     eax, edi
0x180015e17  jmp     loc_180015F45
0x180015e1c  mov     eax, cs:dword_180025038
0x180015e22  mov     ecx, 4
0x180015e27  cmp     eax, ecx
0x180015e29  jbe     short loc_180015E89
0x180015e2b  mov     eax, [rsi+20h]
0x180015e2e  lea     rdx, dword_1800211B4; int
0x180015e35  mov     dword ptr [rbp+57h+Process], eax
0x180015e38  xor     r9d, r9d; int
0x180015e3b  lea     rax, [rbp+57h+var_88]
0x180015e3f  mov     [rbp+57h+var_38], rcx
0x180015e43  mov     [rbp+57h+var_40], rax
0x180015e47  xor     r8d, r8d; int
0x180015e4a  lea     rax, [rbp+57h+Process]
0x180015e4e  mov     [rbp+57h+var_48], rcx
0x180015e52  mov     [rbp+57h+var_50], rax
0x180015e56  lea     rcx, dword_180025038; int
0x180015e5d  lea     rax, aIncomingcallto_1; "IncomingCallToastFeedback: Invoked, cal"...
0x180015e64  mov     [rbp+57h+var_88], ebx
0x180015e67  mov     [rbp+57h+var_60], rax
0x180015e6b  lea     rax, [rbp+57h+var_80]
0x180015e6f  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x180015e74  mov     [rsp+0C0h+var_A0], 5; ULONG
0x180015e7c  mov     [rbp+57h+var_58], 2Bh ; '+'
0x180015e84  call    _tlgWriteTransfer_EventWriteTransfer
0x180015e89  cmp     ebx, 2
0x180015e8c  jnz     short loc_180015ED4
0x180015e8e  lea     rcx, [rsi+20h]
0x180015e92  call    cs:__imp_PhoneRejectIncoming
0x180015e98  mov     ebx, eax
0x180015e9a  test    eax, eax
0x180015e9c  jns     loc_180015F22
0x180015ea2  mov     r9d, 25h ; '%'
0x180015ea8  mov     ecx, eax
0x180015eaa  call    Log_HREvent_2
0x180015eaf  call    cs:__imp_PhoneAPIUninitialize
0x180015eb5  test    eax, eax
0x180015eb7  jns     short loc_180015ED0
0x180015eb9  mov     r8d, 3Eh ; '>'
0x180015ebf  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015ec6  call    Log_AssertionEvent_1
0x180015ecb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015ed0  mov     eax, ebx
0x180015ed2  jmp     short loc_180015F45
0x180015ed4  cmp     ebx, 1
0x180015ed7  jnz     short loc_180015F22
0x180015ed9  xor     ebx, ebx
0x180015edb  lea     r8, [rbp+57h+Process]
0x180015edf  mov     [rbp+57h+Process], rbx
0x180015ee3  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x180015ee8  mov     edi, eax
0x180015eea  test    eax, eax
0x180015eec  js      short loc_180015EFA
0x180015eee  mov     rcx, [rbp+57h+Process]; Process
0x180015ef2  call    cs:__imp_GetProcessId
0x180015ef8  mov     ebx, eax
0x180015efa  mov     rcx, [rbp+57h+Process]; hObject
0x180015efe  mov     [rbp+57h+Process], 0
0x180015f06  lea     rdx, [rcx-1]
0x180015f0a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180015f0e  ja      short loc_180015F16
0x180015f10  call    cs:__imp_CloseHandle
0x180015f16  test    edi, edi
0x180015f18  js      short loc_180015F22
0x180015f1a  mov     ecx, ebx; dwProcessId
0x180015f1c  call    cs:__imp_AllowSetForegroundWindow
0x180015f22  call    cs:__imp_PhoneAPIUninitialize
0x180015f28  test    eax, eax
0x180015f2a  jns     short loc_180015F43
0x180015f2c  mov     r8d, 3Eh ; '>'
0x180015f32  lea     rdx, aOnecoreuapInte_0; "OnecoreUAP\\internal\\Net\\inc\\phsmart"...
0x180015f39  call    Log_AssertionEvent_1
0x180015f3e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180015f43  xor     eax, eax
0x180015f45  mov     rcx, [rbp+57h+var_30]
0x180015f49  xor     rcx, rsp; StackCookie
0x180015f4c  call    __security_check_cookie
0x180015f51  add     rsp, 0A8h
0x180015f58  pop     rdi
0x180015f59  pop     rsi
0x180015f5a  pop     rbx
0x180015f5b  pop     rbp
0x180015f5c  retn
```
