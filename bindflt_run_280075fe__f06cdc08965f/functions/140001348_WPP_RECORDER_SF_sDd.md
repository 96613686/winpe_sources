# WPP_RECORDER_SF_sDd

- ea: `0x140001348`
- end: `0x1400014ee`
- name: `WPP_RECORDER_SF_sDd`
- size: `422`
- prototype: ``
- caller_count: `69`
- callee_count: `2`
- tags: ``

## callers

- `0x140001010`
- `0x140001740`
- `0x140001dd0`
- `0x140001fd0`
- `0x1400060f0`
- `0x14000f008`
- `0x14000f7c0`
- `0x14000f930`
- `0x14000ff58`
- `0x140010384`
- `0x140010898`
- `0x140010d64`
- `0x140011264`
- `0x140011590`
- `0x140011eb0`
- `0x1400127a0`
- `0x140012c60`
- `0x140013610`
- `0x140013780`
- `0x140013864`
- `0x140014178`
- `0x140014324`
- `0x140014b20`
- `0x140014e9c`
- `0x1400152f0`
- `0x1400154b0`
- `0x1400157a0`
- `0x140017360`
- `0x140017920`
- `0x140017bf0`
- `0x140017f00`
- `0x1400194b0`
- `0x140019c44`
- `0x14001ad80`
- `0x14001b280`
- `0x14001c904`
- `0x14001caf8`
- `0x14001cd84`
- `0x14001d194`
- `0x14001d2c0`
- `0x14001d974`
- `0x14001e5c8`
- `0x14001e6fc`
- `0x14001ea74`
- `0x14001efcc`
- `0x14001f40c`
- `0x14001f71c`
- `0x14001fb68`
- `0x14001fcf0`
- `0x14002001c`

## callees

- `0x140001348`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001421`
- `WppRecorder!WppAutoLogTrace` at `0x140001421`

## pseudocode

```c

```

## disassembly

```asm
0x140001348  mov     [rsp+arg_0], rcx
0x14000134d  push    rbx
0x14000134e  push    rbp
0x14000134f  push    rsi
0x140001350  push    rdi
0x140001351  push    r12
0x140001353  push    r13
0x140001355  push    r14
0x140001357  push    r15
0x140001359  sub     rsp, 68h
0x14000135d  mov     r14, cs:WPP_GLOBAL_Control
0x140001364  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140001368  mov     r13d, r8d
0x14000136b  mov     esi, r8d
0x14000136e  lea     r8, aNull; "NULL"
0x140001375  shr     rsi, 10h
0x140001379  movzx   r15d, dl
0x14000137d  lea     ebp, [rdi+6]
0x140001380  lea     ebx, [r13-1]
0x140001384  movzx   r12d, r9w
0x140001388  mov     r10d, ebx
0x14000138b  lea     r9d, [rdi+5]
0x14000138f  shr     r10, 5
0x140001393  lea     rax, [rsi+rsi*4]
0x140001397  and     ebx, 1Fh
0x14000139a  and     r10d, 7FFh
0x1400013a1  mov     edx, ebx
0x1400013a3  mov     rbx, [rsp+0A8h+arg_28]
0x1400013ab  lea     r11, [r10+rax*4]
0x1400013af  mov     eax, [r14+r11*4+2Ch]
0x1400013b4  bt      eax, edx
0x1400013b7  jb      loc_14000143F
0x1400013bd  test    rbx, rbx
0x1400013c0  jz      short loc_1400013D2
0x1400013c2  inc     rdi
0x1400013c5  cmp     byte ptr [rbx+rdi], 0
0x1400013c9  jnz     short loc_1400013C2
0x1400013cb  lea     rbp, [rdi+1]
0x1400013cf  test    rbx, rbx
0x1400013d2  mov     [rsp+0A8h+var_50], 0
0x1400013db  lea     rax, [rsp+0A8h+arg_38]
0x1400013e3  mov     [rsp+0A8h+var_58], r9
0x1400013e8  cmovz   rbx, r8
0x1400013ec  mov     [rsp+0A8h+var_60], rax
0x1400013f1  mov     r8d, r13d
0x1400013f4  mov     [rsp+0A8h+var_68], r9
0x1400013f9  lea     rax, [rsp+0A8h+arg_30]
0x140001401  mov     r9, [rsp+0A8h+arg_20]
0x140001409  mov     edx, r15d
0x14000140c  mov     [rsp+0A8h+var_70], rax
0x140001411  mov     [rsp+0A8h+var_78], rbp
0x140001416  mov     [rsp+0A8h+var_80], rbx
0x14000141b  mov     word ptr [rsp+0A8h+var_88], r12w
0x140001421  call    cs:__imp_WppAutoLogTrace
0x140001428  nop     dword ptr [rax+rax+00h]
0x14000142d  add     rsp, 68h
0x140001431  pop     r15
0x140001433  pop     r14
0x140001435  pop     r13
0x140001437  pop     r12
0x140001439  pop     rdi
0x14000143a  pop     rsi
0x14000143b  pop     rbp
0x14000143c  pop     rbx
0x14000143d  retn
0x14000143f  lea     r10, [rsi+rsi*4]
0x140001443  add     r10, r10
0x140001446  cmp     [r14+r10*8+29h], r15b
0x14000144b  jb      loc_1400013BD
0x140001451  test    rbx, rbx
0x140001454  jz      loc_1400014E6
0x14000145a  mov     rax, rdi
0x14000145d  inc     rax
0x140001460  cmp     byte ptr [rbx+rax], 0
0x140001464  jnz     short loc_14000145D
0x140001466  lea     rdx, [rax+1]
0x14000146a  mov     rax, cs:pfnWppTraceMessage
0x140001471  test    rbx, rbx
0x140001474  mov     [rsp+0A8h+var_58], 0
0x14000147d  mov     rcx, rbx
0x140001480  mov     [rsp+0A8h+var_60], r9
0x140001485  cmovz   rcx, r8
0x140001489  lea     r8, [rsp+0A8h+arg_38]
0x140001491  mov     [rsp+0A8h+var_68], r8
0x140001496  lea     r8, [rsp+0A8h+arg_30]
0x14000149e  mov     [rsp+0A8h+var_70], r9
0x1400014a3  mov     r9d, r12d
0x1400014a6  mov     [rsp+0A8h+var_78], r8
0x1400014ab  mov     r8, [rsp+0A8h+arg_20]
0x1400014b3  mov     [rsp+0A8h+var_80], rdx
0x1400014b8  mov     edx, 2Bh ; '+'
0x1400014bd  mov     [rsp+0A8h+var_88], rcx
0x1400014c2  mov     rcx, [r14+r10*8+18h]
0x1400014c7  call    _guard_dispatch_icall
0x1400014cc  mov     rcx, [rsp+0A8h+arg_0]
0x1400014d4  lea     r8, aNull; "NULL"
0x1400014db  mov     r9d, 4
0x1400014e1  jmp     loc_1400013BD
0x1400014e6  mov     rdx, rbp
0x1400014e9  jmp     loc_14000146A
```
