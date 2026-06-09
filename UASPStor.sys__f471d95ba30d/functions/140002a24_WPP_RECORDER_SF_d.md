# WPP_RECORDER_SF_d

- ea: `0x140002a24`
- end: `0x140002b09`
- name: `WPP_RECORDER_SF_d`
- size: `229`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015cc`
- `0x140002320`
- `0x1400031f0`
- `0x140003b90`
- `0x140004120`
- `0x140005490`
- `0x1400062d0`
- `0x14000785c`
- `0x140007cc0`
- `0x14000a7bc`

## callees

- `0x140002a24`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002af1`
- `WppRecorder!WppAutoLogTrace` at `0x140002af1`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va);
}

```

## disassembly

```asm
0x140002a24  push    rbx
0x140002a26  push    rbp
0x140002a27  push    rsi
0x140002a28  push    rdi
0x140002a29  push    r14
0x140002a2b  sub     rsp, 40h
0x140002a2f  mov     ebp, r8d
0x140002a32  mov     r14, rcx
0x140002a35  mov     ebx, r8d
0x140002a38  shr     rbx, 10h
0x140002a3c  movzx   esi, r9w
0x140002a40  lea     r11d, [rbp-1]
0x140002a44  movzx   edi, dl
0x140002a47  mov     r10d, r11d
0x140002a4a  shr     r10, 5
0x140002a4e  lea     rax, [rbx+rbx*4]
0x140002a52  and     r10d, 7FFh
0x140002a59  lea     rax, [r10+rax*4]
0x140002a5d  mov     r10, cs:WPP_GLOBAL_Control
0x140002a64  mov     eax, [r10+rax*4+2Ch]
0x140002a69  bt      eax, r11d
0x140002a6d  jnb     short loc_140002ABD
0x140002a6f  lea     rcx, [rbx+rbx*4]
0x140002a73  add     rcx, rcx
0x140002a76  cmp     [r10+rcx*8+29h], dil
0x140002a7b  jb      short loc_140002ABD
0x140002a7d  mov     rax, cs:pfnWppTraceMessage
0x140002a84  lea     rdx, [rsp+68h+arg_28]
0x140002a8c  mov     r8, [rsp+68h+arg_20]
0x140002a94  mov     r9d, esi
0x140002a97  mov     rcx, [r10+rcx*8+18h]
0x140002a9c  mov     [rsp+68h+var_38], 0
0x140002aa5  mov     [rsp+68h+var_40], 4
0x140002aae  mov     [rsp+68h+var_48], rdx
0x140002ab3  mov     edx, 2Bh ; '+'
0x140002ab8  call    _guard_dispatch_icall
0x140002abd  mov     r9, [rsp+68h+arg_20]
0x140002ac5  lea     rax, [rsp+68h+arg_28]
0x140002acd  mov     [rsp+68h+var_30], 0
0x140002ad6  mov     r8d, ebp
0x140002ad9  mov     [rsp+68h+var_38], 4
0x140002ae2  mov     edx, edi
0x140002ae4  mov     [rsp+68h+var_40], rax
0x140002ae9  mov     rcx, r14
0x140002aec  mov     word ptr [rsp+68h+var_48], si
0x140002af1  call    cs:__imp_WppAutoLogTrace
0x140002af8  nop     dword ptr [rax+rax+00h]
0x140002afd  add     rsp, 40h
0x140002b01  pop     r14
0x140002b03  pop     rdi
0x140002b04  pop     rsi
0x140002b05  pop     rbp
0x140002b06  pop     rbx
0x140002b07  retn
```
