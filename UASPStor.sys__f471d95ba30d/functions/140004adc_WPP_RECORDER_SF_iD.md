# WPP_RECORDER_SF_iD

- ea: `0x140004adc`
- end: `0x140004bf0`
- name: `WPP_RECORDER_SF_iD`
- size: `276`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b90`
- `0x140005744`
- `0x1400061f4`
- `0x140006690`
- `0x1400081dc`
- `0x140008720`
- `0x140009a88`
- `0x140009c10`
- `0x140009fe0`
- `0x14000a7bc`
- `0x14000c368`

## callees

- `0x140004adc`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004bd6`
- `WppRecorder!WppAutoLogTrace` at `0x140004bd6`

## pseudocode

```c
__int64 WPP_RECORDER_SF_iD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140004adc  push    rbx
0x140004ade  push    rbp
0x140004adf  push    rsi
0x140004ae0  push    rdi
0x140004ae1  push    r14
0x140004ae3  push    r15
0x140004ae5  sub     rsp, 58h
0x140004ae9  mov     r14d, r8d
0x140004aec  mov     r15, rcx
0x140004aef  mov     edi, r8d
0x140004af2  shr     rdi, 10h
0x140004af6  movzx   esi, dl
0x140004af9  lea     ebx, [r14-1]
0x140004afd  movzx   ebp, r9w
0x140004b01  mov     r10d, ebx
0x140004b04  and     ebx, 1Fh
0x140004b07  shr     r10, 5
0x140004b0b  lea     rax, [rdi+rdi*4]
0x140004b0f  and     r10d, 7FFh
0x140004b16  mov     edx, ebx
0x140004b18  mov     ebx, 4
0x140004b1d  lea     r11, [r10+rax*4]
0x140004b21  mov     r10, cs:WPP_GLOBAL_Control
0x140004b28  mov     eax, [r10+r11*4+2Ch]
0x140004b2d  bt      eax, edx
0x140004b30  jnb     short loc_140004B90
0x140004b32  lea     rcx, [rdi+rdi*4]
0x140004b36  add     rcx, rcx
0x140004b39  cmp     [r10+rcx*8+29h], sil
0x140004b3e  jb      short loc_140004B90
0x140004b40  mov     rax, cs:pfnWppTraceMessage
0x140004b47  lea     rdx, [rsp+88h+arg_30]
0x140004b4f  mov     r8, [rsp+88h+arg_20]
0x140004b57  mov     r9d, ebp
0x140004b5a  mov     rcx, [r10+rcx*8+18h]
0x140004b5f  mov     [rsp+88h+var_48], 0
0x140004b68  mov     [rsp+88h+var_50], rbx
0x140004b6d  mov     [rsp+88h+var_58], rdx
0x140004b72  lea     rdx, [rsp+88h+arg_28]
0x140004b7a  mov     [rsp+88h+var_60], 8
0x140004b83  mov     [rsp+88h+var_68], rdx
0x140004b88  lea     edx, [rbx+27h]
0x140004b8b  call    _guard_dispatch_icall
0x140004b90  mov     r9, [rsp+88h+arg_20]
0x140004b98  lea     rax, [rsp+88h+arg_30]
0x140004ba0  mov     [rsp+88h+var_40], 0
0x140004ba9  mov     r8d, r14d
0x140004bac  mov     [rsp+88h+var_48], rbx
0x140004bb1  mov     edx, esi
0x140004bb3  mov     [rsp+88h+var_50], rax
0x140004bb8  mov     rcx, r15
0x140004bbb  lea     rax, [rsp+88h+arg_28]
0x140004bc3  mov     [rsp+88h+var_58], 8
0x140004bcc  mov     [rsp+88h+var_60], rax
0x140004bd1  mov     word ptr [rsp+88h+var_68], bp
0x140004bd6  call    cs:__imp_WppAutoLogTrace
0x140004bdd  nop     dword ptr [rax+rax+00h]
0x140004be2  add     rsp, 58h
0x140004be6  pop     r15
0x140004be8  pop     r14
0x140004bea  pop     rdi
0x140004beb  pop     rsi
0x140004bec  pop     rbp
0x140004bed  pop     rbx
0x140004bee  retn
```
