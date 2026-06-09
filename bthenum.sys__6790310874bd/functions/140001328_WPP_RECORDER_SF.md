# WPP_RECORDER_SF_

- ea: `0x140001328`
- end: `0x1400013df`
- name: `WPP_RECORDER_SF_`
- size: `183`
- prototype: ``
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010d0`
- `0x140001bc0`
- `0x140001cd0`
- `0x140001de0`
- `0x140002330`
- `0x140002b64`
- `0x140002e4c`
- `0x140018a54`
- `0x140018b90`
- `0x140018d54`
- `0x140019058`
- `0x14001aaac`
- `0x14001b564`
- `0x14001bda0`
- `0x14001bfd0`
- `0x14001ca00`
- `0x14001cf90`
- `0x14001d7d8`
- `0x14001de14`
- `0x14001e1e0`
- `0x14001ec38`
- `0x140020078`

## callees

- `0x140001328`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400013c2`
- `WppRecorder!WppAutoLogTrace` at `0x1400013c2`

## pseudocode

```c

```

## disassembly

```asm
0x140001328  mov     [rsp+arg_0], rbx
0x14000132d  mov     [rsp+arg_8], rsi
0x140001332  push    rdi
0x140001333  sub     rsp, 30h
0x140001337  mov     edi, r8d
0x14000133a  mov     rsi, rcx
0x14000133d  mov     r11d, r8d
0x140001340  shr     r11, 10h
0x140001344  movzx   ebx, r9w
0x140001348  lea     r10d, [rdi-1]
0x14000134c  mov     edx, r10d
0x14000134f  and     r10d, 1Fh
0x140001353  shr     rdx, 5
0x140001357  lea     rax, [r11+r11*4]
0x14000135b  and     edx, 7FFh
0x140001361  lea     rax, [rdx+rax*4]
0x140001365  mov     edx, r10d
0x140001368  mov     r10, cs:WPP_GLOBAL_Control
0x14000136f  mov     eax, [r10+rax*4+2Ch]
0x140001374  bt      eax, edx
0x140001377  jnb     short loc_1400013A7
0x140001379  mov     rax, cs:pfnWppTraceMessage
0x140001380  lea     rcx, [r11+r11*4]
0x140001384  mov     r8, [rsp+38h+arg_20]
0x140001389  add     rcx, rcx
0x14000138c  mov     r9d, ebx
0x14000138f  mov     [rsp+38h+var_18], 0
0x140001398  mov     edx, 2Bh ; '+'
0x14000139d  mov     rcx, [r10+rcx*8+18h]
0x1400013a2  call    _guard_dispatch_icall
0x1400013a7  mov     r9, [rsp+38h+arg_20]
0x1400013ac  mov     r8d, edi
0x1400013af  mov     [rsp+38h+var_10], 0
0x1400013b8  xor     edx, edx
0x1400013ba  mov     rcx, rsi
0x1400013bd  mov     word ptr [rsp+38h+var_18], bx
0x1400013c2  call    cs:__imp_WppAutoLogTrace
0x1400013c9  nop     dword ptr [rax+rax+00h]
0x1400013ce  mov     rbx, [rsp+38h+arg_0]
0x1400013d3  mov     rsi, [rsp+38h+arg_8]
0x1400013d8  add     rsp, 30h
0x1400013dc  pop     rdi
0x1400013dd  retn
```
