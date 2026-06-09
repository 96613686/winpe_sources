# WPP_RECORDER_AND_TRACE_SF_sD

- ea: `0x14000d008`
- end: `0x14000d121`
- name: `WPP_RECORDER_AND_TRACE_SF_sD`
- size: `281`
- prototype: ``
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x140001658`
- `0x140001b3c`
- `0x140002288`
- `0x14000420c`
- `0x1400057b0`
- `0x140007990`
- `0x1400089d8`
- `0x1400092ec`
- `0x1400217a4`
- `0x140021f8c`
- `0x140023470`
- `0x140023d68`
- `0x140024184`
- `0x14002ba10`
- `0x14002c1f4`
- `0x14002d3c4`
- `0x14002f134`
- `0x14002f204`
- `0x14002f5f0`
- `0x14003005c`
- `0x1400306f8`
- `0x1400311b0`
- `0x140031780`
- `0x140031a00`
- `0x140032fd8`
- `0x1400333c4`
- `0x140033bd0`
- `0x140035f3c`
- `0x1400377c4`
- `0x140037b8c`
- `0x1400389ec`
- `0x140038b78`
- `0x14003b380`
- `0x14003d620`
- `0x14003e0d8`
- `0x14003ec0c`
- `0x14003f240`
- `0x140042eac`
- `0x14004437c`
- `0x140044508`
- `0x140044794`
- `0x140044af0`
- `0x140044cec`

## callees

- `0x140005cf4`
- `0x14000d008`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d107`
- `WppRecorder!WppAutoLogTrace` at `0x14000d107`

## pseudocode

```c

```

## disassembly

```asm
0x14000d008  push    rbx
0x14000d00a  push    rbp
0x14000d00b  push    rsi
0x14000d00c  push    rdi
0x14000d00d  push    r14
0x14000d00f  push    r15
0x14000d011  sub     rsp, 58h
0x14000d015  mov     rbx, [rsp+88h+arg_40]
0x14000d01d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000d021  movzx   r14d, [rsp+88h+arg_30]
0x14000d02a  mov     bpl, r8b
0x14000d02d  lea     r8, aNull; "NULL"
0x14000d034  mov     r15, r9
0x14000d037  lea     esi, [rdi+6]
0x14000d03a  test    dl, dl
0x14000d03c  jz      short loc_14000D09F
0x14000d03e  test    rbx, rbx
0x14000d041  jz      short loc_14000D054
0x14000d043  mov     rax, rdi
0x14000d046  inc     rax
0x14000d049  cmp     byte ptr [rbx+rax], 0
0x14000d04d  jnz     short loc_14000D046
0x14000d04f  inc     rax
0x14000d052  jmp     short loc_14000D057
0x14000d054  mov     rax, rsi
0x14000d057  mov     [rsp+88h+var_50], 0
0x14000d060  lea     rdx, [rsp+88h+arg_48]
0x14000d068  test    rbx, rbx
0x14000d06b  mov     [rsp+88h+var_58], 4
0x14000d074  mov     [rsp+88h+var_60], rdx
0x14000d079  mov     r9, rbx
0x14000d07c  cmovz   r9, r8
0x14000d080  movzx   ecx, cx
0x14000d083  mov     r8, [rsp+88h+arg_38]
0x14000d08b  mov     edx, r14d
0x14000d08e  mov     [rsp+88h+var_68], rax
0x14000d093  call    FastWppTraceMessage
0x14000d098  lea     r8, aNull; "NULL"
0x14000d09f  test    bpl, bpl
0x14000d0a2  jz      short loc_14000D113
0x14000d0a4  test    rbx, rbx
0x14000d0a7  jz      short loc_14000D0B9
0x14000d0a9  inc     rdi
0x14000d0ac  cmp     byte ptr [rbx+rdi], 0
0x14000d0b0  jnz     short loc_14000D0A9
0x14000d0b2  lea     rsi, [rdi+1]
0x14000d0b6  test    rbx, rbx
0x14000d0b9  mov     r9, [rsp+88h+arg_38]
0x14000d0c1  lea     rax, [rsp+88h+arg_48]
0x14000d0c9  movzx   edx, [rsp+88h+arg_20]
0x14000d0d1  cmovz   rbx, r8
0x14000d0d5  mov     r8d, [rsp+88h+arg_28]
0x14000d0dd  mov     rcx, r15
0x14000d0e0  mov     [rsp+88h+var_40], 0
0x14000d0e9  mov     [rsp+88h+var_48], 4
0x14000d0f2  mov     [rsp+88h+var_50], rax
0x14000d0f7  mov     [rsp+88h+var_58], rsi
0x14000d0fc  mov     [rsp+88h+var_60], rbx
0x14000d101  mov     word ptr [rsp+88h+var_68], r14w
0x14000d107  call    cs:__imp_WppAutoLogTrace
0x14000d10e  nop     dword ptr [rax+rax+00h]
0x14000d113  add     rsp, 58h
0x14000d117  pop     r15
0x14000d119  pop     r14
0x14000d11b  pop     rdi
0x14000d11c  pop     rsi
0x14000d11d  pop     rbp
0x14000d11e  pop     rbx
0x14000d11f  retn
```
