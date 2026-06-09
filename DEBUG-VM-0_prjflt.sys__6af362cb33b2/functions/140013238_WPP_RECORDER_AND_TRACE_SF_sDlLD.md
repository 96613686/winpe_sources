# WPP_RECORDER_AND_TRACE_SF_sDlLD

- ea: `0x140013238`
- end: `0x140013357`
- name: `WPP_RECORDER_AND_TRACE_SF_sDlLD`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003f240`

## callees

- `0x140005cf4`
- `0x140013238`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14001333c`
- `WppRecorder!WppAutoLogTrace` at `0x14001333c`

## pseudocode

```c

```

## disassembly

```asm
0x140013238  mov     r11, rsp
0x14001323b  push    rbx
0x14001323c  push    rbp
0x14001323d  push    rsi
0x14001323e  push    rdi
0x14001323f  push    r15
0x140013241  sub     rsp, 80h
0x140013248  movzx   edi, [rsp+0A8h+arg_30]
0x140013250  mov     rsi, r9
0x140013253  lea     r15, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14001325a  mov     bl, r8b
0x14001325d  mov     ebp, 4
0x140013262  test    dl, dl
0x140013264  jz      short loc_1400132BB
0x140013266  mov     qword ptr [r11-40h], 0
0x14001326e  lea     rax, [r11+68h]
0x140013272  mov     [r11-48h], rbp
0x140013276  lea     r8, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14001327d  mov     [r11-50h], rax
0x140013281  mov     r9, r15
0x140013284  mov     [r11-58h], rbp
0x140013288  lea     rax, [r11+60h]
0x14001328c  mov     [r11-60h], rax
0x140013290  mov     edx, edi
0x140013292  mov     [r11-68h], rbp
0x140013296  lea     rax, [r11+58h]
0x14001329a  mov     [r11-70h], rax
0x14001329e  lea     rax, [r11+50h]
0x1400132a2  mov     [r11-78h], rbp
0x1400132a6  mov     [r11-80h], rax
0x1400132aa  movzx   ecx, cx
0x1400132ad  mov     [rsp+0A8h+var_88], 2Ah ; '*'
0x1400132b6  call    FastWppTraceMessage
0x1400132bb  test    bl, bl
0x1400132bd  jz      loc_140013348
0x1400132c3  movzx   edx, [rsp+0A8h+arg_20]
0x1400132cb  lea     rax, [rsp+0A8h+arg_60]
0x1400132d3  mov     [rsp+0A8h+var_30], 0
0x1400132dc  lea     r9, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x1400132e3  mov     [rsp+0A8h+var_38], rbp
0x1400132e8  mov     r8d, ebp
0x1400132eb  mov     [rsp+0A8h+var_40], rax
0x1400132f0  mov     rcx, rsi
0x1400132f3  mov     [rsp+0A8h+var_48], rbp
0x1400132f8  lea     rax, [rsp+0A8h+arg_58]
0x140013300  mov     [rsp+0A8h+var_50], rax
0x140013305  lea     rax, [rsp+0A8h+arg_50]
0x14001330d  mov     [rsp+0A8h+var_58], rbp
0x140013312  mov     [rsp+0A8h+var_60], rax
0x140013317  lea     rax, [rsp+0A8h+arg_48]
0x14001331f  mov     [rsp+0A8h+var_68], rbp
0x140013324  mov     [rsp+0A8h+var_70], rax
0x140013329  mov     [rsp+0A8h+var_78], 2Ah ; '*'
0x140013332  mov     [rsp+0A8h+var_80], r15
0x140013337  mov     word ptr [rsp+0A8h+var_88], di
0x14001333c  call    cs:__imp_WppAutoLogTrace
0x140013343  nop     dword ptr [rax+rax+00h]
0x140013348  add     rsp, 80h
0x14001334f  pop     r15
0x140013351  pop     rdi
0x140013352  pop     rsi
0x140013353  pop     rbp
0x140013354  pop     rbx
0x140013355  retn
```
