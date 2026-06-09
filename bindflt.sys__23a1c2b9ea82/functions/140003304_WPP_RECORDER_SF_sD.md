# WPP_RECORDER_SF_sD

- ea: `0x140003304`
- end: `0x140003474`
- name: `WPP_RECORDER_SF_sD`
- size: `368`
- prototype: ``
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x140001fd0`
- `0x14000f3d0`
- `0x14000fa74`
- `0x140010384`
- `0x140010898`
- `0x140010d64`
- `0x140011264`
- `0x140012c60`
- `0x140013864`
- `0x140014324`
- `0x140014ccc`
- `0x140014e9c`
- `0x1400157a0`
- `0x140017bf0`
- `0x140019c44`
- `0x14001b280`
- `0x14001cd84`
- `0x14001d2c0`
- `0x14001d974`
- `0x14001e5c8`
- `0x14001ea74`
- `0x14001f40c`
- `0x14001fb68`
- `0x14001fcf0`
- `0x14002001c`
- `0x140020180`
- `0x140021550`
- `0x140021b60`
- `0x140021d1c`
- `0x140023330`
- `0x140024294`
- `0x140025780`
- `0x140025c70`

## callees

- `0x140003304`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003456`
- `WppRecorder!WppAutoLogTrace` at `0x140003456`

## pseudocode

```c

```

## disassembly

```asm
0x140003304  mov     [rsp+arg_0], rcx
0x140003309  push    rbx
0x14000330a  push    rbp
0x14000330b  push    rsi
0x14000330c  push    rdi
0x14000330d  push    r12
0x14000330f  push    r13
0x140003311  push    r14
0x140003313  push    r15
0x140003315  sub     rsp, 58h
0x140003319  mov     r14, cs:WPP_GLOBAL_Control
0x140003320  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140003324  mov     r13d, r8d
0x140003327  mov     esi, r8d
0x14000332a  lea     r8, aNull; "NULL"
0x140003331  shr     rsi, 10h
0x140003335  movzx   r15d, dl
0x140003339  lea     ebp, [rdi+6]
0x14000333c  lea     ebx, [r13-1]
0x140003340  movzx   r12d, r9w
0x140003344  mov     r10d, ebx
0x140003347  and     ebx, 1Fh
0x14000334a  shr     r10, 5
0x14000334e  lea     rax, [rsi+rsi*4]
0x140003352  and     r10d, 7FFh
0x140003359  mov     edx, ebx
0x14000335b  mov     rbx, [rsp+98h+arg_28]
0x140003363  lea     r11, [r10+rax*4]
0x140003367  mov     eax, [r14+r11*4+2Ch]
0x14000336c  bt      eax, edx
0x14000336f  jnb     loc_140003400
0x140003375  lea     r10, [rsi+rsi*4]
0x140003379  add     r10, r10
0x14000337c  cmp     [r14+r10*8+29h], r15b
0x140003381  jb      short loc_140003400
0x140003383  test    rbx, rbx
0x140003386  jz      short loc_14000339A
0x140003388  mov     rax, rdi
0x14000338b  inc     rax
0x14000338e  cmp     byte ptr [rbx+rax], 0
0x140003392  jnz     short loc_14000338B
0x140003394  lea     rdx, [rax+1]
0x140003398  jmp     short loc_14000339D
0x14000339a  mov     rdx, rbp
0x14000339d  mov     rax, cs:pfnWppTraceMessage
0x1400033a4  test    rbx, rbx
0x1400033a7  mov     [rsp+98h+var_58], 0
0x1400033b0  mov     rcx, rbx
0x1400033b3  cmovz   rcx, r8
0x1400033b7  mov     [rsp+98h+var_60], 4
0x1400033c0  lea     r8, [rsp+98h+arg_30]
0x1400033c8  mov     r9d, r12d
0x1400033cb  mov     [rsp+98h+var_68], r8
0x1400033d0  mov     r8, [rsp+98h+arg_20]
0x1400033d8  mov     [rsp+98h+var_70], rdx
0x1400033dd  mov     edx, 2Bh ; '+'
0x1400033e2  mov     [rsp+98h+var_78], rcx
0x1400033e7  mov     rcx, [r14+r10*8+18h]
0x1400033ec  call    _guard_dispatch_icall
0x1400033f1  mov     rcx, [rsp+98h+arg_0]
0x1400033f9  lea     r8, aNull; "NULL"
0x140003400  test    rbx, rbx
0x140003403  jz      short loc_140003415
0x140003405  inc     rdi
0x140003408  cmp     byte ptr [rbx+rdi], 0
0x14000340c  jnz     short loc_140003405
0x14000340e  lea     rbp, [rdi+1]
0x140003412  test    rbx, rbx
0x140003415  mov     r9, [rsp+98h+arg_20]
0x14000341d  lea     rax, [rsp+98h+arg_30]
0x140003425  mov     [rsp+98h+var_50], 0
0x14000342e  cmovz   rbx, r8
0x140003432  mov     [rsp+98h+var_58], 4
0x14000343b  mov     r8d, r13d
0x14000343e  mov     [rsp+98h+var_60], rax
0x140003443  mov     edx, r15d
0x140003446  mov     [rsp+98h+var_68], rbp
0x14000344b  mov     [rsp+98h+var_70], rbx
0x140003450  mov     word ptr [rsp+98h+var_78], r12w
0x140003456  call    cs:__imp_WppAutoLogTrace
0x14000345d  nop     dword ptr [rax+rax+00h]
0x140003462  add     rsp, 58h
0x140003466  pop     r15
0x140003468  pop     r14
0x14000346a  pop     r13
0x14000346c  pop     r12
0x14000346e  pop     rdi
0x14000346f  pop     rsi
0x140003470  pop     rbp
0x140003471  pop     rbx
0x140003472  retn
```
