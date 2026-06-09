# WPP_RECORDER_AND_TRACE_SF_LL

- ea: `0x140006638`
- end: `0x1400066fa`
- name: `WPP_RECORDER_AND_TRACE_SF_LL`
- size: `194`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140005c8c`
- `0x140008e70`

## callees

- `0x140006638`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400066dd`
- `WppRecorder!WppAutoLogTrace` at `0x1400066dd`

## pseudocode

```c

```

## disassembly

```asm
0x140006638  mov     r11, rsp
0x14000663b  mov     [r11+8], rbx
0x14000663f  mov     [r11+10h], rsi
0x140006643  push    rdi
0x140006644  sub     rsp, 50h
0x140006648  movzx   ebx, [rsp+58h+arg_30]
0x140006650  mov     rdi, r9
0x140006653  mov     esi, 4
0x140006658  test    dl, dl
0x14000665a  jz      short loc_140006696
0x14000665c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140006663  lea     rdx, [r11+50h]
0x140006667  mov     r8, [rsp+58h+arg_38]
0x14000666f  mov     r9d, ebx
0x140006672  mov     qword ptr [r11-18h], 0
0x14000667a  mov     [r11-20h], rsi
0x14000667e  mov     [r11-28h], rdx
0x140006682  lea     rdx, [r11+48h]
0x140006686  mov     [r11-30h], rsi
0x14000668a  mov     [r11-38h], rdx
0x14000668e  lea     edx, [rsi+27h]
0x140006691  call    _guard_dispatch_icall
0x140006696  mov     r9, [rsp+58h+arg_38]
0x14000669e  lea     rax, [rsp+58h+arg_48]
0x1400066a6  mov     r8d, [rsp+58h+arg_28]
0x1400066ae  mov     edx, esi
0x1400066b0  mov     [rsp+58h+var_10], 0
0x1400066b9  mov     rcx, rdi
0x1400066bc  mov     [rsp+58h+var_18], rsi
0x1400066c1  mov     [rsp+58h+var_20], rax
0x1400066c6  lea     rax, [rsp+58h+arg_40]
0x1400066ce  mov     [rsp+58h+var_28], rsi
0x1400066d3  mov     [rsp+58h+var_30], rax
0x1400066d8  mov     [rsp+58h+var_38], bx
0x1400066dd  call    cs:__imp_WppAutoLogTrace
0x1400066e4  nop     dword ptr [rax+rax+00h]
0x1400066e9  mov     rbx, [rsp+58h+arg_0]
0x1400066ee  mov     rsi, [rsp+58h+arg_8]
0x1400066f3  add     rsp, 50h
0x1400066f7  pop     rdi
0x1400066f8  retn
```
