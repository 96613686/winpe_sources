# WPP_RECORDER_SF_ddd

- ea: `0x14000d684`
- end: `0x14000d7b4`
- name: `WPP_RECORDER_SF_ddd`
- size: `304`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140012c90`
- `0x14001b47c`
- `0x14001ffa4`
- `0x140021bf8`
- `0x140023248`
- `0x14003df70`
- `0x140040fd4`

## callees

- `0x14000d684`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d79c`
- `WppRecorder!WppAutoLogTrace` at `0x14000d79c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_ddd(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v14; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= 2u )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 2, a3, a5, v11, (__int64 *)va, 4, (__int64 *)va1, 4, va2);
}

```

## disassembly

```asm
0x14000d684  push    rbx
0x14000d686  push    rbp
0x14000d687  push    rsi
0x14000d688  push    rdi
0x14000d689  push    r14
0x14000d68b  sub     rsp, 60h
0x14000d68f  mov     esi, r8d
0x14000d692  mov     rbp, rcx
0x14000d695  mov     ebx, r8d
0x14000d698  mov     r14d, 4
0x14000d69e  shr     rbx, 10h
0x14000d6a2  movzx   edi, r9w
0x14000d6a6  lea     r11d, [rsi-1]
0x14000d6aa  mov     edx, r11d
0x14000d6ad  and     r11d, 1Fh
0x14000d6b1  shr     rdx, 5
0x14000d6b5  lea     rax, [rbx+rbx*4]
0x14000d6b9  and     edx, 7FFh
0x14000d6bf  lea     r10, [rdx+rax*4]
0x14000d6c3  mov     edx, r11d
0x14000d6c6  mov     r11, cs:WPP_GLOBAL_Control
0x14000d6cd  mov     eax, [r11+r10*4+2Ch]
0x14000d6d2  bt      eax, edx
0x14000d6d5  jnb     short loc_14000D745
0x14000d6d7  lea     rcx, [rbx+rbx*4]
0x14000d6db  add     rcx, rcx
0x14000d6de  cmp     byte ptr [r11+rcx*8+29h], 2
0x14000d6e4  jb      short loc_14000D745
0x14000d6e6  mov     rax, cs:pfnWppTraceMessage
0x14000d6ed  lea     rdx, [rsp+88h+arg_38]
0x14000d6f5  mov     r8, [rsp+88h+arg_20]
0x14000d6fd  mov     r9d, edi
0x14000d700  mov     rcx, [r11+rcx*8+18h]
0x14000d705  mov     [rsp+88h+var_38], 0
0x14000d70e  mov     [rsp+88h+var_40], r14
0x14000d713  mov     [rsp+88h+var_48], rdx
0x14000d718  lea     rdx, [rsp+88h+arg_30]
0x14000d720  mov     [rsp+88h+var_50], r14
0x14000d725  mov     [rsp+88h+var_58], rdx
0x14000d72a  lea     rdx, [rsp+88h+arg_28]
0x14000d732  mov     [rsp+88h+var_60], r14
0x14000d737  mov     [rsp+88h+var_68], rdx
0x14000d73c  lea     edx, [r14+27h]
0x14000d740  call    _guard_dispatch_icall
0x14000d745  mov     r9, [rsp+88h+arg_20]
0x14000d74d  lea     rax, [rsp+88h+arg_38]
0x14000d755  mov     [rsp+88h+var_30], 0
0x14000d75e  mov     r8d, esi
0x14000d761  mov     [rsp+88h+var_38], r14
0x14000d766  mov     edx, 2
0x14000d76b  mov     [rsp+88h+var_40], rax
0x14000d770  mov     rcx, rbp
0x14000d773  mov     [rsp+88h+var_48], r14
0x14000d778  lea     rax, [rsp+88h+arg_30]
0x14000d780  mov     [rsp+88h+var_50], rax
0x14000d785  lea     rax, [rsp+88h+arg_28]
0x14000d78d  mov     [rsp+88h+var_58], r14
0x14000d792  mov     [rsp+88h+var_60], rax
0x14000d797  mov     word ptr [rsp+88h+var_68], di
0x14000d79c  call    cs:__imp_WppAutoLogTrace
0x14000d7a3  nop     dword ptr [rax+rax+00h]
0x14000d7a8  add     rsp, 60h
0x14000d7ac  pop     r14
0x14000d7ae  pop     rdi
0x14000d7af  pop     rsi
0x14000d7b0  pop     rbp
0x14000d7b1  pop     rbx
0x14000d7b2  retn
```
