# WPP_RECORDER_AND_TRACE_SF_LdLLL

- ea: `0x140006abc`
- end: `0x140006bd4`
- name: `WPP_RECORDER_AND_TRACE_SF_LdLLL`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005c8c`

## callees

- `0x140006abc`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006bb2`
- `WppRecorder!WppAutoLogTrace` at `0x140006bb2`

## pseudocode

```c

```

## disassembly

```asm
0x140006abc  mov     r11, rsp
0x140006abf  mov     [r11+8], rbx
0x140006ac3  mov     [r11+10h], rsi
0x140006ac7  push    rdi
0x140006ac8  sub     rsp, 80h
0x140006acf  mov     esi, 61h ; 'a'
0x140006ad4  mov     rbx, r9
0x140006ad7  lea     edi, [rsi-5Dh]
0x140006ada  test    dl, dl
0x140006adc  jz      short loc_140006B3B
0x140006ade  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140006ae5  lea     rdx, [r11+68h]
0x140006ae9  mov     qword ptr [r11-18h], 0
0x140006af1  lea     r8, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140006af8  mov     [r11-20h], rdi
0x140006afc  mov     r9d, esi
0x140006aff  mov     [r11-28h], rdx
0x140006b03  lea     rdx, [r11+60h]
0x140006b07  mov     [r11-30h], rdi
0x140006b0b  mov     [r11-38h], rdx
0x140006b0f  lea     rdx, [r11+58h]
0x140006b13  mov     [r11-40h], rdi
0x140006b17  mov     [r11-48h], rdx
0x140006b1b  lea     rdx, [r11+50h]
0x140006b1f  mov     [r11-50h], rdi
0x140006b23  mov     [r11-58h], rdx
0x140006b27  lea     rdx, [r11+48h]
0x140006b2b  mov     [r11-60h], rdi
0x140006b2f  mov     [r11-68h], rdx
0x140006b33  lea     edx, [rsi-36h]
0x140006b36  call    _guard_dispatch_icall
0x140006b3b  mov     [rsp+88h+var_10], 0
0x140006b44  lea     rax, [rsp+88h+arg_60]
0x140006b4c  mov     [rsp+88h+var_18], rdi
0x140006b51  lea     r9, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140006b58  mov     [rsp+88h+var_20], rax
0x140006b5d  mov     r8d, edi
0x140006b60  mov     [rsp+88h+var_28], rdi
0x140006b65  lea     rax, [rsp+88h+arg_58]
0x140006b6d  mov     [rsp+88h+var_30], rax
0x140006b72  mov     edx, edi
0x140006b74  mov     [rsp+88h+var_38], rdi
0x140006b79  lea     rax, [rsp+88h+arg_50]
0x140006b81  mov     [rsp+88h+var_40], rax
0x140006b86  mov     rcx, rbx
0x140006b89  mov     [rsp+88h+var_48], rdi
0x140006b8e  lea     rax, [rsp+88h+arg_48]
0x140006b96  mov     [rsp+88h+var_50], rax
0x140006b9b  lea     rax, [rsp+88h+arg_40]
0x140006ba3  mov     [rsp+88h+var_58], rdi
0x140006ba8  mov     [rsp+88h+var_60], rax
0x140006bad  mov     [rsp+88h+var_68], si
0x140006bb2  call    cs:__imp_WppAutoLogTrace
0x140006bb9  nop     dword ptr [rax+rax+00h]
0x140006bbe  lea     r11, [rsp+88h+var_8]
0x140006bc6  mov     rbx, [r11+10h]
0x140006bca  mov     rsi, [r11+18h]
0x140006bce  mov     rsp, r11
0x140006bd1  pop     rdi
0x140006bd2  retn
```
