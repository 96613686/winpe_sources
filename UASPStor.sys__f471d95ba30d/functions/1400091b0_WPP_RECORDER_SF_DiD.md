# WPP_RECORDER_SF_DiD

- ea: `0x1400091b0`
- end: `0x1400092e6`
- name: `WPP_RECORDER_SF_DiD`
- size: `310`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007010`
- `0x1400072c0`
- `0x140008430`
- `0x140008720`

## callees

- `0x1400091b0`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400092cc`
- `WppRecorder!WppAutoLogTrace` at `0x1400092cc`

## pseudocode

```c
__int64 WPP_RECORDER_SF_DiD(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-78h]
  __int64 v13; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v15; // [rsp+D0h] [rbp+38h] BYREF
  va_list va1; // [rsp+D0h] [rbp+38h]
  va_list va2; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x1400091b0  push    rbx
0x1400091b2  push    rbp
0x1400091b3  push    rsi
0x1400091b4  push    rdi
0x1400091b5  push    r14
0x1400091b7  push    r15
0x1400091b9  sub     rsp, 68h
0x1400091bd  mov     r14d, r8d
0x1400091c0  mov     r15, rcx
0x1400091c3  mov     edi, r8d
0x1400091c6  shr     rdi, 10h
0x1400091ca  movzx   esi, dl
0x1400091cd  lea     ebx, [r14-1]
0x1400091d1  movzx   ebp, r9w
0x1400091d5  mov     r10d, ebx
0x1400091d8  and     ebx, 1Fh
0x1400091db  shr     r10, 5
0x1400091df  lea     rax, [rdi+rdi*4]
0x1400091e3  and     r10d, 7FFh
0x1400091ea  mov     edx, ebx
0x1400091ec  mov     ebx, 4
0x1400091f1  lea     r11, [r10+rax*4]
0x1400091f5  mov     r10, cs:WPP_GLOBAL_Control
0x1400091fc  mov     eax, [r10+r11*4+2Ch]
0x140009201  bt      eax, edx
0x140009204  jnb     short loc_140009275
0x140009206  lea     rcx, [rdi+rdi*4]
0x14000920a  add     rcx, rcx
0x14000920d  cmp     [r10+rcx*8+29h], sil
0x140009212  jb      short loc_140009275
0x140009214  mov     rax, cs:pfnWppTraceMessage
0x14000921b  lea     rdx, [rsp+98h+arg_38]
0x140009223  mov     rcx, [r10+rcx*8+18h]
0x140009228  lea     r8, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x14000922f  mov     [rsp+98h+var_48], 0
0x140009238  mov     r9d, ebp
0x14000923b  mov     [rsp+98h+var_50], rbx
0x140009240  mov     [rsp+98h+var_58], rdx
0x140009245  lea     rdx, [rsp+98h+arg_30]
0x14000924d  mov     [rsp+98h+var_60], 8
0x140009256  mov     [rsp+98h+var_68], rdx
0x14000925b  lea     rdx, [rsp+98h+arg_28]
0x140009263  mov     [rsp+98h+var_70], rbx
0x140009268  mov     [rsp+98h+var_78], rdx
0x14000926d  lea     edx, [rbx+27h]
0x140009270  call    _guard_dispatch_icall
0x140009275  mov     [rsp+98h+var_40], 0
0x14000927e  lea     rax, [rsp+98h+arg_38]
0x140009286  mov     [rsp+98h+var_48], rbx
0x14000928b  lea     r9, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140009292  mov     [rsp+98h+var_50], rax
0x140009297  mov     r8d, r14d
0x14000929a  mov     [rsp+98h+var_58], 8
0x1400092a3  lea     rax, [rsp+98h+arg_30]
0x1400092ab  mov     [rsp+98h+var_60], rax
0x1400092b0  mov     edx, esi
0x1400092b2  lea     rax, [rsp+98h+arg_28]
0x1400092ba  mov     [rsp+98h+var_68], rbx
0x1400092bf  mov     [rsp+98h+var_70], rax
0x1400092c4  mov     rcx, r15
0x1400092c7  mov     word ptr [rsp+98h+var_78], bp
0x1400092cc  call    cs:__imp_WppAutoLogTrace
0x1400092d3  nop     dword ptr [rax+rax+00h]
0x1400092d8  add     rsp, 68h
0x1400092dc  pop     r15
0x1400092de  pop     r14
0x1400092e0  pop     rdi
0x1400092e1  pop     rsi
0x1400092e2  pop     rbp
0x1400092e3  pop     rbx
0x1400092e4  retn
```
