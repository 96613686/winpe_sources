# WPP_RECORDER_AND_TRACE_SF_qdd

- ea: `0x14000700c`
- end: `0x1400070f4`
- name: `WPP_RECORDER_AND_TRACE_SF_qdd`
- size: `232`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b3c`
- `0x140006104`
- `0x140019f30`

## callees

- `0x14000700c`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400070d7`
- `WppRecorder!WppAutoLogTrace` at `0x1400070d7`

## pseudocode

```c

```

## disassembly

```asm
0x14000700c  mov     r11, rsp
0x14000700f  mov     [r11+8], rbx
0x140007013  mov     [r11+10h], rsi
0x140007017  push    rdi
0x140007018  sub     rsp, 60h
0x14000701c  movzx   ebx, [rsp+68h+arg_30]
0x140007024  mov     rdi, r9
0x140007027  mov     esi, 4
0x14000702c  test    dl, dl
0x14000702e  jz      short loc_14000707A
0x140007030  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140007037  lea     rdx, [r11+58h]
0x14000703b  mov     r8, [rsp+68h+arg_38]
0x140007043  mov     r9d, ebx
0x140007046  mov     qword ptr [r11-18h], 0
0x14000704e  mov     [r11-20h], rsi
0x140007052  mov     [r11-28h], rdx
0x140007056  lea     rdx, [r11+50h]
0x14000705a  mov     [r11-30h], rsi
0x14000705e  mov     [r11-38h], rdx
0x140007062  lea     rdx, [r11+48h]
0x140007066  mov     qword ptr [r11-40h], 8
0x14000706e  mov     [r11-48h], rdx
0x140007072  lea     edx, [rsi+27h]
0x140007075  call    _guard_dispatch_icall
0x14000707a  mov     r9, [rsp+68h+arg_38]
0x140007082  lea     rax, [rsp+68h+arg_50]
0x14000708a  mov     r8d, [rsp+68h+arg_28]
0x140007092  mov     edx, esi
0x140007094  mov     [rsp+68h+var_10], 0
0x14000709d  mov     rcx, rdi
0x1400070a0  mov     [rsp+68h+var_18], rsi
0x1400070a5  mov     [rsp+68h+var_20], rax
0x1400070aa  lea     rax, [rsp+68h+arg_48]
0x1400070b2  mov     [rsp+68h+var_28], rsi
0x1400070b7  mov     [rsp+68h+var_30], rax
0x1400070bc  lea     rax, [rsp+68h+arg_40]
0x1400070c4  mov     [rsp+68h+var_38], 8
0x1400070cd  mov     [rsp+68h+var_40], rax
0x1400070d2  mov     [rsp+68h+var_48], bx
0x1400070d7  call    cs:__imp_WppAutoLogTrace
0x1400070de  nop     dword ptr [rax+rax+00h]
0x1400070e3  mov     rbx, [rsp+68h+arg_0]
0x1400070e8  mov     rsi, [rsp+68h+arg_8]
0x1400070ed  add     rsp, 60h
0x1400070f1  pop     rdi
0x1400070f2  retn
```
