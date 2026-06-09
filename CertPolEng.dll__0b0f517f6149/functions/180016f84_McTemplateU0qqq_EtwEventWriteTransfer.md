# McTemplateU0qqq_EtwEventWriteTransfer

- ea: `0x180016f84`
- end: `0x180016ffb`
- name: `McTemplateU0qqq_EtwEventWriteTransfer`
- size: `119`
- prototype: `__int64 __fastcall(int, __int64, int, int, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d51c`
- `0x180015c94`

## callees

- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqq_EtwEventWriteTransfer(int a1, __int64 a2, int a3, int a4, char a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  char *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+A0h] [rbp+20h] BYREF
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v13 = a3;
  v7 = &v13;
  v8 = 4;
  v9 = &v14;
  v11 = &a5;
  v10 = 4;
  v12 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(a1, (unsigned int)CertVerifyFailed, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x180016f84  mov     [rsp-8+arg_18], r9d
0x180016f89  mov     [rsp-8+arg_10], r8d
0x180016f8e  push    rbp
0x180016f8f  mov     rbp, rsp
0x180016f92  sub     rsp, 80h
0x180016f99  mov     rax, cs:__security_cookie
0x180016fa0  xor     rax, rsp
0x180016fa3  mov     [rbp+var_10], rax
0x180016fa7  mov     r9d, 4
0x180016fad  lea     rax, [rbp+arg_10]
0x180016fb1  mov     [rbp+var_40], rax
0x180016fb5  lea     rdx, CertVerifyFailed
0x180016fbc  lea     rax, [rbp+arg_18]
0x180016fc0  mov     [rbp+var_38], r9
0x180016fc4  mov     [rbp+var_30], rax
0x180016fc8  lea     rax, [rbp+arg_20]
0x180016fcc  mov     [rbp+var_20], rax
0x180016fd0  lea     rax, [rbp+var_50]
0x180016fd4  mov     [rsp+80h+var_60], rax
0x180016fd9  mov     [rbp+var_28], r9
0x180016fdd  mov     [rbp+var_18], r9
0x180016fe1  call    McGenEventWrite_EtwEventWriteTransfer
0x180016fe6  mov     rcx, [rbp+var_10]
0x180016fea  xor     rcx, rsp; StackCookie
0x180016fed  call    __security_check_cookie
0x180016ff2  add     rsp, 80h
0x180016ff9  pop     rbp
0x180016ffa  retn
```
