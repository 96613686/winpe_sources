# WPP_RECORDER_AND_TRACE_SF_q

- ea: `0x14000498c`
- end: `0x140004a3d`
- name: `WPP_RECORDER_AND_TRACE_SF_q`
- size: `177`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014c4`
- `0x140003330`
- `0x140008754`
- `0x14000888c`
- `0x14000aac0`
- `0x14000c5b0`
- `0x14000fa40`

## callees

- `0x14000498c`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004a20`
- `WppRecorder!WppAutoLogTrace` at `0x140004a20`

## pseudocode

```c

```

## disassembly

```asm
0x14000498c  mov     r11, rsp
0x14000498f  mov     [r11+8], rbx
0x140004993  mov     [r11+10h], rsi
0x140004997  push    rdi
0x140004998  sub     rsp, 40h
0x14000499c  movzx   ebx, [rsp+48h+arg_30]
0x1400049a4  mov     rsi, r9
0x1400049a7  mov     dil, r8b
0x1400049aa  test    dl, dl
0x1400049ac  jz      short loc_1400049E2
0x1400049ae  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400049b5  lea     rdx, [r11+48h]
0x1400049b9  mov     r8, [rsp+48h+arg_38]
0x1400049c1  mov     r9d, ebx
0x1400049c4  mov     qword ptr [r11-18h], 0
0x1400049cc  mov     qword ptr [r11-20h], 8
0x1400049d4  mov     [r11-28h], rdx
0x1400049d8  mov     edx, 2Bh ; '+'
0x1400049dd  call    _guard_dispatch_icall
0x1400049e2  test    dil, dil
0x1400049e5  jz      short loc_140004A2C
0x1400049e7  mov     r9, [rsp+48h+arg_38]
0x1400049ef  lea     rax, [rsp+48h+arg_40]
0x1400049f7  mov     r8d, [rsp+48h+arg_28]
0x1400049fc  mov     rcx, rsi
0x1400049ff  movzx   edx, [rsp+48h+arg_20]
0x140004a04  mov     [rsp+48h+var_10], 0
0x140004a0d  mov     [rsp+48h+var_18], 8
0x140004a16  mov     [rsp+48h+var_20], rax
0x140004a1b  mov     [rsp+48h+var_28], bx
0x140004a20  call    cs:__imp_WppAutoLogTrace
0x140004a27  nop     dword ptr [rax+rax+00h]
0x140004a2c  mov     rbx, [rsp+48h+arg_0]
0x140004a31  mov     rsi, [rsp+48h+arg_8]
0x140004a36  add     rsp, 40h
0x140004a3a  pop     rdi
0x140004a3b  retn
```
