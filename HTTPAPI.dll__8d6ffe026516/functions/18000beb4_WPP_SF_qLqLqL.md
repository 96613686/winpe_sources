# WPP_SF_qLqLqL

- ea: `0x18000beb4`
- end: `0x18000bf59`
- name: `WPP_SF_qLqLqL`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e70`
- `0x180002b40`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_qLqLqL(_DWORD a1, _DWORD a2, _DWORD a3, __int64 a4, char a5, char a6, ...)
{
  __int64 v7; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v8; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  __int64 v10; // [rsp+C8h] [rbp+40h] BYREF
  va_list va1; // [rsp+C8h] [rbp+40h]
  va_list va2; // [rsp+D0h] [rbp+48h] BYREF

  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  v7 = a4;
  return FastWppTraceMessage(
           1050,
           0xAu,
           (ULONGLONG)WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids,
           &v7,
           8,
           &a5,
           4,
           &a6,
           8,
           va,
           4,
           va1,
           8,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x18000beb4  mov     rax, rsp
0x18000beb7  mov     [rax+20h], r9
0x18000bebb  sub     rsp, 88h
0x18000bec2  mov     qword ptr [rax-10h], 0
0x18000beca  lea     rax, [rax+48h]
0x18000bece  mov     r10d, 0Ah
0x18000bed4  lea     r9, [rsp+88h+arg_18]
0x18000bedc  mov     r11d, 41Ah
0x18000bee2  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x18000bee9  lea     edx, [r10-6]
0x18000beed  mov     [rax-60h], rdx
0x18000bef1  lea     ecx, [rdx+4]
0x18000bef4  mov     [rsp+88h+var_20], rax
0x18000bef9  lea     rax, [rsp+88h+arg_38]
0x18000bf01  mov     [rsp+88h+var_28], rcx
0x18000bf06  mov     [rsp+88h+var_30], rax
0x18000bf0b  lea     rax, [rsp+88h+arg_30]
0x18000bf13  mov     [rsp+88h+var_38], rdx
0x18000bf18  mov     [rsp+88h+var_40], rax
0x18000bf1d  lea     rax, [rsp+88h+arg_28]
0x18000bf25  mov     [rsp+88h+var_48], rcx
0x18000bf2a  mov     [rsp+88h+var_50], rax
0x18000bf2f  lea     rax, [rsp+88h+arg_20]
0x18000bf37  mov     [rsp+88h+var_58], rdx
0x18000bf3c  mov     edx, r10d
0x18000bf3f  mov     [rsp+88h+var_60], rax
0x18000bf44  mov     [rsp+88h+var_68], rcx
0x18000bf49  mov     ecx, r11d
0x18000bf4c  call    FastWppTraceMessage
0x18000bf51  add     rsp, 88h
0x18000bf58  retn
```
