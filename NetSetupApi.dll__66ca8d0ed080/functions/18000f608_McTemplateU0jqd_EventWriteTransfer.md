# McTemplateU0jqd_EventWriteTransfer

- ea: `0x18000f608`
- end: `0x18000f67a`
- name: `McTemplateU0jqd_EventWriteTransfer`
- size: `114`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int, char)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x180001390`
- `0x1800016d0`
- `0x1800017a0`
- `0x180001900`
- `0x180003970`
- `0x180004af0`
- `0x180004fc0`

## callees

- `0x18000f548`
- `0x1800119f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0jqd_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  char *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+A8h] [rbp+28h] BYREF

  v13 = a4;
  v7 = a3;
  v8 = 16;
  v9 = &v13;
  v10 = 4;
  v11 = &a5;
  v12 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EndApi, a3, 4u, &v6);
}

```

## disassembly

```asm
0x18000f608  mov     [rsp-8+arg_18], r9d
0x18000f60d  push    rbp
0x18000f60e  mov     rbp, rsp
0x18000f611  sub     rsp, 80h
0x18000f618  mov     rax, cs:__security_cookie
0x18000f61f  xor     rax, rsp
0x18000f622  mov     [rbp+var_10], rax
0x18000f626  mov     r9d, 4
0x18000f62c  mov     [rbp+var_40], r8
0x18000f630  lea     rax, [rbp+arg_18]
0x18000f634  mov     [rbp+var_38], 10h
0x18000f63c  mov     [rbp+var_30], rax
0x18000f640  lea     rdx, EndApi
0x18000f647  lea     rax, [rbp+arg_20]
0x18000f64b  mov     [rbp+var_28], r9
0x18000f64f  mov     [rbp+var_20], rax
0x18000f653  lea     rax, [rbp+var_50]
0x18000f657  mov     [rsp+80h+var_60], rax
0x18000f65c  mov     [rbp+var_18], r9
0x18000f660  call    McGenEventWrite_EventWriteTransfer
0x18000f665  mov     rcx, [rbp+var_10]
0x18000f669  xor     rcx, rsp; StackCookie
0x18000f66c  call    __security_check_cookie
0x18000f671  add     rsp, 80h
0x18000f678  pop     rbp
0x18000f679  retn
```
