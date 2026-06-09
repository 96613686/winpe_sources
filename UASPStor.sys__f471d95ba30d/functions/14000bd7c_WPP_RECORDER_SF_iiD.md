# WPP_RECORDER_SF_iiD

- ea: `0x14000bd7c`
- end: `0x14000be73`
- name: `WPP_RECORDER_SF_iiD`
- size: `247`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140009fe0`
- `0x14000a2b8`
- `0x14000be7c`
- `0x14000c368`

## callees

- `0x14000bd7c`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000be56`
- `WppRecorder!WppAutoLogTrace` at `0x14000be56`

## pseudocode

```c
__int64 WPP_RECORDER_SF_iiD(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 1, a5, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000bd7c  mov     r11, rsp
0x14000bd7f  mov     [r11+8], rbx
0x14000bd83  mov     [r11+10h], rsi
0x14000bd87  push    rdi
0x14000bd88  sub     rsp, 60h
0x14000bd8c  mov     rdi, rcx
0x14000bd8f  movzx   ebx, r9w
0x14000bd93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd9a  mov     esi, 8
0x14000bd9f  mov     eax, [rcx+2Ch]
0x14000bda2  test    al, 1
0x14000bda4  jz      short loc_14000BDFA
0x14000bda6  cmp     byte ptr [rcx+29h], 2
0x14000bdaa  jb      short loc_14000BDFA
0x14000bdac  mov     rax, cs:pfnWppTraceMessage
0x14000bdb3  lea     rdx, [r11+40h]
0x14000bdb7  mov     r8, [rsp+68h+arg_20]
0x14000bdbf  mov     r9d, ebx
0x14000bdc2  mov     rcx, [rcx+18h]
0x14000bdc6  mov     qword ptr [r11-18h], 0
0x14000bdce  mov     qword ptr [r11-20h], 4
0x14000bdd6  mov     [r11-28h], rdx
0x14000bdda  lea     rdx, [r11+38h]
0x14000bdde  mov     [r11-30h], rsi
0x14000bde2  mov     [r11-38h], rdx
0x14000bde6  lea     rdx, [r11+30h]
0x14000bdea  mov     [r11-40h], rsi
0x14000bdee  mov     [r11-48h], rdx
0x14000bdf2  lea     edx, [rsi+23h]
0x14000bdf5  call    _guard_dispatch_icall
0x14000bdfa  mov     r9, [rsp+68h+arg_20]
0x14000be02  lea     rax, [rsp+68h+arg_38]
0x14000be0a  mov     [rsp+68h+var_10], 0
0x14000be13  mov     edx, 2
0x14000be18  mov     [rsp+68h+var_18], 4
0x14000be21  mov     rcx, rdi
0x14000be24  mov     [rsp+68h+var_20], rax
0x14000be29  lea     rax, [rsp+68h+arg_30]
0x14000be31  mov     [rsp+68h+var_28], rsi
0x14000be36  mov     [rsp+68h+var_30], rax
0x14000be3b  lea     r8d, [rdx-1]
0x14000be3f  lea     rax, [rsp+68h+arg_28]
0x14000be47  mov     [rsp+68h+var_38], rsi
0x14000be4c  mov     [rsp+68h+var_40], rax
0x14000be51  mov     [rsp+68h+var_48], bx
0x14000be56  call    cs:__imp_WppAutoLogTrace
0x14000be5d  nop     dword ptr [rax+rax+00h]
0x14000be62  mov     rbx, [rsp+68h+arg_0]
0x14000be67  mov     rsi, [rsp+68h+arg_8]
0x14000be6c  add     rsp, 60h
0x14000be70  pop     rdi
0x14000be71  retn
```
