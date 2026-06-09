# WPP_RECORDER_SF_qd

- ea: `0x1400018ec`
- end: `0x1400019b8`
- name: `WPP_RECORDER_SF_qd`
- size: `204`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140019058`
- `0x14001a868`
- `0x14001ccc8`

## callees

- `0x1400018ec`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400019a0`
- `WppRecorder!WppAutoLogTrace` at `0x1400019a0`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 0, 3, a5, v8, (__int64 *)va, 8, va1);
}

```

## disassembly

```asm
0x1400018ec  mov     r11, rsp
0x1400018ef  mov     [r11+8], rbx
0x1400018f3  push    rdi
0x1400018f4  sub     rsp, 50h
0x1400018f8  mov     rdi, rcx
0x1400018fb  movzx   ebx, r9w
0x1400018ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140001906  mov     eax, [rcx+2Ch]
0x140001909  test    al, 4
0x14000190b  jz      short loc_140001955
0x14000190d  mov     rax, cs:pfnWppTraceMessage
0x140001914  lea     rdx, [r11+38h]
0x140001918  mov     r8, [rsp+58h+arg_20]
0x140001920  mov     r9d, ebx
0x140001923  mov     rcx, [rcx+18h]
0x140001927  mov     qword ptr [r11-18h], 0
0x14000192f  mov     qword ptr [r11-20h], 4
0x140001937  mov     [r11-28h], rdx
0x14000193b  lea     rdx, [r11+30h]
0x14000193f  mov     qword ptr [r11-30h], 8
0x140001947  mov     [r11-38h], rdx
0x14000194b  mov     edx, 2Bh ; '+'
0x140001950  call    _guard_dispatch_icall
0x140001955  mov     r9, [rsp+58h+arg_20]
0x14000195d  lea     rax, [rsp+58h+arg_30]
0x140001965  mov     [rsp+58h+var_10], 0
0x14000196e  xor     edx, edx
0x140001970  mov     [rsp+58h+var_18], 4
0x140001979  mov     rcx, rdi
0x14000197c  mov     [rsp+58h+var_20], rax
0x140001981  lea     rax, [rsp+58h+arg_28]
0x140001989  mov     [rsp+58h+var_28], 8
0x140001992  mov     [rsp+58h+var_30], rax
0x140001997  lea     r8d, [rdx+3]
0x14000199b  mov     [rsp+58h+var_38], bx
0x1400019a0  call    cs:__imp_WppAutoLogTrace
0x1400019a7  nop     dword ptr [rax+rax+00h]
0x1400019ac  mov     rbx, [rsp+58h+arg_0]
0x1400019b1  add     rsp, 50h
0x1400019b5  pop     rdi
0x1400019b6  retn
```
