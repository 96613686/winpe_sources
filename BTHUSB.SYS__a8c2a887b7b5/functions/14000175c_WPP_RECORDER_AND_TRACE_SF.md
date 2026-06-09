# WPP_RECORDER_AND_TRACE_SF_

- ea: `0x14000175c`
- end: `0x1400017cc`
- name: `WPP_RECORDER_AND_TRACE_SF_`
- size: `112`
- prototype: ``
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140004088`
- `0x1400046b4`
- `0x140004840`
- `0x140004fc8`
- `0x140005180`
- `0x140006104`
- `0x1400077c4`
- `0x1400078a0`
- `0x140007980`
- `0x140007da8`
- `0x140007ea0`
- `0x140007f8c`
- `0x1400085b4`
- `0x140009000`
- `0x140009740`
- `0x140009800`
- `0x1400098bc`
- `0x14000ac54`
- `0x14000ae54`
- `0x140017008`
- `0x140017210`
- `0x14001743c`
- `0x140018b90`
- `0x140019b00`
- `0x140019ea0`
- `0x14001a25c`
- `0x14001a4a8`
- `0x14001a6e8`
- `0x14001accc`
- `0x14001b840`
- `0x14001d03c`

## callees

- `0x14000175c`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400017b4`
- `WppRecorder!WppAutoLogTrace` at `0x1400017b4`

## pseudocode

```c

```

## disassembly

```asm
0x14000175c  mov     [rsp+arg_0], rbx
0x140001761  push    rdi
0x140001762  sub     rsp, 30h
0x140001766  movzx   ebx, [rsp+38h+arg_30]
0x14000176b  mov     rdi, r9
0x14000176e  test    dl, dl
0x140001770  jz      short loc_140001794
0x140001772  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140001779  mov     r9d, ebx
0x14000177c  mov     r8, [rsp+38h+arg_38]
0x140001781  mov     edx, 2Bh ; '+'
0x140001786  mov     [rsp+38h+var_18], 0
0x14000178f  call    _guard_dispatch_icall
0x140001794  mov     r9, [rsp+38h+arg_38]
0x140001799  mov     rcx, rdi
0x14000179c  mov     r8d, [rsp+38h+arg_28]
0x1400017a1  movzx   edx, [rsp+38h+arg_20]
0x1400017a6  mov     [rsp+38h+var_10], 0
0x1400017af  mov     word ptr [rsp+38h+var_18], bx
0x1400017b4  call    cs:__imp_WppAutoLogTrace
0x1400017bb  nop     dword ptr [rax+rax+00h]
0x1400017c0  mov     rbx, [rsp+38h+arg_0]
0x1400017c5  add     rsp, 30h
0x1400017c9  pop     rdi
0x1400017ca  retn
```
