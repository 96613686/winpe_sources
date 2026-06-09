# WPP_RECORDER_AND_TRACE_SF_sDdLlqqq

- ea: `0x1400106ec`
- end: `0x14001089d`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdLlqqq`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140033de8`

## callees

- `0x140005cf4`
- `0x1400106ec`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14001087e`
- `WppRecorder!WppAutoLogTrace` at `0x14001087e`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdLlqqq(
        __int16 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        __int64 a6,
        USHORT a7,
        __int64 a8,
        __int64 a9,
        ...)
{
  int v11; // [rsp+28h] [rbp-89h]
  __int64 v12; // [rsp+140h] [rbp+8Fh] BYREF
  va_list va; // [rsp+140h] [rbp+8Fh]
  __int64 v14; // [rsp+148h] [rbp+97h] BYREF
  va_list va1; // [rsp+148h] [rbp+97h]
  __int64 v16; // [rsp+150h] [rbp+9Fh] BYREF
  va_list va2; // [rsp+150h] [rbp+9Fh]
  __int64 v18; // [rsp+158h] [rbp+A7h] BYREF
  va_list va3; // [rsp+158h] [rbp+A7h]
  __int64 v20; // [rsp+160h] [rbp+AFh] BYREF
  va_list va4; // [rsp+160h] [rbp+AFh]
  __int64 v22; // [rsp+168h] [rbp+B7h] BYREF
  va_list va5; // [rsp+168h] [rbp+B7h]
  va_list va6; // [rsp+170h] [rbp+BFh] BYREF

  va_start(va6, a9);
  va_start(va5, a9);
  va_start(va4, a9);
  va_start(va3, a9);
  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
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
  if ( a2 )
    FastWppTraceMessage(
      a1,
      a7,
      (ULONGLONG)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      43,
      va,
      4,
      va1,
      4,
      va2,
      4,
      va3,
      4,
      va4,
      8,
      va5,
      8,
      va6,
      8,
      0);
  if ( a3 )
  {
    LOWORD(v11) = a7;
    WppAutoLogTrace(
      a4,
      a5,
      14,
      WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      v11,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
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
      8,
      (__int64 *)va5,
      8,
      va6,
      8,
      0);
  }
}

```

## disassembly

```asm
0x1400106ec  mov     r11, rsp
0x1400106ef  push    rbp
0x1400106f0  push    rbx
0x1400106f1  push    rsi
0x1400106f2  push    rdi
0x1400106f3  push    r13
0x1400106f5  push    r14
0x1400106f7  push    r15
0x1400106f9  lea     rbp, [r11-3Fh]
0x1400106fd  sub     rsp, 0B0h
0x140010704  movzx   edi, [rbp+37h+arg_30]
0x140010708  mov     r15d, 8
0x14001070e  lea     r13, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140010715  mov     rsi, r9
0x140010718  mov     bl, r8b
0x14001071b  lea     r14d, [r15-4]
0x14001071f  test    dl, dl
0x140010721  jz      loc_1400107BD
0x140010727  mov     qword ptr [r11-50h], 0
0x14001072f  lea     rax, [rbp+37h+arg_78]
0x140010736  mov     [r11-58h], r15
0x14001073a  lea     r8, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140010741  mov     [r11-60h], rax
0x140010745  mov     r9, r13
0x140010748  mov     [r11-68h], r15
0x14001074c  lea     rax, [rbp+37h+arg_70]
0x140010753  mov     [r11-70h], rax
0x140010757  mov     edx, edi
0x140010759  mov     [r11-78h], r15
0x14001075d  lea     rax, [rbp+37h+arg_68]
0x140010764  mov     [r11-80h], rax
0x140010768  lea     rax, [rbp+37h+arg_60]
0x14001076f  mov     [rsp+0E0h+var_80], r14
0x140010774  mov     [rsp+0E0h+var_88], rax
0x140010779  lea     rax, [rbp+37h+arg_58]
0x140010780  mov     [rsp+0E0h+var_90], r14
0x140010785  mov     [rsp+0E0h+var_98], rax
0x14001078a  lea     rax, [rbp+37h+arg_50]
0x140010791  mov     [rsp+0E0h+var_A0], r14
0x140010796  mov     [rsp+0E0h+var_A8], rax
0x14001079b  lea     rax, [rbp+37h+arg_48]
0x1400107a2  mov     [rsp+0E0h+var_B0], r14
0x1400107a7  mov     [rsp+0E0h+var_B8], rax
0x1400107ac  movzx   ecx, cx
0x1400107af  mov     [rsp+0E0h+var_C0], 2Bh ; '+'
0x1400107b8  call    FastWppTraceMessage
0x1400107bd  test    bl, bl
0x1400107bf  jz      loc_14001088A
0x1400107c5  movzx   edx, [rbp+37h+arg_20]
0x1400107c9  lea     rax, [rbp+37h+arg_78]
0x1400107d0  mov     qword ptr [rsp+0A8h], 0
0x1400107dc  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400107e3  mov     [rsp+0E0h+var_40], r15
0x1400107eb  mov     r8d, 0Eh
0x1400107f1  mov     [rsp+0E0h+var_48], rax
0x1400107f9  mov     rcx, rsi
0x1400107fc  mov     [rsp+0E0h+var_50], r15
0x140010804  lea     rax, [rbp+37h+arg_70]
0x14001080b  mov     [rsp+0E0h+var_58], rax
0x140010813  lea     rax, [rbp+37h+arg_68]
0x14001081a  mov     [rsp+0E0h+var_60], r15
0x140010822  mov     [rsp+0E0h+var_68], rax
0x140010827  lea     rax, [rbp+37h+arg_60]
0x14001082e  mov     [rsp+0E0h+var_70], r14
0x140010833  mov     [rsp+0E0h+var_78], rax
0x140010838  lea     rax, [rbp+37h+arg_58]
0x14001083f  mov     [rsp+0E0h+var_80], r14
0x140010844  mov     [rsp+0E0h+var_88], rax
0x140010849  lea     rax, [rbp+37h+arg_50]
0x140010850  mov     [rsp+0E0h+var_90], r14
0x140010855  mov     [rsp+0E0h+var_98], rax
0x14001085a  lea     rax, [rbp+37h+arg_48]
0x140010861  mov     [rsp+0E0h+var_A0], r14
0x140010866  mov     [rsp+0E0h+var_A8], rax
0x14001086b  mov     [rsp+0E0h+var_B0], 2Bh ; '+'
0x140010874  mov     [rsp+0E0h+var_B8], r13
0x140010879  mov     word ptr [rsp+0E0h+var_C0], di
0x14001087e  call    cs:__imp_WppAutoLogTrace
0x140010885  nop     dword ptr [rax+rax+00h]
0x14001088a  add     rsp, 0B0h
0x140010891  pop     r15
0x140010893  pop     r14
0x140010895  pop     r13
0x140010897  pop     rdi
0x140010898  pop     rsi
0x140010899  pop     rbx
0x14001089a  pop     rbp
0x14001089b  retn
```
