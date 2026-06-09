# WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP

- ea: `0x140004810`
- end: `0x1400048c1`
- name: `WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP`
- size: `177`
- prototype: ``
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x140002630`
- `0x140002b80`
- `0x1400030f0`
- `0x1400031d0`
- `0x140003a80`
- `0x140005dcc`
- `0x140005f38`
- `0x140006108`
- `0x140006c94`
- `0x140008be0`
- `0x140009004`
- `0x140009d70`
- `0x14000a914`
- `0x14000aac0`
- `0x14000b270`
- `0x14000b580`
- `0x14000c5b0`
- `0x14000d608`
- `0x14000d76c`
- `0x14000dcf0`
- `0x14000df64`
- `0x14000e87c`
- `0x14000ecc4`
- `0x14000f500`
- `0x14000f700`
- `0x14000fa40`
- `0x140010878`
- `0x140011b70`
- `0x140011ea8`
- `0x140012100`
- `0x1400123a0`
- `0x140013148`
- `0x1400136b0`
- `0x1400139e8`
- `0x140013ae0`
- `0x140013df8`
- `0x1400285d4`
- `0x140028b28`
- `0x140029824`
- `0x14002bb34`
- `0x14002bedc`
- `0x14002bfac`
- `0x14002c77c`

## callees

- `0x140004810`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400048a4`
- `WppRecorder!WppAutoLogTrace` at `0x1400048a4`

## pseudocode

```c

```

## disassembly

```asm
0x140004810  mov     r11, rsp
0x140004813  mov     [r11+8], rbx
0x140004817  mov     [r11+10h], rsi
0x14000481b  push    rdi
0x14000481c  sub     rsp, 40h
0x140004820  movzx   ebx, [rsp+48h+arg_30]
0x140004828  mov     rsi, r9
0x14000482b  mov     dil, r8b
0x14000482e  test    dl, dl
0x140004830  jz      short loc_140004866
0x140004832  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140004839  lea     rdx, [r11+48h]
0x14000483d  mov     r8, [rsp+48h+arg_38]
0x140004845  mov     r9d, ebx
0x140004848  mov     qword ptr [r11-18h], 0
0x140004850  mov     qword ptr [r11-20h], 4
0x140004858  mov     [r11-28h], rdx
0x14000485c  mov     edx, 2Bh ; '+'
0x140004861  call    _guard_dispatch_icall
0x140004866  test    dil, dil
0x140004869  jz      short loc_1400048B0
0x14000486b  mov     r9, [rsp+48h+arg_38]
0x140004873  lea     rax, [rsp+48h+arg_40]
0x14000487b  mov     r8d, [rsp+48h+arg_28]
0x140004880  mov     rcx, rsi
0x140004883  movzx   edx, [rsp+48h+arg_20]
0x140004888  mov     [rsp+48h+var_10], 0
0x140004891  mov     [rsp+48h+var_18], 4
0x14000489a  mov     [rsp+48h+var_20], rax
0x14000489f  mov     [rsp+48h+var_28], bx
0x1400048a4  call    cs:__imp_WppAutoLogTrace
0x1400048ab  nop     dword ptr [rax+rax+00h]
0x1400048b0  mov     rbx, [rsp+48h+arg_0]
0x1400048b5  mov     rsi, [rsp+48h+arg_8]
0x1400048ba  add     rsp, 40h
0x1400048be  pop     rdi
0x1400048bf  retn
```
