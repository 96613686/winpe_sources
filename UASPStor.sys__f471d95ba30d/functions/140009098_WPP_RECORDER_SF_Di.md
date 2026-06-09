# WPP_RECORDER_SF_Di

- ea: `0x140009098`
- end: `0x1400091aa`
- name: `WPP_RECORDER_SF_Di`
- size: `274`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007010`
- `0x1400072c0`
- `0x140008430`
- `0x140008720`
- `0x140008e00`

## callees

- `0x140009098`
- `0x14000d830`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140009190`
- `WppRecorder!WppAutoLogTrace` at `0x140009190`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Di(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
    ((void (__fastcall *)(_QWORD, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids,
      a4,
      (__int64 *)va,
      4,
      va1,
      8,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140009098  push    rbx
0x14000909a  push    rbp
0x14000909b  push    rsi
0x14000909c  push    rdi
0x14000909d  push    r14
0x14000909f  push    r15
0x1400090a1  sub     rsp, 58h
0x1400090a5  mov     r14d, r8d
0x1400090a8  mov     r15, rcx
0x1400090ab  mov     edi, r8d
0x1400090ae  shr     rdi, 10h
0x1400090b2  movzx   esi, dl
0x1400090b5  lea     ebx, [r14-1]
0x1400090b9  movzx   ebp, r9w
0x1400090bd  mov     r10d, ebx
0x1400090c0  and     ebx, 1Fh
0x1400090c3  shr     r10, 5
0x1400090c7  lea     rax, [rdi+rdi*4]
0x1400090cb  and     r10d, 7FFh
0x1400090d2  mov     edx, ebx
0x1400090d4  mov     ebx, 8
0x1400090d9  lea     r11, [r10+rax*4]
0x1400090dd  mov     r10, cs:WPP_GLOBAL_Control
0x1400090e4  mov     eax, [r10+r11*4+2Ch]
0x1400090e9  bt      eax, edx
0x1400090ec  jnb     short loc_14000914B
0x1400090ee  lea     rcx, [rdi+rdi*4]
0x1400090f2  add     rcx, rcx
0x1400090f5  cmp     [r10+rcx*8+29h], sil
0x1400090fa  jb      short loc_14000914B
0x1400090fc  mov     rax, cs:pfnWppTraceMessage
0x140009103  lea     rdx, [rsp+88h+arg_30]
0x14000910b  mov     rcx, [r10+rcx*8+18h]
0x140009110  lea     r8, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140009117  mov     [rsp+88h+var_48], 0
0x140009120  mov     r9d, ebp
0x140009123  mov     [rsp+88h+var_50], rbx
0x140009128  mov     [rsp+88h+var_58], rdx
0x14000912d  lea     rdx, [rsp+88h+arg_28]
0x140009135  mov     [rsp+88h+var_60], 4
0x14000913e  mov     [rsp+88h+var_68], rdx
0x140009143  lea     edx, [rbx+23h]
0x140009146  call    _guard_dispatch_icall
0x14000914b  mov     [rsp+88h+var_40], 0
0x140009154  lea     rax, [rsp+88h+arg_30]
0x14000915c  mov     [rsp+88h+var_48], rbx
0x140009161  lea     r9, WPP_b6edca29baa332ae0dceb7ae47a85f38_Traceguids
0x140009168  mov     [rsp+88h+var_50], rax
0x14000916d  mov     r8d, r14d
0x140009170  lea     rax, [rsp+88h+arg_28]
0x140009178  mov     [rsp+88h+var_58], 4
0x140009181  mov     [rsp+88h+var_60], rax
0x140009186  mov     edx, esi
0x140009188  mov     rcx, r15
0x14000918b  mov     word ptr [rsp+88h+var_68], bp
0x140009190  call    cs:__imp_WppAutoLogTrace
0x140009197  nop     dword ptr [rax+rax+00h]
0x14000919c  add     rsp, 58h
0x1400091a0  pop     r15
0x1400091a2  pop     r14
0x1400091a4  pop     rdi
0x1400091a5  pop     rsi
0x1400091a6  pop     rbp
0x1400091a7  pop     rbx
0x1400091a8  retn
```
