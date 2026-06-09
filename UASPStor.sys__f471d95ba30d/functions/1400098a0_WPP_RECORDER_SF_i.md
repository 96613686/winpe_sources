# WPP_RECORDER_SF_i

- ea: `0x1400098a0`
- end: `0x140009985`
- name: `WPP_RECORDER_SF_i`
- size: `229`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140007010`
- `0x1400072c0`
- `0x140008430`
- `0x140008720`
- `0x140008e00`
- `0x14000a450`

## callees

- `0x1400098a0`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000996d`
- `WppRecorder!WppAutoLogTrace` at `0x14000996d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_i(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va);
}

```

## disassembly

```asm
0x1400098a0  push    rbx
0x1400098a2  push    rbp
0x1400098a3  push    rsi
0x1400098a4  push    rdi
0x1400098a5  push    r14
0x1400098a7  sub     rsp, 40h
0x1400098ab  mov     ebp, r8d
0x1400098ae  mov     r14, rcx
0x1400098b1  mov     ebx, r8d
0x1400098b4  shr     rbx, 10h
0x1400098b8  movzx   esi, r9w
0x1400098bc  lea     r11d, [rbp-1]
0x1400098c0  movzx   edi, dl
0x1400098c3  mov     r10d, r11d
0x1400098c6  shr     r10, 5
0x1400098ca  lea     rax, [rbx+rbx*4]
0x1400098ce  and     r10d, 7FFh
0x1400098d5  lea     rax, [r10+rax*4]
0x1400098d9  mov     r10, cs:WPP_GLOBAL_Control
0x1400098e0  mov     eax, [r10+rax*4+2Ch]
0x1400098e5  bt      eax, r11d
0x1400098e9  jnb     short loc_140009939
0x1400098eb  lea     rcx, [rbx+rbx*4]
0x1400098ef  add     rcx, rcx
0x1400098f2  cmp     [r10+rcx*8+29h], dil
0x1400098f7  jb      short loc_140009939
0x1400098f9  mov     rax, cs:pfnWppTraceMessage
0x140009900  lea     rdx, [rsp+68h+arg_28]
0x140009908  mov     r8, [rsp+68h+arg_20]
0x140009910  mov     r9d, esi
0x140009913  mov     rcx, [r10+rcx*8+18h]
0x140009918  mov     [rsp+68h+var_38], 0
0x140009921  mov     [rsp+68h+var_40], 8
0x14000992a  mov     [rsp+68h+var_48], rdx
0x14000992f  mov     edx, 2Bh ; '+'
0x140009934  call    _guard_dispatch_icall
0x140009939  mov     r9, [rsp+68h+arg_20]
0x140009941  lea     rax, [rsp+68h+arg_28]
0x140009949  mov     [rsp+68h+var_30], 0
0x140009952  mov     r8d, ebp
0x140009955  mov     [rsp+68h+var_38], 8
0x14000995e  mov     edx, edi
0x140009960  mov     [rsp+68h+var_40], rax
0x140009965  mov     rcx, r14
0x140009968  mov     word ptr [rsp+68h+var_48], si
0x14000996d  call    cs:__imp_WppAutoLogTrace
0x140009974  nop     dword ptr [rax+rax+00h]
0x140009979  add     rsp, 40h
0x14000997d  pop     r14
0x14000997f  pop     rdi
0x140009980  pop     rsi
0x140009981  pop     rbp
0x140009982  pop     rbx
0x140009983  retn
```
