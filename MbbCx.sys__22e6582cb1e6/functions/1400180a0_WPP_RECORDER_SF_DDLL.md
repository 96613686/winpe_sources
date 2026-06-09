# WPP_RECORDER_SF_DDLL

- ea: `0x1400180a0`
- end: `0x1400181ac`
- name: `WPP_RECORDER_SF_DDLL`
- size: `268`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140012c90`

## callees

- `0x1400180a0`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14001818d`
- `WppRecorder!WppAutoLogTrace` at `0x14001818d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DDLL(__int64 a1, _DWORD a2, _DWORD a3, _DWORD a4, __int64 a5, ...)
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
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
      41,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v7) = 41;
  return WppAutoLogTrace(
           a1,
           3,
           3,
           WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
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
0x1400180a0  mov     r11, rsp
0x1400180a3  mov     [r11+8], rbx
0x1400180a7  mov     [r11+10h], rbp
0x1400180ab  push    rdi
0x1400180ac  sub     rsp, 70h
0x1400180b0  mov     rbx, rcx
0x1400180b3  mov     ebp, 29h ; ')'
0x1400180b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180bf  lea     edi, [rbp-25h]
0x1400180c2  mov     eax, [rcx+2Ch]
0x1400180c5  test    dil, al
0x1400180c8  jz      short loc_140018125
0x1400180ca  cmp     byte ptr [rcx+29h], 3
0x1400180ce  jb      short loc_140018125
0x1400180d0  mov     rax, cs:pfnWppTraceMessage
0x1400180d7  lea     rdx, [r11+48h]
0x1400180db  mov     rcx, [rcx+18h]
0x1400180df  lea     r8, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x1400180e6  mov     qword ptr [r11-18h], 0
0x1400180ee  mov     r9d, ebp
0x1400180f1  mov     [r11-20h], rdi
0x1400180f5  mov     [r11-28h], rdx
0x1400180f9  lea     rdx, [r11+40h]
0x1400180fd  mov     [r11-30h], rdi
0x140018101  mov     [r11-38h], rdx
0x140018105  lea     rdx, [r11+38h]
0x140018109  mov     [r11-40h], rdi
0x14001810d  mov     [r11-48h], rdx
0x140018111  lea     rdx, [r11+30h]
0x140018115  mov     [r11-50h], rdi
0x140018119  mov     [r11-58h], rdx
0x14001811d  lea     edx, [rbp+2]
0x140018120  call    _guard_dispatch_icall
0x140018125  mov     [rsp+78h+var_10], 0
0x14001812e  lea     rax, [rsp+78h+arg_40]
0x140018136  mov     [rsp+78h+var_18], rdi
0x14001813b  lea     r9, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140018142  mov     [rsp+78h+var_20], rax
0x140018147  mov     edx, 3
0x14001814c  mov     [rsp+78h+var_28], rdi
0x140018151  lea     rax, [rsp+78h+arg_38]
0x140018159  mov     [rsp+78h+var_30], rax
0x14001815e  mov     r8d, edx
0x140018161  mov     [rsp+78h+var_38], rdi
0x140018166  lea     rax, [rsp+78h+arg_30]
0x14001816e  mov     [rsp+78h+var_40], rax
0x140018173  mov     rcx, rbx
0x140018176  lea     rax, [rsp+78h+arg_28]
0x14001817e  mov     [rsp+78h+var_48], rdi
0x140018183  mov     [rsp+78h+var_50], rax
0x140018188  mov     [rsp+78h+var_58], bp
0x14001818d  call    cs:__imp_WppAutoLogTrace
0x140018194  nop     dword ptr [rax+rax+00h]
0x140018199  lea     r11, [rsp+78h+var_8]
0x14001819e  mov     rbx, [r11+10h]
0x1400181a2  mov     rbp, [r11+18h]
0x1400181a6  mov     rsp, r11
0x1400181a9  pop     rdi
0x1400181aa  retn
```
