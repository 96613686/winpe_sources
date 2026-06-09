# common_flush_all

- ea: `0x1800145d0`
- end: `0x18001462d`
- name: `common_flush_all`
- size: `93`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800146ac`
- `0x1800146f8`

## callees

- `0x1800144f0`

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
0x1800145d0  mov     [rsp-8+arg_0], cl
0x1800145d4  push    rbp
0x1800145d5  mov     rbp, rsp
0x1800145d8  sub     rsp, 40h
0x1800145dc  and     [rbp+arg_18], 0
0x1800145e0  lea     rax, [rbp+arg_18]
0x1800145e4  and     [rbp+arg_10], 0
0x1800145e8  lea     r9, [rbp+var_20]
0x1800145ec  mov     [rbp+var_18], rax
0x1800145f0  lea     r8, [rbp+var_18]
0x1800145f4  lea     rax, [rbp+arg_0]
0x1800145f8  mov     [rbp+var_10], rax
0x1800145fc  lea     rdx, [rbp+var_1C]
0x180014600  lea     rax, [rbp+arg_10]
0x180014604  mov     [rbp+var_8], rax
0x180014608  lea     rcx, [rbp+arg_8]
0x18001460c  mov     eax, 8
0x180014611  mov     [rbp+var_20], eax
0x180014614  mov     [rbp+var_1C], eax
0x180014617  call    __crt_seh_guarded_call_void___operator____lambda_886d6c58226a84441f68b9f2b8217b83___lambda_ab61a845afdef5b7c387490eaf3616ee_____lambda_f7f22ab5edc0698d5f6905b0d3f44752___
0x18001461c  cmp     [rbp+arg_0], 0
0x180014620  mov     eax, [rbp+arg_10]
0x180014623  cmovnz  eax, [rbp+arg_18]
0x180014627  add     rsp, 40h
0x18001462b  pop     rbp
0x18001462c  retn
```
