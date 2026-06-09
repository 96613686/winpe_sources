# McTemplateU0s4pii_EventWriteTransfer

- ea: `0x18006bec8`
- end: `0x18006bf4d`
- name: `McTemplateU0s4pii_EventWriteTransfer`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a00`

## callees

- `0x18000ab90`
- `0x18006be70`

## pseudocode

```c
ULONG McTemplateU0s4pii_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-19h] BYREF
  __int64 v5; // [rsp+40h] [rbp-9h]
  __int64 v6; // [rsp+48h] [rbp-1h]
  va_list v7; // [rsp+50h] [rbp+7h]
  __int64 v8; // [rsp+58h] [rbp+Fh]
  va_list v9; // [rsp+60h] [rbp+17h]
  __int64 v10; // [rsp+68h] [rbp+1Fh]
  va_list v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  __int64 v13; // [rsp+B8h] [rbp+6Fh] BYREF
  va_list va; // [rsp+B8h] [rbp+6Fh]
  __int64 v15; // [rsp+C0h] [rbp+77h] BYREF
  va_list va1; // [rsp+C0h] [rbp+77h]
  va_list va2; // [rsp+C8h] [rbp+7Fh] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v5 = a3;
  va_copy(v7, va);
  v6 = 4;
  va_copy(v9, va1);
  va_copy(v11, va2);
  v8 = 8;
  v10 = 8;
  v12 = 8;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 5u, &v4);
}

```

## disassembly

```asm
0x18006bec8  mov     [rsp-8+arg_18], r9
0x18006becd  push    rbp
0x18006bece  lea     rbp, [rsp-47h]
0x18006bed3  sub     rsp, 90h
0x18006beda  mov     rax, cs:__security_cookie
0x18006bee1  xor     rax, rsp
0x18006bee4  mov     [rbp+47h+var_10], rax
0x18006bee8  lea     rax, [rbp+47h+arg_18]
0x18006beec  mov     [rbp+47h+var_50], r8
0x18006bef0  mov     [rbp+47h+var_40], rax
0x18006bef4  mov     r9d, 5
0x18006befa  lea     rax, [rbp+47h+arg_20]
0x18006befe  mov     [rbp+47h+var_48], 4
0x18006bf06  mov     [rbp+47h+var_30], rax
0x18006bf0a  lea     rax, [rbp+47h+arg_28]
0x18006bf0e  mov     [rbp+47h+var_20], rax
0x18006bf12  lea     rax, [rbp+47h+var_60]
0x18006bf16  mov     [rsp+90h+var_70], rax
0x18006bf1b  mov     [rbp+47h+var_38], 8
0x18006bf23  mov     [rbp+47h+var_28], 8
0x18006bf2b  mov     [rbp+47h+var_18], 8
0x18006bf33  call    McGenEventWrite_EventWriteTransfer
0x18006bf38  mov     rcx, [rbp+47h+var_10]
0x18006bf3c  xor     rcx, rsp; StackCookie
0x18006bf3f  call    __security_check_cookie
0x18006bf44  add     rsp, 90h
0x18006bf4b  pop     rbp
0x18006bf4c  retn
```
