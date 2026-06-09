# WPP_RECORDER_AND_TRACE_SF_qD

- ea: `0x140001924`
- end: `0x1400019ed`
- name: `WPP_RECORDER_AND_TRACE_SF_qD`
- size: `201`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140017210`
- `0x140017858`
- `0x14001a6e8`
- `0x14001b73c`

## callees

- `0x140001924`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400019d5`
- `WppRecorder!WppAutoLogTrace` at `0x1400019d5`

## pseudocode

```c

```

## disassembly

```asm
0x140001924  mov     r11, rsp
0x140001927  mov     [r11+8], rbx
0x14000192b  push    rdi
0x14000192c  sub     rsp, 50h
0x140001930  movzx   ebx, [rsp+58h+arg_30]
0x140001938  mov     rdi, r9
0x14000193b  test    dl, dl
0x14000193d  jz      short loc_140001983
0x14000193f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140001946  lea     rdx, [r11+50h]
0x14000194a  mov     r8, [rsp+58h+arg_38]
0x140001952  mov     r9d, ebx
0x140001955  mov     qword ptr [r11-18h], 0
0x14000195d  mov     qword ptr [r11-20h], 4
0x140001965  mov     [r11-28h], rdx
0x140001969  lea     rdx, [r11+48h]
0x14000196d  mov     qword ptr [r11-30h], 8
0x140001975  mov     [r11-38h], rdx
0x140001979  mov     edx, 2Bh ; '+'
0x14000197e  call    _guard_dispatch_icall
0x140001983  mov     r9, [rsp+58h+arg_38]
0x14000198b  lea     rax, [rsp+58h+arg_48]
0x140001993  mov     r8d, [rsp+58h+arg_28]
0x14000199b  mov     edx, 4
0x1400019a0  mov     [rsp+58h+var_10], 0
0x1400019a9  mov     rcx, rdi
0x1400019ac  mov     [rsp+58h+var_18], 4
0x1400019b5  mov     [rsp+58h+var_20], rax
0x1400019ba  lea     rax, [rsp+58h+arg_40]
0x1400019c2  mov     [rsp+58h+var_28], 8
0x1400019cb  mov     [rsp+58h+var_30], rax
0x1400019d0  mov     [rsp+58h+var_38], bx
0x1400019d5  call    cs:__imp_WppAutoLogTrace
0x1400019dc  nop     dword ptr [rax+rax+00h]
0x1400019e1  mov     rbx, [rsp+58h+arg_0]
0x1400019e6  add     rsp, 50h
0x1400019ea  pop     rdi
0x1400019eb  retn
```
