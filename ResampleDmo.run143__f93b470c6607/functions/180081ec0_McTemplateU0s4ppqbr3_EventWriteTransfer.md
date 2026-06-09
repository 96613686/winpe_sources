# McTemplateU0s4ppqbr3_EventWriteTransfer

- ea: `0x180081ec0`
- end: `0x180081f65`
- name: `McTemplateU0s4ppqbr3_EventWriteTransfer`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180081d60`

## callees

- `0x18000ab90`
- `0x18006be70`

## pseudocode

```c
ULONG McTemplateU0s4ppqbr3_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+30h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-31h] BYREF
  __int64 v6; // [rsp+50h] [rbp-21h]
  __int64 v7; // [rsp+58h] [rbp-19h]
  va_list v8; // [rsp+60h] [rbp-11h]
  __int64 v9; // [rsp+68h] [rbp-9h]
  __int64 *v10; // [rsp+70h] [rbp-1h]
  __int64 v11; // [rsp+78h] [rbp+7h]
  va_list v12; // [rsp+80h] [rbp+Fh]
  __int64 v13; // [rsp+88h] [rbp+17h]
  __int64 v14; // [rsp+90h] [rbp+1Fh]
  int v15; // [rsp+98h] [rbp+27h]
  int v16; // [rsp+9Ch] [rbp+2Bh]
  __int64 v17; // [rsp+D8h] [rbp+67h] BYREF
  va_list va; // [rsp+D8h] [rbp+67h]
  __int64 v19; // [rsp+E0h] [rbp+6Fh]
  __int64 v20; // [rsp+E8h] [rbp+77h] BYREF
  va_list va1; // [rsp+E8h] [rbp+77h]
  __int64 v22; // [rsp+F0h] [rbp+7Fh]
  va_list va2; // [rsp+F8h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v17 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  v22 = va_arg(va2, _QWORD);
  v6 = a3;
  v4 = 0;
  va_copy(v8, va);
  v16 = 0;
  v10 = &v4;
  v7 = 4;
  va_copy(v12, va1);
  v14 = v22;
  v15 = v20;
  v9 = 8;
  v11 = 8;
  v13 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)Media_Type_Change, a3, 6u, &v5);
}

```

## disassembly

```asm
0x180081ec0  mov     [rsp-8+arg_18], r9
0x180081ec5  push    rbp
0x180081ec6  lea     rbp, [rsp-3Fh]
0x180081ecb  sub     rsp, 0B0h
0x180081ed2  mov     rax, cs:__security_cookie
0x180081ed9  xor     rax, rsp
0x180081edc  mov     [rbp+3Fh+var_10], rax
0x180081ee0  xor     r9d, r9d
0x180081ee3  mov     [rbp+3Fh+var_60], r8
0x180081ee7  lea     rax, [rbp+3Fh+arg_18]
0x180081eeb  mov     [rbp+3Fh+var_80], r9
0x180081eef  mov     [rbp+3Fh+var_50], rax
0x180081ef3  lea     rdx, Media_Type_Change
0x180081efa  lea     rax, [rbp+3Fh+var_80]
0x180081efe  mov     [rbp+3Fh+var_14], r9d
0x180081f02  mov     [rbp+3Fh+var_40], rax
0x180081f06  mov     r9d, 6
0x180081f0c  lea     rax, [rbp+3Fh+arg_28]
0x180081f10  mov     [rbp+3Fh+var_58], 4
0x180081f18  mov     [rbp+3Fh+var_30], rax
0x180081f1c  mov     rax, [rbp+3Fh+arg_30]
0x180081f20  mov     [rbp+3Fh+var_20], rax
0x180081f24  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x180081f27  mov     [rbp+3Fh+var_18], eax
0x180081f2a  lea     rax, [rbp+3Fh+var_70]
0x180081f2e  mov     [rsp+0B0h+var_90], rax
0x180081f33  mov     [rbp+3Fh+var_48], 8
0x180081f3b  mov     [rbp+3Fh+var_38], 8
0x180081f43  mov     [rbp+3Fh+var_28], 4
0x180081f4b  call    McGenEventWrite_EventWriteTransfer
0x180081f50  mov     rcx, [rbp+3Fh+var_10]
0x180081f54  xor     rcx, rsp; StackCookie
0x180081f57  call    __security_check_cookie
0x180081f5c  add     rsp, 0B0h
0x180081f63  pop     rbp
0x180081f64  retn
```
