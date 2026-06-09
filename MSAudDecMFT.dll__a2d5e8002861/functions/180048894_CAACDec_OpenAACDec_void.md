# CAACDec::OpenAACDec(void)

- ea: `0x180048894`
- end: `0x180048ae6`
- name: `?OpenAACDec@CAACDec@@IEAAJXZ`
- size: `594`
- prototype: `__int64 __fastcall(CAACDec *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180003ec8`
- `0x1800305b0`

## callees

- `0x180003af0`
- `0x180005288`
- `0x180037fd0`
- `0x180038198`
- `0x180041630`
- `0x180048894`
- `0x180048aec`
- `0x18004be4c`

## string_xrefs

- `0x1800488e6`: `CAACDec::OpenAACDec`
- `0x180048927`: `CAACDec::OpenAACDec`
- `0x1800489af`: `CAACDec::OpenAACDec`
- `0x180048a11`: `CAACDec::OpenAACDec`
- `0x1800488cf`: `CAACDec::OpenAACDec() aacDecoder_Open() failed for transport type %i.`
- `0x18004892e`: `CAACDec::OpenAACDec() aacDecoder_Open() %s`
- `0x1800489b6`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_PCM_LIMITER_ENABLE failed with error 0x%x`
- `0x180048a1f`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_TARGET_LAYOUT_CICP set to %i.`
- `0x180048a4c`: `CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_TARGET_LAYOUT_CICP (%i) failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall CAACDec::OpenAACDec(CAACDec *this)
{
  __int64 v2; // rax
  int v3; // edx
  __int64 result; // rax
  const char *v5; // rax
  int v6; // eax
  unsigned int v7; // r9d
  __int64 v8; // rax
  int v9; // r14d
  int v10; // eax
  TraceLoggingHelperBase *v11; // rcx
  __int64 v12; // rax

  v2 = aacDecoder_Open(*((unsigned int *)this + 61494));
  v3 = *((_DWORD *)this + 61494);
  *((_QWORD *)this + 30745) = v2;
  if ( !v2 )
  {
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)this + 246488),
      2u,
      "CAACDec::OpenAACDec",
      0x151u,
      "CAACDec::OpenAACDec() aacDecoder_Open() failed for transport type %i.",
      v3);
    return 2147500037LL;
  }
  if ( v3 == 2 )
  {
    v5 = "ADTS";
  }
  else
  {
    v5 = "LOAS";
    if ( v3 != 10 )
      v5 = "RAW";
  }
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    4u,
    "CAACDec::OpenAACDec",
    0x156u,
    "CAACDec::OpenAACDec() aacDecoder_Open() %s",
    v5);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetImpl'::`2'::impl) )
  {
    if ( !*((_DWORD *)this + 61517) || *((_DWORD *)this + 61518) != 42 )
    {
      v6 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 16);
      if ( v6 )
      {
        v7 = 361;
LABEL_14:
        TraceLoggingHelperBase::TraceVA(
          (CAACDec *)((char *)this + 246488),
          2u,
          "CAACDec::OpenAACDec",
          v7,
          "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_PCM_LIMITER_ENABLE failed with error 0x%x",
          v6);
      }
    }
  }
  else
  {
    v6 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 16);
    if ( v6 )
    {
      v7 = 371;
      goto LABEL_14;
    }
  }
  v8 = *((unsigned __int16 *)this + 122954);
  if ( (_WORD)v8 != *((_WORD *)this + 122952) || *((_DWORD *)this + 61483) == 1 || *((_BYTE *)this + 100) )
  {
    v9 = dword_1800B73E8[v8];
    v10 = aacDecoder_SetParam(*((_QWORD *)this + 30745), 2304);
    v11 = (CAACDec *)((char *)this + 246488);
    if ( v10 )
      TraceLoggingHelperBase::TraceVA(
        v11,
        2u,
        "CAACDec::OpenAACDec",
        0x187u,
        "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_TARGET_LAYOUT_CICP (%i) failed with error 0x%x",
        v9,
        v10);
    else
      TraceLoggingHelperBase::TraceVA(
        v11,
        4u,
        "CAACDec::OpenAACDec",
        0x183u,
        "CAACDec::OpenAACDec() aacDecoder_SetParam() AAC_TARGET_LAYOUT_CICP set to %i.",
        v9);
    *((_DWORD *)this + 61495) = v9;
    *((_BYTE *)this + 99) = 1;
  }
  if ( *((_DWORD *)this + 61483) == 1 )
  {
    result = CAACDec::SetDecoderDualMonoMode(this);
    if ( (int)result < 0 )
      return result;
    *((_BYTE *)this + 94) = 1;
  }
  if ( *((_DWORD *)this + 61494) || (result = CAACDec::SetDecoderAsc(this), (int)result >= 0) )
  {
    CAACDec::SetDefaultDecoderParameters(this);
    v12 = *((_QWORD *)this + 30745);
    *((_BYTE *)this + 93) = 1;
    *((_BYTE *)this + 95) = 1;
    *((_BYTE *)this + 100) = 0;
    *((_QWORD *)this + 30746) = (v12 + 1352) & -(__int64)(v12 != 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180048894  mov     [rsp+arg_0], rbx
0x180048899  mov     [rsp+arg_8], rbp
0x18004889e  push    r14
0x1800488a0  sub     rsp, 40h
0x1800488a4  mov     rbx, rcx
0x1800488a7  mov     ecx, [rcx+3C0D8h]
0x1800488ad  call    aacDecoder_Open
0x1800488b2  mov     edx, [rbx+3C0D8h]
0x1800488b8  lea     rbp, [rbx+3C2D8h]
0x1800488bf  mov     [rbx+3C0C8h], rax
0x1800488c6  test    rax, rax
0x1800488c9  jnz     short loc_1800488FF
0x1800488cb  mov     dword ptr [rsp+48h+var_20], edx
0x1800488cf  lea     rax, aCaacdecOpenaac_1; "CAACDec::OpenAACDec() aacDecoder_Open()"...
0x1800488d6  mov     edx, 2; unsigned __int8
0x1800488db  mov     [rsp+48h+Format], rax; Format
0x1800488e0  mov     r9d, 151h; unsigned int
0x1800488e6  lea     r8, aCaacdecOpenaac_8; "CAACDec::OpenAACDec"
0x1800488ed  mov     rcx, rbp; this
0x1800488f0  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800488f5  mov     eax, 80004005h
0x1800488fa  jmp     loc_180048AD4
0x1800488ff  cmp     edx, 2
0x180048902  jnz     short loc_18004890D
0x180048904  lea     rax, aAdts; "ADTS"
0x18004890b  jmp     short loc_180048922
0x18004890d  cmp     edx, 0Ah
0x180048910  lea     rax, aLoas; "LOAS"
0x180048917  lea     rcx, aRaw; "RAW"
0x18004891e  cmovnz  rax, rcx
0x180048922  mov     [rsp+48h+var_20], rax
0x180048927  lea     r8, aCaacdecOpenaac_8; "CAACDec::OpenAACDec"
0x18004892e  lea     rax, aCaacdecOpenaac_0; "CAACDec::OpenAACDec() aacDecoder_Open()"...
0x180048935  mov     r9d, 156h; unsigned int
0x18004893b  mov     edx, 4; unsigned __int8
0x180048940  mov     [rsp+48h+Format], rax; Format
0x180048945  mov     rcx, rbp; this
0x180048948  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18004894d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter> `wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetImpl(void)'::`2'::impl
0x180048954  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::__private_IsEnabled(void)
0x180048959  test    al, al
0x18004895b  jz      short loc_18004898E
0x18004895d  cmp     dword ptr [rbx+3C134h], 0
0x180048964  jz      short loc_18004896F
0x180048966  cmp     dword ptr [rbx+3C138h], 2Ah ; '*'
0x18004896d  jz      short loc_1800489CF
0x18004896f  mov     rcx, [rbx+3C0C8h]
0x180048976  xor     r8d, r8d
0x180048979  lea     edx, [r8+10h]
0x18004897d  call    aacDecoder_SetParam
0x180048982  test    eax, eax
0x180048984  jz      short loc_1800489CF
0x180048986  mov     r9d, 169h
0x18004898c  jmp     short loc_1800489AB
0x18004898e  mov     rcx, [rbx+3C0C8h]
0x180048995  xor     r8d, r8d
0x180048998  lea     edx, [r8+10h]
0x18004899c  call    aacDecoder_SetParam
0x1800489a1  test    eax, eax
0x1800489a3  jz      short loc_1800489CF
0x1800489a5  mov     r9d, 173h; unsigned int
0x1800489ab  mov     dword ptr [rsp+48h+var_20], eax
0x1800489af  lea     r8, aCaacdecOpenaac_8; "CAACDec::OpenAACDec"
0x1800489b6  lea     rax, aCaacdecOpenaac_9; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x1800489bd  mov     edx, 2; unsigned __int8
0x1800489c2  mov     rcx, rbp; this
0x1800489c5  mov     [rsp+48h+Format], rax; Format
0x1800489ca  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800489cf  movzx   eax, word ptr [rbx+3C094h]
0x1800489d6  cmp     ax, [rbx+3C090h]
0x1800489dd  jnz     short loc_1800489F2
0x1800489df  cmp     dword ptr [rbx+3C0ACh], 1
0x1800489e6  jz      short loc_1800489F2
0x1800489e8  cmp     byte ptr [rbx+64h], 0
0x1800489ec  jz      loc_180048A72
0x1800489f2  mov     rcx, [rbx+3C0C8h]
0x1800489f9  lea     r14, dword_1800B73E8
0x180048a00  mov     r14d, [r14+rax*4]
0x180048a04  mov     edx, 900h
0x180048a09  mov     r8d, r14d
0x180048a0c  call    aacDecoder_SetParam
0x180048a11  lea     r8, aCaacdecOpenaac_8; "CAACDec::OpenAACDec"
0x180048a18  mov     rcx, rbp; this
0x180048a1b  test    eax, eax
0x180048a1d  jnz     short loc_180048A42
0x180048a1f  lea     rax, aCaacdecOpenaac_11; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x180048a26  mov     dword ptr [rsp+48h+var_20], r14d
0x180048a2b  mov     r9d, 183h; unsigned int
0x180048a31  mov     [rsp+48h+Format], rax; Format
0x180048a36  mov     edx, 4; unsigned __int8
0x180048a3b  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180048a40  jmp     short loc_180048A67
0x180048a42  mov     [rsp+48h+var_18], eax
0x180048a46  mov     r9d, 187h; unsigned int
0x180048a4c  lea     rax, aCaacdecOpenaac; "CAACDec::OpenAACDec() aacDecoder_SetPar"...
0x180048a53  mov     dword ptr [rsp+48h+var_20], r14d
0x180048a58  mov     edx, 2; unsigned __int8
0x180048a5d  mov     [rsp+48h+Format], rax; Format
0x180048a62  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180048a67  mov     [rbx+3C0DCh], r14d
0x180048a6e  mov     byte ptr [rbx+63h], 1
0x180048a72  cmp     dword ptr [rbx+3C0ACh], 1
0x180048a79  jnz     short loc_180048A8B
0x180048a7b  mov     rcx, rbx; this
0x180048a7e  call    ?SetDecoderDualMonoMode@CAACDec@@AEAAJXZ; CAACDec::SetDecoderDualMonoMode(void)
0x180048a83  test    eax, eax
0x180048a85  js      short loc_180048AD4
0x180048a87  mov     byte ptr [rbx+5Eh], 1
0x180048a8b  cmp     dword ptr [rbx+3C0D8h], 0
0x180048a92  jnz     short loc_180048AA0
0x180048a94  mov     rcx, rbx; this
0x180048a97  call    ?SetDecoderAsc@CAACDec@@AEAAJXZ; CAACDec::SetDecoderAsc(void)
0x180048a9c  test    eax, eax
0x180048a9e  js      short loc_180048AD4
0x180048aa0  mov     rcx, rbx; this
0x180048aa3  call    ?SetDefaultDecoderParameters@CAACDec@@AEAAXXZ; CAACDec::SetDefaultDecoderParameters(void)
0x180048aa8  mov     rax, [rbx+3C0C8h]
0x180048aaf  mov     byte ptr [rbx+5Dh], 1
0x180048ab3  mov     byte ptr [rbx+5Fh], 1
0x180048ab7  mov     byte ptr [rbx+64h], 0
0x180048abb  lea     rcx, [rax+548h]
0x180048ac2  neg     rax
0x180048ac5  sbb     rax, rax
0x180048ac8  and     rax, rcx
0x180048acb  mov     [rbx+3C0D0h], rax
0x180048ad2  xor     eax, eax
0x180048ad4  mov     rbx, [rsp+48h+arg_0]
0x180048ad9  mov     rbp, [rsp+48h+arg_8]
0x180048ade  add     rsp, 40h
0x180048ae2  pop     r14
0x180048ae4  retn
```
