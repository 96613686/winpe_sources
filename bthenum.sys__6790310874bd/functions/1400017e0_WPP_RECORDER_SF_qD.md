# WPP_RECORDER_SF_qD

- ea: `0x1400017e0`
- end: `0x1400018e6`
- name: `WPP_RECORDER_SF_qD`
- size: `262`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001833c`
- `0x140018804`
- `0x140019058`

## callees

- `0x1400017e0`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400018d0`
- `WppRecorder!WppAutoLogTrace` at `0x1400018d0`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qD(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, int a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids, v11, (__int64 *)va, 8, va1);
}

```

## disassembly

```asm
0x1400017e0  push    rbx
0x1400017e2  push    rbp
0x1400017e3  push    rsi
0x1400017e4  push    rdi
0x1400017e5  sub     rsp, 58h
0x1400017e9  mov     esi, r8d
0x1400017ec  mov     rbp, rcx
0x1400017ef  mov     ebx, r8d
0x1400017f2  shr     rbx, 10h
0x1400017f6  movzx   edi, r9w
0x1400017fa  lea     r11d, [rsi-1]
0x1400017fe  mov     edx, r11d
0x140001801  and     r11d, 1Fh
0x140001805  shr     rdx, 5
0x140001809  lea     rax, [rbx+rbx*4]
0x14000180d  and     edx, 7FFh
0x140001813  lea     r10, [rdx+rax*4]
0x140001817  mov     edx, r11d
0x14000181a  mov     r11, cs:WPP_GLOBAL_Control
0x140001821  mov     eax, [r11+r10*4+2Ch]
0x140001826  bt      eax, edx
0x140001829  jnb     short loc_140001887
0x14000182b  mov     rax, cs:pfnWppTraceMessage
0x140001832  lea     rdx, [rsp+78h+arg_30]
0x14000183a  mov     [rsp+78h+var_38], 0
0x140001843  lea     rcx, [rbx+rbx*4]
0x140001847  mov     [rsp+78h+var_40], 4
0x140001850  lea     r8, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x140001857  mov     [rsp+78h+var_48], rdx
0x14000185c  add     rcx, rcx
0x14000185f  lea     rdx, [rsp+78h+arg_28]
0x140001867  mov     [rsp+78h+var_50], 8
0x140001870  mov     [rsp+78h+var_58], rdx
0x140001875  mov     r9d, edi
0x140001878  mov     edx, 2Bh ; '+'
0x14000187d  mov     rcx, [r11+rcx*8+18h]
0x140001882  call    _guard_dispatch_icall
0x140001887  mov     [rsp+78h+var_30], 0
0x140001890  lea     rax, [rsp+78h+arg_30]
0x140001898  mov     [rsp+78h+var_38], 4
0x1400018a1  lea     r9, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x1400018a8  mov     [rsp+78h+var_40], rax
0x1400018ad  mov     r8d, esi
0x1400018b0  lea     rax, [rsp+78h+arg_28]
0x1400018b8  mov     [rsp+78h+var_48], 8
0x1400018c1  mov     [rsp+78h+var_50], rax
0x1400018c6  xor     edx, edx
0x1400018c8  mov     rcx, rbp
0x1400018cb  mov     word ptr [rsp+78h+var_58], di
0x1400018d0  call    cs:__imp_WppAutoLogTrace
0x1400018d7  nop     dword ptr [rax+rax+00h]
0x1400018dc  add     rsp, 58h
0x1400018e0  pop     rdi
0x1400018e1  pop     rsi
0x1400018e2  pop     rbp
0x1400018e3  pop     rbx
0x1400018e4  retn
```
