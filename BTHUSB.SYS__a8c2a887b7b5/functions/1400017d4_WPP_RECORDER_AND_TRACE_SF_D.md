# WPP_RECORDER_AND_TRACE_SF_D

- ea: `0x1400017d4`
- end: `0x140001874`
- name: `WPP_RECORDER_AND_TRACE_SF_D`
- size: `160`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140004088`
- `0x140004b3c`
- `0x140005180`
- `0x140005600`
- `0x1400056e8`
- `0x140005c8c`
- `0x140005f60`
- `0x140006104`
- `0x140007f8c`
- `0x1400098bc`
- `0x140009a90`
- `0x14000ac54`
- `0x14000ae54`
- `0x140017210`
- `0x14001743c`
- `0x1400179ac`
- `0x140018b90`
- `0x140019008`
- `0x140019b00`
- `0x140019f30`
- `0x14001a6e8`
- `0x14001b840`
- `0x14001d03c`

## callees

- `0x1400017d4`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000185c`
- `WppRecorder!WppAutoLogTrace` at `0x14000185c`

## pseudocode

```c

```

## disassembly

```asm
0x1400017d4  mov     r11, rsp
0x1400017d7  mov     [r11+8], rbx
0x1400017db  push    rdi
0x1400017dc  sub     rsp, 40h
0x1400017e0  movzx   ebx, [rsp+48h+arg_30]
0x1400017e8  mov     rdi, r9
0x1400017eb  test    dl, dl
0x1400017ed  jz      short loc_140001823
0x1400017ef  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400017f6  lea     rdx, [r11+48h]
0x1400017fa  mov     r8, [rsp+48h+arg_38]
0x140001802  mov     r9d, ebx
0x140001805  mov     qword ptr [r11-18h], 0
0x14000180d  mov     qword ptr [r11-20h], 4
0x140001815  mov     [r11-28h], rdx
0x140001819  mov     edx, 2Bh ; '+'
0x14000181e  call    _guard_dispatch_icall
0x140001823  mov     r9, [rsp+48h+arg_38]
0x14000182b  lea     rax, [rsp+48h+arg_40]
0x140001833  mov     r8d, [rsp+48h+arg_28]
0x140001838  mov     rcx, rdi
0x14000183b  movzx   edx, [rsp+48h+arg_20]
0x140001840  mov     [rsp+48h+var_10], 0
0x140001849  mov     [rsp+48h+var_18], 4
0x140001852  mov     [rsp+48h+var_20], rax
0x140001857  mov     [rsp+48h+var_28], bx
0x14000185c  call    cs:__imp_WppAutoLogTrace
0x140001863  nop     dword ptr [rax+rax+00h]
0x140001868  mov     rbx, [rsp+48h+arg_0]
0x14000186d  add     rsp, 40h
0x140001871  pop     rdi
0x140001872  retn
```
