# WPP_RECORDER_AND_TRACE_SF_q

- ea: `0x14000187c`
- end: `0x14000191c`
- name: `WPP_RECORDER_AND_TRACE_SF_q`
- size: `160`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x1400025e4`
- `0x140002738`
- `0x1400030e0`
- `0x1400049f0`
- `0x14000509c`
- `0x140005180`
- `0x1400076e8`
- `0x1400081b0`
- `0x14000a290`
- `0x140017210`
- `0x14001743c`
- `0x140017858`
- `0x14001868c`
- `0x140018764`
- `0x140018910`
- `0x140018b90`
- `0x140018f10`
- `0x14001946c`
- `0x140019764`

## callees

- `0x14000187c`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001904`
- `WppRecorder!WppAutoLogTrace` at `0x140001904`

## pseudocode

```c

```

## disassembly

```asm
0x14000187c  mov     r11, rsp
0x14000187f  mov     [r11+8], rbx
0x140001883  push    rdi
0x140001884  sub     rsp, 40h
0x140001888  movzx   ebx, [rsp+48h+arg_30]
0x140001890  mov     rdi, r9
0x140001893  test    dl, dl
0x140001895  jz      short loc_1400018CB
0x140001897  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000189e  lea     rdx, [r11+48h]
0x1400018a2  mov     r8, [rsp+48h+arg_38]
0x1400018aa  mov     r9d, ebx
0x1400018ad  mov     qword ptr [r11-18h], 0
0x1400018b5  mov     qword ptr [r11-20h], 8
0x1400018bd  mov     [r11-28h], rdx
0x1400018c1  mov     edx, 2Bh ; '+'
0x1400018c6  call    _guard_dispatch_icall
0x1400018cb  mov     r9, [rsp+48h+arg_38]
0x1400018d3  lea     rax, [rsp+48h+arg_40]
0x1400018db  mov     r8d, [rsp+48h+arg_28]
0x1400018e0  mov     rcx, rdi
0x1400018e3  movzx   edx, [rsp+48h+arg_20]
0x1400018e8  mov     [rsp+48h+var_10], 0
0x1400018f1  mov     [rsp+48h+var_18], 8
0x1400018fa  mov     [rsp+48h+var_20], rax
0x1400018ff  mov     [rsp+48h+var_28], bx
0x140001904  call    cs:__imp_WppAutoLogTrace
0x14000190b  nop     dword ptr [rax+rax+00h]
0x140001910  mov     rbx, [rsp+48h+arg_0]
0x140001915  add     rsp, 40h
0x140001919  pop     rdi
0x14000191a  retn
```
