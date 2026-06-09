# WPP_RECORDER_AND_TRACE_SF_LLL

- ea: `0x140006700`
- end: `0x1400067e0`
- name: `WPP_RECORDER_AND_TRACE_SF_LLL`
- size: `224`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030e0`
- `0x140007334`
- `0x1400081b0`
- `0x140008520`
- `0x140008d90`
- `0x140009a90`

## callees

- `0x140006700`
- `0x14000de00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400067c3`
- `WppRecorder!WppAutoLogTrace` at `0x1400067c3`

## pseudocode

```c

```

## disassembly

```asm
0x140006700  mov     r11, rsp
0x140006703  mov     [r11+8], rbx
0x140006707  mov     [r11+10h], rsi
0x14000670b  push    rdi
0x14000670c  sub     rsp, 60h
0x140006710  movzx   ebx, [rsp+68h+arg_30]
0x140006718  mov     rdi, r9
0x14000671b  mov     esi, 4
0x140006720  test    dl, dl
0x140006722  jz      short loc_14000676A
0x140006724  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x14000672b  lea     rdx, [r11+58h]
0x14000672f  mov     r8, [rsp+68h+arg_38]
0x140006737  mov     r9d, ebx
0x14000673a  mov     qword ptr [r11-18h], 0
0x140006742  mov     [r11-20h], rsi
0x140006746  mov     [r11-28h], rdx
0x14000674a  lea     rdx, [r11+50h]
0x14000674e  mov     [r11-30h], rsi
0x140006752  mov     [r11-38h], rdx
0x140006756  lea     rdx, [r11+48h]
0x14000675a  mov     [r11-40h], rsi
0x14000675e  mov     [r11-48h], rdx
0x140006762  lea     edx, [rsi+27h]
0x140006765  call    _guard_dispatch_icall
0x14000676a  mov     r9, [rsp+68h+arg_38]
0x140006772  lea     rax, [rsp+68h+arg_50]
0x14000677a  mov     r8d, [rsp+68h+arg_28]
0x140006782  mov     edx, esi
0x140006784  mov     [rsp+68h+var_10], 0
0x14000678d  mov     rcx, rdi
0x140006790  mov     [rsp+68h+var_18], rsi
0x140006795  mov     [rsp+68h+var_20], rax
0x14000679a  lea     rax, [rsp+68h+arg_48]
0x1400067a2  mov     [rsp+68h+var_28], rsi
0x1400067a7  mov     [rsp+68h+var_30], rax
0x1400067ac  lea     rax, [rsp+68h+arg_40]
0x1400067b4  mov     [rsp+68h+var_38], rsi
0x1400067b9  mov     [rsp+68h+var_40], rax
0x1400067be  mov     [rsp+68h+var_48], bx
0x1400067c3  call    cs:__imp_WppAutoLogTrace
0x1400067ca  nop     dword ptr [rax+rax+00h]
0x1400067cf  mov     rbx, [rsp+68h+arg_0]
0x1400067d4  mov     rsi, [rsp+68h+arg_8]
0x1400067d9  add     rsp, 60h
0x1400067dd  pop     rdi
0x1400067de  retn
```
