# CalaisCreateAsyncReaderHandlingWork(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)

- ea: `0x180017db0`
- end: `0x180017e64`
- name: `?CalaisCreateAsyncReaderHandlingWork@@YAPEAU_TP_WORK@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z`
- size: `180`
- prototype: `PTP_WORK __fastcall(PTP_WORK_CALLBACK pfnwk, PVOID pv)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002680`
- `0x180017f44`
- `0x18002a150`

## callees

- `0x180017e6c`
- `0x180017ec8`
- `0x1800326d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017e31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180017e31`

## string_xrefs

- `0x180017dd9`: `CalaisCreateAsyncReaderHandlingWork`

## pseudocode

```c
PTP_WORK __fastcall CalaisCreateAsyncReaderHandlingWork(PTP_WORK_CALLBACK pfnwk, PVOID pv)
{
  PTP_WORK ThreadpoolWork; // rbx
  int v6; // [rsp+20h] [rbp-50h] BYREF
  _QWORD *v7; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-40h] BYREF
  char v9[40]; // [rsp+40h] [rbp-30h] BYREF

  v8[0] = v9;
  v6 = 0;
  v8[1] = &v6;
  strcpy(v9, "CalaisCreateAsyncReaderHandlingWork");
  lambda_7bc452c0906793a60a7c43b4907c0666_::operator()(v8);
  v6 = 1;
  v7 = v8;
  ThreadpoolWork = CreateThreadpoolWork(pfnwk, pv, &pcbe);
  WppTraceUnwinder__lambda_7bc452c0906793a60a7c43b4907c0666____::_WppTraceUnwinder__lambda_7bc452c0906793a60a7c43b4907c0666____(&v7);
  return ThreadpoolWork;
}

```

## disassembly

```asm
0x180017db0  mov     [rsp-8+arg_10], rbx
0x180017db5  mov     [rsp-8+arg_18], rdi
0x180017dba  push    rbp
0x180017dbb  mov     rbp, rsp
0x180017dbe  sub     rsp, 70h
0x180017dc2  mov     rax, cs:__security_cookie
0x180017dc9  xor     rax, rsp
0x180017dcc  mov     [rbp+var_8], rax
0x180017dd0  mov     eax, dword ptr cs:aCalaiscreateas+20h; "ork"
0x180017dd6  mov     rbx, rcx
0x180017dd9  movups  xmm0, xmmword ptr cs:aCalaiscreateas; "CalaisCreateAsyncReaderHandlingWork"
0x180017de0  mov     dword ptr [rbp+var_30+20h], eax
0x180017de3  lea     rax, [rbp+var_30]
0x180017de7  movups  xmm1, xmmword ptr cs:aCalaiscreateas+10h; "cReaderHandlingWork"
0x180017dee  mov     [rbp+var_40], rax
0x180017df2  lea     rcx, [rbp+var_40]
0x180017df6  lea     rax, [rbp+var_50]
0x180017dfa  mov     [rbp+var_50], 0
0x180017e01  mov     [rbp+var_38], rax
0x180017e05  mov     rdi, rdx
0x180017e08  movups  xmmword ptr [rbp+var_30], xmm0
0x180017e0c  movups  xmmword ptr [rbp+var_30+10h], xmm1
0x180017e10  call    _lambda_7bc452c0906793a60a7c43b4907c0666___operator__
0x180017e15  lea     rax, [rbp+var_40]
0x180017e19  mov     [rbp+var_50], 1
0x180017e20  lea     r8, pcbe; pcbe
0x180017e27  mov     [rbp+var_48], rax
0x180017e2b  mov     rdx, rdi; pv
0x180017e2e  mov     rcx, rbx; pfnwk
0x180017e31  call    cs:__imp_CreateThreadpoolWork
0x180017e37  lea     rcx, [rbp+var_48]
0x180017e3b  mov     rbx, rax
0x180017e3e  call    WppTraceUnwinder__lambda_7bc452c0906793a60a7c43b4907c0666_______WppTraceUnwinder__lambda_7bc452c0906793a60a7c43b4907c0666____
0x180017e43  mov     rax, rbx
0x180017e46  mov     rcx, [rbp+var_8]
0x180017e4a  xor     rcx, rsp; StackCookie
0x180017e4d  call    __security_check_cookie
0x180017e52  lea     r11, [rsp+70h+var_s0]
0x180017e57  mov     rbx, [r11+20h]
0x180017e5b  mov     rdi, [r11+28h]
0x180017e5f  mov     rsp, r11
0x180017e62  pop     rbp
0x180017e63  retn
```
