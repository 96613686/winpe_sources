# CWMPropTranslator::CreateExceptionProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x180046b58`
- end: `0x180046ef4`
- name: `?CreateExceptionProperty@CWMPropTranslator@@AEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `924`
- prototype: `int(CWMPropTranslator *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800488b0`
- `0x180048db8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180017074`
- `0x18001a330`
- `0x18001c280`
- `0x1800466f4`
- `0x180046b58`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046dac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e47`

## string_xrefs

- `0x180046b6a`: `CWMPropTranslator::CreateExceptionProperty`
- `0x180046e03`: `CWMPropTranslator::CreateExceptionProperty`
- `0x180046e9e`: `CWMPropTranslator::CreateExceptionProperty`

## pseudocode

```c
__int64 __fastcall CWMPropTranslator::CreateExceptionProperty(
        CWMPropTranslator *this,
        const struct _tagpropertykey *a2,
        struct CMFProperty **a3)
{
  __int64 pid; // rdx
  __int64 v7; // rax
  CWMProperty *v8; // rax
  __int64 v9; // rdx
  struct CMFProperty *v10; // rbx
  void **v11; // rax
  __int64 v12; // rax
  CWMProperty *v13; // rax
  __int64 v14; // rax
  CWMProperty *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  CWMProperty *v18; // rax
  __int64 v19; // rax
  CWMProperty *v20; // rax
  __int64 v21; // rax
  CWMProperty *v22; // rax
  unsigned int v23; // edi
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  char v32; // [rsp+68h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v32,
    "CWMPropTranslator::CreateExceptionProperty",
    749);
  pid = a2->pid;
  if ( (_DWORD)pid == PKEY_Media_MCDI.pid )
  {
    v7 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Media_MCDI.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Media_MCDI.fmtid.Data1 )
      v7 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Media_MCDI.fmtid.Data4;
    if ( !v7 )
    {
      v8 = (CWMProperty *)operator new(0x90u);
      v10 = v8;
      if ( v8 )
      {
        CWMProperty::CWMProperty(v8, a2);
        v11 = &CWMMCDIProperty::`vftable';
LABEL_41:
        *(_QWORD *)v10 = v11;
LABEL_43:
        v23 = 0;
        *a3 = v10;
        if ( !v10 )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
          v23 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CWMPropTranslator::CreateExceptionProperty",
                788,
                -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v27 = 53;
LABEL_64:
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v27,
              WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids,
              this,
              v23);
            goto LABEL_65;
          }
        }
        goto LABEL_65;
      }
      goto LABEL_42;
    }
  }
  if ( (_DWORD)pid == PKEY_ThumbnailStream.pid )
  {
    v12 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ThumbnailStream.fmtid.Data1 )
      v12 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ThumbnailStream.fmtid.Data4;
    if ( !v12 )
    {
      v13 = (CWMProperty *)operator new(0x90u);
      v10 = v13;
      if ( v13 )
      {
        CWMProperty::CWMProperty(v13, a2);
        v11 = &CWMThumbnailStreamProperty::`vftable';
        goto LABEL_41;
      }
LABEL_42:
      v10 = 0;
      goto LABEL_43;
    }
  }
  if ( (_DWORD)pid == PKEY_RecordedTV_RecordingTime.pid )
  {
    v14 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_RecordedTV_RecordingTime.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_RecordedTV_RecordingTime.fmtid.Data1 )
      v14 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_RecordedTV_RecordingTime.fmtid.Data4;
    if ( !v14 )
    {
      v15 = (CWMProperty *)operator new(0x90u);
      v10 = v15;
      if ( v15 )
      {
        CWMProperty::CWMProperty(v15, a2);
        v11 = &CMFASFRecordingTimeProperty::`vftable';
        goto LABEL_41;
      }
      goto LABEL_42;
    }
  }
  if ( (_DWORD)pid == PKEY_Author.pid )
  {
    v16 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Author.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Author.fmtid.Data1 )
      v16 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Author.fmtid.Data4;
    if ( !v16 )
      goto LABEL_27;
  }
  if ( (_DWORD)pid == PKEY_Music_Artist.pid )
  {
    v17 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Music_Artist.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Music_Artist.fmtid.Data1 )
      v17 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Music_Artist.fmtid.Data4;
    if ( !v17 )
    {
LABEL_27:
      v18 = (CWMProperty *)operator new(0x90u);
      v10 = v18;
      if ( v18 )
      {
        CWMProperty::CWMProperty(v18, a2);
        v11 = &CWMArtistProperty::`vftable';
        goto LABEL_41;
      }
      goto LABEL_42;
    }
  }
  if ( (_DWORD)pid == PKEY_Rating.pid )
  {
    v19 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Rating.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Rating.fmtid.Data1 )
      v19 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Rating.fmtid.Data4;
    if ( !v19 )
    {
      v20 = (CWMProperty *)operator new(0x90u);
      v10 = v20;
      if ( v20 )
      {
        CWMProperty::CWMProperty(v20, a2);
        v11 = &CWMRatingProperty::`vftable';
        goto LABEL_41;
      }
      goto LABEL_42;
    }
  }
  if ( (_DWORD)pid == PKEY_Media_DateEncoded.pid )
  {
    v21 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Media_DateEncoded.fmtid.Data1 )
      v21 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Media_DateEncoded.fmtid.Data4;
    if ( !v21 )
    {
      v22 = (CWMProperty *)operator new(0x90u);
      v10 = v22;
      if ( v22 )
      {
        CWMProperty::CWMProperty(v22, a2);
        v11 = &CWMEncodingTimeProperty::`vftable';
        goto LABEL_41;
      }
      goto LABEL_42;
    }
  }
  v28 = (__int64 *)CallStackTracing::s_wpInstance;
  v23 = -2147024809;
  *a3 = 0;
  if ( !v28 )
  {
    v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, pid);
    CallStackTracing::s_wpInstance = v29;
    if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v28 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v28 + 8) )
  {
    v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
    if ( *((_DWORD *)v30 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v30, "CWMPropTranslator::CreateExceptionProperty", 786, -2147024809);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v27 = 52;
    goto LABEL_64;
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return v23;
}

```

## disassembly

```asm
0x180046b58  push    rbx
0x180046b5a  push    rbp
0x180046b5b  push    rsi
0x180046b5c  push    rdi
0x180046b5d  sub     rsp, 38h
0x180046b61  mov     rsi, r8
0x180046b64  mov     rdi, rdx
0x180046b67  mov     rbp, rcx
0x180046b6a  lea     rdx, aCwmproptransla_11; "CWMPropTranslator::CreateExceptionPrope"...
0x180046b71  mov     r8d, 2EDh; int
0x180046b77  lea     rcx, [rsp+58h+arg_8]; this
0x180046b7c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046b81  mov     edx, [rdi+10h]
0x180046b84  cmp     edx, cs:PKEY_Media_MCDI.pid
0x180046b8a  jnz     short loc_180046BD5
0x180046b8c  mov     rax, [rdi]
0x180046b8f  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data1
0x180046b96  jnz     short loc_180046BA3
0x180046b98  mov     rax, [rdi+8]
0x180046b9c  sub     rax, qword ptr cs:PKEY_Media_MCDI.fmtid.Data4
0x180046ba3  test    rax, rax
0x180046ba6  jnz     short loc_180046BD5
0x180046ba8  mov     ecx, 90h; Size
0x180046bad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046bb2  mov     rbx, rax
0x180046bb5  test    rax, rax
0x180046bb8  jz      loc_180046D8B
0x180046bbe  mov     rdx, rdi; struct _tagpropertykey *
0x180046bc1  mov     rcx, rax; this
0x180046bc4  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046bc9  lea     rax, ??_7CWMMCDIProperty@@6B@; const CWMMCDIProperty::`vftable'
0x180046bd0  jmp     loc_180046D86
0x180046bd5  cmp     edx, cs:PKEY_ThumbnailStream.pid
0x180046bdb  jnz     short loc_180046C26
0x180046bdd  mov     rax, [rdi]
0x180046be0  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data1
0x180046be7  jnz     short loc_180046BF4
0x180046be9  mov     rax, [rdi+8]
0x180046bed  sub     rax, qword ptr cs:PKEY_ThumbnailStream.fmtid.Data4
0x180046bf4  test    rax, rax
0x180046bf7  jnz     short loc_180046C26
0x180046bf9  mov     ecx, 90h; Size
0x180046bfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046c03  mov     rbx, rax
0x180046c06  test    rax, rax
0x180046c09  jz      loc_180046D8B
0x180046c0f  mov     rdx, rdi; struct _tagpropertykey *
0x180046c12  mov     rcx, rax; this
0x180046c15  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046c1a  lea     rax, ??_7CWMThumbnailStreamProperty@@6B@; const CWMThumbnailStreamProperty::`vftable'
0x180046c21  jmp     loc_180046D86
0x180046c26  cmp     edx, cs:PKEY_RecordedTV_RecordingTime.pid
0x180046c2c  jnz     short loc_180046C77
0x180046c2e  mov     rax, [rdi]
0x180046c31  sub     rax, qword ptr cs:PKEY_RecordedTV_RecordingTime.fmtid.Data1
0x180046c38  jnz     short loc_180046C45
0x180046c3a  mov     rax, [rdi+8]
0x180046c3e  sub     rax, qword ptr cs:PKEY_RecordedTV_RecordingTime.fmtid.Data4
0x180046c45  test    rax, rax
0x180046c48  jnz     short loc_180046C77
0x180046c4a  mov     ecx, 90h; Size
0x180046c4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046c54  mov     rbx, rax
0x180046c57  test    rax, rax
0x180046c5a  jz      loc_180046D8B
0x180046c60  mov     rdx, rdi; struct _tagpropertykey *
0x180046c63  mov     rcx, rax; this
0x180046c66  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046c6b  lea     rax, ??_7CMFASFRecordingTimeProperty@@6B@; const CMFASFRecordingTimeProperty::`vftable'
0x180046c72  jmp     loc_180046D86
0x180046c77  cmp     edx, cs:PKEY_Author.pid
0x180046c7d  jnz     short loc_180046C9B
0x180046c7f  mov     rax, [rdi]
0x180046c82  sub     rax, qword ptr cs:PKEY_Author.fmtid.Data1
0x180046c89  jnz     short loc_180046C96
0x180046c8b  mov     rax, [rdi+8]
0x180046c8f  sub     rax, qword ptr cs:PKEY_Author.fmtid.Data4
0x180046c96  test    rax, rax
0x180046c99  jz      short loc_180046CBF
0x180046c9b  cmp     edx, cs:PKEY_Music_Artist.pid
0x180046ca1  jnz     short loc_180046CEC
0x180046ca3  mov     rax, [rdi]
0x180046ca6  sub     rax, qword ptr cs:PKEY_Music_Artist.fmtid.Data1
0x180046cad  jnz     short loc_180046CBA
0x180046caf  mov     rax, [rdi+8]
0x180046cb3  sub     rax, qword ptr cs:PKEY_Music_Artist.fmtid.Data4
0x180046cba  test    rax, rax
0x180046cbd  jnz     short loc_180046CEC
0x180046cbf  mov     ecx, 90h; Size
0x180046cc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046cc9  mov     rbx, rax
0x180046ccc  test    rax, rax
0x180046ccf  jz      loc_180046D8B
0x180046cd5  mov     rdx, rdi; struct _tagpropertykey *
0x180046cd8  mov     rcx, rax; this
0x180046cdb  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046ce0  lea     rax, ??_7CWMArtistProperty@@6B@; const CWMArtistProperty::`vftable'
0x180046ce7  jmp     loc_180046D86
0x180046cec  cmp     edx, cs:PKEY_Rating.pid
0x180046cf2  jnz     short loc_180046D36
0x180046cf4  mov     rax, [rdi]
0x180046cf7  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data1
0x180046cfe  jnz     short loc_180046D0B
0x180046d00  mov     rax, [rdi+8]
0x180046d04  sub     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x180046d0b  test    rax, rax
0x180046d0e  jnz     short loc_180046D36
0x180046d10  mov     ecx, 90h; Size
0x180046d15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046d1a  mov     rbx, rax
0x180046d1d  test    rax, rax
0x180046d20  jz      short loc_180046D8B
0x180046d22  mov     rdx, rdi; struct _tagpropertykey *
0x180046d25  mov     rcx, rax; this
0x180046d28  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046d2d  lea     rax, ??_7CWMRatingProperty@@6B@; const CWMRatingProperty::`vftable'
0x180046d34  jmp     short loc_180046D86
0x180046d36  cmp     edx, cs:PKEY_Media_DateEncoded.pid
0x180046d3c  jnz     loc_180046E2F
0x180046d42  mov     rax, [rdi]
0x180046d45  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data1
0x180046d4c  jnz     short loc_180046D59
0x180046d4e  mov     rax, [rdi+8]
0x180046d52  sub     rax, qword ptr cs:PKEY_Media_DateEncoded.fmtid.Data4
0x180046d59  test    rax, rax
0x180046d5c  jnz     loc_180046E2F
0x180046d62  mov     ecx, 90h; Size
0x180046d67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046d6c  mov     rbx, rax
0x180046d6f  test    rax, rax
0x180046d72  jz      short loc_180046D8B
0x180046d74  mov     rdx, rdi; struct _tagpropertykey *
0x180046d77  mov     rcx, rax; this
0x180046d7a  call    ??0CWMProperty@@QEAA@AEBU_tagpropertykey@@@Z; CWMProperty::CWMProperty(_tagpropertykey const &)
0x180046d7f  lea     rax, ??_7CWMEncodingTimeProperty@@6B@; const CWMEncodingTimeProperty::`vftable'
0x180046d86  mov     [rbx], rax
0x180046d89  jmp     short loc_180046D8D
0x180046d8b  xor     ebx, ebx
0x180046d8d  xor     edi, edi
0x180046d8f  mov     [rsi], rbx
0x180046d92  test    rbx, rbx
0x180046d95  jnz     loc_180046EDF
0x180046d9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046da2  mov     edi, 8007000Eh
0x180046da7  test    rcx, rcx
0x180046daa  jnz     short loc_180046DED
0x180046dac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046db2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046db9  mov     rcx, rax
0x180046dbc  test    rax, rax
0x180046dbf  jz      short loc_180046DDF
0x180046dc1  mov     rax, [rax]
0x180046dc4  mov     edx, 7F0h
0x180046dc9  mov     rax, [rax+8]
0x180046dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dd2  test    eax, eax
0x180046dd4  jz      short loc_180046DDF
0x180046dd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ddd  jmp     short loc_180046DED
0x180046ddf  lea     rcx, qword_180069A90; this
0x180046de6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ded  cmp     byte ptr [rcx+8], 0
0x180046df1  jz      short loc_180046E18
0x180046df3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046df8  cmp     [rax+7CCh], edi
0x180046dfe  jz      short loc_180046E18
0x180046e00  mov     r9d, edi; int
0x180046e03  lea     rdx, aCwmproptransla_11; "CWMPropTranslator::CreateExceptionPrope"...
0x180046e0a  mov     r8d, 314h; int
0x180046e10  mov     rcx, rax; this
0x180046e13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046e18  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046e1d  cmp     al, 1
0x180046e1f  jb      loc_180046EDF
0x180046e25  mov     edx, 35h ; '5'
0x180046e2a  jmp     loc_180046EC1
0x180046e2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e36  mov     edi, 80070057h
0x180046e3b  mov     qword ptr [rsi], 0
0x180046e42  test    rcx, rcx
0x180046e45  jnz     short loc_180046E88
0x180046e47  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046e4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e54  mov     rcx, rax
0x180046e57  test    rax, rax
0x180046e5a  jz      short loc_180046E7A
0x180046e5c  mov     rax, [rax]
0x180046e5f  mov     edx, 7F0h
0x180046e64  mov     rax, [rax+8]
0x180046e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e6d  test    eax, eax
0x180046e6f  jz      short loc_180046E7A
0x180046e71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e78  jmp     short loc_180046E88
0x180046e7a  lea     rcx, qword_180069A90; this
0x180046e81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e88  cmp     byte ptr [rcx+8], 0
0x180046e8c  jz      short loc_180046EB3
0x180046e8e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046e93  cmp     [rax+7CCh], edi
0x180046e99  jz      short loc_180046EB3
0x180046e9b  mov     r9d, edi; int
0x180046e9e  lea     rdx, aCwmproptransla_11; "CWMPropTranslator::CreateExceptionPrope"...
0x180046ea5  mov     r8d, 312h; int
0x180046eab  mov     rcx, rax; this
0x180046eae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046eb3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180046eb8  cmp     al, 1
0x180046eba  jb      short loc_180046EDF
0x180046ebc  mov     edx, 34h ; '4'
0x180046ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ec8  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x180046ecf  mov     r9, rbp
0x180046ed2  mov     [rsp+58h+var_38], edi
0x180046ed6  mov     rcx, [rcx+10h]
0x180046eda  call    WPP_SF_qd
0x180046edf  lea     rcx, [rsp+58h+arg_8]; this
0x180046ee4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180046ee9  mov     eax, edi
0x180046eeb  add     rsp, 38h
0x180046eef  pop     rdi
0x180046ef0  pop     rsi
0x180046ef1  pop     rbp
0x180046ef2  pop     rbx
0x180046ef3  retn
```
