# WPP_RECORDER_AND_TRACE_SF_LLLL

- ea: `0x1400067e8`
- end: `0x1400068e1`
- name: `WPP_RECORDER_AND_TRACE_SF_LLLL`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140005c8c`

## callees

- `0x1400067e8`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400068c2`
- `WppRecorder!WppAutoLogTrace` at `0x1400068c2`

## pseudocode

```c

```

## disassembly

```asm
0x1400067e8  mov     r11, rsp
0x1400067eb  mov     [r11+8], rbx
0x1400067ef  mov     [r11+10h], rsi
0x1400067f3  push    rdi
0x1400067f4  sub     rsp, 70h
0x1400067f8  movzx   ebx, [rsp+78h+arg_30]
0x140006800  mov     rdi, r9
0x140006803  mov     esi, 4
0x140006808  test    dl, dl
0x14000680a  jz      short loc_14000685D
0x14000680c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140006813  lea     rdx, [r11+60h]
0x140006817  mov     qword ptr [r11-18h], 0
0x14000681f  lea     r8, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140006826  mov     [r11-20h], rsi
0x14000682a  mov     r9d, ebx
0x14000682d  mov     [r11-28h], rdx
0x140006831  lea     rdx, [r11+58h]
0x140006835  mov     [r11-30h], rsi
0x140006839  mov     [r11-38h], rdx
0x14000683d  lea     rdx, [r11+50h]
0x140006841  mov     [r11-40h], rsi
0x140006845  mov     [r11-48h], rdx
0x140006849  lea     rdx, [r11+48h]
0x14000684d  mov     [r11-50h], rsi
0x140006851  mov     [r11-58h], rdx
0x140006855  lea     edx, [rsi+27h]
0x140006858  call    _guard_dispatch_icall
0x14000685d  mov     [rsp+78h+var_10], 0
0x140006866  lea     rax, [rsp+78h+arg_58]
0x14000686e  mov     [rsp+78h+var_18], rsi
0x140006873  lea     r9, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000687a  mov     [rsp+78h+var_20], rax
0x14000687f  mov     r8d, esi
0x140006882  mov     [rsp+78h+var_28], rsi
0x140006887  lea     rax, [rsp+78h+arg_50]
0x14000688f  mov     [rsp+78h+var_30], rax
0x140006894  mov     edx, esi
0x140006896  mov     [rsp+78h+var_38], rsi
0x14000689b  lea     rax, [rsp+78h+arg_48]
0x1400068a3  mov     [rsp+78h+var_40], rax
0x1400068a8  mov     rcx, rdi
0x1400068ab  lea     rax, [rsp+78h+arg_40]
0x1400068b3  mov     [rsp+78h+var_48], rsi
0x1400068b8  mov     [rsp+78h+var_50], rax
0x1400068bd  mov     [rsp+78h+var_58], bx
0x1400068c2  call    cs:__imp_WppAutoLogTrace
0x1400068c9  nop     dword ptr [rax+rax+00h]
0x1400068ce  lea     r11, [rsp+78h+var_8]
0x1400068d3  mov     rbx, [r11+10h]
0x1400068d7  mov     rsi, [r11+18h]
0x1400068db  mov     rsp, r11
0x1400068de  pop     rdi
0x1400068df  retn
```
