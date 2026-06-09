# WPP_RECORDER_SF_sDdd

- ea: `0x140003140`
- end: `0x1400032fe`
- name: `WPP_RECORDER_SF_sDdd`
- size: `446`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fa74`
- `0x140010384`
- `0x140010d64`
- `0x14001bbb4`
- `0x14001d974`
- `0x14001ea74`
- `0x140021d1c`
- `0x140022edc`
- `0x140024294`
- `0x140024e50`
- `0x140025c70`

## callees

- `0x140003140`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400032e0`
- `WppRecorder!WppAutoLogTrace` at `0x1400032e0`

## pseudocode

```c

```

## disassembly

```asm
0x140003140  mov     [rsp+arg_0], rcx
0x140003145  push    rbx
0x140003146  push    rbp
0x140003147  push    rsi
0x140003148  push    rdi
0x140003149  push    r12
0x14000314b  push    r13
0x14000314d  push    r14
0x14000314f  push    r15
0x140003151  sub     rsp, 78h
0x140003155  mov     r14, cs:WPP_GLOBAL_Control
0x14000315c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140003160  mov     r13d, r8d
0x140003163  mov     esi, r8d
0x140003166  lea     r8, aNull; "NULL"
0x14000316d  shr     rsi, 10h
0x140003171  movzx   r15d, dl
0x140003175  lea     ebp, [rdi+6]
0x140003178  lea     ebx, [r13-1]
0x14000317c  movzx   r12d, r9w
0x140003180  mov     r10d, ebx
0x140003183  lea     r9d, [rdi+5]
0x140003187  shr     r10, 5
0x14000318b  lea     rax, [rsi+rsi*4]
0x14000318f  and     ebx, 1Fh
0x140003192  and     r10d, 7FFh
0x140003199  mov     edx, ebx
0x14000319b  mov     rbx, [rsp+0B8h+arg_28]
0x1400031a3  lea     r11, [r10+rax*4]
0x1400031a7  mov     eax, [r14+r11*4+2Ch]
0x1400031ac  bt      eax, edx
0x1400031af  jnb     loc_14000326A
0x1400031b5  lea     r10, [rsi+rsi*4]
0x1400031b9  add     r10, r10
0x1400031bc  cmp     [r14+r10*8+29h], r15b
0x1400031c1  jb      loc_14000326A
0x1400031c7  test    rbx, rbx
0x1400031ca  jz      short loc_1400031DE
0x1400031cc  mov     rax, rdi
0x1400031cf  inc     rax
0x1400031d2  cmp     byte ptr [rbx+rax], 0
0x1400031d6  jnz     short loc_1400031CF
0x1400031d8  lea     rdx, [rax+1]
0x1400031dc  jmp     short loc_1400031E1
0x1400031de  mov     rdx, rbp
0x1400031e1  mov     rax, cs:pfnWppTraceMessage
0x1400031e8  test    rbx, rbx
0x1400031eb  mov     [rsp+0B8h+var_58], 0
0x1400031f4  mov     rcx, rbx
0x1400031f7  mov     [rsp+0B8h+var_60], r9
0x1400031fc  cmovz   rcx, r8
0x140003200  lea     r8, [rsp+0B8h+arg_40]
0x140003208  mov     [rsp+0B8h+var_68], r8
0x14000320d  lea     r8, [rsp+0B8h+arg_38]
0x140003215  mov     [rsp+0B8h+var_70], r9
0x14000321a  mov     [rsp+0B8h+var_78], r8
0x14000321f  lea     r8, [rsp+0B8h+arg_30]
0x140003227  mov     [rsp+0B8h+var_80], r9
0x14000322c  mov     r9d, r12d
0x14000322f  mov     [rsp+0B8h+var_88], r8
0x140003234  mov     r8, [rsp+0B8h+arg_20]
0x14000323c  mov     [rsp+0B8h+var_90], rdx
0x140003241  mov     edx, 2Bh ; '+'
0x140003246  mov     [rsp+0B8h+var_98], rcx
0x14000324b  mov     rcx, [r14+r10*8+18h]
0x140003250  call    _guard_dispatch_icall
0x140003255  mov     rcx, [rsp+0B8h+arg_0]
0x14000325d  lea     r8, aNull; "NULL"
0x140003264  mov     r9d, 4
0x14000326a  test    rbx, rbx
0x14000326d  jz      short loc_14000327F
0x14000326f  inc     rdi
0x140003272  cmp     byte ptr [rbx+rdi], 0
0x140003276  jnz     short loc_14000326F
0x140003278  lea     rbp, [rdi+1]
0x14000327c  test    rbx, rbx
0x14000327f  mov     [rsp+0B8h+var_50], 0
0x140003288  lea     rax, [rsp+0B8h+arg_40]
0x140003290  mov     [rsp+0B8h+var_58], r9
0x140003295  cmovz   rbx, r8
0x140003299  mov     [rsp+0B8h+var_60], rax
0x14000329e  mov     r8d, r13d
0x1400032a1  mov     [rsp+0B8h+var_68], r9
0x1400032a6  lea     rax, [rsp+0B8h+arg_38]
0x1400032ae  mov     [rsp+0B8h+var_70], rax
0x1400032b3  mov     edx, r15d
0x1400032b6  mov     [rsp+0B8h+var_78], r9
0x1400032bb  lea     rax, [rsp+0B8h+arg_30]
0x1400032c3  mov     r9, [rsp+0B8h+arg_20]
0x1400032cb  mov     [rsp+0B8h+var_80], rax
0x1400032d0  mov     [rsp+0B8h+var_88], rbp
0x1400032d5  mov     [rsp+0B8h+var_90], rbx
0x1400032da  mov     word ptr [rsp+0B8h+var_98], r12w
0x1400032e0  call    cs:__imp_WppAutoLogTrace
0x1400032e7  nop     dword ptr [rax+rax+00h]
0x1400032ec  add     rsp, 78h
0x1400032f0  pop     r15
0x1400032f2  pop     r14
0x1400032f4  pop     r13
0x1400032f6  pop     r12
0x1400032f8  pop     rdi
0x1400032f9  pop     rsi
0x1400032fa  pop     rbp
0x1400032fb  pop     rbx
0x1400032fc  retn
```
