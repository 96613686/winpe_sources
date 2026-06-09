# WPP_RECORDER_AND_TRACE_SF_qd

- ea: `0x140001da0`
- end: `0x140001e6c`
- name: `WPP_RECORDER_AND_TRACE_SF_qd`
- size: `204`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f44`
- `0x140005f60`
- `0x14000a290`
- `0x140018910`
- `0x140018b90`
- `0x140019008`
- `0x14001946c`
- `0x140019894`
- `0x14001a054`
- `0x14001accc`

## callees

- `0x140001da0`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001e54`
- `WppRecorder!WppAutoLogTrace` at `0x140001e54`

## pseudocode

```c

```

## disassembly

```asm
0x140001da0  mov     r11, rsp
0x140001da3  mov     [r11+8], rbx
0x140001da7  push    rdi
0x140001da8  sub     rsp, 50h
0x140001dac  movzx   ebx, [rsp+58h+arg_30]
0x140001db4  mov     rdi, r9
0x140001db7  test    dl, dl
0x140001db9  jz      short loc_140001DFF
0x140001dbb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140001dc2  lea     rdx, [r11+50h]
0x140001dc6  mov     r8, [rsp+58h+arg_38]
0x140001dce  mov     r9d, ebx
0x140001dd1  mov     qword ptr [r11-18h], 0
0x140001dd9  mov     qword ptr [r11-20h], 4
0x140001de1  mov     [r11-28h], rdx
0x140001de5  lea     rdx, [r11+48h]
0x140001de9  mov     qword ptr [r11-30h], 8
0x140001df1  mov     [r11-38h], rdx
0x140001df5  mov     edx, 2Bh ; '+'
0x140001dfa  call    _guard_dispatch_icall
0x140001dff  mov     r9, [rsp+58h+arg_38]
0x140001e07  lea     rax, [rsp+58h+arg_48]
0x140001e0f  mov     r8d, [rsp+58h+arg_28]
0x140001e17  mov     rcx, rdi
0x140001e1a  movzx   edx, [rsp+58h+arg_20]
0x140001e22  mov     [rsp+58h+var_10], 0
0x140001e2b  mov     [rsp+58h+var_18], 4
0x140001e34  mov     [rsp+58h+var_20], rax
0x140001e39  lea     rax, [rsp+58h+arg_40]
0x140001e41  mov     [rsp+58h+var_28], 8
0x140001e4a  mov     [rsp+58h+var_30], rax
0x140001e4f  mov     [rsp+58h+var_38], bx
0x140001e54  call    cs:__imp_WppAutoLogTrace
0x140001e5b  nop     dword ptr [rax+rax+00h]
0x140001e60  mov     rbx, [rsp+58h+arg_0]
0x140001e65  add     rsp, 50h
0x140001e69  pop     rdi
0x140001e6a  retn
```
