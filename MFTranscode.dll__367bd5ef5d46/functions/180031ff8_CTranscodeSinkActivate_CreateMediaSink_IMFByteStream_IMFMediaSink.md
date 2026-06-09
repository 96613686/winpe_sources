# CTranscodeSinkActivate::CreateMediaSink(IMFByteStream *,IMFMediaSink * *)

- ea: `0x180031ff8`
- end: `0x1800323bb`
- name: `?CreateMediaSink@CTranscodeSinkActivate@@IEAAJPEAUIMFByteStream@@PEAPEAUIMFMediaSink@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CTranscodeSinkActivate *__hidden this, struct IMFByteStream *, struct IMFMediaSink **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180031580`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800133b0`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180031ff8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032250`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032074`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032250`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322e4`

## string_xrefs

- `0x18003201d`: `CTranscodeSinkActivate::CreateMediaSink`
- `0x1800320cb`: `CTranscodeSinkActivate::CreateMediaSink`
- `0x1800322a7`: `CTranscodeSinkActivate::CreateMediaSink`
- `0x18003233b`: `CTranscodeSinkActivate::CreateMediaSink`

## pseudocode

```c
__int64 __fastcall CTranscodeSinkActivate::CreateMediaSink(
        CTranscodeSinkActivate *this,
        struct IMFByteStream *a2,
        struct IMFMediaSink **a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  _BYTE v21[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  GUID Buf2; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v21, "CTranscodeSinkActivate::CreateMediaSink", 212);
  v6 = *((_QWORD *)this + 18);
  v22 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 64LL))(v6, &v22);
  if ( v8 >= 0 )
  {
    if ( v22
      && (*(int (__fastcall **)(__int64, const IID *, GUID *))(*(_QWORD *)v22 + 80LL))(
           v22,
           &MF_TRANSCODE_CONTAINERTYPE,
           &Buf2) >= 0 )
    {
      if ( memcmp_0(&MFTranscodeContainerType_MPEG4, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_FMPEG4, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_3GP, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_MP3, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_FLAC, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_AC3, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_WAVE, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_ADTS, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_MPEG2, &Buf2, 0x10u)
        && memcmp_0(&MFTranscodeContainerType_AVI, &Buf2, 0x10u) )
      {
        v8 = -2147467263;
        goto LABEL_47;
      }
      v8 = CTranscodeSinkActivate::CreateBuiltInMediaSink(this, &Buf2, a2, a3);
      if ( v8 < 0 )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeSinkActivate::CreateMediaSink", 241, v8);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v12 = 27;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -1072847856;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != -1072847856 )
          CallStackContext::TraceFailure(v19, "CTranscodeSinkActivate::CreateMediaSink", 227, -1072847856);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 26;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CTranscodeSinkActivate::CreateMediaSink", 222, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 25;
LABEL_46:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids, this, v8);
    }
  }
LABEL_47:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031ff8  push    rbp
0x180031ffa  push    rbx
0x180031ffb  push    rsi
0x180031ffc  push    rdi
0x180031ffd  push    r14
0x180031fff  mov     rbp, rsp
0x180032002  sub     rsp, 60h
0x180032006  mov     rax, cs:__security_cookie
0x18003200d  xor     rax, rsp
0x180032010  mov     [rbp+var_10], rax
0x180032014  mov     r14, r8
0x180032017  mov     rsi, rdx
0x18003201a  mov     rdi, rcx
0x18003201d  lea     rdx, aCtranscodesink_8; "CTranscodeSinkActivate::CreateMediaSink"
0x180032024  mov     r8d, 0D4h; int
0x18003202a  lea     rcx, [rbp+var_30]; this
0x18003202e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180032033  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003203a  mov     rcx, [rdi+90h]
0x180032041  lea     rdx, [rbp+var_28]
0x180032045  mov     [rbp+var_28], 0
0x18003204d  movdqu  [rbp+Buf2], xmm0
0x180032052  mov     rax, [rcx]
0x180032055  mov     rax, [rax+40h]
0x180032059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003205e  mov     ebx, eax
0x180032060  test    eax, eax
0x180032062  jns     loc_1800320F7
0x180032068  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003206f  test    rcx, rcx
0x180032072  jnz     short loc_1800320B5
0x180032074  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003207a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032081  mov     rcx, rax
0x180032084  test    rax, rax
0x180032087  jz      short loc_1800320A7
0x180032089  mov     rax, [rax]
0x18003208c  mov     edx, 7F0h
0x180032091  mov     rax, [rax+8]
0x180032095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003209a  test    eax, eax
0x18003209c  jz      short loc_1800320A7
0x18003209e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800320a5  jmp     short loc_1800320B5
0x1800320a7  lea     rcx, qword_180069A90; this
0x1800320ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800320b5  cmp     byte ptr [rcx+8], 0
0x1800320b9  jz      short loc_1800320E0
0x1800320bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800320c0  cmp     [rax+7CCh], ebx
0x1800320c6  jz      short loc_1800320E0
0x1800320c8  mov     r9d, ebx; int
0x1800320cb  lea     rdx, aCtranscodesink_8; "CTranscodeSinkActivate::CreateMediaSink"
0x1800320d2  mov     r8d, 0DEh; int
0x1800320d8  mov     rcx, rax; this
0x1800320db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800320e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800320e5  cmp     al, 1
0x1800320e7  jb      loc_18003237C
0x1800320ed  mov     edx, 19h
0x1800320f2  jmp     loc_18003235E
0x1800320f7  mov     rcx, [rbp+var_28]
0x1800320fb  test    rcx, rcx
0x1800320fe  jz      loc_1800322D3
0x180032104  mov     rax, [rcx]
0x180032107  lea     r8, [rbp+Buf2]
0x18003210b  lea     rdx, MF_TRANSCODE_CONTAINERTYPE
0x180032112  mov     rax, [rax+50h]
0x180032116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003211b  test    eax, eax
0x18003211d  js      loc_1800322D3
0x180032123  mov     ebx, 10h
0x180032128  lea     rdx, [rbp+Buf2]; Buf2
0x18003212c  mov     r8d, ebx; Size
0x18003212f  lea     rcx, MFTranscodeContainerType_MPEG4; Buf1
0x180032136  call    memcmp_0
0x18003213b  test    eax, eax
0x18003213d  jz      loc_180032228
0x180032143  mov     r8d, ebx; Size
0x180032146  lea     rdx, [rbp+Buf2]; Buf2
0x18003214a  lea     rcx, MFTranscodeContainerType_FMPEG4; Buf1
0x180032151  call    memcmp_0
0x180032156  test    eax, eax
0x180032158  jz      loc_180032228
0x18003215e  mov     r8d, ebx; Size
0x180032161  lea     rdx, [rbp+Buf2]; Buf2
0x180032165  lea     rcx, MFTranscodeContainerType_3GP; Buf1
0x18003216c  call    memcmp_0
0x180032171  test    eax, eax
0x180032173  jz      loc_180032228
0x180032179  mov     r8d, ebx; Size
0x18003217c  lea     rdx, [rbp+Buf2]; Buf2
0x180032180  lea     rcx, MFTranscodeContainerType_MP3; Buf1
0x180032187  call    memcmp_0
0x18003218c  test    eax, eax
0x18003218e  jz      loc_180032228
0x180032194  mov     r8d, ebx; Size
0x180032197  lea     rdx, [rbp+Buf2]; Buf2
0x18003219b  lea     rcx, MFTranscodeContainerType_FLAC; Buf1
0x1800321a2  call    memcmp_0
0x1800321a7  test    eax, eax
0x1800321a9  jz      short loc_180032228
0x1800321ab  mov     r8d, ebx; Size
0x1800321ae  lea     rdx, [rbp+Buf2]; Buf2
0x1800321b2  lea     rcx, MFTranscodeContainerType_AC3; Buf1
0x1800321b9  call    memcmp_0
0x1800321be  test    eax, eax
0x1800321c0  jz      short loc_180032228
0x1800321c2  mov     r8d, ebx; Size
0x1800321c5  lea     rdx, [rbp+Buf2]; Buf2
0x1800321c9  lea     rcx, MFTranscodeContainerType_WAVE; Buf1
0x1800321d0  call    memcmp_0
0x1800321d5  test    eax, eax
0x1800321d7  jz      short loc_180032228
0x1800321d9  mov     r8d, ebx; Size
0x1800321dc  lea     rdx, [rbp+Buf2]; Buf2
0x1800321e0  lea     rcx, MFTranscodeContainerType_ADTS; Buf1
0x1800321e7  call    memcmp_0
0x1800321ec  test    eax, eax
0x1800321ee  jz      short loc_180032228
0x1800321f0  mov     r8d, ebx; Size
0x1800321f3  lea     rdx, [rbp+Buf2]; Buf2
0x1800321f7  lea     rcx, MFTranscodeContainerType_MPEG2; Buf1
0x1800321fe  call    memcmp_0
0x180032203  test    eax, eax
0x180032205  jz      short loc_180032228
0x180032207  mov     r8d, ebx; Size
0x18003220a  lea     rdx, [rbp+Buf2]; Buf2
0x18003220e  lea     rcx, MFTranscodeContainerType_AVI; Buf1
0x180032215  call    memcmp_0
0x18003221a  test    eax, eax
0x18003221c  jz      short loc_180032228
0x18003221e  mov     ebx, 80004001h
0x180032223  jmp     loc_18003237C
0x180032228  mov     r9, r14; struct IMFMediaSink **
0x18003222b  lea     rdx, [rbp+Buf2]; struct _GUID *
0x18003222f  mov     r8, rsi; struct IMFByteStream *
0x180032232  mov     rcx, rdi; this
0x180032235  call    ?CreateBuiltInMediaSink@CTranscodeSinkActivate@@IEAAJAEBU_GUID@@PEAUIMFByteStream@@PEAPEAUIMFMediaSink@@@Z; CTranscodeSinkActivate::CreateBuiltInMediaSink(_GUID const &,IMFByteStream *,IMFMediaSink * *)
0x18003223a  mov     ebx, eax
0x18003223c  test    eax, eax
0x18003223e  jns     loc_18003237C
0x180032244  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003224b  test    rcx, rcx
0x18003224e  jnz     short loc_180032291
0x180032250  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032256  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003225d  mov     rcx, rax
0x180032260  test    rax, rax
0x180032263  jz      short loc_180032283
0x180032265  mov     rax, [rax]
0x180032268  mov     edx, 7F0h
0x18003226d  mov     rax, [rax+8]
0x180032271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032276  test    eax, eax
0x180032278  jz      short loc_180032283
0x18003227a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032281  jmp     short loc_180032291
0x180032283  lea     rcx, qword_180069A90; this
0x18003228a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032291  cmp     byte ptr [rcx+8], 0
0x180032295  jz      short loc_1800322BC
0x180032297  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003229c  cmp     [rax+7CCh], ebx
0x1800322a2  jz      short loc_1800322BC
0x1800322a4  mov     r9d, ebx; int
0x1800322a7  lea     rdx, aCtranscodesink_8; "CTranscodeSinkActivate::CreateMediaSink"
0x1800322ae  mov     r8d, 0F1h; int
0x1800322b4  mov     rcx, rax; this
0x1800322b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800322bc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800322c1  cmp     al, 1
0x1800322c3  jb      loc_18003237C
0x1800322c9  mov     edx, 1Bh
0x1800322ce  jmp     loc_18003235E
0x1800322d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800322da  mov     ebx, 0C00DA410h
0x1800322df  test    rcx, rcx
0x1800322e2  jnz     short loc_180032325
0x1800322e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800322ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800322f1  mov     rcx, rax
0x1800322f4  test    rax, rax
0x1800322f7  jz      short loc_180032317
0x1800322f9  mov     rax, [rax]
0x1800322fc  mov     edx, 7F0h
0x180032301  mov     rax, [rax+8]
0x180032305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003230a  test    eax, eax
0x18003230c  jz      short loc_180032317
0x18003230e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032315  jmp     short loc_180032325
0x180032317  lea     rcx, qword_180069A90; this
0x18003231e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032325  cmp     byte ptr [rcx+8], 0
0x180032329  jz      short loc_180032350
0x18003232b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032330  cmp     [rax+7CCh], ebx
0x180032336  jz      short loc_180032350
0x180032338  mov     r9d, ebx; int
0x18003233b  lea     rdx, aCtranscodesink_8; "CTranscodeSinkActivate::CreateMediaSink"
0x180032342  mov     r8d, 0E3h; int
0x180032348  mov     rcx, rax; this
0x18003234b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032350  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180032355  cmp     al, 1
0x180032357  jb      short loc_18003237C
0x180032359  mov     edx, 1Ah
0x18003235e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032365  lea     r8, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids
0x18003236c  mov     r9, rdi
0x18003236f  mov     [rsp+60h+var_40], ebx
0x180032373  mov     rcx, [rcx+10h]
0x180032377  call    WPP_SF_qd
0x18003237c  mov     rcx, [rbp+var_28]
0x180032380  test    rcx, rcx
0x180032383  jz      short loc_180032399
0x180032385  mov     rax, [rcx]
0x180032388  mov     rax, [rax+10h]
0x18003238c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032391  mov     [rbp+var_28], 0
0x180032399  lea     rcx, [rbp+var_30]; this
0x18003239d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800323a2  mov     eax, ebx
0x1800323a4  mov     rcx, [rbp+var_10]
0x1800323a8  xor     rcx, rsp; StackCookie
0x1800323ab  call    __security_check_cookie
0x1800323b0  add     rsp, 60h
0x1800323b4  pop     r14
0x1800323b6  pop     rdi
0x1800323b7  pop     rsi
0x1800323b8  pop     rbx
0x1800323b9  pop     rbp
0x1800323ba  retn
```
