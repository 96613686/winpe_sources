# WPP_RECORDER_SF_i_IPV4_

- ea: `0x140046378`
- end: `0x140046450`
- name: `WPP_RECORDER_SF_i_IPV4_`
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

- `0x140046378`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140046433`
- `WppRecorder!WppAutoLogTrace` at `0x140046433`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_i_IPV4_(
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
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 4, 2, WPP_f53708f2277a3aabca584f524242a299_Traceguids, v11, &a6, 8, v7, 4, 0);
}

```

## disassembly

```asm
0x140046378  mov     r11, rsp
0x14004637b  mov     [r11+8], rbx
0x14004637f  mov     [r11+10h], rsi
0x140046383  push    rdi
0x140046384  sub     rsp, 50h
0x140046388  mov     rdi, [rsp+58h+arg_30]
0x140046390  mov     rsi, rcx
0x140046393  mov     rcx, cs:WPP_GLOBAL_Control
0x14004639a  movzx   ebx, r9w
0x14004639e  mov     eax, [rcx+2Ch]
0x1400463a1  test    al, 2
0x1400463a3  jz      short loc_1400463EE
0x1400463a5  cmp     byte ptr [rcx+29h], 4
0x1400463a9  jb      short loc_1400463EE
0x1400463ab  mov     rax, cs:pfnWppTraceMessage
0x1400463b2  lea     rdx, [r11+30h]
0x1400463b6  mov     rcx, [rcx+18h]
0x1400463ba  lea     r8, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400463c1  mov     qword ptr [r11-18h], 0
0x1400463c9  mov     r9d, ebx
0x1400463cc  mov     qword ptr [r11-20h], 4
0x1400463d4  mov     [r11-28h], rdi
0x1400463d8  mov     qword ptr [r11-30h], 8
0x1400463e0  mov     [r11-38h], rdx
0x1400463e4  mov     edx, 2Bh ; '+'
0x1400463e9  call    _guard_dispatch_icall
0x1400463ee  mov     [rsp+58h+var_10], 0
0x1400463f7  lea     rax, [rsp+58h+arg_28]
0x1400463ff  mov     [rsp+58h+var_18], 4
0x140046408  lea     r9, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x14004640f  mov     [rsp+58h+var_20], rdi
0x140046414  mov     edx, 4
0x140046419  mov     [rsp+58h+var_28], 8
0x140046422  mov     rcx, rsi
0x140046425  mov     [rsp+58h+var_30], rax
0x14004642a  mov     [rsp+58h+var_38], bx
0x14004642f  lea     r8d, [rdx-2]
0x140046433  call    cs:__imp_WppAutoLogTrace
0x14004643a  nop     dword ptr [rax+rax+00h]
0x14004643f  mov     rbx, [rsp+58h+arg_0]
0x140046444  mov     rsi, [rsp+58h+arg_8]
0x140046449  add     rsp, 50h
0x14004644d  pop     rdi
0x14004644e  retn
```
