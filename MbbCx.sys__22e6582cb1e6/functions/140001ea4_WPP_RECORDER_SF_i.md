# WPP_RECORDER_SF_i

- ea: `0x140001ea4`
- end: `0x140001f89`
- name: `WPP_RECORDER_SF_i`
- size: `229`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b34`
- `0x1400024cc`
- `0x1400061b0`
- `0x140006d90`
- `0x140009694`
- `0x14000ada0`
- `0x14000ca94`
- `0x14000cc8c`
- `0x140046c6c`
- `0x140046d80`

## callees

- `0x140001ea4`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001f71`
- `WppRecorder!WppAutoLogTrace` at `0x140001f71`

## pseudocode

```c
__int64 WPP_RECORDER_SF_i(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  __int64 v14; // [rsp+48h] [rbp-20h]
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
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va, 8, 0, v13, v14);
}

```

## disassembly

```asm
0x140001ea4  push    rbx
0x140001ea6  push    rbp
0x140001ea7  push    rsi
0x140001ea8  push    rdi
0x140001ea9  push    r14
0x140001eab  sub     rsp, 40h
0x140001eaf  mov     ebp, r8d
0x140001eb2  mov     r14, rcx
0x140001eb5  mov     ebx, r8d
0x140001eb8  shr     rbx, 10h
0x140001ebc  movzx   esi, r9w
0x140001ec0  lea     r11d, [rbp-1]
0x140001ec4  movzx   edi, dl
0x140001ec7  mov     r10d, r11d
0x140001eca  shr     r10, 5
0x140001ece  lea     rax, [rbx+rbx*4]
0x140001ed2  and     r10d, 7FFh
0x140001ed9  lea     rax, [r10+rax*4]
0x140001edd  mov     r10, cs:WPP_GLOBAL_Control
0x140001ee4  mov     eax, [r10+rax*4+2Ch]
0x140001ee9  bt      eax, r11d
0x140001eed  jnb     short loc_140001F3D
0x140001eef  lea     rcx, [rbx+rbx*4]
0x140001ef3  add     rcx, rcx
0x140001ef6  cmp     [r10+rcx*8+29h], dil
0x140001efb  jb      short loc_140001F3D
0x140001efd  mov     rax, cs:pfnWppTraceMessage
0x140001f04  lea     rdx, [rsp+68h+arg_28]
0x140001f0c  mov     r8, [rsp+68h+arg_20]
0x140001f14  mov     r9d, esi
0x140001f17  mov     rcx, [r10+rcx*8+18h]
0x140001f1c  mov     [rsp+68h+var_38], 0
0x140001f25  mov     [rsp+68h+var_40], 8
0x140001f2e  mov     [rsp+68h+var_48], rdx
0x140001f33  mov     edx, 2Bh ; '+'
0x140001f38  call    _guard_dispatch_icall
0x140001f3d  mov     r9, [rsp+68h+arg_20]
0x140001f45  lea     rax, [rsp+68h+arg_28]
0x140001f4d  mov     [rsp+68h+var_30], 0
0x140001f56  mov     r8d, ebp
0x140001f59  mov     [rsp+68h+var_38], 8
0x140001f62  mov     edx, edi
0x140001f64  mov     [rsp+68h+var_40], rax
0x140001f69  mov     rcx, r14
0x140001f6c  mov     word ptr [rsp+68h+var_48], si
0x140001f71  call    cs:__imp_WppAutoLogTrace
0x140001f78  nop     dword ptr [rax+rax+00h]
0x140001f7d  add     rsp, 40h
0x140001f81  pop     r14
0x140001f83  pop     rdi
0x140001f84  pop     rsi
0x140001f85  pop     rbp
0x140001f86  pop     rbx
0x140001f87  retn
```
