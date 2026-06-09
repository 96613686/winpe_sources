# McTemplateU0s4pupqii_EventWriteTransfer

- ea: `0x18006bfcc`
- end: `0x18006c076`
- name: `McTemplateU0s4pupqii_EventWriteTransfer`
- size: `170`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e40`
- `0x180004810`
- `0x180005bd0`
- `0x180005e70`

## callees

- `0x18000ab90`
- `0x18006be70`

## pseudocode

```c
ULONG McTemplateU0s4pupqii_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+30h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-61h] BYREF
  __int64 v6; // [rsp+50h] [rbp-51h]
  __int64 v7; // [rsp+58h] [rbp-49h]
  va_list v8; // [rsp+60h] [rbp-41h]
  __int64 v9; // [rsp+68h] [rbp-39h]
  va_list v10; // [rsp+70h] [rbp-31h]
  __int64 v11; // [rsp+78h] [rbp-29h]
  va_list v12; // [rsp+80h] [rbp-21h]
  __int64 v13; // [rsp+88h] [rbp-19h]
  va_list v14; // [rsp+90h] [rbp-11h]
  __int64 v15; // [rsp+98h] [rbp-9h]
  va_list v16; // [rsp+A0h] [rbp-1h]
  __int64 v17; // [rsp+A8h] [rbp+7h]
  __int64 *v18; // [rsp+B0h] [rbp+Fh]
  __int64 v19; // [rsp+B8h] [rbp+17h]
  __int64 v20; // [rsp+F8h] [rbp+57h] BYREF
  va_list va; // [rsp+F8h] [rbp+57h]
  __int64 v22; // [rsp+100h] [rbp+5Fh] BYREF
  va_list va1; // [rsp+100h] [rbp+5Fh]
  __int64 v24; // [rsp+108h] [rbp+67h] BYREF
  va_list va2; // [rsp+108h] [rbp+67h]
  __int64 v26; // [rsp+110h] [rbp+6Fh] BYREF
  va_list va3; // [rsp+110h] [rbp+6Fh]
  va_list va4; // [rsp+118h] [rbp+77h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v20 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v22 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v24 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v26 = va_arg(va4, _QWORD);
  v6 = a3;
  v4 = 0;
  va_copy(v8, va);
  va_copy(v10, va1);
  va_copy(v12, va2);
  v7 = 4;
  va_copy(v14, va3);
  va_copy(v16, va4);
  v18 = &v4;
  v9 = 8;
  v11 = 1;
  v13 = 8;
  v15 = 4;
  v17 = 8;
  v19 = 8;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 8u, &v5);
}

```

## disassembly

```asm
0x18006bfcc  mov     [rsp-8+arg_18], r9
0x18006bfd1  push    rbp
0x18006bfd2  lea     rbp, [rsp-2Fh]
0x18006bfd7  sub     rsp, 0D0h
0x18006bfde  mov     rax, cs:__security_cookie
0x18006bfe5  xor     rax, rsp
0x18006bfe8  mov     [rbp+2Fh+var_10], rax
0x18006bfec  xor     r10d, r10d
0x18006bfef  mov     [rbp+2Fh+var_80], r8
0x18006bff3  lea     rax, [rbp+2Fh+arg_18]
0x18006bff7  mov     [rbp+2Fh+var_A0], r10
0x18006bffb  mov     [rbp+2Fh+var_70], rax
0x18006bfff  lea     rax, [rbp+2Fh+arg_20]
0x18006c003  mov     [rbp+2Fh+var_60], rax
0x18006c007  lea     rax, [rbp+2Fh+arg_28]
0x18006c00b  mov     [rbp+2Fh+var_50], rax
0x18006c00f  lea     r9d, [r10+8]
0x18006c013  lea     rax, [rbp+2Fh+arg_30]
0x18006c017  mov     [rbp+2Fh+var_78], 4
0x18006c01f  mov     [rbp+2Fh+var_40], rax
0x18006c023  lea     rax, [rbp+2Fh+arg_38]
0x18006c027  mov     [rbp+2Fh+var_30], rax
0x18006c02b  lea     rax, [rbp+2Fh+var_A0]
0x18006c02f  mov     [rbp+2Fh+var_20], rax
0x18006c033  lea     rax, [rbp+2Fh+var_90]
0x18006c037  mov     [rsp+0D0h+var_B0], rax
0x18006c03c  mov     [rbp+2Fh+var_68], r9
0x18006c040  mov     [rbp+2Fh+var_58], 1
0x18006c048  mov     [rbp+2Fh+var_48], r9
0x18006c04c  mov     [rbp+2Fh+var_38], 4
0x18006c054  mov     [rbp+2Fh+var_28], r9
0x18006c058  mov     [rbp+2Fh+var_18], r9
0x18006c05c  call    McGenEventWrite_EventWriteTransfer
0x18006c061  mov     rcx, [rbp+2Fh+var_10]
0x18006c065  xor     rcx, rsp; StackCookie
0x18006c068  call    __security_check_cookie
0x18006c06d  add     rsp, 0D0h
0x18006c074  pop     rbp
0x18006c075  retn
```
