# CWMThumbnailStreamProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18004d1e0`
- end: `0x18004d625`
- name: `?SetShellValue@CWMThumbnailStreamProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CWMThumbnailStreamProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x18004aec0`
- `0x18004d1e0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d2b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d358`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d2b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004d358`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004d3fa`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004d3fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d236`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d236`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d2d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d4bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d568`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::SetShellValue(PROPVARIANT *this, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rdx
  bool v5; // zf
  __int64 *v6; // rcx
  int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v32; // [rsp+58h] [rbp+10h] BYREF
  struct IStream *v33; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v32,
    "CWMThumbnailStreamProperty::SetShellValue",
    516);
  v5 = pvarSrc->vt == 66;
  v33 = 0;
  if ( v5 )
  {
    v7 = PropVariantClear(this + 4);
    if ( v7 >= 0 )
    {
      v7 = PropVariantClear(this + 5);
      if ( v7 >= 0 )
      {
        v7 = PropVariantCopy(this + 4, pvarSrc);
        if ( v7 >= 0 )
        {
          v7 = CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
                 (CWMThumbnailStreamProperty *)this,
                 pvarSrc->pStream,
                 &v33);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(PROPVARIANT *, struct IStream *))(*(_QWORD *)&this->vt + 312LL))(this, v33);
            if ( v7 < 0 )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                CallStackTracing::s_wpInstance = v29;
                if ( v29
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CWMThumbnailStreamProperty::SetShellValue",
                    534,
                    v7);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 51;
                goto LABEL_67;
              }
            }
          }
          else
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != v7 )
                CallStackContext::TraceFailure(v26, "CWMThumbnailStreamProperty::SetShellValue", 532, v7);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 50;
              goto LABEL_67;
            }
          }
        }
        else
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v7 )
              CallStackContext::TraceFailure(v22, "CWMThumbnailStreamProperty::SetShellValue", 530, v7);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 49;
            goto LABEL_67;
          }
        }
      }
      else
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v7 )
            CallStackContext::TraceFailure(v18, "CWMThumbnailStreamProperty::SetShellValue", 528, v7);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 48;
          goto LABEL_67;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != v7 )
          CallStackContext::TraceFailure(v14, "CWMThumbnailStreamProperty::SetShellValue", 527, v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 47;
        goto LABEL_67;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v9 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v9, "CWMThumbnailStreamProperty::SetShellValue", 524, -2147024809);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 46;
LABEL_67:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v7);
    }
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v33);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004d1e0  mov     [rsp+arg_0], rbx
0x18004d1e5  mov     [rsp+arg_18], rbp
0x18004d1ea  push    rsi
0x18004d1eb  push    rdi
0x18004d1ec  push    r15
0x18004d1ee  sub     rsp, 30h
0x18004d1f2  mov     rsi, rdx
0x18004d1f5  lea     r15, aCwmthumbnailst_0; "CWMThumbnailStreamProperty::SetShellVal"...
0x18004d1fc  mov     rdi, rcx
0x18004d1ff  mov     rdx, r15; char *
0x18004d202  mov     r8d, 204h; int
0x18004d208  lea     rcx, [rsp+48h+arg_8]; this
0x18004d20d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004d212  cmp     word ptr [rsi], 42h ; 'B'
0x18004d216  mov     [rsp+48h+arg_10], 0
0x18004d21f  jz      loc_18004D2B5
0x18004d225  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d22c  mov     ebx, 80070057h
0x18004d231  test    rcx, rcx
0x18004d234  jnz     short loc_18004D277
0x18004d236  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d23c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d243  mov     rcx, rax
0x18004d246  test    rax, rax
0x18004d249  jz      short loc_18004D269
0x18004d24b  mov     rax, [rax]
0x18004d24e  mov     edx, 7F0h
0x18004d253  mov     rax, [rax+8]
0x18004d257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d25c  test    eax, eax
0x18004d25e  jz      short loc_18004D269
0x18004d260  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d267  jmp     short loc_18004D277
0x18004d269  lea     rcx, qword_180069A90; this
0x18004d270  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d277  cmp     byte ptr [rcx+8], 0
0x18004d27b  jz      short loc_18004D29E
0x18004d27d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d282  cmp     [rax+7CCh], ebx
0x18004d288  jz      short loc_18004D29E
0x18004d28a  mov     r9d, ebx; int
0x18004d28d  mov     r8d, 20Ch; int
0x18004d293  mov     rdx, r15; char *
0x18004d296  mov     rcx, rax; this
0x18004d299  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d29e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d2a3  cmp     al, 1
0x18004d2a5  jb      loc_18004D5FC
0x18004d2ab  mov     edx, 2Eh ; '.'
0x18004d2b0  jmp     loc_18004D5DE
0x18004d2b5  lea     rcx, [rdi+60h]; pvar
0x18004d2b9  call    cs:__imp_PropVariantClear
0x18004d2bf  mov     ebx, eax
0x18004d2c1  test    eax, eax
0x18004d2c3  jns     loc_18004D354
0x18004d2c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2d0  test    rcx, rcx
0x18004d2d3  jnz     short loc_18004D316
0x18004d2d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d2db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2e2  mov     rcx, rax
0x18004d2e5  test    rax, rax
0x18004d2e8  jz      short loc_18004D308
0x18004d2ea  mov     rax, [rax]
0x18004d2ed  mov     edx, 7F0h
0x18004d2f2  mov     rax, [rax+8]
0x18004d2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d2fb  test    eax, eax
0x18004d2fd  jz      short loc_18004D308
0x18004d2ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d306  jmp     short loc_18004D316
0x18004d308  lea     rcx, qword_180069A90; this
0x18004d30f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d316  cmp     byte ptr [rcx+8], 0
0x18004d31a  jz      short loc_18004D33D
0x18004d31c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d321  cmp     [rax+7CCh], ebx
0x18004d327  jz      short loc_18004D33D
0x18004d329  mov     r9d, ebx; int
0x18004d32c  mov     r8d, 20Fh; int
0x18004d332  mov     rdx, r15; char *
0x18004d335  mov     rcx, rax; this
0x18004d338  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d33d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d342  cmp     al, 1
0x18004d344  jb      loc_18004D5FC
0x18004d34a  mov     edx, 2Fh ; '/'
0x18004d34f  jmp     loc_18004D5DE
0x18004d354  lea     rcx, [rdi+78h]; pvar
0x18004d358  call    cs:__imp_PropVariantClear
0x18004d35e  mov     ebx, eax
0x18004d360  test    eax, eax
0x18004d362  jns     loc_18004D3F3
0x18004d368  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d36f  test    rcx, rcx
0x18004d372  jnz     short loc_18004D3B5
0x18004d374  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d37a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d381  mov     rcx, rax
0x18004d384  test    rax, rax
0x18004d387  jz      short loc_18004D3A7
0x18004d389  mov     rax, [rax]
0x18004d38c  mov     edx, 7F0h
0x18004d391  mov     rax, [rax+8]
0x18004d395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d39a  test    eax, eax
0x18004d39c  jz      short loc_18004D3A7
0x18004d39e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d3a5  jmp     short loc_18004D3B5
0x18004d3a7  lea     rcx, qword_180069A90; this
0x18004d3ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d3b5  cmp     byte ptr [rcx+8], 0
0x18004d3b9  jz      short loc_18004D3DC
0x18004d3bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d3c0  cmp     [rax+7CCh], ebx
0x18004d3c6  jz      short loc_18004D3DC
0x18004d3c8  mov     r9d, ebx; int
0x18004d3cb  mov     r8d, 210h; int
0x18004d3d1  mov     rdx, r15; char *
0x18004d3d4  mov     rcx, rax; this
0x18004d3d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d3dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d3e1  cmp     al, 1
0x18004d3e3  jb      loc_18004D5FC
0x18004d3e9  mov     edx, 30h ; '0'
0x18004d3ee  jmp     loc_18004D5DE
0x18004d3f3  mov     rdx, rsi; pvarSrc
0x18004d3f6  lea     rcx, [rdi+60h]; pvarDest
0x18004d3fa  call    cs:__imp_PropVariantCopy
0x18004d400  mov     ebx, eax
0x18004d402  test    eax, eax
0x18004d404  jns     loc_18004D495
0x18004d40a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d411  test    rcx, rcx
0x18004d414  jnz     short loc_18004D457
0x18004d416  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d41c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d423  mov     rcx, rax
0x18004d426  test    rax, rax
0x18004d429  jz      short loc_18004D449
0x18004d42b  mov     rax, [rax]
0x18004d42e  mov     edx, 7F0h
0x18004d433  mov     rax, [rax+8]
0x18004d437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d43c  test    eax, eax
0x18004d43e  jz      short loc_18004D449
0x18004d440  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d447  jmp     short loc_18004D457
0x18004d449  lea     rcx, qword_180069A90; this
0x18004d450  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d457  cmp     byte ptr [rcx+8], 0
0x18004d45b  jz      short loc_18004D47E
0x18004d45d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d462  cmp     [rax+7CCh], ebx
0x18004d468  jz      short loc_18004D47E
0x18004d46a  mov     r9d, ebx; int
0x18004d46d  mov     r8d, 212h; int
0x18004d473  mov     rdx, r15; char *
0x18004d476  mov     rcx, rax; this
0x18004d479  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d47e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d483  cmp     al, 1
0x18004d485  jb      loc_18004D5FC
0x18004d48b  mov     edx, 31h ; '1'
0x18004d490  jmp     loc_18004D5DE
0x18004d495  mov     rdx, [rsi+8]; struct IStream *
0x18004d499  lea     r8, [rsp+48h+arg_10]; struct IStream **
0x18004d49e  mov     rcx, rdi; this
0x18004d4a1  call    ?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z; CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)
0x18004d4a6  mov     ebx, eax
0x18004d4a8  test    eax, eax
0x18004d4aa  jns     loc_18004D53B
0x18004d4b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d4b7  test    rcx, rcx
0x18004d4ba  jnz     short loc_18004D4FD
0x18004d4bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d4c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d4c9  mov     rcx, rax
0x18004d4cc  test    rax, rax
0x18004d4cf  jz      short loc_18004D4EF
0x18004d4d1  mov     rax, [rax]
0x18004d4d4  mov     edx, 7F0h
0x18004d4d9  mov     rax, [rax+8]
0x18004d4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4e2  test    eax, eax
0x18004d4e4  jz      short loc_18004D4EF
0x18004d4e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d4ed  jmp     short loc_18004D4FD
0x18004d4ef  lea     rcx, qword_180069A90; this
0x18004d4f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d4fd  cmp     byte ptr [rcx+8], 0
0x18004d501  jz      short loc_18004D524
0x18004d503  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d508  cmp     [rax+7CCh], ebx
0x18004d50e  jz      short loc_18004D524
0x18004d510  mov     r9d, ebx; int
0x18004d513  mov     r8d, 214h; int
0x18004d519  mov     rdx, r15; char *
0x18004d51c  mov     rcx, rax; this
0x18004d51f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d524  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d529  cmp     al, 1
0x18004d52b  jb      loc_18004D5FC
0x18004d531  mov     edx, 32h ; '2'
0x18004d536  jmp     loc_18004D5DE
0x18004d53b  mov     rax, [rdi]
0x18004d53e  mov     rcx, rdi
0x18004d541  mov     rdx, [rsp+48h+arg_10]
0x18004d546  mov     rax, [rax+138h]
0x18004d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d552  mov     ebx, eax
0x18004d554  test    eax, eax
0x18004d556  jns     loc_18004D5FC
0x18004d55c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d563  test    rcx, rcx
0x18004d566  jnz     short loc_18004D5A9
0x18004d568  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d56e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d575  mov     rcx, rax
0x18004d578  test    rax, rax
0x18004d57b  jz      short loc_18004D59B
0x18004d57d  mov     rax, [rax]
0x18004d580  mov     edx, 7F0h
0x18004d585  mov     rax, [rax+8]
0x18004d589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d58e  test    eax, eax
0x18004d590  jz      short loc_18004D59B
0x18004d592  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d599  jmp     short loc_18004D5A9
0x18004d59b  lea     rcx, qword_180069A90; this
0x18004d5a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d5a9  cmp     byte ptr [rcx+8], 0
0x18004d5ad  jz      short loc_18004D5D0
0x18004d5af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d5b4  cmp     [rax+7CCh], ebx
0x18004d5ba  jz      short loc_18004D5D0
0x18004d5bc  mov     r9d, ebx; int
0x18004d5bf  mov     r8d, 216h; int
0x18004d5c5  mov     rdx, r15; char *
0x18004d5c8  mov     rcx, rax; this
0x18004d5cb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d5d0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004d5d5  cmp     al, 1
0x18004d5d7  jb      short loc_18004D5FC
0x18004d5d9  mov     edx, 33h ; '3'
0x18004d5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d5e5  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18004d5ec  mov     r9, rdi
0x18004d5ef  mov     [rsp+48h+var_28], ebx
0x18004d5f3  mov     rcx, [rcx+10h]
0x18004d5f7  call    WPP_SF_qd
0x18004d5fc  lea     rcx, [rsp+48h+arg_10]
0x18004d601  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18004d606  lea     rcx, [rsp+48h+arg_8]; this
0x18004d60b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004d610  mov     rbp, [rsp+48h+arg_18]
0x18004d615  mov     eax, ebx
0x18004d617  mov     rbx, [rsp+48h+arg_0]
0x18004d61c  add     rsp, 30h
0x18004d620  pop     r15
0x18004d622  pop     rdi
0x18004d623  pop     rsi
0x18004d624  retn
```
