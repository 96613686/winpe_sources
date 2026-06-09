# WPP_RECORDER_AND_TRACE_SF_D

- ea: `0x1400146bc`
- end: `0x14001476c`
- name: `WPP_RECORDER_AND_TRACE_SF_D`
- size: `176`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400016d4`
- `0x14000e87c`
- `0x1400100cc`
- `0x140010878`
- `0x14002bb34`
- `0x14002c1a4`

## callees

- `0x1400146bc`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14001474f`
- `WppRecorder!WppAutoLogTrace` at `0x14001474f`

## pseudocode

```c

```

## disassembly

```asm
0x1400146bc  mov     r11, rsp
0x1400146bf  mov     [r11+8], rbx
0x1400146c3  mov     [r11+10h], rsi
0x1400146c7  push    rdi
0x1400146c8  sub     rsp, 40h
0x1400146cc  movzx   ebx, [rsp+48h+arg_30]
0x1400146d4  mov     rsi, r9
0x1400146d7  mov     dil, r8b
0x1400146da  test    dl, dl
0x1400146dc  jz      short loc_140014711
0x1400146de  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400146e5  lea     rdx, [r11+48h]
0x1400146e9  mov     qword ptr [r11-18h], 0
0x1400146f1  lea     r8, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x1400146f8  mov     qword ptr [r11-20h], 4
0x140014700  mov     r9d, ebx
0x140014703  mov     [r11-28h], rdx
0x140014707  mov     edx, 2Bh ; '+'
0x14001470c  call    _guard_dispatch_icall
0x140014711  test    dil, dil
0x140014714  jz      short loc_14001475B
0x140014716  movzx   edx, [rsp+48h+arg_20]
0x14001471b  lea     rax, [rsp+48h+arg_40]
0x140014723  mov     [rsp+48h+var_10], 0
0x14001472c  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014733  mov     [rsp+48h+var_18], 4
0x14001473c  mov     r8d, 5
0x140014742  mov     [rsp+48h+var_20], rax
0x140014747  mov     rcx, rsi
0x14001474a  mov     [rsp+48h+var_28], bx
0x14001474f  call    cs:__imp_WppAutoLogTrace
0x140014756  nop     dword ptr [rax+rax+00h]
0x14001475b  mov     rbx, [rsp+48h+arg_0]
0x140014760  mov     rsi, [rsp+48h+arg_8]
0x140014765  add     rsp, 40h
0x140014769  pop     rdi
0x14001476a  retn
```
