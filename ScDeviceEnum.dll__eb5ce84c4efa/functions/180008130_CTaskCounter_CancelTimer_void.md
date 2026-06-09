# CTaskCounter::_CancelTimer(void)

- ea: `0x180008130`
- end: `0x1800081e2`
- name: `?_CancelTimer@CTaskCounter@@AEAAXXZ`
- size: `178`
- prototype: `void __fastcall(CTaskCounter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007d34`

## callees

- `0x180007664`
- `0x18000788c`
- `0x180008130`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800081a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800081a7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800081b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800081b9`

## string_xrefs

- `0x18000814b`: `CTaskCounter::_CancelTimer`

## pseudocode

```c
void __fastcall CTaskCounter::_CancelTimer(CTaskCounter *this)
{
  struct _TP_TIMER *v2; // rcx
  int v3; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v4; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v5[2]; // [rsp+30h] [rbp-40h] BYREF
  char v6[32]; // [rsp+40h] [rbp-30h] BYREF

  v5[0] = v6;
  v3 = 0;
  strcpy(v6, "CTaskCounter::_CancelTimer");
  v5[1] = &v3;
  lambda_48d192f5eb5960395e6be2e86b987162_::operator()(v5);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 16);
  v3 = 1;
  v4 = v5;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 16), 1);
  }
  WppTraceUnwinder__lambda_48d192f5eb5960395e6be2e86b987162____::_WppTraceUnwinder__lambda_48d192f5eb5960395e6be2e86b987162____(&v4);
}

```

## disassembly

```asm
0x180008130  mov     [rsp-8+arg_8], rbx
0x180008135  push    rbp
0x180008136  mov     rbp, rsp
0x180008139  sub     rsp, 70h
0x18000813d  mov     rax, cs:__security_cookie
0x180008144  xor     rax, rsp
0x180008147  mov     [rbp+var_10], rax
0x18000814b  movups  xmm0, xmmword ptr cs:aCtaskcounterCa; "CTaskCounter::_CancelTimer"
0x180008152  lea     rax, [rbp+var_30]
0x180008156  mov     rbx, rcx
0x180008159  movups  xmm1, xmmword ptr cs:aCtaskcounterCa+0Bh; "r::_CancelTimer"
0x180008160  mov     [rbp+var_40], rax
0x180008164  lea     rcx, [rbp+var_40]
0x180008168  lea     rax, [rbp+var_50]
0x18000816c  mov     [rbp+var_50], 0
0x180008173  movups  xmmword ptr [rbp+var_30], xmm0
0x180008177  mov     [rbp+var_38], rax
0x18000817b  movups  xmmword ptr [rbp+var_30+0Bh], xmm1
0x18000817f  call    _lambda_48d192f5eb5960395e6be2e86b987162___operator__
0x180008184  mov     rcx, [rbx+80h]; pti
0x18000818b  lea     rax, [rbp+var_40]
0x18000818f  mov     [rbp+var_50], 1
0x180008196  mov     [rbp+var_48], rax
0x18000819a  test    rcx, rcx
0x18000819d  jz      short loc_1800081BF
0x18000819f  xor     r9d, r9d; msWindowLength
0x1800081a2  xor     r8d, r8d; msPeriod
0x1800081a5  xor     edx, edx; pftDueTime
0x1800081a7  call    cs:__imp_SetThreadpoolTimer
0x1800081ad  mov     rcx, [rbx+80h]; pti
0x1800081b4  mov     edx, 1; fCancelPendingCallbacks
0x1800081b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800081bf  lea     rcx, [rbp+var_48]
0x1800081c3  call    WppTraceUnwinder__lambda_48d192f5eb5960395e6be2e86b987162_______WppTraceUnwinder__lambda_48d192f5eb5960395e6be2e86b987162____
0x1800081c8  mov     rcx, [rbp+var_10]
0x1800081cc  xor     rcx, rsp; StackCookie
0x1800081cf  call    __security_check_cookie
0x1800081d4  mov     rbx, [rsp+70h+arg_8]
0x1800081dc  add     rsp, 70h
0x1800081e0  pop     rbp
0x1800081e1  retn
```
