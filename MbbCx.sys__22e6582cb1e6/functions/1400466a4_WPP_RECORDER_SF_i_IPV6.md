# WPP_RECORDER_SF_i_IPV6_

- ea: `0x1400466a4`
- end: `0x14004677c`
- name: `WPP_RECORDER_SF_i_IPV6_`
- size: `216`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140042bf4`
- `0x140042e30`
- `0x1400445e8`
- `0x1400448c8`
- `0x1400450ac`
- `0x140045448`

## callees

- `0x1400466a4`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14004675f`
- `WppRecorder!WppAutoLogTrace` at `0x14004675f`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_i_IPV6_(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6,
        __int64 a7)
{
  __int64 v7; // rdi
  int v11; // [rsp+20h] [rbp-38h]

  v7 = a7;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, char *, __int64, __int64, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_f53708f2277a3aabca584f524242a299_Traceguids,
      a4,
      &a6,
      8,
      a7,
      16,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 4, 2, WPP_f53708f2277a3aabca584f524242a299_Traceguids, v11, &a6, 8, v7, 16, 0);
}

```

## disassembly

```asm
0x1400466a4  mov     r11, rsp
0x1400466a7  mov     [r11+8], rbx
0x1400466ab  mov     [r11+10h], rsi
0x1400466af  push    rdi
0x1400466b0  sub     rsp, 50h
0x1400466b4  mov     rdi, [rsp+58h+arg_30]
0x1400466bc  mov     rsi, rcx
0x1400466bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400466c6  movzx   ebx, r9w
0x1400466ca  mov     eax, [rcx+2Ch]
0x1400466cd  test    al, 2
0x1400466cf  jz      short loc_14004671A
0x1400466d1  cmp     byte ptr [rcx+29h], 4
0x1400466d5  jb      short loc_14004671A
0x1400466d7  mov     rax, cs:pfnWppTraceMessage
0x1400466de  lea     rdx, [r11+30h]
0x1400466e2  mov     rcx, [rcx+18h]
0x1400466e6  lea     r8, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400466ed  mov     qword ptr [r11-18h], 0
0x1400466f5  mov     r9d, ebx
0x1400466f8  mov     qword ptr [r11-20h], 10h
0x140046700  mov     [r11-28h], rdi
0x140046704  mov     qword ptr [r11-30h], 8
0x14004670c  mov     [r11-38h], rdx
0x140046710  mov     edx, 2Bh ; '+'
0x140046715  call    _guard_dispatch_icall
0x14004671a  mov     [rsp+58h+var_10], 0
0x140046723  lea     rax, [rsp+58h+arg_28]
0x14004672b  mov     [rsp+58h+var_18], 10h
0x140046734  lea     r9, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x14004673b  mov     [rsp+58h+var_20], rdi
0x140046740  mov     edx, 4
0x140046745  mov     [rsp+58h+var_28], 8
0x14004674e  mov     rcx, rsi
0x140046751  mov     [rsp+58h+var_30], rax
0x140046756  mov     [rsp+58h+var_38], bx
0x14004675b  lea     r8d, [rdx-2]
0x14004675f  call    cs:__imp_WppAutoLogTrace
0x140046766  nop     dword ptr [rax+rax+00h]
0x14004676b  mov     rbx, [rsp+58h+arg_0]
0x140046770  mov     rsi, [rsp+58h+arg_8]
0x140046775  add     rsp, 50h
0x140046779  pop     rdi
0x14004677a  retn
```
