# CTranscodeEngine::CreateInstance(MFTranscodeEngineSettings const &,IMFTranscodeProfile *,IMFTranscodeEngine * *)

- ea: `0x18002c348`
- end: `0x18002c7d1`
- name: `?CreateInstance@CTranscodeEngine@@SAJAEBUMFTranscodeEngineSettings@@PEAUIMFTranscodeProfile@@PEAPEAUIMFTranscodeEngine@@@Z`
- size: `1161`
- prototype: `__int64 __fastcall(const struct MFTranscodeEngineSettings *, struct IMFTranscodeProfile *, struct IMFTranscodeEngine **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031110`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x180017074`
- `0x18001a330`
- `0x18001c050`
- `0x18001c280`
- `0x18001c9e8`
- `0x18002bce4`
- `0x18002c348`
- `0x18002cae4`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c3c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c47a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c52d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c5da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c70a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c3c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c47a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c52d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c5da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c70a`

## string_xrefs

- `0x18002c35d`: `CTranscodeEngine::CreateInstance`

## pseudocode

```c
__int64 __fastcall CTranscodeEngine::CreateInstance(
        const struct MFTranscodeEngineSettings *a1,
        struct IMFTranscodeProfile *a2,
        struct IMFTranscodeEngine **a3)
{
  __int64 v6; // rdx
  Windows::Media *v7; // rcx
  HRESULT v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  struct IMFTranscodeProfile *v21; // rbx
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CTranscodeEngine *v26; // rax
  __int64 v27; // rdx
  CTranscodeEngine *v28; // rax
  CTranscodeEngine *v29; // r8
  __int64 v30; // r9
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  IMFTranscodeProfile *ppTranscodeProfile; // [rsp+50h] [rbp+8h] BYREF
  CTranscodeEngine *v39; // [rsp+60h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppTranscodeProfile,
    "CTranscodeEngine::CreateInstance",
    48);
  v39 = 0;
  ComSmartPtr<IMFTranscodeProfile>::ComSmartPtr<IMFTranscodeProfile>(&ppTranscodeProfile, a2);
  *a3 = 0;
  if ( *((_QWORD *)a1 + 3) || (v8 = Windows::Media::Report(v7, v6), v8 >= 0) )
  {
    if ( *(__int64 *)a1 <= 0
      || (v13 = *((_QWORD *)a1 + 1), v13 <= 0)
      || *(_QWORD *)a1 <= v13
      || (v8 = Windows::Media::Report(v7, v6), v8 >= 0) )
    {
      if ( *(_QWORD *)a1 != 0x7FFFFFFFFFFFFFFFLL && *((_QWORD *)a1 + 1) != 0x7FFFFFFFFFFFFFFFLL
        || (v8 = Windows::Media::Report(v7, v6), v8 >= 0) )
      {
        v21 = ppTranscodeProfile;
        if ( !ppTranscodeProfile )
        {
          v8 = MFCreateTranscodeProfile(&ppTranscodeProfile);
          if ( v8 < 0 )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeEngine::CreateInstance", 81, v8);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v12 = 14;
              goto LABEL_69;
            }
            goto LABEL_70;
          }
          v21 = ppTranscodeProfile;
        }
        v26 = (CTranscodeEngine *)operator new(0x2B8u);
        if ( v26 && (v28 = CTranscodeEngine::CTranscodeEngine(v26, a1, v21), v39 = v28, (v29 = v28) != 0) )
        {
          *((_QWORD *)v28 + 80) = 0;
          if ( !*((_QWORD *)v28 + 29) )
          {
            *((_DWORD *)v28 + 60) = 1;
            v30 = 0;
            v31 = (_QWORD *)((char *)v28 + 248);
            *((_QWORD *)v29 + 29) = v31;
            *v31 = 0;
            do
            {
              v32 = v30 + 2 * v30 + 1;
              ++v30;
              v33 = *((_QWORD *)v29 + 29) + 8 * v32;
              *(_QWORD *)(v33 + 8) = *((_QWORD *)v29 + 28);
              *((_QWORD *)v29 + 28) = v33;
            }
            while ( v30 != 16 );
          }
          v8 = 0;
          v39 = 0;
          *a3 = v29;
        }
        else
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          v8 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v34 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v34 + 8) )
          {
            v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
            if ( *((_DWORD *)v36 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v36, "CTranscodeEngine::CreateInstance", 85, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v12 = 15;
            goto LABEL_69;
          }
        }
        goto LABEL_70;
      }
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != v8 )
          CallStackContext::TraceFailure(v20, "CTranscodeEngine::CreateInstance", 76, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 13;
        goto LABEL_69;
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CTranscodeEngine::CreateInstance", 70, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 12;
        goto LABEL_69;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
        CallStackContext::TraceFailure(v11, "CTranscodeEngine::CreateInstance", 56, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 11;
LABEL_69:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids, 0, v8);
    }
  }
LABEL_70:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppTranscodeProfile);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v39);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppTranscodeProfile);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c348  mov     [rsp+arg_8], rbx
0x18002c34d  mov     [rsp+arg_18], rbp
0x18002c352  push    rsi
0x18002c353  push    rdi
0x18002c354  push    r14
0x18002c356  sub     rsp, 30h
0x18002c35a  mov     rsi, r8
0x18002c35d  lea     r14, aCtranscodeengi_27; "CTranscodeEngine::CreateInstance"
0x18002c364  mov     rbx, rdx
0x18002c367  mov     rdi, rcx
0x18002c36a  mov     rdx, r14; char *
0x18002c36d  lea     rcx, [rsp+48h+ppTranscodeProfile]; this
0x18002c372  mov     r8d, 30h ; '0'; int
0x18002c378  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002c37d  xor     ebp, ebp
0x18002c37f  lea     rcx, [rsp+48h+ppTranscodeProfile]
0x18002c384  mov     rdx, rbx
0x18002c387  mov     [rsp+48h+arg_10], rbp
0x18002c38c  call    ??0?$ComSmartPtr@UIMFTranscodeProfile@@@@QEAA@PEAUIMFTranscodeProfile@@@Z; ComSmartPtr<IMFTranscodeProfile>::ComSmartPtr<IMFTranscodeProfile>(IMFTranscodeProfile *)
0x18002c391  mov     [rsi], rbp
0x18002c394  cmp     [rdi+18h], ebp
0x18002c397  jnz     loc_18002C440
0x18002c39d  cmp     [rdi+1Ch], ebp
0x18002c3a0  jnz     loc_18002C440
0x18002c3a6  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x18002c3ab  mov     ebx, eax
0x18002c3ad  test    eax, eax
0x18002c3af  jns     loc_18002C440
0x18002c3b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c3bc  test    rcx, rcx
0x18002c3bf  jnz     short loc_18002C402
0x18002c3c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c3c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c3ce  mov     rcx, rax
0x18002c3d1  test    rax, rax
0x18002c3d4  jz      short loc_18002C3F4
0x18002c3d6  mov     rax, [rax]
0x18002c3d9  mov     edx, 7F0h
0x18002c3de  mov     rax, [rax+8]
0x18002c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3e7  test    eax, eax
0x18002c3e9  jz      short loc_18002C3F4
0x18002c3eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c3f2  jmp     short loc_18002C402
0x18002c3f4  lea     rcx, qword_180069A90; this
0x18002c3fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c402  cmp     [rcx+8], bpl
0x18002c406  jz      short loc_18002C429
0x18002c408  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c40d  cmp     [rax+7CCh], ebx
0x18002c413  jz      short loc_18002C429
0x18002c415  mov     r9d, ebx; int
0x18002c418  mov     r8d, 38h ; '8'; int
0x18002c41e  mov     rdx, r14; char *
0x18002c421  mov     rcx, rax; this
0x18002c424  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c429  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c42e  cmp     al, 1
0x18002c430  jb      loc_18002C79E
0x18002c436  mov     edx, 0Bh
0x18002c43b  jmp     loc_18002C780
0x18002c440  cmp     [rdi], rbp
0x18002c443  jle     loc_18002C4F9
0x18002c449  mov     rax, [rdi+8]
0x18002c44d  test    rax, rax
0x18002c450  jle     loc_18002C4F9
0x18002c456  cmp     [rdi], rax
0x18002c459  jle     loc_18002C4F9
0x18002c45f  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x18002c464  mov     ebx, eax
0x18002c466  test    eax, eax
0x18002c468  jns     loc_18002C4F9
0x18002c46e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c475  test    rcx, rcx
0x18002c478  jnz     short loc_18002C4BB
0x18002c47a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c480  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c487  mov     rcx, rax
0x18002c48a  test    rax, rax
0x18002c48d  jz      short loc_18002C4AD
0x18002c48f  mov     rax, [rax]
0x18002c492  mov     edx, 7F0h
0x18002c497  mov     rax, [rax+8]
0x18002c49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4a0  test    eax, eax
0x18002c4a2  jz      short loc_18002C4AD
0x18002c4a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c4ab  jmp     short loc_18002C4BB
0x18002c4ad  lea     rcx, qword_180069A90; this
0x18002c4b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c4bb  cmp     [rcx+8], bpl
0x18002c4bf  jz      short loc_18002C4E2
0x18002c4c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c4c6  cmp     [rax+7CCh], ebx
0x18002c4cc  jz      short loc_18002C4E2
0x18002c4ce  mov     r9d, ebx; int
0x18002c4d1  mov     r8d, 46h ; 'F'; int
0x18002c4d7  mov     rdx, r14; char *
0x18002c4da  mov     rcx, rax; this
0x18002c4dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c4e2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c4e7  cmp     al, 1
0x18002c4e9  jb      loc_18002C79E
0x18002c4ef  mov     edx, 0Ch
0x18002c4f4  jmp     loc_18002C780
0x18002c4f9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002c503  cmp     [rdi], rax
0x18002c506  jge     short loc_18002C512
0x18002c508  cmp     [rdi+8], rax
0x18002c50c  jl      loc_18002C5AC
0x18002c512  call    ?Report@Media@Windows@@YAJJ@Z; Windows::Media::Report(long)
0x18002c517  mov     ebx, eax
0x18002c519  test    eax, eax
0x18002c51b  jns     loc_18002C5AC
0x18002c521  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c528  test    rcx, rcx
0x18002c52b  jnz     short loc_18002C56E
0x18002c52d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c533  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c53a  mov     rcx, rax
0x18002c53d  test    rax, rax
0x18002c540  jz      short loc_18002C560
0x18002c542  mov     rax, [rax]
0x18002c545  mov     edx, 7F0h
0x18002c54a  mov     rax, [rax+8]
0x18002c54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c553  test    eax, eax
0x18002c555  jz      short loc_18002C560
0x18002c557  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c55e  jmp     short loc_18002C56E
0x18002c560  lea     rcx, qword_180069A90; this
0x18002c567  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c56e  cmp     [rcx+8], bpl
0x18002c572  jz      short loc_18002C595
0x18002c574  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c579  cmp     [rax+7CCh], ebx
0x18002c57f  jz      short loc_18002C595
0x18002c581  mov     r9d, ebx; int
0x18002c584  mov     r8d, 4Ch ; 'L'; int
0x18002c58a  mov     rdx, r14; char *
0x18002c58d  mov     rcx, rax; this
0x18002c590  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c595  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c59a  cmp     al, 1
0x18002c59c  jb      loc_18002C79E
0x18002c5a2  mov     edx, 0Dh
0x18002c5a7  jmp     loc_18002C780
0x18002c5ac  mov     rbx, [rsp+48h+ppTranscodeProfile]
0x18002c5b1  test    rbx, rbx
0x18002c5b4  jnz     loc_18002C65E
0x18002c5ba  lea     rcx, [rsp+48h+ppTranscodeProfile]; ppTranscodeProfile
0x18002c5bf  call    MFCreateTranscodeProfile
0x18002c5c4  mov     ebx, eax
0x18002c5c6  test    eax, eax
0x18002c5c8  jns     loc_18002C659
0x18002c5ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5d5  test    rcx, rcx
0x18002c5d8  jnz     short loc_18002C61B
0x18002c5da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c5e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5e7  mov     rcx, rax
0x18002c5ea  test    rax, rax
0x18002c5ed  jz      short loc_18002C60D
0x18002c5ef  mov     rax, [rax]
0x18002c5f2  mov     edx, 7F0h
0x18002c5f7  mov     rax, [rax+8]
0x18002c5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c600  test    eax, eax
0x18002c602  jz      short loc_18002C60D
0x18002c604  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c60b  jmp     short loc_18002C61B
0x18002c60d  lea     rcx, qword_180069A90; this
0x18002c614  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c61b  cmp     [rcx+8], bpl
0x18002c61f  jz      short loc_18002C642
0x18002c621  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c626  cmp     [rax+7CCh], ebx
0x18002c62c  jz      short loc_18002C642
0x18002c62e  mov     r9d, ebx; int
0x18002c631  mov     r8d, 51h ; 'Q'; int
0x18002c637  mov     rdx, r14; char *
0x18002c63a  mov     rcx, rax; this
0x18002c63d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c642  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c647  cmp     al, 1
0x18002c649  jb      loc_18002C79E
0x18002c64f  mov     edx, 0Eh
0x18002c654  jmp     loc_18002C780
0x18002c659  mov     rbx, [rsp+48h+ppTranscodeProfile]
0x18002c65e  mov     ecx, 2B8h; Size
0x18002c663  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c668  test    rax, rax
0x18002c66b  jz      loc_18002C6F9
0x18002c671  mov     r8, rbx; struct IMFTranscodeProfile *
0x18002c674  mov     rdx, rdi; struct MFTranscodeEngineSettings *
0x18002c677  mov     rcx, rax; this
0x18002c67a  call    ??0CTranscodeEngine@@IEAA@AEBUMFTranscodeEngineSettings@@PEAUIMFTranscodeProfile@@@Z; CTranscodeEngine::CTranscodeEngine(MFTranscodeEngineSettings const &,IMFTranscodeProfile *)
0x18002c67f  mov     [rsp+48h+arg_10], rax
0x18002c684  mov     r8, rax
0x18002c687  test    rax, rax
0x18002c68a  jz      short loc_18002C6F9
0x18002c68c  mov     [rax+280h], rbp
0x18002c693  cmp     [rax+0E8h], rbp
0x18002c69a  jnz     short loc_18002C6EA
0x18002c69c  mov     dword ptr [rax+0F0h], 1
0x18002c6a6  mov     r9, rbp
0x18002c6a9  add     rax, 0F8h
0x18002c6af  mov     [r8+0E8h], rax
0x18002c6b6  mov     [rax], rbp
0x18002c6b9  mov     rax, [r8+0E8h]
0x18002c6c0  lea     rdx, ds:1[r9*2]
0x18002c6c8  add     rdx, r9
0x18002c6cb  inc     r9
0x18002c6ce  lea     rdx, [rax+rdx*8]
0x18002c6d2  mov     rax, [r8+0E0h]
0x18002c6d9  mov     [rdx+8], rax
0x18002c6dd  mov     [r8+0E0h], rdx
0x18002c6e4  cmp     r9, 10h
0x18002c6e8  jnz     short loc_18002C6B9
0x18002c6ea  mov     ebx, ebp
0x18002c6ec  mov     [rsp+48h+arg_10], rbp
0x18002c6f1  mov     [rsi], r8
0x18002c6f4  jmp     loc_18002C79E
0x18002c6f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c700  mov     ebx, 8007000Eh
0x18002c705  test    rcx, rcx
0x18002c708  jnz     short loc_18002C74B
0x18002c70a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c710  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c717  mov     rcx, rax
0x18002c71a  test    rax, rax
0x18002c71d  jz      short loc_18002C73D
0x18002c71f  mov     rax, [rax]
0x18002c722  mov     edx, 7F0h
0x18002c727  mov     rax, [rax+8]
0x18002c72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c730  test    eax, eax
0x18002c732  jz      short loc_18002C73D
0x18002c734  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c73b  jmp     short loc_18002C74B
0x18002c73d  lea     rcx, qword_180069A90; this
0x18002c744  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c74b  cmp     [rcx+8], bpl
0x18002c74f  jz      short loc_18002C772
0x18002c751  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c756  cmp     [rax+7CCh], ebx
0x18002c75c  jz      short loc_18002C772
0x18002c75e  mov     r9d, ebx; int
0x18002c761  mov     r8d, 55h ; 'U'; int
0x18002c767  mov     rdx, r14; char *
0x18002c76a  mov     rcx, rax; this
0x18002c76d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c772  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002c777  cmp     al, 1
0x18002c779  jb      short loc_18002C79E
0x18002c77b  mov     edx, 0Fh
0x18002c780  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c787  lea     r8, WPP_e568207c201a3850f272ae9c45155cdf_Traceguids
0x18002c78e  xor     r9d, r9d
0x18002c791  mov     [rsp+48h+var_28], ebx
0x18002c795  mov     rcx, [rcx+10h]
0x18002c799  call    WPP_SF_qd
0x18002c79e  lea     rcx, [rsp+48h+ppTranscodeProfile]
0x18002c7a3  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002c7a8  lea     rcx, [rsp+48h+arg_10]
0x18002c7ad  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002c7b2  lea     rcx, [rsp+48h+ppTranscodeProfile]; this
0x18002c7b7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002c7bc  mov     rbp, [rsp+48h+arg_18]
0x18002c7c1  mov     eax, ebx
0x18002c7c3  mov     rbx, [rsp+48h+arg_8]
0x18002c7c8  add     rsp, 30h
0x18002c7cc  pop     r14
0x18002c7ce  pop     rdi
0x18002c7cf  pop     rsi
0x18002c7d0  retn
```
