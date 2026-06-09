# WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE

- ea: `0x140014c60`
- end: `0x140014d1a`
- name: `WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE`
- size: `186`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001790`
- `0x14000ce50`
- `0x14000e510`
- `0x14000fff0`
- `0x1400112c4`

## callees

- `0x140014c60`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140014d04`
- `WppRecorder!WppAutoLogTrace` at `0x140014d04`

## pseudocode

```c

```

## disassembly

```asm
0x140014c60  mov     r11, rsp
0x140014c63  push    rbx
0x140014c64  push    rbp
0x140014c65  push    rsi
0x140014c66  push    rdi
0x140014c67  sub     rsp, 58h
0x140014c6b  movzx   ebx, [rsp+78h+arg_30]
0x140014c73  mov     rsi, r9
0x140014c76  mov     dil, r8b
0x140014c79  mov     ebp, 4
0x140014c7e  test    dl, dl
0x140014c80  jz      short loc_140014CBB
0x140014c82  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140014c89  lea     rdx, [r11+50h]
0x140014c8d  mov     qword ptr [r11-38h], 0
0x140014c95  lea     r8, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014c9c  mov     [r11-40h], rbp
0x140014ca0  mov     r9d, ebx
0x140014ca3  mov     [r11-48h], rdx
0x140014ca7  lea     rdx, [r11+48h]
0x140014cab  mov     [r11-50h], rbp
0x140014caf  mov     [r11-58h], rdx
0x140014cb3  lea     edx, [rbp+27h]
0x140014cb6  call    _guard_dispatch_icall
0x140014cbb  test    dil, dil
0x140014cbe  jz      short loc_140014D10
0x140014cc0  mov     [rsp+78h+var_30], 0
0x140014cc9  lea     rax, [rsp+78h+arg_48]
0x140014cd1  mov     [rsp+78h+var_38], rbp
0x140014cd6  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014cdd  mov     [rsp+78h+var_40], rax
0x140014ce2  mov     r8d, 5
0x140014ce8  lea     rax, [rsp+78h+arg_40]
0x140014cf0  mov     [rsp+78h+var_48], rbp
0x140014cf5  mov     [rsp+78h+var_50], rax
0x140014cfa  mov     edx, ebp
0x140014cfc  mov     rcx, rsi
0x140014cff  mov     [rsp+78h+var_58], bx
0x140014d04  call    cs:__imp_WppAutoLogTrace
0x140014d0b  nop     dword ptr [rax+rax+00h]
0x140014d10  add     rsp, 58h
0x140014d14  pop     rdi
0x140014d15  pop     rsi
0x140014d16  pop     rbp
0x140014d17  pop     rbx
0x140014d18  retn
```
