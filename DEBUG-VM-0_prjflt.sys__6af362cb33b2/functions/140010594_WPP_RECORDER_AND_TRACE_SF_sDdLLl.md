# WPP_RECORDER_AND_TRACE_SF_sDdLLl

- ea: `0x140010594`
- end: `0x1400106e5`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdLLl`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14002fda4`

## callees

- `0x140005cf4`
- `0x140010594`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400106c9`
- `WppRecorder!WppAutoLogTrace` at `0x1400106c9`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdLLl(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        ...)
{
  int v12; // [rsp+20h] [rbp-A8h]
  _QWORD v13[7]; // [rsp+90h] [rbp-38h] BYREF
  __int64 v14; // [rsp+120h] [rbp+58h] BYREF
  va_list va; // [rsp+120h] [rbp+58h]
  __int64 v16; // [rsp+128h] [rbp+60h] BYREF
  va_list va1; // [rsp+128h] [rbp+60h]
  __int64 v18; // [rsp+130h] [rbp+68h] BYREF
  va_list va2; // [rsp+130h] [rbp+68h]
  va_list va3; // [rsp+138h] [rbp+70h] BYREF

  va_start(va3, a10);
  va_start(va2, a10);
  va_start(va1, a10);
  va_start(va, a10);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v18 = va_arg(va3, _QWORD);
  LODWORD(v13[0]) = 3702;
  if ( a2 )
    FastWppTraceMessage(
      782,
      0x86u,
      (ULONGLONG)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      43,
      v13,
      4,
      va,
      4,
      va1,
      4,
      va2,
      4,
      va3,
      4,
      0);
  if ( a3 )
  {
    LOWORD(v12) = 134;
    WppAutoLogTrace(
      a4,
      3,
      14,
      WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      v12,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      43,
      v13,
      4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0,
      v13[0],
      v13[1],
      v13[2],
      v13[3]);
  }
}

```

## disassembly

```asm
0x140010594  mov     r11, rsp
0x140010597  push    rbx
0x140010598  push    rsi
0x140010599  push    rdi
0x14001059a  push    r14
0x14001059c  push    r15
0x14001059e  sub     rsp, 0A0h
0x1400105a5  mov     dword ptr [r11-38h], 0E76h
0x1400105ad  mov     rdi, r9
0x1400105b0  lea     r15, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400105b7  mov     bl, r8b
0x1400105ba  mov     esi, 4
0x1400105bf  mov     r14d, 86h
0x1400105c5  test    dl, dl
0x1400105c7  jz      short loc_140010631
0x1400105c9  mov     qword ptr [r11-50h], 0
0x1400105d1  lea     rax, [r11+70h]
0x1400105d5  mov     [r11-58h], rsi
0x1400105d9  lea     r8, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400105e0  mov     [r11-60h], rax
0x1400105e4  mov     ecx, 30Eh
0x1400105e9  mov     [r11-68h], rsi
0x1400105ed  lea     rax, [r11+68h]
0x1400105f1  mov     [r11-70h], rax
0x1400105f5  mov     r9, r15
0x1400105f8  mov     [r11-78h], rsi
0x1400105fc  lea     rax, [r11+60h]
0x140010600  mov     [r11-80h], rax
0x140010604  mov     edx, r14d
0x140010607  mov     [rsp+0C8h+var_88], rsi
0x14001060c  lea     rax, [r11+58h]
0x140010610  mov     [rsp+0C8h+var_90], rax
0x140010615  lea     rax, [r11-38h]
0x140010619  mov     [rsp+0C8h+var_98], rsi
0x14001061e  mov     [rsp+0C8h+var_A0], rax
0x140010623  mov     [rsp+0C8h+var_A8], 2Bh ; '+'
0x14001062c  call    FastWppTraceMessage
0x140010631  test    bl, bl
0x140010633  jz      loc_1400106D5
0x140010639  mov     [rsp+0C8h+var_40], 0
0x140010645  lea     rax, [rsp+0C8h+arg_68]
0x14001064d  mov     [rsp+0C8h+var_48], rsi
0x140010655  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14001065c  mov     [rsp+0C8h+var_50], rax
0x140010661  mov     edx, 3
0x140010666  mov     [rsp+0C8h+var_58], rsi
0x14001066b  lea     rax, [rsp+0C8h+arg_60]
0x140010673  mov     [rsp+0C8h+var_60], rax
0x140010678  mov     rcx, rdi
0x14001067b  mov     [rsp+0C8h+var_68], rsi
0x140010680  lea     rax, [rsp+0C8h+arg_58]
0x140010688  mov     [rsp+0C8h+var_70], rax
0x14001068d  lea     r8d, [rdx+0Bh]
0x140010691  mov     [rsp+0C8h+var_78], rsi
0x140010696  lea     rax, [rsp+0C8h+arg_50]
0x14001069e  mov     [rsp+0C8h+var_80], rax
0x1400106a3  lea     rax, [rsp+0C8h+var_38]
0x1400106ab  mov     [rsp+0C8h+var_88], rsi
0x1400106b0  mov     [rsp+0C8h+var_90], rax
0x1400106b5  mov     [rsp+0C8h+var_98], 2Bh ; '+'
0x1400106be  mov     [rsp+0C8h+var_A0], r15
0x1400106c3  mov     word ptr [rsp+0C8h+var_A8], r14w
0x1400106c9  call    cs:__imp_WppAutoLogTrace
0x1400106d0  nop     dword ptr [rax+rax+00h]
0x1400106d5  add     rsp, 0A0h
0x1400106dc  pop     r15
0x1400106de  pop     r14
0x1400106e0  pop     rdi
0x1400106e1  pop     rsi
0x1400106e2  pop     rbx
0x1400106e3  retn
```
