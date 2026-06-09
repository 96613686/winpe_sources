# WPP_RECORDER_AND_TRACE_SF_L

- ea: `0x140006580`
- end: `0x140006631`
- name: `WPP_RECORDER_AND_TRACE_SF_L`
- size: `177`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140004088`
- `0x140004b3c`
- `0x1400081b0`
- `0x140009a90`
- `0x140019b00`

## callees

- `0x140006580`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006614`
- `WppRecorder!WppAutoLogTrace` at `0x140006614`

## pseudocode

```c

```

## disassembly

```asm
0x140006580  mov     r11, rsp
0x140006583  mov     [r11+8], rbx
0x140006587  mov     [r11+10h], rsi
0x14000658b  push    rdi
0x14000658c  sub     rsp, 40h
0x140006590  movzx   ebx, [rsp+48h+arg_30]
0x140006598  mov     rsi, r9
0x14000659b  mov     dil, r8b
0x14000659e  test    dl, dl
0x1400065a0  jz      short loc_1400065D6
0x1400065a2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400065a9  lea     rdx, [r11+48h]
0x1400065ad  mov     r8, [rsp+48h+arg_38]
0x1400065b5  mov     r9d, ebx
0x1400065b8  mov     qword ptr [r11-18h], 0
0x1400065c0  mov     qword ptr [r11-20h], 4
0x1400065c8  mov     [r11-28h], rdx
0x1400065cc  mov     edx, 2Bh ; '+'
0x1400065d1  call    _guard_dispatch_icall
0x1400065d6  test    dil, dil
0x1400065d9  jz      short loc_140006620
0x1400065db  mov     r9, [rsp+48h+arg_38]
0x1400065e3  lea     rax, [rsp+48h+arg_40]
0x1400065eb  mov     r8d, [rsp+48h+arg_28]
0x1400065f0  mov     rcx, rsi
0x1400065f3  movzx   edx, [rsp+48h+arg_20]
0x1400065f8  mov     [rsp+48h+var_10], 0
0x140006601  mov     [rsp+48h+var_18], 4
0x14000660a  mov     [rsp+48h+var_20], rax
0x14000660f  mov     [rsp+48h+var_28], bx
0x140006614  call    cs:__imp_WppAutoLogTrace
0x14000661b  nop     dword ptr [rax+rax+00h]
0x140006620  mov     rbx, [rsp+48h+arg_0]
0x140006625  mov     rsi, [rsp+48h+arg_8]
0x14000662a  add     rsp, 40h
0x14000662e  pop     rdi
0x14000662f  retn
```
