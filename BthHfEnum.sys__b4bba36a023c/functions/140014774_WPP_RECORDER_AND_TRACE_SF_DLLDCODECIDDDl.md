# WPP_RECORDER_AND_TRACE_SF_DLLDCODECIDDDl

- ea: `0x140014774`
- end: `0x140014911`
- name: `WPP_RECORDER_AND_TRACE_SF_DLLDCODECIDDDl`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d238`

## callees

- `0x140014774`
- `0x14001ae00`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400148f6`
- `WppRecorder!WppAutoLogTrace` at `0x1400148f6`

## pseudocode

```c
__int64 WPP_RECORDER_AND_TRACE_SF_DLLDCODECIDDDl(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        ...)
{
  __int64 result; // rax
  int v11; // [rsp+28h] [rbp-89h]
  __int64 v12; // [rsp+128h] [rbp+77h] BYREF
  va_list va; // [rsp+128h] [rbp+77h]
  __int64 v14; // [rsp+130h] [rbp+7Fh] BYREF
  va_list va1; // [rsp+130h] [rbp+7Fh]
  __int64 v16; // [rsp+138h] [rbp+87h] BYREF
  va_list va2; // [rsp+138h] [rbp+87h]
  __int64 v18; // [rsp+140h] [rbp+8Fh] BYREF
  va_list va3; // [rsp+140h] [rbp+8Fh]
  __int64 v20; // [rsp+148h] [rbp+97h] BYREF
  va_list va4; // [rsp+148h] [rbp+97h]
  __int64 v22; // [rsp+150h] [rbp+9Fh] BYREF
  va_list va5; // [rsp+150h] [rbp+9Fh]
  __int64 v24; // [rsp+158h] [rbp+A7h] BYREF
  va_list va6; // [rsp+158h] [rbp+A7h]
  va_list va7; // [rsp+160h] [rbp+AFh] BYREF

  va_start(va7, a8);
  va_start(va6, a8);
  va_start(va5, a8);
  va_start(va4, a8);
  va_start(va3, a8);
  va_start(va2, a8);
  va_start(va1, a8);
  va_start(va, a8);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v16 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v18 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v20 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v22 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v24 = va_arg(va7, _QWORD);
  if ( a2 )
    result = ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.DeviceObject)(
               a1,
               43,
               WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
               43,
               (__int64 *)va,
               4,
               (__int64 *)va1,
               4,
               (__int64 *)va2,
               4,
               (__int64 *)va3,
               4,
               (__int64 *)va4,
               4,
               (__int64 *)va5,
               4,
               (__int64 *)va6,
               4,
               va7,
               4,
               0);
  if ( a3 )
  {
    LOWORD(v11) = 43;
    return WppAutoLogTrace(
             a4,
             4,
             5,
             WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
             v11,
             (__int64 *)va,
             4,
             (__int64 *)va1,
             4,
             (__int64 *)va2,
             4,
             (__int64 *)va3,
             4,
             (__int64 *)va4,
             4,
             (__int64 *)va5,
             4,
             (__int64 *)va6,
             4,
             va7,
             4,
             0);
  }
  return result;
}

```

## disassembly

```asm
0x140014774  mov     r11, rsp
0x140014777  push    rbp
0x140014778  push    rbx
0x140014779  push    rsi
0x14001477a  push    rdi
0x14001477b  push    r14
0x14001477d  lea     rbp, [r11-2Fh]
0x140014781  sub     rsp, 0B0h
0x140014788  mov     esi, 4
0x14001478d  mov     rdi, r9
0x140014790  mov     bl, r8b
0x140014793  lea     r14d, [rsi+27h]
0x140014797  test    dl, dl
0x140014799  jz      loc_140014839
0x14001479f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x1400147a6  lea     rdx, [rbp+27h+arg_78]
0x1400147ad  mov     qword ptr [r11-38h], 0
0x1400147b5  lea     r8, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x1400147bc  mov     [r11-40h], rsi
0x1400147c0  mov     r9d, r14d
0x1400147c3  mov     [r11-48h], rdx
0x1400147c7  lea     rdx, [rbp+27h+arg_70]
0x1400147ce  mov     [r11-50h], rsi
0x1400147d2  mov     [r11-58h], rdx
0x1400147d6  lea     rdx, [rbp+27h+arg_68]
0x1400147dd  mov     [r11-60h], rsi
0x1400147e1  mov     [r11-68h], rdx
0x1400147e5  lea     rdx, [rbp+27h+arg_60]
0x1400147ec  mov     [r11-70h], rsi
0x1400147f0  mov     [r11-78h], rdx
0x1400147f4  lea     rdx, [rbp+27h+arg_58]
0x1400147fb  mov     [r11-80h], rsi
0x1400147ff  mov     [rsp+0D0h+var_80], rdx
0x140014804  lea     rdx, [rbp+27h+arg_50]
0x14001480b  mov     [rsp+0D0h+var_88], rsi
0x140014810  mov     [rsp+0D0h+var_90], rdx
0x140014815  lea     rdx, [rbp+27h+arg_48]
0x140014819  mov     [rsp+0D0h+var_98], rsi
0x14001481e  mov     [rsp+0D0h+var_A0], rdx
0x140014823  lea     rdx, [rbp+27h+arg_40]
0x140014827  mov     [rsp+0D0h+var_A8], rsi
0x14001482c  mov     [rsp+0D0h+var_B0], rdx
0x140014831  mov     edx, r14d
0x140014834  call    _guard_dispatch_icall
0x140014839  test    bl, bl
0x14001483b  jz      loc_140014902
0x140014841  mov     qword ptr [rsp+0A8h], 0
0x14001484d  lea     rax, [rbp+27h+arg_78]
0x140014854  mov     [rsp+0D0h+var_30], rsi
0x14001485c  lea     r9, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x140014863  mov     [rsp+0D0h+var_38], rax
0x14001486b  mov     r8d, 5
0x140014871  mov     [rsp+0D0h+var_40], rsi
0x140014879  lea     rax, [rbp+27h+arg_70]
0x140014880  mov     [rsp+0D0h+var_48], rax
0x140014888  mov     edx, esi
0x14001488a  mov     [rsp+0D0h+var_50], rsi
0x140014892  lea     rax, [rbp+27h+arg_68]
0x140014899  mov     [rsp+0D0h+var_58], rax
0x14001489e  mov     rcx, rdi
0x1400148a1  mov     [rsp+0D0h+var_60], rsi
0x1400148a6  lea     rax, [rbp+27h+arg_60]
0x1400148ad  mov     [rsp+0D0h+var_68], rax
0x1400148b2  lea     rax, [rbp+27h+arg_58]
0x1400148b9  mov     [rsp+0D0h+var_70], rsi
0x1400148be  mov     [rsp+0D0h+var_78], rax
0x1400148c3  lea     rax, [rbp+27h+arg_50]
0x1400148ca  mov     [rsp+0D0h+var_80], rsi
0x1400148cf  mov     [rsp+0D0h+var_88], rax
0x1400148d4  lea     rax, [rbp+27h+arg_48]
0x1400148d8  mov     [rsp+0D0h+var_90], rsi
0x1400148dd  mov     [rsp+0D0h+var_98], rax
0x1400148e2  lea     rax, [rbp+27h+arg_40]
0x1400148e6  mov     [rsp+0D0h+var_A0], rsi
0x1400148eb  mov     [rsp+0D0h+var_A8], rax
0x1400148f0  mov     word ptr [rsp+0D0h+var_B0], r14w
0x1400148f6  call    cs:__imp_WppAutoLogTrace
0x1400148fd  nop     dword ptr [rax+rax+00h]
0x140014902  add     rsp, 0B0h
0x140014909  pop     r14
0x14001490b  pop     rdi
0x14001490c  pop     rsi
0x14001490d  pop     rbx
0x14001490e  pop     rbp
0x14001490f  retn
```
