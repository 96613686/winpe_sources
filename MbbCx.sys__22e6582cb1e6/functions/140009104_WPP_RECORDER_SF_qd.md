# WPP_RECORDER_SF_qd

- ea: `0x140009104`
- end: `0x140009218`
- name: `WPP_RECORDER_SF_qd`
- size: `276`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400092e0`
- `0x1400099cc`
- `0x14000b230`
- `0x14000bb48`
- `0x14000c648`
- `0x14000e900`
- `0x14006703c`

## callees

- `0x140009104`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400091fe`
- `WppRecorder!WppAutoLogTrace` at `0x1400091fe`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x140009104  push    rbx
0x140009106  push    rbp
0x140009107  push    rsi
0x140009108  push    rdi
0x140009109  push    r14
0x14000910b  push    r15
0x14000910d  sub     rsp, 58h
0x140009111  mov     r14d, r8d
0x140009114  mov     r15, rcx
0x140009117  mov     edi, r8d
0x14000911a  shr     rdi, 10h
0x14000911e  movzx   esi, dl
0x140009121  lea     ebx, [r14-1]
0x140009125  movzx   ebp, r9w
0x140009129  mov     r10d, ebx
0x14000912c  and     ebx, 1Fh
0x14000912f  shr     r10, 5
0x140009133  lea     rax, [rdi+rdi*4]
0x140009137  and     r10d, 7FFh
0x14000913e  mov     edx, ebx
0x140009140  mov     ebx, 4
0x140009145  lea     r11, [r10+rax*4]
0x140009149  mov     r10, cs:WPP_GLOBAL_Control
0x140009150  mov     eax, [r10+r11*4+2Ch]
0x140009155  bt      eax, edx
0x140009158  jnb     short loc_1400091B8
0x14000915a  lea     rcx, [rdi+rdi*4]
0x14000915e  add     rcx, rcx
0x140009161  cmp     [r10+rcx*8+29h], sil
0x140009166  jb      short loc_1400091B8
0x140009168  mov     rax, cs:pfnWppTraceMessage
0x14000916f  lea     rdx, [rsp+88h+arg_30]
0x140009177  mov     r8, [rsp+88h+arg_20]
0x14000917f  mov     r9d, ebp
0x140009182  mov     rcx, [r10+rcx*8+18h]
0x140009187  mov     [rsp+88h+var_48], 0
0x140009190  mov     [rsp+88h+var_50], rbx
0x140009195  mov     [rsp+88h+var_58], rdx
0x14000919a  lea     rdx, [rsp+88h+arg_28]
0x1400091a2  mov     [rsp+88h+var_60], 8
0x1400091ab  mov     [rsp+88h+var_68], rdx
0x1400091b0  lea     edx, [rbx+27h]
0x1400091b3  call    _guard_dispatch_icall
0x1400091b8  mov     r9, [rsp+88h+arg_20]
0x1400091c0  lea     rax, [rsp+88h+arg_30]
0x1400091c8  mov     [rsp+88h+var_40], 0
0x1400091d1  mov     r8d, r14d
0x1400091d4  mov     [rsp+88h+var_48], rbx
0x1400091d9  mov     edx, esi
0x1400091db  mov     [rsp+88h+var_50], rax
0x1400091e0  mov     rcx, r15
0x1400091e3  lea     rax, [rsp+88h+arg_28]
0x1400091eb  mov     [rsp+88h+var_58], 8
0x1400091f4  mov     [rsp+88h+var_60], rax
0x1400091f9  mov     word ptr [rsp+88h+var_68], bp
0x1400091fe  call    cs:__imp_WppAutoLogTrace
0x140009205  nop     dword ptr [rax+rax+00h]
0x14000920a  add     rsp, 58h
0x14000920e  pop     r15
0x140009210  pop     r14
0x140009212  pop     rdi
0x140009213  pop     rsi
0x140009214  pop     rbp
0x140009215  pop     rbx
0x140009216  retn
```
