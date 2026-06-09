# WPP_RECORDER_SF_Dddd

- ea: `0x1400187d8`
- end: `0x140018930`
- name: `WPP_RECORDER_SF_Dddd`
- size: `344`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140014ea0`
- `0x140015710`
- `0x14002be90`
- `0x14002d460`
- `0x140030830`
- `0x140036030`
- `0x140038010`
- `0x140039510`
- `0x14003a500`

## callees

- `0x1400187d8`
- `0x140047e90`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140018918`
- `WppRecorder!WppAutoLogTrace` at `0x140018918`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Dddd(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-78h]
  __int64 v12; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v14; // [rsp+D0h] [rbp+38h] BYREF
  va_list va1; // [rsp+D0h] [rbp+38h]
  __int64 v16; // [rsp+D8h] [rbp+40h] BYREF
  va_list va2; // [rsp+D8h] [rbp+40h]
  va_list va3; // [rsp+E0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v16 = va_arg(va3, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= 2u )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 2, a3, a5, v11, (__int64 *)va, 4, (__int64 *)va1, 4, (__int64 *)va2);
}

```

## disassembly

```asm
0x1400187d8  push    rbx
0x1400187da  push    rbp
0x1400187db  push    rsi
0x1400187dc  push    rdi
0x1400187dd  push    r14
0x1400187df  sub     rsp, 70h
0x1400187e3  mov     esi, r8d
0x1400187e6  mov     rbp, rcx
0x1400187e9  mov     ebx, r8d
0x1400187ec  mov     r14d, 4
0x1400187f2  shr     rbx, 10h
0x1400187f6  movzx   edi, r9w
0x1400187fa  lea     r11d, [rsi-1]
0x1400187fe  mov     edx, r11d
0x140018801  and     r11d, 1Fh
0x140018805  shr     rdx, 5
0x140018809  lea     rax, [rbx+rbx*4]
0x14001880d  and     edx, 7FFh
0x140018813  lea     r10, [rdx+rax*4]
0x140018817  mov     edx, r11d
0x14001881a  mov     r11, cs:WPP_GLOBAL_Control
0x140018821  mov     eax, [r11+r10*4+2Ch]
0x140018826  bt      eax, edx
0x140018829  jnb     loc_1400188AF
0x14001882f  lea     rcx, [rbx+rbx*4]
0x140018833  add     rcx, rcx
0x140018836  cmp     byte ptr [r11+rcx*8+29h], 2
0x14001883c  jb      short loc_1400188AF
0x14001883e  mov     rax, cs:pfnWppTraceMessage
0x140018845  lea     rdx, [rsp+98h+arg_40]
0x14001884d  mov     r8, [rsp+98h+arg_20]
0x140018855  mov     r9d, edi
0x140018858  mov     rcx, [r11+rcx*8+18h]
0x14001885d  mov     [rsp+98h+var_38], 0
0x140018866  mov     [rsp+98h+var_40], r14
0x14001886b  mov     [rsp+98h+var_48], rdx
0x140018870  lea     rdx, [rsp+98h+arg_38]
0x140018878  mov     [rsp+98h+var_50], r14
0x14001887d  mov     [rsp+98h+var_58], rdx
0x140018882  lea     rdx, [rsp+98h+arg_30]
0x14001888a  mov     [rsp+98h+var_60], r14
0x14001888f  mov     [rsp+98h+var_68], rdx
0x140018894  lea     rdx, [rsp+98h+arg_28]
0x14001889c  mov     [rsp+98h+var_70], r14
0x1400188a1  mov     [rsp+98h+var_78], rdx
0x1400188a6  lea     edx, [r14+27h]
0x1400188aa  call    _guard_dispatch_icall
0x1400188af  mov     r9, [rsp+98h+arg_20]
0x1400188b7  lea     rax, [rsp+98h+arg_40]
0x1400188bf  mov     [rsp+98h+var_30], 0
0x1400188c8  mov     r8d, esi
0x1400188cb  mov     [rsp+98h+var_38], r14
0x1400188d0  mov     edx, 2
0x1400188d5  mov     [rsp+98h+var_40], rax
0x1400188da  mov     rcx, rbp
0x1400188dd  mov     [rsp+98h+var_48], r14
0x1400188e2  lea     rax, [rsp+98h+arg_38]
0x1400188ea  mov     [rsp+98h+var_50], rax
0x1400188ef  lea     rax, [rsp+98h+arg_30]
0x1400188f7  mov     [rsp+98h+var_58], r14
0x1400188fc  mov     [rsp+98h+var_60], rax
0x140018901  lea     rax, [rsp+98h+arg_28]
0x140018909  mov     [rsp+98h+var_68], r14
0x14001890e  mov     [rsp+98h+var_70], rax
0x140018913  mov     word ptr [rsp+98h+var_78], di
0x140018918  call    cs:__imp_WppAutoLogTrace
0x14001891f  nop     dword ptr [rax+rax+00h]
0x140018924  add     rsp, 70h
0x140018928  pop     r14
0x14001892a  pop     rdi
0x14001892b  pop     rsi
0x14001892c  pop     rbp
0x14001892d  pop     rbx
0x14001892e  retn
```
