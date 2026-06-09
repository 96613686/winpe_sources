# BfTelemetryAndTracingInit

- ea: `0x140027558`
- end: `0x1400276a6`
- name: `BfTelemetryAndTracingInit`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140027078`

## callees

- `0x140001348`
- `0x140004b90`
- `0x140011664`
- `0x1400117f0`
- `0x1400118b8`
- `0x140027558`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140027620`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140027620`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14002760d`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14002760d`

## pseudocode

```c
__int64 __fastcall BfTelemetryAndTracingInit(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // edx
  int v6; // [rsp+38h] [rbp-30h]
  _QWORD v7[2]; // [rsp+40h] [rbp-28h] BYREF

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_BindFltTrace;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(a1, a2);
  v7[0] = 0x100000010LL;
  v7[1] = 0x200000002LL;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, v7);
  BfTraceRecorder = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
  result = TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  if ( (int)result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = result;
    LOBYTE(v5) = 2;
    return WPP_RECORDER_SF_sDd(
             WPP_GLOBAL_Control->DeviceExtension,
             v5,
             1,
             10,
             (__int64)WPP_cdf94b27e759309871abc3849a751d26_Traceguids,
             (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\telemetry.c",
             87,
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x140027558  mov     [rsp+arg_10], rbx
0x14002755d  push    rdi
0x14002755e  sub     rsp, 60h
0x140027562  mov     rax, cs:__security_cookie
0x140027569  xor     rax, rsp
0x14002756c  mov     [rsp+68h+var_18], rax
0x140027571  lea     rax, WPP_ThisDir_CTLGUID_BindFltTrace
0x140027578  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140027583  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14002758a  mov     rdi, rdx
0x14002758d  xor     eax, eax
0x14002758f  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14002759a  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1400275a0  mov     rbx, rcx
0x1400275a3  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400275ae  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400275b9  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400275c4  call    WppLoadTracingSupport
0x1400275c9  mov     rdx, rdi
0x1400275cc  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400275d7  mov     rcx, rbx
0x1400275da  call    WppInitKm
0x1400275df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400275e6  lea     rdx, [rsp+68h+var_28]
0x1400275eb  xorps   xmm0, xmm0
0x1400275ee  mov     ebx, 2
0x1400275f3  movups  [rsp+68h+var_28], xmm0
0x1400275f8  mov     dword ptr [rsp+68h+var_28], 10h
0x140027600  mov     byte ptr [rsp+68h+var_28+4], 1
0x140027605  mov     dword ptr [rsp+68h+var_28+8], ebx
0x140027609  mov     dword ptr [rsp+68h+var_28+0Ch], ebx
0x14002760d  call    cs:__imp_imp_WppRecorderConfigure
0x140027614  nop     dword ptr [rax+rax+00h]
0x140027619  mov     rcx, cs:WPP_GLOBAL_Control
0x140027620  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140027627  nop     dword ptr [rax+rax+00h]
0x14002762c  mov     cs:_BfTraceRecorder, rax
0x140027633  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140027638  test    eax, eax
0x14002763a  jns     short loc_14002768A
0x14002763c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140027643  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002764a  jz      short loc_14002768A
0x14002764c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027653  lea     r9d, [rbx+8]
0x140027657  mov     [rsp+68h+var_30], eax
0x14002765b  lea     r8d, [rbx-1]
0x14002765f  lea     rax, aOnecoreBaseFsW_7; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140027666  mov     [rsp+68h+var_38], 57h ; 'W'
0x14002766e  mov     [rsp+68h+var_40], rax
0x140027673  mov     dl, bl
0x140027675  mov     rcx, [rcx+40h]
0x140027679  lea     rax, WPP_cdf94b27e759309871abc3849a751d26_Traceguids
0x140027680  mov     [rsp+68h+var_48], rax
0x140027685  call    WPP_RECORDER_SF_sDd
0x14002768a  mov     rcx, [rsp+68h+var_18]
0x14002768f  xor     rcx, rsp; StackCookie
0x140027692  call    __security_check_cookie
0x140027697  mov     rbx, [rsp+68h+arg_10]
0x14002769f  add     rsp, 60h
0x1400276a3  pop     rdi
0x1400276a4  retn
```
