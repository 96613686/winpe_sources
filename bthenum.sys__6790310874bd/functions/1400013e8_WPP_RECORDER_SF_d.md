# WPP_RECORDER_SF_d

- ea: `0x1400013e8`
- end: `0x1400014c5`
- name: `WPP_RECORDER_SF_d`
- size: `221`
- prototype: `__int64(_DWORD, _DWORD, _DWORD, _DWORD, __int64, ...)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010d0`
- `0x140001bc0`
- `0x140001cd0`
- `0x140001de0`
- `0x140002660`
- `0x140002dc0`
- `0x140002e4c`
- `0x140003060`
- `0x140018008`
- `0x14001812c`
- `0x140018234`
- `0x14001833c`
- `0x140018a54`
- `0x140018b90`
- `0x140018d54`
- `0x140019058`
- `0x14001aaac`
- `0x14001b564`
- `0x14001bfd0`
- `0x14001ce58`
- `0x14001cf90`
- `0x14001d7d8`
- `0x14001dba4`
- `0x14001dcec`
- `0x14001df2c`
- `0x14001e1e0`
- `0x14001ec38`
- `0x14001f1ac`
- `0x140020078`

## callees

- `0x1400013e8`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400014a8`
- `WppRecorder!WppAutoLogTrace` at `0x1400014a8`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, _DWORD a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va, 4, 0);
}

```

## disassembly

```asm
0x1400013e8  mov     [rsp+arg_0], rbx
0x1400013ed  mov     [rsp+arg_8], rsi
0x1400013f2  push    rdi
0x1400013f3  sub     rsp, 40h
0x1400013f7  mov     edi, r8d
0x1400013fa  mov     rsi, rcx
0x1400013fd  mov     r11d, r8d
0x140001400  shr     r11, 10h
0x140001404  movzx   ebx, r9w
0x140001408  lea     r10d, [rdi-1]
0x14000140c  mov     edx, r10d
0x14000140f  and     r10d, 1Fh
0x140001413  shr     rdx, 5
0x140001417  lea     rax, [r11+r11*4]
0x14000141b  and     edx, 7FFh
0x140001421  lea     rax, [rdx+rax*4]
0x140001425  mov     edx, r10d
0x140001428  mov     r10, cs:WPP_GLOBAL_Control
0x14000142f  mov     eax, [r10+rax*4+2Ch]
0x140001434  bt      eax, edx
0x140001437  jnb     short loc_14000147A
0x140001439  mov     rax, cs:pfnWppTraceMessage
0x140001440  lea     rdx, [rsp+48h+arg_28]
0x140001445  mov     r8, [rsp+48h+arg_20]
0x14000144a  lea     rcx, [r11+r11*4]
0x14000144e  add     rcx, rcx
0x140001451  mov     [rsp+48h+var_18], 0
0x14000145a  mov     [rsp+48h+var_20], 4
0x140001463  mov     r9d, ebx
0x140001466  mov     [rsp+48h+var_28], rdx
0x14000146b  mov     edx, 2Bh ; '+'
0x140001470  mov     rcx, [r10+rcx*8+18h]
0x140001475  call    _guard_dispatch_icall
0x14000147a  mov     r9, [rsp+48h+arg_20]
0x14000147f  lea     rax, [rsp+48h+arg_28]
0x140001484  mov     [rsp+48h+var_10], 0
0x14000148d  mov     r8d, edi
0x140001490  mov     [rsp+48h+var_18], 4
0x140001499  xor     edx, edx
0x14000149b  mov     [rsp+48h+var_20], rax
0x1400014a0  mov     rcx, rsi
0x1400014a3  mov     word ptr [rsp+48h+var_28], bx
0x1400014a8  call    cs:__imp_WppAutoLogTrace
0x1400014af  nop     dword ptr [rax+rax+00h]
0x1400014b4  mov     rbx, [rsp+48h+arg_0]
0x1400014b9  mov     rsi, [rsp+48h+arg_8]
0x1400014be  add     rsp, 40h
0x1400014c2  pop     rdi
0x1400014c3  retn
```
