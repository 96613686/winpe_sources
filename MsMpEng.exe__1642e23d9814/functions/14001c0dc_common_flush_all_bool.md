# common_flush_all(bool)

- ea: `0x14001c0dc`
- end: `0x14001c139`
- name: `?common_flush_all@@YAH_N@Z`
- size: `93`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001c1c8`
- `0x14001c29c`

## callees

- `0x14001bff8`

## pseudocode

```c
__int64 __fastcall common_flush_all(char a1)
{
  __int64 result; // rax
  int v2; // [rsp+20h] [rbp-20h] BYREF
  int v3; // [rsp+24h] [rbp-1Ch] BYREF
  _QWORD v4[3]; // [rsp+28h] [rbp-18h] BYREF
  char v5; // [rsp+50h] [rbp+10h] BYREF
  char v6; // [rsp+58h] [rbp+18h] BYREF
  unsigned int v7; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v8; // [rsp+68h] [rbp+28h] BYREF

  v5 = a1;
  v8 = 0;
  v7 = 0;
  v4[0] = &v8;
  v4[1] = &v5;
  v4[2] = &v7;
  v2 = 8;
  v3 = 8;
  ((void (__fastcall *)(char *, int *, _QWORD *, int *))__crt_seh_guarded_call<void>::operator()<_lambda_886d6c58226a84441f68b9f2b8217b83_,_lambda_ab61a845afdef5b7c387490eaf3616ee_ &,_lambda_f7f22ab5edc0698d5f6905b0d3f44752_>)(
    &v6,
    &v3,
    v4,
    &v2);
  result = v7;
  if ( v5 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x14001c0dc  mov     [rsp-8+arg_0], cl
0x14001c0e0  push    rbp
0x14001c0e1  mov     rbp, rsp
0x14001c0e4  sub     rsp, 40h
0x14001c0e8  and     [rbp+arg_18], 0
0x14001c0ec  lea     rax, [rbp+arg_18]
0x14001c0f0  and     [rbp+arg_10], 0
0x14001c0f4  lea     r9, [rbp+var_20]
0x14001c0f8  mov     [rbp+var_18], rax
0x14001c0fc  lea     r8, [rbp+var_18]
0x14001c100  lea     rax, [rbp+arg_0]
0x14001c104  mov     [rbp+var_10], rax
0x14001c108  lea     rdx, [rbp+var_1C]
0x14001c10c  lea     rax, [rbp+arg_10]
0x14001c110  mov     [rbp+var_8], rax
0x14001c114  lea     rcx, [rbp+arg_8]
0x14001c118  mov     eax, 8
0x14001c11d  mov     [rbp+var_20], eax
0x14001c120  mov     [rbp+var_1C], eax
0x14001c123  call    ??$?RV_lambda_886d6c58226a84441f68b9f2b8217b83_@@AEAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@V_lambda_f7f22ab5edc0698d5f6905b0d3f44752_@@@?$__crt_seh_guarded_call@X@@QEAAX$$QEAV_lambda_886d6c58226a84441f68b9f2b8217b83_@@AEAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@$$QEAV_lambda_f7f22ab5edc0698d5f6905b0d3f44752_@@@Z
0x14001c128  cmp     [rbp+arg_0], 0
0x14001c12c  mov     eax, [rbp+arg_10]
0x14001c12f  cmovnz  eax, [rbp+arg_18]
0x14001c133  add     rsp, 40h
0x14001c137  pop     rbp
0x14001c138  retn
```
