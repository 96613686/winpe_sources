# WPP_RECORDER_AND_TRACE_SF_sDDd

- ea: `0x14000ef78`
- end: `0x14000f0e1`
- name: `WPP_RECORDER_AND_TRACE_SF_sDDd`
- size: `361`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400047cc`
- `0x140009d20`
- `0x14002e374`
- `0x140031a00`
- `0x14003b724`
- `0x14003f240`

## callees

- `0x140005cf4`
- `0x14000ef78`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000f0c5`
- `WppRecorder!WppAutoLogTrace` at `0x14000f0c5`

## pseudocode

```c

```

## disassembly

```asm
0x14000ef78  push    rbx
0x14000ef7a  push    rbp
0x14000ef7b  push    rsi
0x14000ef7c  push    rdi
0x14000ef7d  push    r13
0x14000ef7f  push    r14
0x14000ef81  push    r15
0x14000ef83  sub     rsp, 70h
0x14000ef87  mov     rbx, [rsp+0A8h+arg_40]
0x14000ef8f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000ef93  movzx   r14d, [rsp+0A8h+arg_30]
0x14000ef9c  mov     bpl, r8b
0x14000ef9f  lea     r8, aNull; "NULL"
0x14000efa6  mov     r15, r9
0x14000efa9  lea     esi, [rdi+6]
0x14000efac  lea     r13d, [rdi+5]
0x14000efb0  test    dl, dl
0x14000efb2  jz      loc_14000F039
0x14000efb8  test    rbx, rbx
0x14000efbb  jz      short loc_14000EFCE
0x14000efbd  mov     rax, rdi
0x14000efc0  inc     rax
0x14000efc3  cmp     byte ptr [rbx+rax], 0
0x14000efc7  jnz     short loc_14000EFC0
0x14000efc9  inc     rax
0x14000efcc  jmp     short loc_14000EFD1
0x14000efce  mov     rax, rsi
0x14000efd1  mov     [rsp+0A8h+var_50], 0
0x14000efda  lea     rdx, [rsp+0A8h+arg_58]
0x14000efe2  mov     [rsp+0A8h+var_58], r13
0x14000efe7  test    rbx, rbx
0x14000efea  mov     [rsp+0A8h+var_60], rdx
0x14000efef  mov     r9, rbx
0x14000eff2  mov     [rsp+0A8h+var_68], r13
0x14000eff7  lea     rdx, [rsp+0A8h+arg_50]
0x14000efff  mov     [rsp+0A8h+var_70], rdx
0x14000f004  cmovz   r9, r8
0x14000f008  mov     r8, [rsp+0A8h+arg_38]
0x14000f010  lea     rdx, [rsp+0A8h+arg_48]
0x14000f018  mov     [rsp+0A8h+var_78], r13
0x14000f01d  mov     [rsp+0A8h+var_80], rdx
0x14000f022  mov     edx, r14d
0x14000f025  movzx   ecx, cx
0x14000f028  mov     [rsp+0A8h+var_88], rax
0x14000f02d  call    FastWppTraceMessage
0x14000f032  lea     r8, aNull; "NULL"
0x14000f039  test    bpl, bpl
0x14000f03c  jz      loc_14000F0D1
0x14000f042  test    rbx, rbx
0x14000f045  jz      short loc_14000F057
0x14000f047  inc     rdi
0x14000f04a  cmp     byte ptr [rbx+rdi], 0
0x14000f04e  jnz     short loc_14000F047
0x14000f050  lea     rsi, [rdi+1]
0x14000f054  test    rbx, rbx
0x14000f057  mov     r9, [rsp+0A8h+arg_38]
0x14000f05f  lea     rax, [rsp+0A8h+arg_58]
0x14000f067  movzx   edx, [rsp+0A8h+arg_20]
0x14000f06f  cmovz   rbx, r8
0x14000f073  mov     r8d, [rsp+0A8h+arg_28]
0x14000f07b  mov     rcx, r15
0x14000f07e  mov     [rsp+0A8h+var_40], 0
0x14000f087  mov     [rsp+0A8h+var_48], r13
0x14000f08c  mov     [rsp+0A8h+var_50], rax
0x14000f091  lea     rax, [rsp+0A8h+arg_50]
0x14000f099  mov     [rsp+0A8h+var_58], r13
0x14000f09e  mov     [rsp+0A8h+var_60], rax
0x14000f0a3  lea     rax, [rsp+0A8h+arg_48]
0x14000f0ab  mov     [rsp+0A8h+var_68], r13
0x14000f0b0  mov     [rsp+0A8h+var_70], rax
0x14000f0b5  mov     [rsp+0A8h+var_78], rsi
0x14000f0ba  mov     [rsp+0A8h+var_80], rbx
0x14000f0bf  mov     word ptr [rsp+0A8h+var_88], r14w
0x14000f0c5  call    cs:__imp_WppAutoLogTrace
0x14000f0cc  nop     dword ptr [rax+rax+00h]
0x14000f0d1  add     rsp, 70h
0x14000f0d5  pop     r15
0x14000f0d7  pop     r14
0x14000f0d9  pop     r13
0x14000f0db  pop     rdi
0x14000f0dc  pop     rsi
0x14000f0dd  pop     rbp
0x14000f0de  pop     rbx
0x14000f0df  retn
```
