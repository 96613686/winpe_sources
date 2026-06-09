# WPP_RECORDER_SF_DLLd

- ea: `0x1400183f8`
- end: `0x140018511`
- name: `WPP_RECORDER_SF_DLLd`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140010b00`
- `0x140011330`

## callees

- `0x1400183f8`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400184ef`
- `WppRecorder!WppAutoLogTrace` at `0x1400184ef`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DLLd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-68h]
  _DWORD v9[4]; // [rsp+70h] [rbp-18h] BYREF
  __int64 v10; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v12; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v12 = va_arg(va2, _QWORD);
  v9[0] = -1073741823;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _DWORD *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      v9,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(
           a1,
           2,
           3,
           WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
           v8,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           va2,
           4,
           v9,
           4,
           0);
}

```

## disassembly

```asm
0x1400183f8  mov     r11, rsp
0x1400183fb  mov     [r11+8], rbx
0x1400183ff  mov     [r11+10h], rsi
0x140018403  push    rdi
0x140018404  sub     rsp, 80h
0x14001840b  mov     rdi, rcx
0x14001840e  mov     [rsp+88h+var_18], 0C0000001h
0x140018416  mov     rcx, cs:WPP_GLOBAL_Control
0x14001841d  mov     esi, 4
0x140018422  movzx   ebx, r9w
0x140018426  mov     eax, [rcx+2Ch]
0x140018429  test    sil, al
0x14001842c  jz      short loc_140018489
0x14001842e  cmp     byte ptr [rcx+29h], 2
0x140018432  jb      short loc_140018489
0x140018434  mov     rax, cs:pfnWppTraceMessage
0x14001843b  lea     rdx, [r11-18h]
0x14001843f  mov     rcx, [rcx+18h]
0x140018443  lea     r8, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x14001844a  mov     qword ptr [r11-28h], 0
0x140018452  mov     r9d, ebx
0x140018455  mov     [r11-30h], rsi
0x140018459  mov     [r11-38h], rdx
0x14001845d  lea     rdx, [r11+40h]
0x140018461  mov     [r11-40h], rsi
0x140018465  mov     [r11-48h], rdx
0x140018469  lea     rdx, [r11+38h]
0x14001846d  mov     [r11-50h], rsi
0x140018471  mov     [r11-58h], rdx
0x140018475  lea     rdx, [r11+30h]
0x140018479  mov     [r11-60h], rsi
0x14001847d  mov     [r11-68h], rdx
0x140018481  lea     edx, [rsi+27h]
0x140018484  call    _guard_dispatch_icall
0x140018489  mov     [rsp+88h+var_20], 0
0x140018492  lea     rax, [rsp+88h+var_18]
0x140018497  mov     [rsp+88h+var_28], rsi
0x14001849c  lea     r9, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400184a3  mov     [rsp+88h+var_30], rax
0x1400184a8  mov     edx, 2
0x1400184ad  mov     [rsp+88h+var_38], rsi
0x1400184b2  lea     rax, [rsp+88h+arg_38]
0x1400184ba  mov     [rsp+88h+var_40], rax
0x1400184bf  mov     rcx, rdi
0x1400184c2  mov     [rsp+88h+var_48], rsi
0x1400184c7  lea     rax, [rsp+88h+arg_30]
0x1400184cf  mov     [rsp+88h+var_50], rax
0x1400184d4  lea     r8d, [rdx+1]
0x1400184d8  lea     rax, [rsp+88h+arg_28]
0x1400184e0  mov     [rsp+88h+var_58], rsi
0x1400184e5  mov     [rsp+88h+var_60], rax
0x1400184ea  mov     [rsp+88h+var_68], bx
0x1400184ef  call    cs:__imp_WppAutoLogTrace
0x1400184f6  nop     dword ptr [rax+rax+00h]
0x1400184fb  lea     r11, [rsp+88h+var_8]
0x140018503  mov     rbx, [r11+10h]
0x140018507  mov     rsi, [r11+18h]
0x14001850b  mov     rsp, r11
0x14001850e  pop     rdi
0x14001850f  retn
```
