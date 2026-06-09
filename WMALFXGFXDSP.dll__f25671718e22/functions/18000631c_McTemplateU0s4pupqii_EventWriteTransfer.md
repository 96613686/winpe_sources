# McTemplateU0s4pupqii_EventWriteTransfer

- ea: `0x18000631c`
- end: `0x1800063d6`
- name: `McTemplateU0s4pupqii_EventWriteTransfer`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005bd0`

## callees

- `0x180005b68`
- `0x180015190`

## pseudocode

```c
ULONG McTemplateU0s4pupqii_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  char v4; // [rsp+30h] [rbp-71h] BYREF
  __int64 v5; // [rsp+38h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-61h] BYREF
  __int64 v7; // [rsp+50h] [rbp-51h]
  __int64 v8; // [rsp+58h] [rbp-49h]
  va_list v9; // [rsp+60h] [rbp-41h]
  __int64 v10; // [rsp+68h] [rbp-39h]
  char *v11; // [rsp+70h] [rbp-31h]
  __int64 v12; // [rsp+78h] [rbp-29h]
  va_list v13; // [rsp+80h] [rbp-21h]
  __int64 v14; // [rsp+88h] [rbp-19h]
  va_list v15; // [rsp+90h] [rbp-11h]
  __int64 v16; // [rsp+98h] [rbp-9h]
  va_list v17; // [rsp+A0h] [rbp-1h]
  __int64 v18; // [rsp+A8h] [rbp+7h]
  __int64 *v19; // [rsp+B0h] [rbp+Fh]
  __int64 v20; // [rsp+B8h] [rbp+17h]
  __int64 v21; // [rsp+F8h] [rbp+57h] BYREF
  va_list va; // [rsp+F8h] [rbp+57h]
  __int64 v23; // [rsp+100h] [rbp+5Fh]
  __int64 v24; // [rsp+108h] [rbp+67h] BYREF
  va_list va1; // [rsp+108h] [rbp+67h]
  __int64 v26; // [rsp+110h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+110h] [rbp+6Fh]
  va_list va3; // [rsp+118h] [rbp+77h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  v23 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v24 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v26 = va_arg(va3, _QWORD);
  v4 = 25;
  va_copy(v9, va);
  v5 = 0;
  v11 = &v4;
  va_copy(v13, va1);
  va_copy(v15, va2);
  va_copy(v17, va3);
  v19 = &v5;
  v7 = a3;
  v8 = 4;
  v10 = 8;
  v12 = 1;
  v14 = 8;
  v16 = 4;
  v18 = 8;
  v20 = 8;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 0, &v6);
}

```

## disassembly

```asm
0x18000631c  mov     [rsp-8+arg_18], r9
0x180006321  push    rbp
0x180006322  lea     rbp, [rsp-2Fh]
0x180006327  sub     rsp, 0D0h
0x18000632e  mov     rax, cs:__security_cookie
0x180006335  xor     rax, rsp
0x180006338  mov     [rbp+2Fh+var_10], rax
0x18000633c  lea     rax, [rbp+2Fh+arg_18]
0x180006340  mov     [rbp+2Fh+var_A0], 19h
0x180006344  mov     [rbp+2Fh+var_70], rax
0x180006348  xor     r9d, r9d; int
0x18000634b  lea     rax, [rbp+2Fh+var_A0]
0x18000634f  mov     [rbp+2Fh+var_98], r9
0x180006353  mov     [rbp+2Fh+var_60], rax
0x180006357  lea     rax, [rbp+2Fh+arg_28]
0x18000635b  mov     [rbp+2Fh+var_50], rax
0x18000635f  lea     rax, [rbp+2Fh+arg_30]
0x180006363  mov     [rbp+2Fh+var_40], rax
0x180006367  lea     rax, [rbp+2Fh+arg_38]
0x18000636b  mov     [rbp+2Fh+var_30], rax
0x18000636f  lea     rax, [rbp+2Fh+var_98]
0x180006373  mov     [rbp+2Fh+var_20], rax
0x180006377  lea     rax, [rbp+2Fh+var_90]
0x18000637b  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x180006380  mov     [rbp+2Fh+var_80], r8
0x180006384  mov     [rbp+2Fh+var_78], 4
0x18000638c  mov     [rbp+2Fh+var_68], 8
0x180006394  mov     [rbp+2Fh+var_58], 1
0x18000639c  mov     [rbp+2Fh+var_48], 8
0x1800063a4  mov     [rbp+2Fh+var_38], 4
0x1800063ac  mov     [rbp+2Fh+var_28], 8
0x1800063b4  mov     [rbp+2Fh+var_18], 8
0x1800063bc  call    McGenEventWrite_EventWriteTransfer
0x1800063c1  mov     rcx, [rbp+2Fh+var_10]
0x1800063c5  xor     rcx, rsp; StackCookie
0x1800063c8  call    __security_check_cookie
0x1800063cd  add     rsp, 0D0h
0x1800063d4  pop     rbp
0x1800063d5  retn
```
