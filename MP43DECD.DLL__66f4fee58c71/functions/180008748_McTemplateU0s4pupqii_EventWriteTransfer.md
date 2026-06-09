# McTemplateU0s4pupqii_EventWriteTransfer

- ea: `0x180008748`
- end: `0x1800087f2`
- name: `McTemplateU0s4pupqii_EventWriteTransfer`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dd0`
- `0x180007050`

## callees

- `0x180001880`
- `0x1800086f0`

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
0x180008748  mov     [rsp-8+arg_18], r9
0x18000874d  push    rbp
0x18000874e  lea     rbp, [rsp-2Fh]
0x180008753  sub     rsp, 0D0h
0x18000875a  mov     rax, cs:__security_cookie
0x180008761  xor     rax, rsp
0x180008764  mov     [rbp+2Fh+var_10], rax
0x180008768  xor     r10d, r10d
0x18000876b  mov     [rbp+2Fh+var_80], r8
0x18000876f  lea     rax, [rbp+2Fh+arg_18]
0x180008773  mov     [rbp+2Fh+var_A0], r10
0x180008777  mov     [rbp+2Fh+var_70], rax
0x18000877b  lea     rax, [rbp+2Fh+arg_20]
0x18000877f  mov     [rbp+2Fh+var_60], rax
0x180008783  lea     rax, [rbp+2Fh+arg_28]
0x180008787  mov     [rbp+2Fh+var_50], rax
0x18000878b  lea     r9d, [r10+8]
0x18000878f  lea     rax, [rbp+2Fh+arg_30]
0x180008793  mov     [rbp+2Fh+var_78], 4
0x18000879b  mov     [rbp+2Fh+var_40], rax
0x18000879f  lea     rax, [rbp+2Fh+arg_38]
0x1800087a3  mov     [rbp+2Fh+var_30], rax
0x1800087a7  lea     rax, [rbp+2Fh+var_A0]
0x1800087ab  mov     [rbp+2Fh+var_20], rax
0x1800087af  lea     rax, [rbp+2Fh+var_90]
0x1800087b3  mov     [rsp+0D0h+var_B0], rax
0x1800087b8  mov     [rbp+2Fh+var_68], r9
0x1800087bc  mov     [rbp+2Fh+var_58], 1
0x1800087c4  mov     [rbp+2Fh+var_48], r9
0x1800087c8  mov     [rbp+2Fh+var_38], 4
0x1800087d0  mov     [rbp+2Fh+var_28], r9
0x1800087d4  mov     [rbp+2Fh+var_18], r9
0x1800087d8  call    McGenEventWrite_EventWriteTransfer
0x1800087dd  mov     rcx, [rbp+2Fh+var_10]
0x1800087e1  xor     rcx, rsp; StackCookie
0x1800087e4  call    __security_check_cookie
0x1800087e9  add     rsp, 0D0h
0x1800087f0  pop     rbp
0x1800087f1  retn
```
