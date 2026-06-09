# CTaskCounter::_StartTimer(void)

- ea: `0x180008274`
- end: `0x18000831e`
- name: `?_StartTimer@CTaskCounter@@AEAAXXZ`
- size: `170`
- prototype: `void __fastcall(CTaskCounter *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007bb4`
- `0x180007ec0`

## callees

- `0x18000762c`
- `0x1800077d4`
- `0x180008274`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082f5`

## string_xrefs

- `0x18000828f`: `CTaskCounter::_StartTimer`

## pseudocode

```c
void __fastcall CTaskCounter::_StartTimer(CTaskCounter *this)
{
  struct _TP_TIMER *v2; // rcx
  int v3; // [rsp+20h] [rbp-50h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v5; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v6[2]; // [rsp+38h] [rbp-38h] BYREF
  char v7[32]; // [rsp+48h] [rbp-28h] BYREF

  v6[0] = v7;
  v3 = 0;
  strcpy(v7, "CTaskCounter::_StartTimer");
  v6[1] = &v3;
  lambda_177e4d5068e9471e6d4e8c500c6eb1f7_::operator()(v6);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 16);
  v3 = 1;
  v5 = v6;
  pftDueTime = (struct _FILETIME)-600000000LL;
  if ( v2 )
    SetThreadpoolTimer(v2, &pftDueTime, 0, 0);
  WppTraceUnwinder__lambda_177e4d5068e9471e6d4e8c500c6eb1f7____::_WppTraceUnwinder__lambda_177e4d5068e9471e6d4e8c500c6eb1f7____(&v5);
}

```

## disassembly

```asm
0x180008274  mov     [rsp-8+arg_8], rbx
0x180008279  push    rbp
0x18000827a  mov     rbp, rsp
0x18000827d  sub     rsp, 70h
0x180008281  mov     rax, cs:__security_cookie
0x180008288  xor     rax, rsp
0x18000828b  mov     [rbp+var_8], rax
0x18000828f  movups  xmm0, xmmword ptr cs:aCtaskcounterSt; "CTaskCounter::_StartTimer"
0x180008296  lea     rax, [rbp+var_28]
0x18000829a  mov     rbx, rcx
0x18000829d  movups  xmm1, xmmword ptr cs:aCtaskcounterSt+0Ah; "er::_StartTimer"
0x1800082a4  mov     [rbp+var_38], rax
0x1800082a8  lea     rcx, [rbp+var_38]
0x1800082ac  lea     rax, [rbp+var_50]
0x1800082b0  mov     [rbp+var_50], 0
0x1800082b7  movups  xmmword ptr [rbp+var_28], xmm0
0x1800082bb  mov     [rbp+var_30], rax
0x1800082bf  movups  xmmword ptr [rbp+var_28+0Ah], xmm1
0x1800082c3  call    _lambda_177e4d5068e9471e6d4e8c500c6eb1f7___operator__
0x1800082c8  mov     rcx, [rbx+80h]; pti
0x1800082cf  lea     rax, [rbp+var_38]
0x1800082d3  mov     [rbp+var_50], 1
0x1800082da  mov     [rbp+var_40], rax
0x1800082de  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x1800082e6  test    rcx, rcx
0x1800082e9  jz      short loc_1800082FB
0x1800082eb  xor     r9d, r9d; msWindowLength
0x1800082ee  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800082f2  xor     r8d, r8d; msPeriod
0x1800082f5  call    cs:__imp_SetThreadpoolTimer
0x1800082fb  lea     rcx, [rbp+var_40]
0x1800082ff  call    WppTraceUnwinder__lambda_177e4d5068e9471e6d4e8c500c6eb1f7_______WppTraceUnwinder__lambda_177e4d5068e9471e6d4e8c500c6eb1f7____
0x180008304  mov     rcx, [rbp+var_8]
0x180008308  xor     rcx, rsp; StackCookie
0x18000830b  call    __security_check_cookie
0x180008310  mov     rbx, [rsp+70h+arg_8]
0x180008318  add     rsp, 70h
0x18000831c  pop     rbp
0x18000831d  retn
```
