# WPP_RECORDER_SF_sDD

- ea: `0x140002740`
- end: `0x1400028fd`
- name: `WPP_RECORDER_SF_sDD`
- size: `445`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140014ccc`
- `0x14001bbb4`
- `0x14001ea74`
- `0x140020ae0`
- `0x140021d1c`
- `0x140024384`
- `0x140024e40`
- `0x140025c60`

## callees

- `0x140002740`
- `0x140004c70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002831`
- `WppRecorder!WppAutoLogTrace` at `0x140002831`

## pseudocode

```c

```

## disassembly

```asm
0x140002740  mov     [rsp+arg_8], rbx
0x140002745  mov     [rsp+arg_10], rbp
0x14000274a  mov     [rsp+arg_0], rcx
0x14000274f  push    rsi
0x140002750  push    rdi
0x140002751  push    r12
0x140002753  push    r14
0x140002755  push    r15
0x140002757  sub     rsp, 60h
0x14000275b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002762  mov     esi, 5
0x140002767  mov     rdi, [rsp+88h+arg_28]
0x14000276f  mov     ebp, r8d
0x140002772  mov     r14d, r8d
0x140002775  lea     r8, aNull; "NULL"
0x14000277c  shr     r14, 10h
0x140002780  movzx   r15d, dl
0x140002784  lea     ebx, [rbp-1]
0x140002787  movzx   r12d, r9w
0x14000278b  mov     r10d, ebx
0x14000278e  and     ebx, 1Fh
0x140002791  shr     r10, 5
0x140002795  lea     rax, [r14+r14*4]
0x140002799  and     r10d, 7FFh
0x1400027a0  mov     edx, ebx
0x1400027a2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400027a9  lea     r11, [r10+rax*4]
0x1400027ad  mov     eax, [rcx+r11*4+2Ch]
0x1400027b2  bt      eax, edx
0x1400027b5  jb      loc_140002857
0x1400027bb  test    rdi, rdi
0x1400027be  jz      short loc_1400027D2
0x1400027c0  cmp     byte ptr [rdi+rbx+1], 0
0x1400027c5  lea     rbx, [rbx+1]
0x1400027c9  jnz     short loc_1400027C0
0x1400027cb  lea     rsi, [rbx+1]
0x1400027cf  test    rdi, rdi
0x1400027d2  mov     r9, [rsp+88h+arg_20]
0x1400027da  lea     rax, [rsp+88h+arg_38]
0x1400027e2  mov     rcx, [rsp+88h+arg_0]
0x1400027ea  cmovz   rdi, r8
0x1400027ee  mov     [rsp+88h+var_30], 0
0x1400027f7  mov     r8d, ebp
0x1400027fa  mov     [rsp+88h+var_38], 4
0x140002803  mov     edx, r15d
0x140002806  mov     [rsp+88h+var_40], rax
0x14000280b  lea     rax, [rsp+88h+arg_30]
0x140002813  mov     [rsp+88h+var_48], 4
0x14000281c  mov     [rsp+88h+var_50], rax
0x140002821  mov     [rsp+88h+var_58], rsi
0x140002826  mov     [rsp+88h+var_60], rdi
0x14000282b  mov     word ptr [rsp+88h+var_68], r12w
0x140002831  call    cs:__imp_WppAutoLogTrace
0x140002838  nop     dword ptr [rax+rax+00h]
0x14000283d  lea     r11, [rsp+88h+var_28]
0x140002842  mov     rbx, [r11+38h]
0x140002846  mov     rbp, [r11+40h]
0x14000284a  mov     rsp, r11
0x14000284d  pop     r15
0x14000284f  pop     r14
0x140002851  pop     r12
0x140002853  pop     rdi
0x140002854  pop     rsi
0x140002855  retn
0x140002857  lea     r10, [r14+r14*4]
0x14000285b  shl     r10, 4
0x14000285f  add     r10, rcx
0x140002862  cmp     [r10+29h], r15b
0x140002866  jb      loc_1400027BB
0x14000286c  test    rdi, rdi
0x14000286f  jz      short loc_140002885
0x140002871  mov     rax, rbx
0x140002874  cmp     byte ptr [rdi+rax+1], 0
0x140002879  lea     rax, [rax+1]
0x14000287d  jnz     short loc_140002874
0x14000287f  lea     rcx, [rax+1]
0x140002883  jmp     short loc_140002888
0x140002885  mov     rcx, rsi
0x140002888  mov     rax, cs:pfnWppTraceMessage
0x14000288f  test    rdi, rdi
0x140002892  mov     [rsp+88h+var_38], 0
0x14000289b  mov     rdx, rdi
0x14000289e  cmovz   rdx, r8
0x1400028a2  mov     [rsp+88h+var_40], 4
0x1400028ab  lea     r8, [rsp+88h+arg_38]
0x1400028b3  mov     r9d, r12d
0x1400028b6  mov     [rsp+88h+var_48], r8
0x1400028bb  lea     r8, [rsp+88h+arg_30]
0x1400028c3  mov     [rsp+88h+var_50], 4
0x1400028cc  mov     [rsp+88h+var_58], r8
0x1400028d1  mov     r8, [rsp+88h+arg_20]
0x1400028d9  mov     [rsp+88h+var_60], rcx
0x1400028de  mov     rcx, [r10+18h]
0x1400028e2  mov     [rsp+88h+var_68], rdx
0x1400028e7  mov     edx, 2Bh ; '+'
0x1400028ec  call    _guard_dispatch_icall
0x1400028f1  lea     r8, aNull; "NULL"
0x1400028f8  jmp     loc_1400027BB
```
