# WPP_RECORDER_AND_TRACE_SF_ll

- ea: `0x1400048c8`
- end: `0x140004986`
- name: `WPP_RECORDER_AND_TRACE_SF_ll`
- size: `190`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003000`
- `0x14001117c`
- `0x140028dd0`

## callees

- `0x1400048c8`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004970`
- `WppRecorder!WppAutoLogTrace` at `0x140004970`

## pseudocode

```c

```

## disassembly

```asm
0x1400048c8  mov     r11, rsp
0x1400048cb  push    rbx
0x1400048cc  push    rbp
0x1400048cd  push    rsi
0x1400048ce  push    rdi
0x1400048cf  sub     rsp, 58h
0x1400048d3  movzx   ebx, [rsp+78h+arg_30]
0x1400048db  mov     rsi, r9
0x1400048de  mov     dil, r8b
0x1400048e1  mov     ebp, 4
0x1400048e6  test    dl, dl
0x1400048e8  jz      short loc_140004924
0x1400048ea  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400048f1  lea     rdx, [r11+50h]
0x1400048f5  mov     r8, [rsp+78h+arg_38]
0x1400048fd  mov     r9d, ebx
0x140004900  mov     qword ptr [r11-38h], 0
0x140004908  mov     [r11-40h], rbp
0x14000490c  mov     [r11-48h], rdx
0x140004910  lea     rdx, [r11+48h]
0x140004914  mov     [r11-50h], rbp
0x140004918  mov     [r11-58h], rdx
0x14000491c  lea     edx, [rbp+27h]
0x14000491f  call    _guard_dispatch_icall
0x140004924  test    dil, dil
0x140004927  jz      short loc_14000497C
0x140004929  mov     r9, [rsp+78h+arg_38]
0x140004931  lea     rax, [rsp+78h+arg_48]
0x140004939  mov     r8d, [rsp+78h+arg_28]
0x140004941  mov     edx, ebp
0x140004943  mov     [rsp+78h+var_30], 0
0x14000494c  mov     rcx, rsi
0x14000494f  mov     [rsp+78h+var_38], rbp
0x140004954  mov     [rsp+78h+var_40], rax
0x140004959  lea     rax, [rsp+78h+arg_40]
0x140004961  mov     [rsp+78h+var_48], rbp
0x140004966  mov     [rsp+78h+var_50], rax
0x14000496b  mov     [rsp+78h+var_58], bx
0x140004970  call    cs:__imp_WppAutoLogTrace
0x140004977  nop     dword ptr [rax+rax+00h]
0x14000497c  add     rsp, 58h
0x140004980  pop     rdi
0x140004981  pop     rsi
0x140004982  pop     rbp
0x140004983  pop     rbx
0x140004984  retn
```
