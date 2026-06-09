# WPP_RECORDER_AND_TRACE_SF_dd

- ea: `0x140006db0`
- end: `0x140006e78`
- name: `WPP_RECORDER_AND_TRACE_SF_dd`
- size: `200`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400046b4`
- `0x140005f60`
- `0x140006104`
- `0x1400081b0`
- `0x14001a4a8`
- `0x14001b840`

## callees

- `0x140006db0`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006e5b`
- `WppRecorder!WppAutoLogTrace` at `0x140006e5b`

## pseudocode

```c

```

## disassembly

```asm
0x140006db0  mov     r11, rsp
0x140006db3  mov     [r11+8], rbx
0x140006db7  mov     [r11+10h], rsi
0x140006dbb  push    rdi
0x140006dbc  sub     rsp, 50h
0x140006dc0  movzx   ebx, [rsp+58h+arg_30]
0x140006dc8  mov     rdi, r9
0x140006dcb  mov     esi, 4
0x140006dd0  test    dl, dl
0x140006dd2  jz      short loc_140006E0E
0x140006dd4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140006ddb  lea     rdx, [r11+50h]
0x140006ddf  mov     r8, [rsp+58h+arg_38]
0x140006de7  mov     r9d, ebx
0x140006dea  mov     qword ptr [r11-18h], 0
0x140006df2  mov     [r11-20h], rsi
0x140006df6  mov     [r11-28h], rdx
0x140006dfa  lea     rdx, [r11+48h]
0x140006dfe  mov     [r11-30h], rsi
0x140006e02  mov     [r11-38h], rdx
0x140006e06  lea     edx, [rsi+27h]
0x140006e09  call    _guard_dispatch_icall
0x140006e0e  mov     r9, [rsp+58h+arg_38]
0x140006e16  lea     rax, [rsp+58h+arg_48]
0x140006e1e  mov     r8d, [rsp+58h+arg_28]
0x140006e26  mov     rcx, rdi
0x140006e29  movzx   edx, [rsp+58h+arg_20]
0x140006e31  mov     [rsp+58h+var_10], 0
0x140006e3a  mov     [rsp+58h+var_18], rsi
0x140006e3f  mov     [rsp+58h+var_20], rax
0x140006e44  lea     rax, [rsp+58h+arg_40]
0x140006e4c  mov     [rsp+58h+var_28], rsi
0x140006e51  mov     [rsp+58h+var_30], rax
0x140006e56  mov     [rsp+58h+var_38], bx
0x140006e5b  call    cs:__imp_WppAutoLogTrace
0x140006e62  nop     dword ptr [rax+rax+00h]
0x140006e67  mov     rbx, [rsp+58h+arg_0]
0x140006e6c  mov     rsi, [rsp+58h+arg_8]
0x140006e71  add     rsp, 50h
0x140006e75  pop     rdi
0x140006e76  retn
```
