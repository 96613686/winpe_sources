# WPP_RECORDER_SF_

- ea: `0x14000c60c`
- end: `0x14000c6c7`
- name: `WPP_RECORDER_SF_`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c280`
- `0x14000c314`
- `0x14001bd90`

## callees

- `0x14000c60c`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000c6aa`
- `WppRecorder!WppAutoLogTrace` at `0x14000c6aa`

## pseudocode

```c

```

## disassembly

```asm
0x14000c60c  mov     [rsp+arg_0], rbx
0x14000c611  mov     [rsp+arg_8], rsi
0x14000c616  push    rdi
0x14000c617  sub     rsp, 30h
0x14000c61b  mov     edi, r8d
0x14000c61e  mov     rsi, rcx
0x14000c621  mov     r11d, r8d
0x14000c624  shr     r11, 10h
0x14000c628  movzx   ebx, r9w
0x14000c62c  lea     r10d, [rdi-1]
0x14000c630  mov     edx, r10d
0x14000c633  and     r10d, 1Fh
0x14000c637  shr     rdx, 5
0x14000c63b  lea     rax, [r11+r11*4]
0x14000c63f  and     edx, 7FFh
0x14000c645  lea     rax, [rdx+rax*4]
0x14000c649  mov     edx, r10d
0x14000c64c  mov     r10, cs:WPP_GLOBAL_Control
0x14000c653  mov     eax, [r10+rax*4+2Ch]
0x14000c658  bt      eax, edx
0x14000c65b  jnb     short loc_14000C68D
0x14000c65d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000c664  lea     rcx, [r11+r11*4]
0x14000c668  add     rcx, rcx
0x14000c66b  mov     [rsp+38h+var_18], 0
0x14000c674  mov     r9d, ebx
0x14000c677  lea     r8, WPP_a133576297673b8c8ce34a9383ada487_Traceguids
0x14000c67e  mov     edx, 2Bh ; '+'
0x14000c683  mov     rcx, [r10+rcx*8+18h]
0x14000c688  call    _guard_dispatch_icall
0x14000c68d  mov     [rsp+38h+var_10], 0
0x14000c696  lea     r9, WPP_a133576297673b8c8ce34a9383ada487_Traceguids
0x14000c69d  mov     r8d, edi
0x14000c6a0  mov     word ptr [rsp+38h+var_18], bx
0x14000c6a5  xor     edx, edx
0x14000c6a7  mov     rcx, rsi
0x14000c6aa  call    cs:__imp_WppAutoLogTrace
0x14000c6b1  nop     dword ptr [rax+rax+00h]
0x14000c6b6  mov     rbx, [rsp+38h+arg_0]
0x14000c6bb  mov     rsi, [rsp+38h+arg_8]
0x14000c6c0  add     rsp, 30h
0x14000c6c4  pop     rdi
0x14000c6c5  retn
```
