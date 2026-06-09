# McTemplateU0qqbr1_EtwEventWriteTransfer

- ea: `0x18001374c`
- end: `0x1800137ca`
- name: `McTemplateU0qqbr1_EtwEventWriteTransfer`
- size: `126`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d90`
- `0x1800058e0`

## callees

- `0x180007da0`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqbr1_EtwEventWriteTransfer(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  _BYTE v6[16]; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  int *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  int v14; // [rsp+A0h] [rbp+20h] BYREF
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a3;
  v12 = a4;
  v8 = 4;
  v7 = &v14;
  v10 = 4;
  v9 = &v15;
  v11 = a5;
  v13 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(0, (unsigned int)PrivateKeyNotFound, a3, 4, (__int64)v6);
}

```

## disassembly

```asm
0x18001374c  mov     [rsp-8+arg_18], r9d
0x180013751  mov     [rsp-8+arg_10], r8d
0x180013756  push    rbp
0x180013757  mov     rbp, rsp
0x18001375a  sub     rsp, 80h
0x180013761  mov     rax, cs:__security_cookie
0x180013768  xor     rax, rsp
0x18001376b  mov     [rbp+var_10], rax
0x18001376f  mov     edx, 4
0x180013774  mov     [rbp+var_18], r9d
0x180013778  lea     rax, [rbp+arg_10]
0x18001377c  mov     [rbp+var_38], rdx
0x180013780  mov     [rbp+var_40], rax
0x180013784  xor     ecx, ecx
0x180013786  lea     rax, [rbp+arg_18]
0x18001378a  mov     [rbp+var_28], rdx
0x18001378e  mov     [rbp+var_30], rax
0x180013792  mov     r9d, edx
0x180013795  mov     rax, [rbp+arg_20]
0x180013799  lea     rdx, PrivateKeyNotFound
0x1800137a0  mov     [rbp+var_20], rax
0x1800137a4  lea     rax, [rbp+var_50]
0x1800137a8  mov     [rsp+80h+var_60], rax
0x1800137ad  mov     [rbp+var_14], ecx
0x1800137b0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800137b5  mov     rcx, [rbp+var_10]
0x1800137b9  xor     rcx, rsp; StackCookie
0x1800137bc  call    __security_check_cookie
0x1800137c1  add     rsp, 80h
0x1800137c8  pop     rbp
0x1800137c9  retn
```
