# WPP_RECORDER_SF_dD

- ea: `0x14000492c`
- end: `0x1400049fd`
- name: `WPP_RECORDER_SF_dD`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004120`
- `0x1400052b8`

## callees

- `0x14000492c`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400049e0`
- `WppRecorder!WppAutoLogTrace` at `0x1400049e0`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dD(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 1, a5, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000492c  mov     r11, rsp
0x14000492f  mov     [r11+8], rbx
0x140004933  mov     [r11+10h], rsi
0x140004937  push    rdi
0x140004938  sub     rsp, 50h
0x14000493c  mov     rdi, rcx
0x14000493f  movzx   ebx, r9w
0x140004943  mov     rcx, cs:WPP_GLOBAL_Control
0x14000494a  mov     esi, 4
0x14000494f  mov     eax, [rcx+2Ch]
0x140004952  test    al, 1
0x140004954  jz      short loc_14000499A
0x140004956  cmp     byte ptr [rcx+29h], 2
0x14000495a  jb      short loc_14000499A
0x14000495c  mov     rax, cs:pfnWppTraceMessage
0x140004963  lea     rdx, [r11+38h]
0x140004967  mov     r8, [rsp+58h+arg_20]
0x14000496f  mov     r9d, ebx
0x140004972  mov     rcx, [rcx+18h]
0x140004976  mov     qword ptr [r11-18h], 0
0x14000497e  mov     [r11-20h], rsi
0x140004982  mov     [r11-28h], rdx
0x140004986  lea     rdx, [r11+30h]
0x14000498a  mov     [r11-30h], rsi
0x14000498e  mov     [r11-38h], rdx
0x140004992  lea     edx, [rsi+27h]
0x140004995  call    _guard_dispatch_icall
0x14000499a  mov     r9, [rsp+58h+arg_20]
0x1400049a2  lea     rax, [rsp+58h+arg_30]
0x1400049aa  mov     [rsp+58h+var_10], 0
0x1400049b3  mov     edx, 2
0x1400049b8  mov     [rsp+58h+var_18], rsi
0x1400049bd  mov     rcx, rdi
0x1400049c0  mov     [rsp+58h+var_20], rax
0x1400049c5  lea     rax, [rsp+58h+arg_28]
0x1400049cd  mov     [rsp+58h+var_28], rsi
0x1400049d2  mov     [rsp+58h+var_30], rax
0x1400049d7  lea     r8d, [rdx-1]
0x1400049db  mov     [rsp+58h+var_38], bx
0x1400049e0  call    cs:__imp_WppAutoLogTrace
0x1400049e7  nop     dword ptr [rax+rax+00h]
0x1400049ec  mov     rbx, [rsp+58h+arg_0]
0x1400049f1  mov     rsi, [rsp+58h+arg_8]
0x1400049f6  add     rsp, 50h
0x1400049fa  pop     rdi
0x1400049fb  retn
```
