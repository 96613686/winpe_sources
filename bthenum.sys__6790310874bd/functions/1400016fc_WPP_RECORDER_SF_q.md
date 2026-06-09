# WPP_RECORDER_SF_q

- ea: `0x1400016fc`
- end: `0x1400017d9`
- name: `WPP_RECORDER_SF_q`
- size: `221`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a28`
- `0x140019058`
- `0x14001ec38`
- `0x14001f054`

## callees

- `0x1400016fc`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400017bc`
- `WppRecorder!WppAutoLogTrace` at `0x1400017bc`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7), 43, a5, a4, va, 8, 0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va, 8, 0);
}

```

## disassembly

```asm
0x1400016fc  mov     [rsp+arg_0], rbx
0x140001701  mov     [rsp+arg_8], rsi
0x140001706  push    rdi
0x140001707  sub     rsp, 40h
0x14000170b  mov     edi, r8d
0x14000170e  mov     rsi, rcx
0x140001711  mov     r11d, r8d
0x140001714  shr     r11, 10h
0x140001718  movzx   ebx, r9w
0x14000171c  lea     r10d, [rdi-1]
0x140001720  mov     edx, r10d
0x140001723  and     r10d, 1Fh
0x140001727  shr     rdx, 5
0x14000172b  lea     rax, [r11+r11*4]
0x14000172f  and     edx, 7FFh
0x140001735  lea     rax, [rdx+rax*4]
0x140001739  mov     edx, r10d
0x14000173c  mov     r10, cs:WPP_GLOBAL_Control
0x140001743  mov     eax, [r10+rax*4+2Ch]
0x140001748  bt      eax, edx
0x14000174b  jnb     short loc_14000178E
0x14000174d  mov     rax, cs:pfnWppTraceMessage
0x140001754  lea     rdx, [rsp+48h+arg_28]
0x140001759  mov     r8, [rsp+48h+arg_20]
0x14000175e  lea     rcx, [r11+r11*4]
0x140001762  add     rcx, rcx
0x140001765  mov     [rsp+48h+var_18], 0
0x14000176e  mov     [rsp+48h+var_20], 8
0x140001777  mov     r9d, ebx
0x14000177a  mov     [rsp+48h+var_28], rdx
0x14000177f  mov     edx, 2Bh ; '+'
0x140001784  mov     rcx, [r10+rcx*8+18h]
0x140001789  call    _guard_dispatch_icall
0x14000178e  mov     r9, [rsp+48h+arg_20]
0x140001793  lea     rax, [rsp+48h+arg_28]
0x140001798  mov     [rsp+48h+var_10], 0
0x1400017a1  mov     r8d, edi
0x1400017a4  mov     [rsp+48h+var_18], 8
0x1400017ad  xor     edx, edx
0x1400017af  mov     [rsp+48h+var_20], rax
0x1400017b4  mov     rcx, rsi
0x1400017b7  mov     word ptr [rsp+48h+var_28], bx
0x1400017bc  call    cs:__imp_WppAutoLogTrace
0x1400017c3  nop     dword ptr [rax+rax+00h]
0x1400017c8  mov     rbx, [rsp+48h+arg_0]
0x1400017cd  mov     rsi, [rsp+48h+arg_8]
0x1400017d2  add     rsp, 40h
0x1400017d6  pop     rdi
0x1400017d7  retn
```
