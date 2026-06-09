# WPP_RECORDER_AND_TRACE_SF_sDLLd

- ea: `0x1400130f8`
- end: `0x140013232`
- name: `WPP_RECORDER_AND_TRACE_SF_sDLLd`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003f240`

## callees

- `0x140005cf4`
- `0x1400130f8`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140013216`
- `WppRecorder!WppAutoLogTrace` at `0x140013216`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDLLd(
        _DWORD a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        ...)
{
  int v13; // [rsp+20h] [rbp-A8h]
  __int64 v14; // [rsp+80h] [rbp-48h] BYREF
  __int64 v15; // [rsp+88h] [rbp-40h] BYREF
  _QWORD v16[7]; // [rsp+90h] [rbp-38h] BYREF
  va_list va; // [rsp+128h] [rbp+60h] BYREF

  va_start(va, a11);
  LODWORD(v14) = -1073741438;
  LODWORD(v15) = 0x100000;
  LODWORD(v16[0]) = 556;
  if ( a2 )
    FastWppTraceMessage(
      516,
      0x12u,
      (ULONGLONG)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      42,
      v16,
      4,
      &v15,
      4,
      va,
      4,
      &v14,
      4,
      0);
  if ( a3 )
  {
    LOWORD(v13) = 18;
    WppAutoLogTrace(
      a4,
      2,
      4,
      WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      v13,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      42,
      v16,
      4,
      &v15,
      4,
      va,
      4,
      &v14,
      4,
      0,
      v14,
      v15,
      v16[0],
      v16[1],
      v16[2],
      v16[3]);
  }
}

```

## disassembly

```asm
0x1400130f8  mov     r11, rsp
0x1400130fb  push    rbx
0x1400130fc  push    rsi
0x1400130fd  push    rdi
0x1400130fe  push    r14
0x140013100  push    r15
0x140013102  sub     rsp, 0A0h
0x140013109  mov     dword ptr [r11-48h], 0C0000182h
0x140013111  mov     esi, 4
0x140013116  mov     dword ptr [r11-40h], 100000h
0x14001311e  mov     rdi, r9
0x140013121  mov     dword ptr [r11-38h], 22Ch
0x140013129  mov     bl, r8b
0x14001312c  lea     r15, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140013133  lea     r14d, [rsi+0Eh]
0x140013137  test    dl, dl
0x140013139  jz      short loc_140013197
0x14001313b  mov     qword ptr [r11-60h], 0
0x140013143  lea     rax, [r11-48h]
0x140013147  mov     [r11-68h], rsi
0x14001314b  lea     r8, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140013152  mov     [r11-70h], rax
0x140013156  mov     ecx, 204h
0x14001315b  mov     [r11-78h], rsi
0x14001315f  lea     rax, [r11+60h]
0x140013163  mov     [r11-80h], rax
0x140013167  mov     r9, r15
0x14001316a  mov     [rsp+0C8h+var_88], rsi
0x14001316f  lea     rax, [r11-40h]
0x140013173  mov     [rsp+0C8h+var_90], rax
0x140013178  mov     edx, r14d
0x14001317b  lea     rax, [r11-38h]
0x14001317f  mov     [rsp+0C8h+var_98], rsi
0x140013184  mov     [rsp+0C8h+var_A0], rax
0x140013189  mov     [rsp+0C8h+var_A8], 2Ah ; '*'
0x140013192  call    FastWppTraceMessage
0x140013197  test    bl, bl
0x140013199  jz      loc_140013222
0x14001319f  mov     [rsp+0C8h+var_50], 0
0x1400131a8  lea     rax, [rsp+0C8h+var_48]
0x1400131b0  mov     [rsp+0C8h+var_58], rsi
0x1400131b5  lea     r9, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x1400131bc  mov     [rsp+0C8h+var_60], rax
0x1400131c1  mov     r8d, esi
0x1400131c4  mov     [rsp+0C8h+var_68], rsi
0x1400131c9  lea     rax, [rsp+0C8h+arg_58]
0x1400131d1  mov     [rsp+0C8h+var_70], rax
0x1400131d6  mov     edx, 2
0x1400131db  mov     [rsp+0C8h+var_78], rsi
0x1400131e0  lea     rax, [rsp+0C8h+var_40]
0x1400131e8  mov     [rsp+0C8h+var_80], rax
0x1400131ed  mov     rcx, rdi
0x1400131f0  mov     [rsp+0C8h+var_88], rsi
0x1400131f5  lea     rax, [rsp+0C8h+var_38]
0x1400131fd  mov     [rsp+0C8h+var_90], rax
0x140013202  mov     [rsp+0C8h+var_98], 2Ah ; '*'
0x14001320b  mov     [rsp+0C8h+var_A0], r15
0x140013210  mov     word ptr [rsp+0C8h+var_A8], r14w
0x140013216  call    cs:__imp_WppAutoLogTrace
0x14001321d  nop     dword ptr [rax+rax+00h]
0x140013222  add     rsp, 0A0h
0x140013229  pop     r15
0x14001322b  pop     r14
0x14001322d  pop     rdi
0x14001322e  pop     rsi
0x14001322f  pop     rbx
0x140013230  retn
```
