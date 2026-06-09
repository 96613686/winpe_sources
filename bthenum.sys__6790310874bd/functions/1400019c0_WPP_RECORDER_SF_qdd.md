# WPP_RECORDER_SF_qdd

- ea: `0x1400019c0`
- end: `0x140001aaf`
- name: `WPP_RECORDER_SF_qdd`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a868`
- `0x14001ccc8`

## callees

- `0x1400019c0`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001a92`
- `WppRecorder!WppAutoLogTrace` at `0x140001a92`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qdd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v11; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 0, 3, a5, v8, (__int64 *)va, 8, (__int64 *)va1);
}

```

## disassembly

```asm
0x1400019c0  mov     r11, rsp
0x1400019c3  mov     [r11+8], rbx
0x1400019c7  mov     [r11+10h], rsi
0x1400019cb  push    rdi
0x1400019cc  sub     rsp, 60h
0x1400019d0  mov     rdi, rcx
0x1400019d3  movzx   ebx, r9w
0x1400019d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019de  mov     esi, 4
0x1400019e3  mov     eax, [rcx+2Ch]
0x1400019e6  test    sil, al
0x1400019e9  jz      short loc_140001A39
0x1400019eb  mov     rax, cs:pfnWppTraceMessage
0x1400019f2  lea     rdx, [r11+40h]
0x1400019f6  mov     r8, [rsp+68h+arg_20]
0x1400019fe  mov     r9d, ebx
0x140001a01  mov     rcx, [rcx+18h]
0x140001a05  mov     qword ptr [r11-18h], 0
0x140001a0d  mov     [r11-20h], rsi
0x140001a11  mov     [r11-28h], rdx
0x140001a15  lea     rdx, [r11+38h]
0x140001a19  mov     [r11-30h], rsi
0x140001a1d  mov     [r11-38h], rdx
0x140001a21  lea     rdx, [r11+30h]
0x140001a25  mov     qword ptr [r11-40h], 8
0x140001a2d  mov     [r11-48h], rdx
0x140001a31  lea     edx, [rsi+27h]
0x140001a34  call    _guard_dispatch_icall
0x140001a39  mov     r9, [rsp+68h+arg_20]
0x140001a41  lea     rax, [rsp+68h+arg_38]
0x140001a49  mov     [rsp+68h+var_10], 0
0x140001a52  xor     edx, edx
0x140001a54  mov     [rsp+68h+var_18], rsi
0x140001a59  mov     rcx, rdi
0x140001a5c  mov     [rsp+68h+var_20], rax
0x140001a61  lea     rax, [rsp+68h+arg_30]
0x140001a69  mov     [rsp+68h+var_28], rsi
0x140001a6e  mov     [rsp+68h+var_30], rax
0x140001a73  lea     r8d, [rdx+3]
0x140001a77  lea     rax, [rsp+68h+arg_28]
0x140001a7f  mov     [rsp+68h+var_38], 8
0x140001a88  mov     [rsp+68h+var_40], rax
0x140001a8d  mov     [rsp+68h+var_48], bx
0x140001a92  call    cs:__imp_WppAutoLogTrace
0x140001a99  nop     dword ptr [rax+rax+00h]
0x140001a9e  mov     rbx, [rsp+68h+arg_0]
0x140001aa3  mov     rsi, [rsp+68h+arg_8]
0x140001aa8  add     rsp, 60h
0x140001aac  pop     rdi
0x140001aad  retn
```
