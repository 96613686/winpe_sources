# common_flush_all

- ea: `0x140016458`
- end: `0x1400164b5`
- name: `common_flush_all`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016544`
- `0x140016618`

## callees

- `0x140016374`

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
  ((void (__fastcall *)(char *, int *, _QWORD *, int *))_crt_seh_guarded_call_void_::operator()__lambda_886d6c58226a84441f68b9f2b8217b83___lambda_ab61a845afdef5b7c387490eaf3616ee_____lambda_f7f22ab5edc0698d5f6905b0d3f44752___)(
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
0x140016458  mov     [rsp-8+arg_0], cl
0x14001645c  push    rbp
0x14001645d  mov     rbp, rsp
0x140016460  sub     rsp, 40h
0x140016464  and     [rbp+arg_18], 0
0x140016468  lea     rax, [rbp+arg_18]
0x14001646c  and     [rbp+arg_10], 0
0x140016470  lea     r9, [rbp+var_20]
0x140016474  mov     [rbp+var_18], rax
0x140016478  lea     r8, [rbp+var_18]
0x14001647c  lea     rax, [rbp+arg_0]
0x140016480  mov     [rbp+var_10], rax
0x140016484  lea     rdx, [rbp+var_1C]
0x140016488  lea     rax, [rbp+arg_10]
0x14001648c  mov     [rbp+var_8], rax
0x140016490  lea     rcx, [rbp+arg_8]
0x140016494  mov     eax, 8
0x140016499  mov     [rbp+var_20], eax
0x14001649c  mov     [rbp+var_1C], eax
0x14001649f  call    __crt_seh_guarded_call_void___operator____lambda_886d6c58226a84441f68b9f2b8217b83___lambda_ab61a845afdef5b7c387490eaf3616ee_____lambda_f7f22ab5edc0698d5f6905b0d3f44752___
0x1400164a4  cmp     [rbp+arg_0], 0
0x1400164a8  mov     eax, [rbp+arg_10]
0x1400164ab  cmovnz  eax, [rbp+arg_18]
0x1400164af  add     rsp, 40h
0x1400164b3  pop     rbp
0x1400164b4  retn
```
