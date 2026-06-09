# WPP_RECORDER_AND_TRACE_SF_

- ea: `0x1400041d0`
- end: `0x140004252`
- name: `WPP_RECORDER_AND_TRACE_SF_`
- size: `130`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, _DWORD, __int16, __int64)`
- caller_count: `68`
- callee_count: `2`
- tags: ``

## callers

- `0x140001d64`
- `0x140001e70`
- `0x140002630`
- `0x140002a30`
- `0x140002ee0`
- `0x140002f70`
- `0x1400032b0`
- `0x1400037d0`
- `0x140003a80`
- `0x140005f38`
- `0x1400062a0`
- `0x140006470`
- `0x140006c94`
- `0x140006f60`
- `0x140007154`
- `0x140007478`
- `0x140007b28`
- `0x140007c68`
- `0x140007dc0`
- `0x14000816c`
- `0x14000828c`
- `0x1400083b8`
- `0x140008620`
- `0x1400089c0`
- `0x140008ad0`
- `0x140008be0`
- `0x140009004`
- `0x1400095c8`
- `0x140009750`
- `0x1400098ac`
- `0x140009ad4`
- `0x140009f44`
- `0x14000a05c`
- `0x14000a914`
- `0x14000b44c`
- `0x14000c030`
- `0x14000c0e0`
- `0x14000c5b0`
- `0x14000c7d0`
- `0x14000c910`
- `0x14000ca10`
- `0x14000ce50`
- `0x14000d140`
- `0x14000d76c`
- `0x14000dcf0`
- `0x14000e87c`
- `0x14000f2a0`
- `0x14000f700`
- `0x14000f890`
- `0x14000fa40`

## callees

- `0x1400041d0`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004235`
- `WppRecorder!WppAutoLogTrace` at `0x140004235`

## pseudocode

```c

```

## disassembly

```asm
0x1400041d0  mov     [rsp+arg_0], rbx
0x1400041d5  mov     [rsp+arg_8], rsi
0x1400041da  push    rdi
0x1400041db  sub     rsp, 30h
0x1400041df  movzx   ebx, [rsp+38h+arg_30]
0x1400041e4  mov     rsi, r9
0x1400041e7  mov     dil, r8b
0x1400041ea  test    dl, dl
0x1400041ec  jz      short loc_140004210
0x1400041ee  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400041f5  mov     r9d, ebx
0x1400041f8  mov     r8, [rsp+38h+arg_38]
0x1400041fd  mov     edx, 2Bh ; '+'
0x140004202  mov     [rsp+38h+var_18], 0
0x14000420b  call    _guard_dispatch_icall
0x140004210  test    dil, dil
0x140004213  jz      short loc_140004241
0x140004215  mov     r9, [rsp+38h+arg_38]
0x14000421a  mov     rcx, rsi
0x14000421d  mov     r8d, [rsp+38h+arg_28]
0x140004222  movzx   edx, [rsp+38h+arg_20]
0x140004227  mov     [rsp+38h+var_10], 0
0x140004230  mov     word ptr [rsp+38h+var_18], bx
0x140004235  call    cs:__imp_WppAutoLogTrace
0x14000423c  nop     dword ptr [rax+rax+00h]
0x140004241  mov     rbx, [rsp+38h+arg_0]
0x140004246  mov     rsi, [rsp+38h+arg_8]
0x14000424b  add     rsp, 30h
0x14000424f  pop     rdi
0x140004250  retn
```
