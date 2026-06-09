# CAACDec::SetDefaultDecoderParameters(void)

- ea: `0x180037fd0`
- end: `0x180038192`
- name: `?SetDefaultDecoderParameters@CAACDec@@AEAAXXZ`
- size: `450`
- prototype: `void __fastcall(CAACDec *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180048894`

## callees

- `0x180003af0`
- `0x180037fd0`
- `0x180038198`
- `0x180055524`

## import_xrefs

- `ext-ms-mf-pal-l2-1-0!IsXboxPlatformSra` at `0x180038079`
- `ext-ms-mf-pal-l2-1-0!IsXboxPlatformSra` at `0x180038079`

## string_xrefs

- `0x180038012`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL Desktop %u`
- `0x1800380af`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL Xbox %u`
- `0x1800380e1`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL failed with error 0x%x`
- `0x180038133`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL failed with error 0x%x`
- `0x180038174`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_UNIDRC_SET_EFFECT failed with error 0x%x`

## pseudocode

```c
void __fastcall CAACDec::SetDefaultDecoderParameters(CAACDec *this)
{
  int v2; // r14d
  TraceLoggingHelperBase *v3; // rbp
  int v4; // eax
  int v5; // r14d
  unsigned int v6; // r9d

  if ( (unsigned __int8)IsIsXboxPlatformSraPresent() && (unsigned int)IsXboxPlatformSra() )
  {
    v5 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 514);
    v3 = (CAACDec *)((char *)this + 246488);
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)this + 246488),
      4u,
      "CAACDec::SetDefaultDecoderParameters",
      0x114u,
      "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL Xbox %u",
      96);
    if ( v5 )
      TraceLoggingHelperBase::TraceVA(
        (CAACDec *)((char *)this + 246488),
        4u,
        "CAACDec::SetDefaultDecoderParameters",
        0x117u,
        "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL failed with error 0x%x",
        v5);
    v4 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 518);
    if ( v4 )
    {
      v6 = 286;
LABEL_12:
      TraceLoggingHelperBase::TraceVA(
        v3,
        4u,
        "CAACDec::SetDefaultDecoderParameters",
        v6,
        "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_UNIDRC_SET_EFFECT failed with error 0x%x",
        v4);
    }
  }
  else
  {
    v2 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 514);
    v3 = (CAACDec *)((char *)this + 246488);
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)this + 246488),
      4u,
      "CAACDec::SetDefaultDecoderParameters",
      0x125u,
      "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL Desktop %u",
      64);
    if ( v2 )
      TraceLoggingHelperBase::TraceVA(
        (CAACDec *)((char *)this + 246488),
        4u,
        "CAACDec::SetDefaultDecoderParameters",
        0x128u,
        "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_DRC_REFERENCE_LEVEL failed with error 0x%x",
        v2);
    v4 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 518);
    if ( v4 )
    {
      v6 = 303;
      goto LABEL_12;
    }
  }
}

```

## disassembly

```asm
0x180037fd0  mov     [rsp+arg_0], rbp
0x180037fd5  mov     [rsp+arg_8], rsi
0x180037fda  push    r14
0x180037fdc  sub     rsp, 30h
0x180037fe0  mov     rsi, rcx
0x180037fe3  call    IsIsXboxPlatformSraPresent
0x180037fe8  test    al, al
0x180037fea  jnz     loc_180038079
0x180037ff0  mov     rcx, [rsi+3C0C8h]
0x180037ff7  mov     edx, 202h
0x180037ffc  mov     r8d, 40h ; '@'
0x180038002  call    aacDecoder_SetParam
0x180038007  mov     r14d, eax
0x18003800a  mov     [rsp+38h+var_10], 40h ; '@'
0x180038012  lea     rax, aCaacdecOpenaac_6; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x180038019  mov     r9d, 125h; unsigned int
0x18003801f  lea     rbp, [rsi+3C2D8h]
0x180038026  mov     [rsp+38h+Format], rax; Format
0x18003802b  lea     r8, aCaacdecSetdefa; "CAACDec::SetDefaultDecoderParameters"
0x180038032  mov     edx, 4; unsigned __int8
0x180038037  mov     rcx, rbp; this
0x18003803a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003803f  test    r14d, r14d
0x180038042  jnz     loc_180038133
0x180038048  mov     rcx, [rsi+3C0C8h]
0x18003804f  mov     edx, 206h
0x180038054  mov     r8d, 3
0x18003805a  call    aacDecoder_SetParam
0x18003805f  test    eax, eax
0x180038061  jnz     loc_180038163
0x180038067  mov     rbp, [rsp+38h+arg_0]
0x18003806c  mov     rsi, [rsp+38h+arg_8]
0x180038071  add     rsp, 30h
0x180038075  pop     r14
0x180038077  retn
0x180038079  call    cs:__imp_IsXboxPlatformSra
0x180038080  nop     dword ptr [rax+rax+00h]
0x180038085  test    eax, eax
0x180038087  jz      loc_180037FF0
0x18003808d  mov     rcx, [rsi+3C0C8h]
0x180038094  mov     edx, 202h
0x180038099  mov     r8d, 60h ; '`'
0x18003809f  call    aacDecoder_SetParam
0x1800380a4  mov     r14d, eax
0x1800380a7  mov     [rsp+38h+var_10], 60h ; '`'
0x1800380af  lea     rax, aCaacdecOpenaac_4; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x1800380b6  mov     r9d, 114h; unsigned int
0x1800380bc  lea     rbp, [rsi+3C2D8h]
0x1800380c3  mov     [rsp+38h+Format], rax; Format
0x1800380c8  lea     r8, aCaacdecSetdefa; "CAACDec::SetDefaultDecoderParameters"
0x1800380cf  mov     edx, 4; unsigned __int8
0x1800380d4  mov     rcx, rbp; this
0x1800380d7  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800380dc  test    r14d, r14d
0x1800380df  jz      short loc_18003810C
0x1800380e1  lea     rax, aCaacdecOpenaac_7; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x1800380e8  mov     [rsp+38h+var_10], r14d
0x1800380ed  mov     r9d, 117h; unsigned int
0x1800380f3  mov     [rsp+38h+Format], rax; Format
0x1800380f8  lea     r8, aCaacdecSetdefa; "CAACDec::SetDefaultDecoderParameters"
0x1800380ff  mov     edx, 4; unsigned __int8
0x180038104  mov     rcx, rbp; this
0x180038107  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003810c  mov     rcx, [rsi+3C0C8h]
0x180038113  mov     edx, 206h
0x180038118  mov     r8d, 6
0x18003811e  call    aacDecoder_SetParam
0x180038123  test    eax, eax
0x180038125  jz      loc_180038067
0x18003812b  mov     r9d, 11Eh
0x180038131  jmp     short loc_180038169
0x180038133  lea     rax, aCaacdecOpenaac_7; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x18003813a  mov     [rsp+38h+var_10], r14d
0x18003813f  mov     r9d, 128h; unsigned int
0x180038145  mov     [rsp+38h+Format], rax; Format
0x18003814a  lea     r8, aCaacdecSetdefa; "CAACDec::SetDefaultDecoderParameters"
0x180038151  mov     edx, 4; unsigned __int8
0x180038156  mov     rcx, rbp; this
0x180038159  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003815e  jmp     loc_180038048
0x180038163  mov     r9d, 12Fh; unsigned int
0x180038169  mov     [rsp+38h+var_10], eax
0x18003816d  lea     r8, aCaacdecSetdefa; "CAACDec::SetDefaultDecoderParameters"
0x180038174  lea     rax, aCaacdecOpenaac_10; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x18003817b  mov     edx, 4; unsigned __int8
0x180038180  mov     rcx, rbp; this
0x180038183  mov     [rsp+38h+Format], rax; Format
0x180038188  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003818d  jmp     loc_180038067
```
