# McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer

- ea: `0x1800122a0`
- end: `0x180012382`
- name: `McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer`
- size: `226`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, __int64, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f668`
- `0x1800128d0`

## callees

- `0x180001d40`
- `0x18000c224`

## pseudocode

```c
ULONG McTemplateU0qxqqbr3qqbr6q_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-91h] BYREF
  int *v5; // [rsp+40h] [rbp-81h]
  __int64 v6; // [rsp+48h] [rbp-79h]
  va_list v7; // [rsp+50h] [rbp-71h]
  __int64 v8; // [rsp+58h] [rbp-69h]
  va_list v9; // [rsp+60h] [rbp-61h]
  __int64 v10; // [rsp+68h] [rbp-59h]
  va_list v11; // [rsp+70h] [rbp-51h]
  __int64 v12; // [rsp+78h] [rbp-49h]
  __int64 v13; // [rsp+80h] [rbp-41h]
  int v14; // [rsp+88h] [rbp-39h]
  int v15; // [rsp+8Ch] [rbp-35h]
  va_list v16; // [rsp+90h] [rbp-31h]
  __int64 v17; // [rsp+98h] [rbp-29h]
  va_list v18; // [rsp+A0h] [rbp-21h]
  __int64 v19; // [rsp+A8h] [rbp-19h]
  __int64 v20; // [rsp+B0h] [rbp-11h]
  int v21; // [rsp+B8h] [rbp-9h]
  int v22; // [rsp+BCh] [rbp-5h]
  va_list v23; // [rsp+C0h] [rbp-1h]
  __int64 v24; // [rsp+C8h] [rbp+7h]
  int v25; // [rsp+100h] [rbp+3Fh] BYREF
  __int64 v26; // [rsp+108h] [rbp+47h] BYREF
  va_list va; // [rsp+108h] [rbp+47h]
  __int64 v28; // [rsp+110h] [rbp+4Fh] BYREF
  va_list va1; // [rsp+110h] [rbp+4Fh]
  __int64 v30; // [rsp+118h] [rbp+57h] BYREF
  va_list va2; // [rsp+118h] [rbp+57h]
  __int64 v32; // [rsp+120h] [rbp+5Fh]
  __int64 v33; // [rsp+128h] [rbp+67h] BYREF
  va_list va3; // [rsp+128h] [rbp+67h]
  __int64 v35; // [rsp+130h] [rbp+6Fh] BYREF
  va_list va4; // [rsp+130h] [rbp+6Fh]
  __int64 v37; // [rsp+138h] [rbp+77h]
  va_list va5; // [rsp+140h] [rbp+7Fh] BYREF

  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v26 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v28 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v30 = va_arg(va3, _QWORD);
  v32 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v33 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v35 = va_arg(va5, _QWORD);
  v37 = va_arg(va5, _QWORD);
  v25 = a3;
  v6 = 4;
  v8 = 8;
  v5 = &v25;
  va_copy(v7, va);
  va_copy(v9, va1);
  v10 = 4;
  va_copy(v11, va2);
  v13 = v32;
  v14 = v30;
  va_copy(v16, va3);
  va_copy(v18, va4);
  v20 = v37;
  v21 = v35;
  va_copy(v23, va5);
  v12 = 4;
  v15 = 0;
  v17 = 4;
  v19 = 4;
  v22 = 0;
  v24 = 4;
  return McGenEventWrite_EventWriteTransfer(0, a2, a3, 0xAu, &v4);
}

```

## disassembly

```asm
0x1800122a0  mov     [rsp-8+arg_18], r9
0x1800122a5  mov     [rsp-8+arg_10], r8d
0x1800122aa  push    rbp
0x1800122ab  lea     rbp, [rsp-1Fh]
0x1800122b0  sub     rsp, 0E0h
0x1800122b7  mov     rax, cs:__security_cookie
0x1800122be  xor     rax, rsp
0x1800122c1  mov     [rbp+1Fh+var_10], rax
0x1800122c5  xor     ecx, ecx
0x1800122c7  mov     [rbp+1Fh+var_98], 4
0x1800122cf  lea     rax, [rbp+1Fh+arg_10]
0x1800122d3  mov     [rbp+1Fh+var_88], 8
0x1800122db  mov     [rsp+0E0h+var_A0], rax
0x1800122e0  lea     rax, [rbp+1Fh+arg_18]
0x1800122e4  mov     [rbp+1Fh+var_90], rax
0x1800122e8  lea     rax, [rbp+1Fh+arg_20]
0x1800122ec  mov     [rbp+1Fh+var_80], rax
0x1800122f0  lea     r9d, [rcx+0Ah]
0x1800122f4  lea     rax, [rbp+1Fh+arg_28]
0x1800122f8  mov     [rbp+1Fh+var_78], 4
0x180012300  mov     [rbp+1Fh+var_70], rax
0x180012304  mov     rax, [rbp+1Fh+arg_30]
0x180012308  mov     [rbp+1Fh+var_60], rax
0x18001230c  mov     eax, dword ptr [rbp+1Fh+arg_28]
0x18001230f  mov     [rbp+1Fh+var_58], eax
0x180012312  lea     rax, [rbp+1Fh+arg_38]
0x180012316  mov     [rbp+1Fh+var_50], rax
0x18001231a  lea     rax, [rbp+1Fh+arg_40]
0x18001231e  mov     [rbp+1Fh+var_40], rax
0x180012322  mov     rax, [rbp+1Fh+arg_48]
0x180012326  mov     [rbp+1Fh+var_30], rax
0x18001232a  mov     eax, dword ptr [rbp+1Fh+arg_40]
0x18001232d  mov     [rbp+1Fh+var_28], eax
0x180012330  lea     rax, [rbp+1Fh+arg_50]
0x180012334  mov     [rbp+1Fh+var_20], rax
0x180012338  lea     rax, [rsp+0E0h+var_B0]
0x18001233d  mov     [rsp+0E0h+var_C0], rax
0x180012342  mov     [rbp+1Fh+var_68], 4
0x18001234a  mov     [rbp+1Fh+var_54], ecx
0x18001234d  mov     [rbp+1Fh+var_48], 4
0x180012355  mov     [rbp+1Fh+var_38], 4
0x18001235d  mov     [rbp+1Fh+var_24], ecx
0x180012360  mov     [rbp+1Fh+var_18], 4
0x180012368  call    McGenEventWrite_EventWriteTransfer
0x18001236d  mov     rcx, [rbp+1Fh+var_10]
0x180012371  xor     rcx, rsp; StackCookie
0x180012374  call    __security_check_cookie
0x180012379  add     rsp, 0E0h
0x180012380  pop     rbp
0x180012381  retn
```
