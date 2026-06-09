# WPP_SF_ddllllldddd

- ea: `0x1800162f4`
- end: `0x1800163d8`
- name: `WPP_SF_ddllllldddd`
- size: `228`
- prototype: `ULONG(__int64, __int64, __int64, int, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fde8`

## callees

- `0x1800014b0`
- `0x18000b794`

## pseudocode

```c
ULONG WPP_SF_ddllllldddd(__int64 a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+D8h] [rbp-9h] BYREF
  __int64 v6; // [rsp+118h] [rbp+37h] BYREF
  va_list va; // [rsp+118h] [rbp+37h]
  __int64 v8; // [rsp+120h] [rbp+3Fh] BYREF
  va_list va1; // [rsp+120h] [rbp+3Fh]
  __int64 v10; // [rsp+128h] [rbp+47h] BYREF
  va_list va2; // [rsp+128h] [rbp+47h]
  __int64 v12; // [rsp+130h] [rbp+4Fh] BYREF
  va_list va3; // [rsp+130h] [rbp+4Fh]
  __int64 v14; // [rsp+138h] [rbp+57h] BYREF
  va_list va4; // [rsp+138h] [rbp+57h]
  __int64 v16; // [rsp+140h] [rbp+5Fh] BYREF
  va_list va5; // [rsp+140h] [rbp+5Fh]
  __int64 v18; // [rsp+148h] [rbp+67h] BYREF
  va_list va6; // [rsp+148h] [rbp+67h]
  __int64 v20; // [rsp+150h] [rbp+6Fh] BYREF
  va_list va7; // [rsp+150h] [rbp+6Fh]
  __int64 v22; // [rsp+158h] [rbp+77h] BYREF
  va_list va8; // [rsp+158h] [rbp+77h]
  va_list va9; // [rsp+160h] [rbp+7Fh] BYREF

  va_start(va9, a4);
  va_start(va8, a4);
  va_start(va7, a4);
  va_start(va6, a4);
  va_start(va5, a4);
  va_start(va4, a4);
  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v12 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v14 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v16 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v18 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v20 = va_arg(va8, _QWORD);
  va_copy(va9, va8);
  v22 = va_arg(va9, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(
           1035,
           0x13u,
           (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids,
           &v5,
           4,
           va,
           4,
           va1,
           4,
           va2,
           4,
           va3,
           4,
           va4,
           4,
           va5,
           4,
           va6,
           4,
           va7,
           4,
           va8,
           4,
           va9,
           4,
           0);
}

```

## disassembly

```asm
0x1800162f4  mov     r11, rsp
0x1800162f7  push    rbp
0x1800162f8  lea     rbp, [r11-0Fh]
0x1800162fc  sub     rsp, 0E0h
0x180016303  mov     rax, cs:__security_cookie
0x18001630a  xor     rax, rsp
0x18001630d  mov     [rbp+7+var_8], rax
0x180016311  mov     qword ptr [r11-20h], 0
0x180016319  lea     rax, [rbp+7+arg_68]
0x18001631d  mov     edx, 13h
0x180016322  mov     [rbp+7+var_10], r9d
0x180016326  mov     r10d, 40Bh
0x18001632c  lea     r9, [rbp+7+var_10]
0x180016330  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180016337  lea     ecx, [rdx-0Fh]
0x18001633a  mov     [r11-28h], rcx
0x18001633e  mov     [r11-30h], rax
0x180016342  lea     rax, [rbp+7+arg_60]
0x180016346  mov     [r11-38h], rcx
0x18001634a  mov     [r11-40h], rax
0x18001634e  lea     rax, [rbp+7+arg_58]
0x180016352  mov     [r11-48h], rcx
0x180016356  mov     [r11-50h], rax
0x18001635a  lea     rax, [rbp+7+arg_50]
0x18001635e  mov     [r11-58h], rcx
0x180016362  mov     [r11-60h], rax
0x180016366  lea     rax, [rbp+7+arg_48]
0x18001636a  mov     [r11-68h], rcx
0x18001636e  mov     [r11-70h], rax
0x180016372  lea     rax, [rbp+7+arg_40]
0x180016376  mov     [r11-78h], rcx
0x18001637a  mov     [r11-80h], rax
0x18001637e  lea     rax, [rbp+7+arg_38]
0x180016382  mov     [rsp+60h], rcx
0x180016387  mov     [rsp+0E0h+var_88], rax
0x18001638c  lea     rax, [rbp+7+arg_30]
0x180016390  mov     [rsp+0E0h+var_90], rcx
0x180016395  mov     [rsp+0E0h+var_98], rax
0x18001639a  lea     rax, [rbp+7+arg_28]
0x18001639e  mov     [rsp+0E0h+var_A0], rcx
0x1800163a3  mov     [rsp+0E0h+var_A8], rax
0x1800163a8  lea     rax, [rbp+7+arg_20]
0x1800163ac  mov     [rsp+0E0h+var_B0], rcx
0x1800163b1  mov     [rsp+0E0h+var_B8], rax
0x1800163b6  mov     [rsp+0E0h+var_C0], rcx
0x1800163bb  mov     ecx, r10d
0x1800163be  call    FastWppTraceMessage
0x1800163c3  mov     rcx, [rbp+7+var_8]
0x1800163c7  xor     rcx, rsp; StackCookie
0x1800163ca  call    __security_check_cookie
0x1800163cf  add     rsp, 0E0h
0x1800163d6  pop     rbp
0x1800163d7  retn
```
