# WPP_RECORDER_AND_TRACE_SF_dd

- ea: `0x14000a594`
- end: `0x14000a658`
- name: `WPP_RECORDER_AND_TRACE_SF_dd`
- size: `196`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400084e4`
- `0x14000a05c`
- `0x14000e510`
- `0x14002ba2c`

## callees

- `0x14000a594`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000a642`
- `WppRecorder!WppAutoLogTrace` at `0x14000a642`

## pseudocode

```c

```

## disassembly

```asm
0x14000a594  mov     r11, rsp
0x14000a597  push    rbx
0x14000a598  push    rbp
0x14000a599  push    rsi
0x14000a59a  push    rdi
0x14000a59b  sub     rsp, 58h
0x14000a59f  movzx   ebx, [rsp+78h+arg_30]
0x14000a5a7  mov     rsi, r9
0x14000a5aa  mov     dil, r8b
0x14000a5ad  mov     ebp, 4
0x14000a5b2  test    dl, dl
0x14000a5b4  jz      short loc_14000A5F0
0x14000a5b6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000a5bd  lea     rdx, [r11+50h]
0x14000a5c1  mov     r8, [rsp+78h+arg_38]
0x14000a5c9  mov     r9d, ebx
0x14000a5cc  mov     qword ptr [r11-38h], 0
0x14000a5d4  mov     [r11-40h], rbp
0x14000a5d8  mov     [r11-48h], rdx
0x14000a5dc  lea     rdx, [r11+48h]
0x14000a5e0  mov     [r11-50h], rbp
0x14000a5e4  mov     [r11-58h], rdx
0x14000a5e8  lea     edx, [rbp+27h]
0x14000a5eb  call    _guard_dispatch_icall
0x14000a5f0  test    dil, dil
0x14000a5f3  jz      short loc_14000A64E
0x14000a5f5  mov     r9, [rsp+78h+arg_38]
0x14000a5fd  lea     rax, [rsp+78h+arg_48]
0x14000a605  mov     r8d, [rsp+78h+arg_28]
0x14000a60d  mov     rcx, rsi
0x14000a610  movzx   edx, [rsp+78h+arg_20]
0x14000a618  mov     [rsp+78h+var_30], 0
0x14000a621  mov     [rsp+78h+var_38], rbp
0x14000a626  mov     [rsp+78h+var_40], rax
0x14000a62b  lea     rax, [rsp+78h+arg_40]
0x14000a633  mov     [rsp+78h+var_48], rbp
0x14000a638  mov     [rsp+78h+var_50], rax
0x14000a63d  mov     [rsp+78h+var_58], bx
0x14000a642  call    cs:__imp_WppAutoLogTrace
0x14000a649  nop     dword ptr [rax+rax+00h]
0x14000a64e  add     rsp, 58h
0x14000a652  pop     rdi
0x14000a653  pop     rsi
0x14000a654  pop     rbp
0x14000a655  pop     rbx
0x14000a656  retn
```
