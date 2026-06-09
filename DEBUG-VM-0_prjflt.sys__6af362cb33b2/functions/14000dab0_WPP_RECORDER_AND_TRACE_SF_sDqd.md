# WPP_RECORDER_AND_TRACE_SF_sDqd

- ea: `0x14000dab0`
- end: `0x14000dc21`
- name: `WPP_RECORDER_AND_TRACE_SF_sDqd`
- size: `369`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f3c`
- `0x1400217a4`
- `0x140022320`
- `0x140024758`
- `0x140029650`
- `0x14002e1a4`
- `0x14003a84c`
- `0x14003d620`
- `0x140042658`

## callees

- `0x140005cf4`
- `0x14000dab0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000dc05`
- `WppRecorder!WppAutoLogTrace` at `0x14000dc05`

## pseudocode

```c

```

## disassembly

```asm
0x14000dab0  push    rbx
0x14000dab2  push    rbp
0x14000dab3  push    rsi
0x14000dab4  push    rdi
0x14000dab5  push    r13
0x14000dab7  push    r14
0x14000dab9  push    r15
0x14000dabb  sub     rsp, 70h
0x14000dabf  mov     rbx, [rsp+0A8h+arg_40]
0x14000dac7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000dacb  movzx   r14d, [rsp+0A8h+arg_30]
0x14000dad4  mov     bpl, r8b
0x14000dad7  lea     r8, aNull; "NULL"
0x14000dade  mov     r15, r9
0x14000dae1  lea     esi, [rdi+6]
0x14000dae4  lea     r13d, [rdi+5]
0x14000dae8  test    dl, dl
0x14000daea  jz      loc_14000DB75
0x14000daf0  test    rbx, rbx
0x14000daf3  jz      short loc_14000DB06
0x14000daf5  mov     rax, rdi
0x14000daf8  inc     rax
0x14000dafb  cmp     byte ptr [rbx+rax], 0
0x14000daff  jnz     short loc_14000DAF8
0x14000db01  inc     rax
0x14000db04  jmp     short loc_14000DB09
0x14000db06  mov     rax, rsi
0x14000db09  mov     [rsp+0A8h+var_50], 0
0x14000db12  lea     rdx, [rsp+0A8h+arg_58]
0x14000db1a  mov     [rsp+0A8h+var_58], r13
0x14000db1f  test    rbx, rbx
0x14000db22  mov     [rsp+0A8h+var_60], rdx
0x14000db27  mov     r9, rbx
0x14000db2a  mov     [rsp+0A8h+var_68], 8
0x14000db33  lea     rdx, [rsp+0A8h+arg_50]
0x14000db3b  mov     [rsp+0A8h+var_70], rdx
0x14000db40  cmovz   r9, r8
0x14000db44  mov     r8, [rsp+0A8h+arg_38]
0x14000db4c  lea     rdx, [rsp+0A8h+arg_48]
0x14000db54  mov     [rsp+0A8h+var_78], r13
0x14000db59  mov     [rsp+0A8h+var_80], rdx
0x14000db5e  mov     edx, r14d
0x14000db61  movzx   ecx, cx
0x14000db64  mov     [rsp+0A8h+var_88], rax
0x14000db69  call    FastWppTraceMessage
0x14000db6e  lea     r8, aNull; "NULL"
0x14000db75  test    bpl, bpl
0x14000db78  jz      loc_14000DC11
0x14000db7e  test    rbx, rbx
0x14000db81  jz      short loc_14000DB93
0x14000db83  inc     rdi
0x14000db86  cmp     byte ptr [rbx+rdi], 0
0x14000db8a  jnz     short loc_14000DB83
0x14000db8c  lea     rsi, [rdi+1]
0x14000db90  test    rbx, rbx
0x14000db93  mov     r9, [rsp+0A8h+arg_38]
0x14000db9b  lea     rax, [rsp+0A8h+arg_58]
0x14000dba3  movzx   edx, [rsp+0A8h+arg_20]
0x14000dbab  cmovz   rbx, r8
0x14000dbaf  mov     r8d, [rsp+0A8h+arg_28]
0x14000dbb7  mov     rcx, r15
0x14000dbba  mov     [rsp+0A8h+var_40], 0
0x14000dbc3  mov     [rsp+0A8h+var_48], r13
0x14000dbc8  mov     [rsp+0A8h+var_50], rax
0x14000dbcd  lea     rax, [rsp+0A8h+arg_50]
0x14000dbd5  mov     [rsp+0A8h+var_58], 8
0x14000dbde  mov     [rsp+0A8h+var_60], rax
0x14000dbe3  lea     rax, [rsp+0A8h+arg_48]
0x14000dbeb  mov     [rsp+0A8h+var_68], r13
0x14000dbf0  mov     [rsp+0A8h+var_70], rax
0x14000dbf5  mov     [rsp+0A8h+var_78], rsi
0x14000dbfa  mov     [rsp+0A8h+var_80], rbx
0x14000dbff  mov     word ptr [rsp+0A8h+var_88], r14w
0x14000dc05  call    cs:__imp_WppAutoLogTrace
0x14000dc0c  nop     dword ptr [rax+rax+00h]
0x14000dc11  add     rsp, 70h
0x14000dc15  pop     r15
0x14000dc17  pop     r14
0x14000dc19  pop     r13
0x14000dc1b  pop     rdi
0x14000dc1c  pop     rsi
0x14000dc1d  pop     rbp
0x14000dc1e  pop     rbx
0x14000dc1f  retn
```
