# WPP_RECORDER_SF_sDZd

- ea: `0x140002e0c`
- end: `0x14000306b`
- name: `WPP_RECORDER_SF_sDZd`
- size: `607`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140013864`
- `0x1400152f0`
- `0x1400157a0`
- `0x140018b60`
- `0x14001c904`
- `0x140023420`
- `0x140023dc8`

## callees

- `0x140002e0c`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000304a`
- `WppRecorder!WppAutoLogTrace` at `0x14000304a`

## pseudocode

```c

```

## disassembly

```asm
0x140002e0c  mov     rax, rsp
0x140002e0f  mov     [rax+20h], r9w
0x140002e14  mov     [rax+18h], r8d
0x140002e18  mov     [rax+10h], dl
0x140002e1b  mov     [rax+8], rcx
0x140002e1f  push    rbx
0x140002e20  push    rbp
0x140002e21  push    rsi
0x140002e22  push    rdi
0x140002e23  push    r12
0x140002e25  push    r13
0x140002e27  push    r14
0x140002e29  push    r15
0x140002e2b  sub     rsp, 88h
0x140002e32  mov     r12, cs:WPP_GLOBAL_Control
0x140002e39  lea     r13, aNull_0; "NULL"
0x140002e40  mov     rdi, [rsp+0C8h+arg_28]
0x140002e48  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140002e4c  mov     eax, r8d
0x140002e4f  mov     r8b, dl
0x140002e52  mov     esi, eax
0x140002e54  shr     rsi, 10h
0x140002e58  lea     ebx, [rax-1]
0x140002e5b  mov     r10d, ebx
0x140002e5e  and     ebx, 1Fh
0x140002e61  shr     r10, 5
0x140002e65  lea     rax, [rsi+rsi*4]
0x140002e69  and     r10d, 7FFh
0x140002e70  mov     edx, ebx
0x140002e72  mov     rbx, [rsp+0C8h+arg_38]
0x140002e7a  lea     r11, [r10+rax*4]
0x140002e7e  mov     eax, [r12+r11*4+2Ch]
0x140002e83  lea     r10, asc_140008A70; "\b"
0x140002e8a  xor     r11d, r11d
0x140002e8d  bt      eax, edx
0x140002e90  lea     r14d, [r11+8]
0x140002e94  lea     r15d, [r11+5]
0x140002e98  jnb     loc_140002F9F
0x140002e9e  lea     r10, [rsi+rsi*4]
0x140002ea2  add     r10, r10
0x140002ea5  cmp     [r12+r10*8+29h], r8b
0x140002eaa  jb      loc_140002F98
0x140002eb0  test    rbx, rbx
0x140002eb3  jz      short loc_140002EC4
0x140002eb5  movzx   edx, word ptr [rbx]
0x140002eb8  cmp     [rbx], r11w
0x140002ebc  jz      short loc_140002EC7
0x140002ebe  mov     r11, [rbx+8]
0x140002ec2  jmp     short loc_140002ECA
0x140002ec4  mov     rdx, r14
0x140002ec7  mov     r11, r13
0x140002eca  test    rbx, rbx
0x140002ecd  lea     rax, asc_140008A70; "\b"
0x140002ed4  mov     r9, rbx
0x140002ed7  cmovz   r9, rax
0x140002edb  test    rdi, rdi
0x140002ede  jz      short loc_140002EF2
0x140002ee0  mov     rax, rbp
0x140002ee3  inc     rax
0x140002ee6  cmp     byte ptr [rdi+rax], 0
0x140002eea  jnz     short loc_140002EE3
0x140002eec  lea     r8, [rax+1]
0x140002ef0  jmp     short loc_140002EF5
0x140002ef2  mov     r8, r15
0x140002ef5  mov     [rsp+0C8h+var_58], 0
0x140002efe  lea     rax, aNull; "NULL"
0x140002f05  mov     [rsp+0C8h+var_60], 4
0x140002f0e  lea     rsi, [rsp+0C8h+arg_40]
0x140002f16  mov     [rsp+0C8h+var_68], rsi
0x140002f1b  test    rdi, rdi
0x140002f1e  mov     [rsp+0C8h+var_70], rdx
0x140002f23  mov     rcx, rdi
0x140002f26  mov     [rsp+0C8h+var_78], r11
0x140002f2b  lea     rdx, [rsp+0C8h+arg_30]
0x140002f33  mov     [rsp+0C8h+var_80], 2
0x140002f3c  cmovz   rcx, rax
0x140002f40  mov     rax, cs:pfnWppTraceMessage
0x140002f47  mov     [rsp+0C8h+var_88], r9
0x140002f4c  movzx   r9d, [rsp+0C8h+arg_18]
0x140002f55  mov     [rsp+0C8h+var_90], 4
0x140002f5e  mov     [rsp+0C8h+var_98], rdx
0x140002f63  mov     edx, 2Bh ; '+'
0x140002f68  mov     [rsp+0C8h+var_A0], r8
0x140002f6d  mov     r8, [rsp+0C8h+arg_20]
0x140002f75  mov     [rsp+0C8h+var_A8], rcx
0x140002f7a  mov     rcx, [r12+r10*8+18h]
0x140002f7f  call    _guard_dispatch_icall
0x140002f84  movzx   r9d, [rsp+0C8h+arg_18]
0x140002f8d  xor     r11d, r11d
0x140002f90  mov     rcx, [rsp+0C8h+arg_0]
0x140002f98  lea     r10, asc_140008A70; "\b"
0x140002f9f  test    rbx, rbx
0x140002fa2  jz      short loc_140002FB5
0x140002fa4  movzx   r14d, word ptr [rbx]
0x140002fa8  cmp     [rbx], r11w
0x140002fac  jz      short loc_140002FB2
0x140002fae  mov     r13, [rbx+8]
0x140002fb2  test    rbx, rbx
0x140002fb5  cmovz   rbx, r10
0x140002fb9  test    rdi, rdi
0x140002fbc  jz      short loc_140002FCE
0x140002fbe  inc     rbp
0x140002fc1  cmp     [rdi+rbp], r11b
0x140002fc5  jnz     short loc_140002FBE
0x140002fc7  lea     r15, [rbp+1]
0x140002fcb  test    rdi, rdi
0x140002fce  mov     r8d, [rsp+0C8h+arg_10]
0x140002fd6  lea     rax, aNull; "NULL"
0x140002fdd  movzx   edx, [rsp+0C8h+arg_8]
0x140002fe5  cmovz   rdi, rax
0x140002fe9  mov     [rsp+0C8h+var_50], r11
0x140002fee  lea     rax, [rsp+0C8h+arg_40]
0x140002ff6  mov     [rsp+0C8h+var_58], 4
0x140002fff  mov     [rsp+0C8h+var_60], rax
0x140003004  lea     rax, [rsp+0C8h+arg_30]
0x14000300c  mov     [rsp+0C8h+var_68], r14
0x140003011  mov     [rsp+0C8h+var_70], r13
0x140003016  mov     [rsp+0C8h+var_78], 2
0x14000301f  mov     [rsp+0C8h+var_80], rbx
0x140003024  mov     [rsp+0C8h+var_88], 4
0x14000302d  mov     [rsp+0C8h+var_90], rax
0x140003032  mov     [rsp+0C8h+var_98], r15
0x140003037  mov     [rsp+0C8h+var_A0], rdi
0x14000303c  mov     word ptr [rsp+0C8h+var_A8], r9w
0x140003042  mov     r9, [rsp+0C8h+arg_20]
0x14000304a  call    cs:__imp_WppAutoLogTrace
0x140003051  nop     dword ptr [rax+rax+00h]
0x140003056  add     rsp, 88h
0x14000305d  pop     r15
0x14000305f  pop     r14
0x140003061  pop     r13
0x140003063  pop     r12
0x140003065  pop     rdi
0x140003066  pop     rsi
0x140003067  pop     rbp
0x140003068  pop     rbx
0x140003069  retn
```
