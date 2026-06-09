# WPP_RECORDER_SF_qq

- ea: `0x140001ab8`
- end: `0x140001bb3`
- name: `WPP_RECORDER_SF_qq`
- size: `251`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140002330`
- `0x140002b64`
- `0x14001833c`
- `0x140018804`
- `0x14001a868`
- `0x14001d440`

## callees

- `0x140001ab8`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001b9d`
- `WppRecorder!WppAutoLogTrace` at `0x140001b9d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qq(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
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
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      8,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, (__int64 *)va, 8, va1);
}

```

## disassembly

```asm
0x140001ab8  push    rbx
0x140001aba  push    rbp
0x140001abb  push    rsi
0x140001abc  push    rdi
0x140001abd  sub     rsp, 58h
0x140001ac1  mov     edi, r8d
0x140001ac4  mov     rsi, rcx
0x140001ac7  mov     r11d, r8d
0x140001aca  mov     ebp, 8
0x140001acf  shr     r11, 10h
0x140001ad3  movzx   ebx, r9w
0x140001ad7  lea     r10d, [rdi-1]
0x140001adb  mov     edx, r10d
0x140001ade  and     r10d, 1Fh
0x140001ae2  shr     rdx, 5
0x140001ae6  lea     rax, [r11+r11*4]
0x140001aea  and     edx, 7FFh
0x140001af0  lea     rax, [rdx+rax*4]
0x140001af4  mov     edx, r10d
0x140001af7  mov     r10, cs:WPP_GLOBAL_Control
0x140001afe  mov     eax, [r10+rax*4+2Ch]
0x140001b03  bt      eax, edx
0x140001b06  jnb     short loc_140001B5B
0x140001b08  mov     rax, cs:pfnWppTraceMessage
0x140001b0f  lea     rcx, [r11+r11*4]
0x140001b13  mov     r8, [rsp+78h+arg_20]
0x140001b1b  lea     rdx, [rsp+78h+arg_30]
0x140001b23  mov     [rsp+78h+var_38], 0
0x140001b2c  add     rcx, rcx
0x140001b2f  mov     [rsp+78h+var_40], rbp
0x140001b34  mov     r9d, ebx
0x140001b37  mov     [rsp+78h+var_48], rdx
0x140001b3c  lea     rdx, [rsp+78h+arg_28]
0x140001b44  mov     [rsp+78h+var_50], rbp
0x140001b49  mov     rcx, [r10+rcx*8+18h]
0x140001b4e  mov     [rsp+78h+var_58], rdx
0x140001b53  lea     edx, [rbp+23h]
0x140001b56  call    _guard_dispatch_icall
0x140001b5b  mov     r9, [rsp+78h+arg_20]
0x140001b63  lea     rax, [rsp+78h+arg_30]
0x140001b6b  mov     [rsp+78h+var_30], 0
0x140001b74  mov     r8d, edi
0x140001b77  mov     [rsp+78h+var_38], rbp
0x140001b7c  xor     edx, edx
0x140001b7e  mov     [rsp+78h+var_40], rax
0x140001b83  mov     rcx, rsi
0x140001b86  lea     rax, [rsp+78h+arg_28]
0x140001b8e  mov     [rsp+78h+var_48], rbp
0x140001b93  mov     [rsp+78h+var_50], rax
0x140001b98  mov     word ptr [rsp+78h+var_58], bx
0x140001b9d  call    cs:__imp_WppAutoLogTrace
0x140001ba4  nop     dword ptr [rax+rax+00h]
0x140001ba9  add     rsp, 58h
0x140001bad  pop     rdi
0x140001bae  pop     rsi
0x140001baf  pop     rbp
0x140001bb0  pop     rbx
0x140001bb1  retn
```
