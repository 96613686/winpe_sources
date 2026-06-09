# WPP_RECORDER_AND_TRACE_SF__guid_

- ea: `0x1400044dc`
- end: `0x140004584`
- name: `WPP_RECORDER_AND_TRACE_SF__guid_`
- size: `168`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140007dc0`
- `0x1400281d0`
- `0x1400285d4`

## callees

- `0x1400044dc`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000456e`
- `WppRecorder!WppAutoLogTrace` at `0x14000456e`

## pseudocode

```c

```

## disassembly

```asm
0x1400044dc  push    rbx
0x1400044de  push    rbp
0x1400044df  push    rsi
0x1400044e0  push    rdi
0x1400044e1  sub     rsp, 48h
0x1400044e5  mov     rbx, [rsp+68h+arg_40]
0x1400044ed  mov     rbp, r9
0x1400044f0  movzx   edi, [rsp+68h+arg_30]
0x1400044f8  mov     sil, r8b
0x1400044fb  test    dl, dl
0x1400044fd  jz      short loc_140004532
0x1400044ff  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140004506  mov     r9d, edi
0x140004509  mov     r8, [rsp+68h+arg_38]
0x140004511  mov     edx, 2Bh ; '+'
0x140004516  mov     [rsp+68h+var_38], 0
0x14000451f  mov     [rsp+68h+var_40], 10h
0x140004528  mov     [rsp+68h+var_48], rbx
0x14000452d  call    _guard_dispatch_icall
0x140004532  test    sil, sil
0x140004535  jz      short loc_14000457A
0x140004537  mov     r9, [rsp+68h+arg_38]
0x14000453f  mov     rcx, rbp
0x140004542  mov     r8d, [rsp+68h+arg_28]
0x14000454a  movzx   edx, [rsp+68h+arg_20]
0x140004552  mov     [rsp+68h+var_30], 0
0x14000455b  mov     [rsp+68h+var_38], 10h
0x140004564  mov     [rsp+68h+var_40], rbx
0x140004569  mov     word ptr [rsp+68h+var_48], di
0x14000456e  call    cs:__imp_WppAutoLogTrace
0x140004575  nop     dword ptr [rax+rax+00h]
0x14000457a  add     rsp, 48h
0x14000457e  pop     rdi
0x14000457f  pop     rsi
0x140004580  pop     rbp
0x140004581  pop     rbx
0x140004582  retn
```
