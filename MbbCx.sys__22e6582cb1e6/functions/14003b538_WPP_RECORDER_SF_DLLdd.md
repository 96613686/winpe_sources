# WPP_RECORDER_SF_DLLdd

- ea: `0x14003b538`
- end: `0x14003b669`
- name: `WPP_RECORDER_SF_DLLdd`
- size: `305`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140026698`
- `0x140026e44`

## callees

- `0x14003b538`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14003b647`
- `WppRecorder!WppAutoLogTrace` at `0x14003b647`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DLLdd(__int64 a1, _DWORD a2, _DWORD a3, _DWORD a4, __int64 a5, ...)
{
  int v7; // [rsp+20h] [rbp-68h]
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  __int64 v12; // [rsp+C8h] [rbp+40h] BYREF
  va_list va2; // [rsp+C8h] [rbp+40h]
  __int64 v14; // [rsp+D0h] [rbp+48h] BYREF
  va_list va3; // [rsp+D0h] [rbp+48h]
  va_list va4; // [rsp+D8h] [rbp+50h] BYREF

  va_start(va4, a5);
  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v12 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v14 = va_arg(va4, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
      114,
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
  LOWORD(v7) = 114;
  return WppAutoLogTrace(
           a1,
           2,
           3,
           WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
           v7,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           (__int64 *)va3,
           4,
           va4);
}

```

## disassembly

```asm
0x14003b538  mov     r11, rsp
0x14003b53b  mov     [r11+8], rbx
0x14003b53f  mov     [r11+10h], rsi
0x14003b543  push    rdi
0x14003b544  sub     rsp, 80h
0x14003b54b  mov     rbx, rcx
0x14003b54e  mov     esi, 72h ; 'r'
0x14003b553  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b55a  lea     edi, [rsi-6Eh]
0x14003b55d  mov     eax, [rcx+2Ch]
0x14003b560  test    dil, al
0x14003b563  jz      short loc_14003B5CC
0x14003b565  cmp     byte ptr [rcx+29h], 2
0x14003b569  jb      short loc_14003B5CC
0x14003b56b  mov     rax, cs:pfnWppTraceMessage
0x14003b572  lea     rdx, [r11+50h]
0x14003b576  mov     rcx, [rcx+18h]
0x14003b57a  lea     r8, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003b581  mov     qword ptr [r11-18h], 0
0x14003b589  mov     r9d, esi
0x14003b58c  mov     [r11-20h], rdi
0x14003b590  mov     [r11-28h], rdx
0x14003b594  lea     rdx, [r11+48h]
0x14003b598  mov     [r11-30h], rdi
0x14003b59c  mov     [r11-38h], rdx
0x14003b5a0  lea     rdx, [r11+40h]
0x14003b5a4  mov     [r11-40h], rdi
0x14003b5a8  mov     [r11-48h], rdx
0x14003b5ac  lea     rdx, [r11+38h]
0x14003b5b0  mov     [r11-50h], rdi
0x14003b5b4  mov     [r11-58h], rdx
0x14003b5b8  lea     rdx, [r11+30h]
0x14003b5bc  mov     [r11-60h], rdi
0x14003b5c0  mov     [r11-68h], rdx
0x14003b5c4  lea     edx, [rsi-47h]
0x14003b5c7  call    _guard_dispatch_icall
0x14003b5cc  mov     [rsp+88h+var_10], 0
0x14003b5d5  lea     rax, [rsp+88h+arg_48]
0x14003b5dd  mov     [rsp+88h+var_18], rdi
0x14003b5e2  lea     r9, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003b5e9  mov     [rsp+88h+var_20], rax
0x14003b5ee  mov     edx, 2
0x14003b5f3  mov     [rsp+88h+var_28], rdi
0x14003b5f8  lea     rax, [rsp+88h+arg_40]
0x14003b600  mov     [rsp+88h+var_30], rax
0x14003b605  mov     rcx, rbx
0x14003b608  mov     [rsp+88h+var_38], rdi
0x14003b60d  lea     rax, [rsp+88h+arg_38]
0x14003b615  mov     [rsp+88h+var_40], rax
0x14003b61a  lea     r8d, [rdx+1]
0x14003b61e  mov     [rsp+88h+var_48], rdi
0x14003b623  lea     rax, [rsp+88h+arg_30]
0x14003b62b  mov     [rsp+88h+var_50], rax
0x14003b630  lea     rax, [rsp+88h+arg_28]
0x14003b638  mov     [rsp+88h+var_58], rdi
0x14003b63d  mov     [rsp+88h+var_60], rax
0x14003b642  mov     [rsp+88h+var_68], si
0x14003b647  call    cs:__imp_WppAutoLogTrace
0x14003b64e  nop     dword ptr [rax+rax+00h]
0x14003b653  lea     r11, [rsp+88h+var_8]
0x14003b65b  mov     rbx, [r11+10h]
0x14003b65f  mov     rsi, [r11+18h]
0x14003b663  mov     rsp, r11
0x14003b666  pop     rdi
0x14003b667  retn
```
