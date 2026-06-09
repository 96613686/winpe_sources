# WPP_RECORDER_AND_TRACE_SF_qRFCOMM_CONNECTION_STATUSq

- ea: `0x14000a82c`
- end: `0x14000a90b`
- name: `WPP_RECORDER_AND_TRACE_SF_qRFCOMM_CONNECTION_STATUSq`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007768`

## callees

- `0x14000a82c`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000a8f4`
- `WppRecorder!WppAutoLogTrace` at `0x14000a8f4`

## pseudocode

```c

```

## disassembly

```asm
0x14000a82c  mov     r11, rsp
0x14000a82f  push    rbx
0x14000a830  push    rsi
0x14000a831  push    rdi
0x14000a832  push    r14
0x14000a834  sub     rsp, 68h
0x14000a838  mov     esi, 8
0x14000a83d  mov     rdi, r9
0x14000a840  mov     bl, r8b
0x14000a843  lea     r14d, [rsi+13h]
0x14000a847  test    dl, dl
0x14000a849  jz      short loc_14000A894
0x14000a84b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000a852  lea     rdx, [r11+58h]
0x14000a856  mov     qword ptr [r11-38h], 0
0x14000a85e  lea     r8, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000a865  mov     [r11-40h], rsi
0x14000a869  mov     r9d, r14d
0x14000a86c  mov     [r11-48h], rdx
0x14000a870  lea     rdx, [r11+50h]
0x14000a874  mov     qword ptr [r11-50h], 4
0x14000a87c  mov     [r11-58h], rdx
0x14000a880  lea     rdx, [r11+48h]
0x14000a884  mov     [r11-60h], rsi
0x14000a888  mov     [r11-68h], rdx
0x14000a88c  lea     edx, [rsi+23h]
0x14000a88f  call    _guard_dispatch_icall
0x14000a894  test    bl, bl
0x14000a896  jz      short loc_14000A900
0x14000a898  mov     [rsp+88h+var_30], 0
0x14000a8a1  lea     rax, [rsp+88h+arg_50]
0x14000a8a9  mov     [rsp+88h+var_38], rsi
0x14000a8ae  lea     r9, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000a8b5  mov     [rsp+88h+var_40], rax
0x14000a8ba  mov     edx, 4
0x14000a8bf  mov     [rsp+88h+var_48], 4
0x14000a8c8  lea     rax, [rsp+88h+arg_48]
0x14000a8d0  mov     [rsp+88h+var_50], rax
0x14000a8d5  mov     rcx, rdi
0x14000a8d8  lea     rax, [rsp+88h+arg_40]
0x14000a8e0  mov     [rsp+88h+var_58], rsi
0x14000a8e5  mov     [rsp+88h+var_60], rax
0x14000a8ea  lea     r8d, [rdx-1]
0x14000a8ee  mov     [rsp+88h+var_68], r14w
0x14000a8f4  call    cs:__imp_WppAutoLogTrace
0x14000a8fb  nop     dword ptr [rax+rax+00h]
0x14000a900  add     rsp, 68h
0x14000a904  pop     r14
0x14000a906  pop     rdi
0x14000a907  pop     rsi
0x14000a908  pop     rbx
0x14000a909  retn
```
