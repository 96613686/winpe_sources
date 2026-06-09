# WPP_RECORDER_SF_Ddddd

- ea: `0x14003bacc`
- end: `0x14003bbfe`
- name: `WPP_RECORDER_SF_Ddddd`
- size: `306`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x14002b930`
- `0x140033f50`
- `0x140035b60`
- `0x140037c00`

## callees

- `0x14003bacc`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14003bbdc`
- `WppRecorder!WppAutoLogTrace` at `0x14003bbdc`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Ddddd(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-68h]
  __int64 v9; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v11; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  __int64 v13; // [rsp+C8h] [rbp+40h] BYREF
  va_list va2; // [rsp+C8h] [rbp+40h]
  __int64 v15; // [rsp+D0h] [rbp+48h] BYREF
  va_list va3; // [rsp+D0h] [rbp+48h]
  va_list va4; // [rsp+D8h] [rbp+50h] BYREF

  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v15 = va_arg(va4, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      va4,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(
           a1,
           2,
           3,
           WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
           v8,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2);
}

```

## disassembly

```asm
0x14003bacc  mov     r11, rsp
0x14003bacf  mov     [r11+8], rbx
0x14003bad3  mov     [r11+10h], rsi
0x14003bad7  push    rdi
0x14003bad8  sub     rsp, 80h
0x14003badf  mov     rdi, rcx
0x14003bae2  movzx   ebx, r9w
0x14003bae6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003baed  mov     esi, 4
0x14003baf2  mov     eax, [rcx+2Ch]
0x14003baf5  test    sil, al
0x14003baf8  jz      short loc_14003BB61
0x14003bafa  cmp     byte ptr [rcx+29h], 2
0x14003bafe  jb      short loc_14003BB61
0x14003bb00  mov     rax, cs:pfnWppTraceMessage
0x14003bb07  lea     rdx, [r11+50h]
0x14003bb0b  mov     rcx, [rcx+18h]
0x14003bb0f  lea     r8, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003bb16  mov     qword ptr [r11-18h], 0
0x14003bb1e  mov     r9d, ebx
0x14003bb21  mov     [r11-20h], rsi
0x14003bb25  mov     [r11-28h], rdx
0x14003bb29  lea     rdx, [r11+48h]
0x14003bb2d  mov     [r11-30h], rsi
0x14003bb31  mov     [r11-38h], rdx
0x14003bb35  lea     rdx, [r11+40h]
0x14003bb39  mov     [r11-40h], rsi
0x14003bb3d  mov     [r11-48h], rdx
0x14003bb41  lea     rdx, [r11+38h]
0x14003bb45  mov     [r11-50h], rsi
0x14003bb49  mov     [r11-58h], rdx
0x14003bb4d  lea     rdx, [r11+30h]
0x14003bb51  mov     [r11-60h], rsi
0x14003bb55  mov     [r11-68h], rdx
0x14003bb59  lea     edx, [rsi+27h]
0x14003bb5c  call    _guard_dispatch_icall
0x14003bb61  mov     [rsp+88h+var_10], 0
0x14003bb6a  lea     rax, [rsp+88h+arg_48]
0x14003bb72  mov     [rsp+88h+var_18], rsi
0x14003bb77  lea     r9, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003bb7e  mov     [rsp+88h+var_20], rax
0x14003bb83  mov     edx, 2
0x14003bb88  mov     [rsp+88h+var_28], rsi
0x14003bb8d  lea     rax, [rsp+88h+arg_40]
0x14003bb95  mov     [rsp+88h+var_30], rax
0x14003bb9a  mov     rcx, rdi
0x14003bb9d  mov     [rsp+88h+var_38], rsi
0x14003bba2  lea     rax, [rsp+88h+arg_38]
0x14003bbaa  mov     [rsp+88h+var_40], rax
0x14003bbaf  lea     r8d, [rdx+1]
0x14003bbb3  mov     [rsp+88h+var_48], rsi
0x14003bbb8  lea     rax, [rsp+88h+arg_30]
0x14003bbc0  mov     [rsp+88h+var_50], rax
0x14003bbc5  lea     rax, [rsp+88h+arg_28]
0x14003bbcd  mov     [rsp+88h+var_58], rsi
0x14003bbd2  mov     [rsp+88h+var_60], rax
0x14003bbd7  mov     [rsp+88h+var_68], bx
0x14003bbdc  call    cs:__imp_WppAutoLogTrace
0x14003bbe3  nop     dword ptr [rax+rax+00h]
0x14003bbe8  lea     r11, [rsp+88h+var_8]
0x14003bbf0  mov     rbx, [r11+10h]
0x14003bbf4  mov     rsi, [r11+18h]
0x14003bbf8  mov     rsp, r11
0x14003bbfb  pop     rdi
0x14003bbfc  retn
```
