# WPP_RECORDER_SF_P

- ea: `0x140002bec`
- end: `0x140002cd3`
- name: `WPP_RECORDER_SF_P`
- size: `231`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002320`
- `0x140008348`
- `0x14000a230`
- `0x14000c2e0`

## callees

- `0x140002bec`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002cbd`
- `WppRecorder!WppAutoLogTrace` at `0x140002cbd`

## pseudocode

```c
__int64 WPP_RECORDER_SF_P(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= 4u )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      8,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 4, a3, a5, v11, va);
}

```

## disassembly

```asm
0x140002bec  push    rbx
0x140002bee  push    rbp
0x140002bef  push    rsi
0x140002bf0  push    rdi
0x140002bf1  sub     rsp, 48h
0x140002bf5  mov     esi, r8d
0x140002bf8  mov     rbp, rcx
0x140002bfb  mov     ebx, r8d
0x140002bfe  shr     rbx, 10h
0x140002c02  movzx   edi, r9w
0x140002c06  lea     r11d, [rsi-1]
0x140002c0a  mov     edx, r11d
0x140002c0d  and     r11d, 1Fh
0x140002c11  shr     rdx, 5
0x140002c15  lea     rax, [rbx+rbx*4]
0x140002c19  and     edx, 7FFh
0x140002c1f  lea     r10, [rdx+rax*4]
0x140002c23  mov     edx, r11d
0x140002c26  mov     r11, cs:WPP_GLOBAL_Control
0x140002c2d  mov     eax, [r11+r10*4+2Ch]
0x140002c32  bt      eax, edx
0x140002c35  jnb     short loc_140002C86
0x140002c37  lea     rcx, [rbx+rbx*4]
0x140002c3b  add     rcx, rcx
0x140002c3e  cmp     byte ptr [r11+rcx*8+29h], 4
0x140002c44  jb      short loc_140002C86
0x140002c46  mov     rax, cs:pfnWppTraceMessage
0x140002c4d  lea     rdx, [rsp+68h+arg_28]
0x140002c55  mov     r8, [rsp+68h+arg_20]
0x140002c5d  mov     r9d, edi
0x140002c60  mov     rcx, [r11+rcx*8+18h]
0x140002c65  mov     [rsp+68h+var_38], 0
0x140002c6e  mov     [rsp+68h+var_40], 8
0x140002c77  mov     [rsp+68h+var_48], rdx
0x140002c7c  mov     edx, 2Bh ; '+'
0x140002c81  call    _guard_dispatch_icall
0x140002c86  mov     r9, [rsp+68h+arg_20]
0x140002c8e  lea     rax, [rsp+68h+arg_28]
0x140002c96  mov     [rsp+68h+var_30], 0
0x140002c9f  mov     r8d, esi
0x140002ca2  mov     [rsp+68h+var_38], 8
0x140002cab  mov     edx, 4
0x140002cb0  mov     [rsp+68h+var_40], rax
0x140002cb5  mov     rcx, rbp
0x140002cb8  mov     word ptr [rsp+68h+var_48], di
0x140002cbd  call    cs:__imp_WppAutoLogTrace
0x140002cc4  nop     dword ptr [rax+rax+00h]
0x140002cc9  add     rsp, 48h
0x140002ccd  pop     rdi
0x140002cce  pop     rsi
0x140002ccf  pop     rbp
0x140002cd0  pop     rbx
0x140002cd1  retn
```
