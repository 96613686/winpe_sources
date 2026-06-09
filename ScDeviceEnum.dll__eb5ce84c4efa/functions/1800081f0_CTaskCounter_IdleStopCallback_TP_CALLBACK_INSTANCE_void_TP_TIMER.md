# CTaskCounter::_IdleStopCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800081f0`
- end: `0x18000826c`
- name: `?_IdleStopCallback@CTaskCounter@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `124`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800064c4`
- `0x18000769c`
- `0x180007944`
- `0x18001e020`

## string_xrefs

- `0x180008207`: `CTaskCounter::_IdleStopCallback`

## pseudocode

```c
void __fastcall CTaskCounter::_IdleStopCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  unsigned int v3; // ecx
  int v4; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v5; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v6[2]; // [rsp+30h] [rbp-40h] BYREF
  char v7[32]; // [rsp+40h] [rbp-30h] BYREF

  v4 = 0;
  v6[0] = v7;
  v6[1] = &v4;
  strcpy(v7, "CTaskCounter::_IdleStopCallback");
  lambda_659cec5dfa28274cb0707d2d5dcb7dde_::operator()(v6, Context, Timer);
  v4 = 1;
  v5 = v6;
  ScDeviceEnumInitiateShutdown(v3);
  WppTraceUnwinder__lambda_659cec5dfa28274cb0707d2d5dcb7dde____::_WppTraceUnwinder__lambda_659cec5dfa28274cb0707d2d5dcb7dde____(&v5);
}

```

## disassembly

```asm
0x1800081f0  push    rbp
0x1800081f2  mov     rbp, rsp
0x1800081f5  sub     rsp, 70h
0x1800081f9  mov     rax, cs:__security_cookie
0x180008200  xor     rax, rsp
0x180008203  mov     [rbp+var_10], rax
0x180008207  movups  xmm0, xmmword ptr cs:aCtaskcounterId; "CTaskCounter::_IdleStopCallback"
0x18000820e  lea     rax, [rbp+var_30]
0x180008212  mov     [rbp+var_50], 0
0x180008219  movups  xmm1, xmmword ptr cs:aCtaskcounterId+10h; "dleStopCallback"
0x180008220  mov     [rbp+var_40], rax
0x180008224  lea     rcx, [rbp+var_40]
0x180008228  lea     rax, [rbp+var_50]
0x18000822c  mov     [rbp+var_38], rax
0x180008230  movups  xmmword ptr [rbp+var_30], xmm0
0x180008234  movups  xmmword ptr [rbp+var_30+10h], xmm1
0x180008238  call    _lambda_659cec5dfa28274cb0707d2d5dcb7dde___operator__
0x18000823d  lea     rax, [rbp+var_40]
0x180008241  mov     [rbp+var_50], 1
0x180008248  mov     [rbp+var_48], rax
0x18000824c  call    ?ScDeviceEnumInitiateShutdown@@YAXK@Z; ScDeviceEnumInitiateShutdown(ulong)
0x180008251  lea     rcx, [rbp+var_48]
0x180008255  call    WppTraceUnwinder__lambda_659cec5dfa28274cb0707d2d5dcb7dde_______WppTraceUnwinder__lambda_659cec5dfa28274cb0707d2d5dcb7dde____
0x18000825a  mov     rcx, [rbp+var_10]
0x18000825e  xor     rcx, rsp; StackCookie
0x180008261  call    __security_check_cookie
0x180008266  add     rsp, 70h
0x18000826a  pop     rbp
0x18000826b  retn
```
