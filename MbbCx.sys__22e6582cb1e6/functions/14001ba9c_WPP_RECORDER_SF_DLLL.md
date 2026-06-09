# WPP_RECORDER_SF_DLLL

- ea: `0x14001ba9c`
- end: `0x14001bba7`
- name: `WPP_RECORDER_SF_DLLL`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a9ec`

## callees

- `0x14001ba9c`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14001bb88`
- `WppRecorder!WppAutoLogTrace` at `0x14001bb88`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DLLL(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-58h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v10; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v12; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
      12,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v7) = 12;
  return WppAutoLogTrace(
           a1,
           4,
           5,
           WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids,
           v7,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x14001ba9c  mov     r11, rsp
0x14001ba9f  mov     [r11+8], rbx
0x14001baa3  mov     [r11+10h], rsi
0x14001baa7  push    rdi
0x14001baa8  sub     rsp, 70h
0x14001baac  mov     rbx, rcx
0x14001baaf  mov     edi, 4
0x14001bab4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001babb  lea     esi, [rdi+8]
0x14001babe  mov     eax, [rcx+2Ch]
0x14001bac1  test    al, 10h
0x14001bac3  jz      short loc_14001BB20
0x14001bac5  cmp     [rcx+29h], dil
0x14001bac9  jb      short loc_14001BB20
0x14001bacb  mov     rax, cs:pfnWppTraceMessage
0x14001bad2  lea     rdx, [r11+48h]
0x14001bad6  mov     rcx, [rcx+18h]
0x14001bada  lea     r8, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x14001bae1  mov     qword ptr [r11-18h], 0
0x14001bae9  mov     r9d, esi
0x14001baec  mov     [r11-20h], rdi
0x14001baf0  mov     [r11-28h], rdx
0x14001baf4  lea     rdx, [r11+40h]
0x14001baf8  mov     [r11-30h], rdi
0x14001bafc  mov     [r11-38h], rdx
0x14001bb00  lea     rdx, [r11+38h]
0x14001bb04  mov     [r11-40h], rdi
0x14001bb08  mov     [r11-48h], rdx
0x14001bb0c  lea     rdx, [r11+30h]
0x14001bb10  mov     [r11-50h], rdi
0x14001bb14  mov     [r11-58h], rdx
0x14001bb18  lea     edx, [rdi+27h]
0x14001bb1b  call    _guard_dispatch_icall
0x14001bb20  mov     [rsp+78h+var_10], 0
0x14001bb29  lea     rax, [rsp+78h+arg_40]
0x14001bb31  mov     [rsp+78h+var_18], rdi
0x14001bb36  lea     r9, WPP_801d9c80458c3ec5e4bb5440382a0f20_Traceguids
0x14001bb3d  mov     [rsp+78h+var_20], rax
0x14001bb42  mov     r8d, 5
0x14001bb48  mov     [rsp+78h+var_28], rdi
0x14001bb4d  lea     rax, [rsp+78h+arg_38]
0x14001bb55  mov     [rsp+78h+var_30], rax
0x14001bb5a  mov     edx, edi
0x14001bb5c  mov     [rsp+78h+var_38], rdi
0x14001bb61  lea     rax, [rsp+78h+arg_30]
0x14001bb69  mov     [rsp+78h+var_40], rax
0x14001bb6e  mov     rcx, rbx
0x14001bb71  lea     rax, [rsp+78h+arg_28]
0x14001bb79  mov     [rsp+78h+var_48], rdi
0x14001bb7e  mov     [rsp+78h+var_50], rax
0x14001bb83  mov     [rsp+78h+var_58], si
0x14001bb88  call    cs:__imp_WppAutoLogTrace
0x14001bb8f  nop     dword ptr [rax+rax+00h]
0x14001bb94  lea     r11, [rsp+78h+var_8]
0x14001bb99  mov     rbx, [r11+10h]
0x14001bb9d  mov     rsi, [r11+18h]
0x14001bba1  mov     rsp, r11
0x14001bba4  pop     rdi
0x14001bba5  retn
```
