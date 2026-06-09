# WPP_RECORDER_AND_TRACE_SF_DDll

- ea: `0x14000b4c0`
- end: `0x14000b5b7`
- name: `WPP_RECORDER_AND_TRACE_SF_DDll`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001accc`

## callees

- `0x14000b4c0`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b598`
- `WppRecorder!WppAutoLogTrace` at `0x14000b598`

## pseudocode

```c

```

## disassembly

```asm
0x14000b4c0  mov     r11, rsp
0x14000b4c3  mov     [r11+8], rbx
0x14000b4c7  mov     [r11+10h], rsi
0x14000b4cb  push    rdi
0x14000b4cc  sub     rsp, 70h
0x14000b4d0  mov     esi, 43h ; 'C'
0x14000b4d5  mov     rbx, r9
0x14000b4d8  lea     edi, [rsi-3Fh]
0x14000b4db  test    dl, dl
0x14000b4dd  jz      short loc_14000B530
0x14000b4df  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000b4e6  lea     rdx, [r11+60h]
0x14000b4ea  mov     qword ptr [r11-18h], 0
0x14000b4f2  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000b4f9  mov     [r11-20h], rdi
0x14000b4fd  mov     r9d, esi
0x14000b500  mov     [r11-28h], rdx
0x14000b504  lea     rdx, [r11+58h]
0x14000b508  mov     [r11-30h], rdi
0x14000b50c  mov     [r11-38h], rdx
0x14000b510  lea     rdx, [r11+50h]
0x14000b514  mov     [r11-40h], rdi
0x14000b518  mov     [r11-48h], rdx
0x14000b51c  lea     rdx, [r11+48h]
0x14000b520  mov     [r11-50h], rdi
0x14000b524  mov     [r11-58h], rdx
0x14000b528  lea     edx, [rsi-18h]
0x14000b52b  call    _guard_dispatch_icall
0x14000b530  mov     [rsp+78h+var_10], 0
0x14000b539  lea     rax, [rsp+78h+arg_58]
0x14000b541  mov     [rsp+78h+var_18], rdi
0x14000b546  lea     r9, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000b54d  mov     [rsp+78h+var_20], rax
0x14000b552  mov     edx, 3
0x14000b557  mov     [rsp+78h+var_28], rdi
0x14000b55c  lea     rax, [rsp+78h+arg_50]
0x14000b564  mov     [rsp+78h+var_30], rax
0x14000b569  mov     r8d, edx
0x14000b56c  mov     [rsp+78h+var_38], rdi
0x14000b571  lea     rax, [rsp+78h+arg_48]
0x14000b579  mov     [rsp+78h+var_40], rax
0x14000b57e  mov     rcx, rbx
0x14000b581  lea     rax, [rsp+78h+arg_40]
0x14000b589  mov     [rsp+78h+var_48], rdi
0x14000b58e  mov     [rsp+78h+var_50], rax
0x14000b593  mov     [rsp+78h+var_58], si
0x14000b598  call    cs:__imp_WppAutoLogTrace
0x14000b59f  nop     dword ptr [rax+rax+00h]
0x14000b5a4  lea     r11, [rsp+78h+var_8]
0x14000b5a9  mov     rbx, [r11+10h]
0x14000b5ad  mov     rsi, [r11+18h]
0x14000b5b1  mov     rsp, r11
0x14000b5b4  pop     rdi
0x14000b5b5  retn
```
