# WPP_RECORDER_AND_TRACE_SF_i

- ea: `0x140014f24`
- end: `0x140014fd4`
- name: `WPP_RECORDER_AND_TRACE_SF_i`
- size: `176`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140010c80`
- `0x140011ea8`
- `0x14002c77c`

## callees

- `0x140014f24`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140014fb7`
- `WppRecorder!WppAutoLogTrace` at `0x140014fb7`

## pseudocode

```c

```

## disassembly

```asm
0x140014f24  mov     r11, rsp
0x140014f27  mov     [r11+8], rbx
0x140014f2b  mov     [r11+10h], rsi
0x140014f2f  push    rdi
0x140014f30  sub     rsp, 40h
0x140014f34  movzx   ebx, [rsp+48h+arg_30]
0x140014f3c  mov     rsi, r9
0x140014f3f  mov     dil, r8b
0x140014f42  test    dl, dl
0x140014f44  jz      short loc_140014F79
0x140014f46  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140014f4d  lea     rdx, [r11+48h]
0x140014f51  mov     qword ptr [r11-18h], 0
0x140014f59  lea     r8, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014f60  mov     qword ptr [r11-20h], 8
0x140014f68  mov     r9d, ebx
0x140014f6b  mov     [r11-28h], rdx
0x140014f6f  mov     edx, 2Bh ; '+'
0x140014f74  call    _guard_dispatch_icall
0x140014f79  test    dil, dil
0x140014f7c  jz      short loc_140014FC3
0x140014f7e  movzx   edx, [rsp+48h+arg_20]
0x140014f83  lea     rax, [rsp+48h+arg_40]
0x140014f8b  mov     [rsp+48h+var_10], 0
0x140014f94  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014f9b  mov     [rsp+48h+var_18], 8
0x140014fa4  mov     r8d, 5
0x140014faa  mov     [rsp+48h+var_20], rax
0x140014faf  mov     rcx, rsi
0x140014fb2  mov     [rsp+48h+var_28], bx
0x140014fb7  call    cs:__imp_WppAutoLogTrace
0x140014fbe  nop     dword ptr [rax+rax+00h]
0x140014fc3  mov     rbx, [rsp+48h+arg_0]
0x140014fc8  mov     rsi, [rsp+48h+arg_8]
0x140014fcd  add     rsp, 40h
0x140014fd1  pop     rdi
0x140014fd2  retn
```
