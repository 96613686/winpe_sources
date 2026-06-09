# WPP_RECORDER_SF_DdLL

- ea: `0x14003b880`
- end: `0x14003b98d`
- name: `WPP_RECORDER_SF_DdLL`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140026698`
- `0x140026e44`

## callees

- `0x14003b880`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14003b96e`
- `WppRecorder!WppAutoLogTrace` at `0x14003b96e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DdLL(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v11; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v13; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
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
      va3,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(
           a1,
           4,
           3,
           WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
           v8,
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
0x14003b880  mov     r11, rsp
0x14003b883  mov     [r11+8], rbx
0x14003b887  mov     [r11+10h], rsi
0x14003b88b  push    rdi
0x14003b88c  sub     rsp, 70h
0x14003b890  mov     rdi, rcx
0x14003b893  movzx   ebx, r9w
0x14003b897  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b89e  mov     esi, 4
0x14003b8a3  mov     eax, [rcx+2Ch]
0x14003b8a6  test    sil, al
0x14003b8a9  jz      short loc_14003B906
0x14003b8ab  cmp     [rcx+29h], sil
0x14003b8af  jb      short loc_14003B906
0x14003b8b1  mov     rax, cs:pfnWppTraceMessage
0x14003b8b8  lea     rdx, [r11+48h]
0x14003b8bc  mov     rcx, [rcx+18h]
0x14003b8c0  lea     r8, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003b8c7  mov     qword ptr [r11-18h], 0
0x14003b8cf  mov     r9d, ebx
0x14003b8d2  mov     [r11-20h], rsi
0x14003b8d6  mov     [r11-28h], rdx
0x14003b8da  lea     rdx, [r11+40h]
0x14003b8de  mov     [r11-30h], rsi
0x14003b8e2  mov     [r11-38h], rdx
0x14003b8e6  lea     rdx, [r11+38h]
0x14003b8ea  mov     [r11-40h], rsi
0x14003b8ee  mov     [r11-48h], rdx
0x14003b8f2  lea     rdx, [r11+30h]
0x14003b8f6  mov     [r11-50h], rsi
0x14003b8fa  mov     [r11-58h], rdx
0x14003b8fe  lea     edx, [rsi+27h]
0x14003b901  call    _guard_dispatch_icall
0x14003b906  mov     [rsp+78h+var_10], 0
0x14003b90f  lea     rax, [rsp+78h+arg_40]
0x14003b917  mov     [rsp+78h+var_18], rsi
0x14003b91c  lea     r9, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x14003b923  mov     [rsp+78h+var_20], rax
0x14003b928  mov     r8d, 3
0x14003b92e  mov     [rsp+78h+var_28], rsi
0x14003b933  lea     rax, [rsp+78h+arg_38]
0x14003b93b  mov     [rsp+78h+var_30], rax
0x14003b940  mov     edx, esi
0x14003b942  mov     [rsp+78h+var_38], rsi
0x14003b947  lea     rax, [rsp+78h+arg_30]
0x14003b94f  mov     [rsp+78h+var_40], rax
0x14003b954  mov     rcx, rdi
0x14003b957  lea     rax, [rsp+78h+arg_28]
0x14003b95f  mov     [rsp+78h+var_48], rsi
0x14003b964  mov     [rsp+78h+var_50], rax
0x14003b969  mov     [rsp+78h+var_58], bx
0x14003b96e  call    cs:__imp_WppAutoLogTrace
0x14003b975  nop     dword ptr [rax+rax+00h]
0x14003b97a  lea     r11, [rsp+78h+var_8]
0x14003b97f  mov     rbx, [r11+10h]
0x14003b983  mov     rsi, [r11+18h]
0x14003b987  mov     rsp, r11
0x14003b98a  pop     rdi
0x14003b98b  retn
```
