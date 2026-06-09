# WPP_RECORDER_AND_TRACE_SF_qqD

- ea: `0x140002dcc`
- end: `0x140002eb7`
- name: `WPP_RECORDER_AND_TRACE_SF_qqD`
- size: `235`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002234`
- `0x140005600`
- `0x14000ae54`
- `0x14000b0c0`

## callees

- `0x140002dcc`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002e9a`
- `WppRecorder!WppAutoLogTrace` at `0x140002e9a`

## pseudocode

```c

```

## disassembly

```asm
0x140002dcc  mov     r11, rsp
0x140002dcf  mov     [r11+8], rbx
0x140002dd3  mov     [r11+10h], rsi
0x140002dd7  push    rdi
0x140002dd8  sub     rsp, 60h
0x140002ddc  movzx   ebx, [rsp+68h+arg_30]
0x140002de4  mov     rdi, r9
0x140002de7  mov     esi, 8
0x140002dec  test    dl, dl
0x140002dee  jz      short loc_140002E3A
0x140002df0  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140002df7  lea     rdx, [r11+58h]
0x140002dfb  mov     r8, [rsp+68h+arg_38]
0x140002e03  mov     r9d, ebx
0x140002e06  mov     qword ptr [r11-18h], 0
0x140002e0e  mov     qword ptr [r11-20h], 4
0x140002e16  mov     [r11-28h], rdx
0x140002e1a  lea     rdx, [r11+50h]
0x140002e1e  mov     [r11-30h], rsi
0x140002e22  mov     [r11-38h], rdx
0x140002e26  lea     rdx, [r11+48h]
0x140002e2a  mov     [r11-40h], rsi
0x140002e2e  mov     [r11-48h], rdx
0x140002e32  lea     edx, [rsi+23h]
0x140002e35  call    _guard_dispatch_icall
0x140002e3a  mov     r9, [rsp+68h+arg_38]
0x140002e42  lea     rax, [rsp+68h+arg_50]
0x140002e4a  mov     r8d, [rsp+68h+arg_28]
0x140002e52  mov     edx, 4
0x140002e57  mov     [rsp+68h+var_10], 0
0x140002e60  mov     rcx, rdi
0x140002e63  mov     [rsp+68h+var_18], 4
0x140002e6c  mov     [rsp+68h+var_20], rax
0x140002e71  lea     rax, [rsp+68h+arg_48]
0x140002e79  mov     [rsp+68h+var_28], rsi
0x140002e7e  mov     [rsp+68h+var_30], rax
0x140002e83  lea     rax, [rsp+68h+arg_40]
0x140002e8b  mov     [rsp+68h+var_38], rsi
0x140002e90  mov     [rsp+68h+var_40], rax
0x140002e95  mov     [rsp+68h+var_48], bx
0x140002e9a  call    cs:__imp_WppAutoLogTrace
0x140002ea1  nop     dword ptr [rax+rax+00h]
0x140002ea6  mov     rbx, [rsp+68h+arg_0]
0x140002eab  mov     rsi, [rsp+68h+arg_8]
0x140002eb0  add     rsp, 60h
0x140002eb4  pop     rdi
0x140002eb5  retn
```
