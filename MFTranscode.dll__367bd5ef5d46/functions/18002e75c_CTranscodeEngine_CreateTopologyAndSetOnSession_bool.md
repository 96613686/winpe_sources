# CTranscodeEngine::_CreateTopologyAndSetOnSession(bool)

- ea: `0x18002e75c`
- end: `0x18002ef04`
- name: `?_CreateTopologyAndSetOnSession@CTranscodeEngine@@IEAAJ_N@Z`
- size: `1960`
- prototype: `__int64 __fastcall(CTranscodeEngine *__hidden this, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180010630`
- `0x180010bcc`
- `0x18002ff18`

## callees

- `0x1800019a0`
- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x18002e75c`
- `0x18002f314`
- `0x180030244`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e7f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e8a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e95f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eab9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ec1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ecc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ed7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ee2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e7f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e8a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e95f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eab9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ec1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ecc9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ed7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ee2c`
- `MFPlat!MFCreateAttributes` at `0x18002e886`
- `MFPlat!MFCreateAttributes` at `0x18002e886`
- `MFCORE!MFCreateMediaSession` at `0x18002eb4d`
- `MFCORE!MFCreateMediaSession` at `0x18002eb4d`

## string_xrefs

- `0x18002e7a9`: `CTranscodeEngine::_CreateTopologyAndSetOnSession`

## pseudocode

```c
__int64 __fastcall CTranscodeEngine::_CreateTopologyAndSetOnSession(CTranscodeEngine *this, char a2)
{
  char v4; // si
  __int64 v5; // rdx
  int inserted; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
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
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  _BYTE v48[8]; // [rsp+30h] [rbp-48h] BYREF
  struct IMFTopology *v49; // [rsp+38h] [rbp-40h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-38h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, char *); // [rsp+48h] [rbp-30h] BYREF
  __int128 v52; // [rsp+50h] [rbp-28h] BYREF

  v49 = 0;
  v51 = 0;
  ppMFAttributes = 0;
  if ( *((_QWORD *)this + 7) || (v4 = 0, *((_QWORD *)this + 8)) )
    v4 = 1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v48,
    "CTranscodeEngine::_CreateTopologyAndSetOnSession",
    830);
  inserted = MFCreateTranscodeTopologyFromByteStream(
               *((_QWORD *)this + 22),
               *((_QWORD *)this + 17),
               *((struct IMFTranscodeProfile **)this + 19),
               &v49);
  if ( inserted < 0 )
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != inserted )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeEngine::_CreateTopologyAndSetOnSession",
          830,
          inserted);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 105;
LABEL_118:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids,
        this,
        inserted);
      goto LABEL_119;
    }
    goto LABEL_119;
  }
  if ( a2 )
  {
LABEL_38:
    if ( v4 && (inserted = CTranscodeEngine::_SetTrimPoints(this, v49), inserted < 0) )
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
        if ( *((_DWORD *)v22 + 499) != inserted )
          CallStackContext::TraceFailure(v22, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 843, inserted);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 108;
        goto LABEL_118;
      }
    }
    else if ( *((_DWORD *)this + 166) && (inserted = CTranscodeEngine::_InsertEffects(this, v49), inserted < 0) )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
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
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != inserted )
          CallStackContext::TraceFailure(v26, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 848, inserted);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 109;
        goto LABEL_118;
      }
    }
    else if ( a2 || (inserted = MFCreateMediaSession(ppMFAttributes, (IMFMediaSession **)this + 21), inserted >= 0) )
    {
      inserted = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 21) + 32LL))(
                   *((_QWORD *)this + 21),
                   (char *)this + 688,
                   0);
      if ( inserted >= 0 )
      {
        inserted = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))(**((_QWORD **)this + 21) + 112LL))(
                     *((_QWORD *)this + 21),
                     &v51);
        if ( inserted >= 0 )
        {
          inserted = (**v51)(v51, &GUID_868ce85c_8ea9_4f55_ab82_b009a910a805, (char *)this + 184);
          if ( inserted >= 0 )
          {
            inserted = (*(__int64 (__fastcall **)(_QWORD, __int64, struct IMFTopology *))(**((_QWORD **)this + 21) + 56LL))(
                         *((_QWORD *)this + 21),
                         1,
                         v49);
            if ( inserted < 0 )
            {
              v44 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
                CallStackTracing::s_wpInstance = v45;
                if ( v45
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
                {
                  v44 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v44 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v44 + 8) )
              {
                v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                if ( *((_DWORD *)v46 + 499) != inserted )
                  CallStackContext::TraceFailure(v46, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 861, inserted);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 114;
                goto LABEL_118;
              }
            }
          }
          else
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
              CallStackTracing::s_wpInstance = v41;
              if ( v41
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
              {
                v40 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v40 + 8) )
            {
              v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
              if ( *((_DWORD *)v42 + 499) != inserted )
                CallStackContext::TraceFailure(v42, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 859, inserted);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 113;
              goto LABEL_118;
            }
          }
        }
        else
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != inserted )
              CallStackContext::TraceFailure(v38, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 858, inserted);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 112;
            goto LABEL_118;
          }
        }
      }
      else
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != inserted )
            CallStackContext::TraceFailure(v34, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 856, inserted);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 111;
          goto LABEL_118;
        }
      }
    }
    else
    {
      v28 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
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
        if ( *((_DWORD *)v30 + 499) != inserted )
          CallStackContext::TraceFailure(v30, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 853, inserted);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 110;
        goto LABEL_118;
      }
    }
    goto LABEL_119;
  }
  inserted = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( inserted >= 0 )
  {
    v52 = *(_OWORD *)((char *)this + 92);
    inserted = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int128 *))ppMFAttributes->lpVtbl->SetGUID)(
                 ppMFAttributes,
                 MEDIA_TELEMETRY_SESSION_ID,
                 &v52);
    if ( inserted < 0 )
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
        if ( *((_DWORD *)v18 + 499) != inserted )
          CallStackContext::TraceFailure(v18, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 838, inserted);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 107;
        goto LABEL_118;
      }
      goto LABEL_119;
    }
    goto LABEL_38;
  }
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
    if ( *((_DWORD *)v14 + 499) != inserted )
      CallStackContext::TraceFailure(v14, "CTranscodeEngine::_CreateTopologyAndSetOnSession", 834, inserted);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v10 = 106;
    goto LABEL_118;
  }
LABEL_119:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFAttributes);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v51);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v49);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002e75c  push    rbp
0x18002e75e  push    rbx
0x18002e75f  push    rsi
0x18002e760  push    rdi
0x18002e761  push    r12
0x18002e763  push    r13
0x18002e765  push    r14
0x18002e767  push    r15
0x18002e769  mov     rbp, rsp
0x18002e76c  sub     rsp, 78h
0x18002e770  mov     rax, cs:__security_cookie
0x18002e777  xor     rax, rsp
0x18002e77a  mov     [rbp+var_18], rax
0x18002e77e  xor     r15d, r15d
0x18002e781  mov     r14b, dl
0x18002e784  mov     rdi, rcx
0x18002e787  mov     [rbp+var_40], r15
0x18002e78b  mov     [rbp+var_30], r15
0x18002e78f  mov     [rbp+ppMFAttributes], r15
0x18002e793  lea     r12d, [r15+1]
0x18002e797  cmp     [rcx+38h], r15
0x18002e79b  jnz     short loc_18002E7A6
0x18002e79d  mov     sil, r15b
0x18002e7a0  cmp     [rcx+40h], r15
0x18002e7a4  jz      short loc_18002E7A9
0x18002e7a6  mov     sil, r12b
0x18002e7a9  lea     r13, aCtranscodeengi_18; "CTranscodeEngine::_CreateTopologyAndSet"...
0x18002e7b0  mov     r8d, 33Eh; int
0x18002e7b6  mov     rdx, r13; char *
0x18002e7b9  lea     rcx, [rbp+var_48]; this
0x18002e7bd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002e7c2  mov     r8, [rdi+98h]
0x18002e7c9  lea     r9, [rbp+var_40]
0x18002e7cd  mov     rdx, [rdi+88h]
0x18002e7d4  mov     rcx, [rdi+0B0h]
0x18002e7db  call    MFCreateTranscodeTopologyFromByteStream
0x18002e7e0  mov     ebx, eax
0x18002e7e2  test    eax, eax
0x18002e7e4  jns     loc_18002E876
0x18002e7ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e7f1  test    rcx, rcx
0x18002e7f4  jnz     short loc_18002E837
0x18002e7f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e7fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e803  mov     rcx, rax
0x18002e806  test    rax, rax
0x18002e809  jz      short loc_18002E829
0x18002e80b  mov     rax, [rax]
0x18002e80e  mov     edx, 7F0h
0x18002e813  mov     rax, [rax+8]
0x18002e817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e81c  test    eax, eax
0x18002e81e  jz      short loc_18002E829
0x18002e820  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e827  jmp     short loc_18002E837
0x18002e829  lea     rcx, qword_180069A90; this
0x18002e830  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e837  cmp     [rcx+8], r15b
0x18002e83b  jz      short loc_18002E85E
0x18002e83d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e842  cmp     [rax+7CCh], ebx
0x18002e848  jz      short loc_18002E85E
0x18002e84a  mov     r9d, ebx; int
0x18002e84d  mov     r8d, 33Eh; int
0x18002e853  mov     rdx, r13; char *
0x18002e856  mov     rcx, rax; this
0x18002e859  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e85e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e863  cmp     al, r12b
0x18002e866  jb      loc_18002EEC1
0x18002e86c  mov     edx, 69h ; 'i'
0x18002e871  jmp     loc_18002EEA3
0x18002e876  test    r14b, r14b
0x18002e879  jnz     loc_18002E9DF
0x18002e87f  mov     edx, r12d; cInitialSize
0x18002e882  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002e886  call    cs:__imp_MFCreateAttributes
0x18002e88c  mov     ebx, eax
0x18002e88e  test    eax, eax
0x18002e890  jns     loc_18002E922
0x18002e896  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e89d  test    rcx, rcx
0x18002e8a0  jnz     short loc_18002E8E3
0x18002e8a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e8a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8af  mov     rcx, rax
0x18002e8b2  test    rax, rax
0x18002e8b5  jz      short loc_18002E8D5
0x18002e8b7  mov     rax, [rax]
0x18002e8ba  mov     edx, 7F0h
0x18002e8bf  mov     rax, [rax+8]
0x18002e8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c8  test    eax, eax
0x18002e8ca  jz      short loc_18002E8D5
0x18002e8cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8d3  jmp     short loc_18002E8E3
0x18002e8d5  lea     rcx, qword_180069A90; this
0x18002e8dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e8e3  cmp     [rcx+8], r15b
0x18002e8e7  jz      short loc_18002E90A
0x18002e8e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e8ee  cmp     [rax+7CCh], ebx
0x18002e8f4  jz      short loc_18002E90A
0x18002e8f6  mov     r9d, ebx; int
0x18002e8f9  mov     r8d, 342h; int
0x18002e8ff  mov     rdx, r13; char *
0x18002e902  mov     rcx, rax; this
0x18002e905  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e90a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e90f  cmp     al, r12b
0x18002e912  jb      loc_18002EEC1
0x18002e918  mov     edx, 6Ah ; 'j'
0x18002e91d  jmp     loc_18002EEA3
0x18002e922  movups  xmm0, xmmword ptr [rdi+5Ch]
0x18002e926  mov     rcx, [rbp+ppMFAttributes]
0x18002e92a  lea     r8, [rbp+var_28]
0x18002e92e  lea     rdx, MEDIA_TELEMETRY_SESSION_ID
0x18002e935  movdqu  [rbp+var_28], xmm0
0x18002e93a  mov     rax, [rcx]
0x18002e93d  mov     rax, [rax+0C0h]
0x18002e944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e949  mov     ebx, eax
0x18002e94b  test    eax, eax
0x18002e94d  jns     loc_18002E9DF
0x18002e953  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e95a  test    rcx, rcx
0x18002e95d  jnz     short loc_18002E9A0
0x18002e95f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e965  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e96c  mov     rcx, rax
0x18002e96f  test    rax, rax
0x18002e972  jz      short loc_18002E992
0x18002e974  mov     rax, [rax]
0x18002e977  mov     edx, 7F0h
0x18002e97c  mov     rax, [rax+8]
0x18002e980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e985  test    eax, eax
0x18002e987  jz      short loc_18002E992
0x18002e989  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e990  jmp     short loc_18002E9A0
0x18002e992  lea     rcx, qword_180069A90; this
0x18002e999  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e9a0  cmp     [rcx+8], r15b
0x18002e9a4  jz      short loc_18002E9C7
0x18002e9a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e9ab  cmp     [rax+7CCh], ebx
0x18002e9b1  jz      short loc_18002E9C7
0x18002e9b3  mov     r9d, ebx; int
0x18002e9b6  mov     r8d, 346h; int
0x18002e9bc  mov     rdx, r13; char *
0x18002e9bf  mov     rcx, rax; this
0x18002e9c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e9c7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e9cc  cmp     al, r12b
0x18002e9cf  jb      loc_18002EEC1
0x18002e9d5  mov     edx, 6Bh ; 'k'
0x18002e9da  jmp     loc_18002EEA3
0x18002e9df  test    sil, sil
0x18002e9e2  jz      loc_18002EA8A
0x18002e9e8  mov     rdx, [rbp+var_40]; struct IMFTopology *
0x18002e9ec  mov     rcx, rdi; this
0x18002e9ef  call    ?_SetTrimPoints@CTranscodeEngine@@IEAAJPEAUIMFTopology@@@Z; CTranscodeEngine::_SetTrimPoints(IMFTopology *)
0x18002e9f4  mov     ebx, eax
0x18002e9f6  test    eax, eax
0x18002e9f8  jns     loc_18002EA8A
0x18002e9fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea05  test    rcx, rcx
0x18002ea08  jnz     short loc_18002EA4B
0x18002ea0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002ea10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea17  mov     rcx, rax
0x18002ea1a  test    rax, rax
0x18002ea1d  jz      short loc_18002EA3D
0x18002ea1f  mov     rax, [rax]
0x18002ea22  mov     edx, 7F0h
0x18002ea27  mov     rax, [rax+8]
0x18002ea2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea30  test    eax, eax
0x18002ea32  jz      short loc_18002EA3D
0x18002ea34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea3b  jmp     short loc_18002EA4B
0x18002ea3d  lea     rcx, qword_180069A90; this
0x18002ea44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ea4b  cmp     [rcx+8], r15b
0x18002ea4f  jz      short loc_18002EA72
0x18002ea51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002ea56  cmp     [rax+7CCh], ebx
0x18002ea5c  jz      short loc_18002EA72
0x18002ea5e  mov     r9d, ebx; int
0x18002ea61  mov     r8d, 34Bh; int
0x18002ea67  mov     rdx, r13; char *
0x18002ea6a  mov     rcx, rax; this
0x18002ea6d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002ea72  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ea77  cmp     al, r12b
0x18002ea7a  jb      loc_18002EEC1
0x18002ea80  mov     edx, 6Ch ; 'l'
0x18002ea85  jmp     loc_18002EEA3
0x18002ea8a  cmp     [rdi+298h], r15d
0x18002ea91  jz      loc_18002EB39
0x18002ea97  mov     rdx, [rbp+var_40]; struct IMFTopology *
0x18002ea9b  mov     rcx, rdi; this
0x18002ea9e  call    ?_InsertEffects@CTranscodeEngine@@IEAAJPEAUIMFTopology@@@Z; CTranscodeEngine::_InsertEffects(IMFTopology *)
0x18002eaa3  mov     ebx, eax
0x18002eaa5  test    eax, eax
0x18002eaa7  jns     loc_18002EB39
0x18002eaad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eab4  test    rcx, rcx
0x18002eab7  jnz     short loc_18002EAFA
0x18002eab9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002eabf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eac6  mov     rcx, rax
0x18002eac9  test    rax, rax
0x18002eacc  jz      short loc_18002EAEC
0x18002eace  mov     rax, [rax]
0x18002ead1  mov     edx, 7F0h
0x18002ead6  mov     rax, [rax+8]
0x18002eada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eadf  test    eax, eax
0x18002eae1  jz      short loc_18002EAEC
0x18002eae3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eaea  jmp     short loc_18002EAFA
0x18002eaec  lea     rcx, qword_180069A90; this
0x18002eaf3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eafa  cmp     [rcx+8], r15b
0x18002eafe  jz      short loc_18002EB21
0x18002eb00  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002eb05  cmp     [rax+7CCh], ebx
0x18002eb0b  jz      short loc_18002EB21
0x18002eb0d  mov     r9d, ebx; int
0x18002eb10  mov     r8d, 350h; int
0x18002eb16  mov     rdx, r13; char *
0x18002eb19  mov     rcx, rax; this
0x18002eb1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002eb21  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002eb26  cmp     al, r12b
0x18002eb29  jb      loc_18002EEC1
0x18002eb2f  mov     edx, 6Dh ; 'm'
0x18002eb34  jmp     loc_18002EEA3
0x18002eb39  test    r14b, r14b
0x18002eb3c  jnz     loc_18002EBE9
0x18002eb42  mov     rcx, [rbp+ppMFAttributes]; pConfiguration
0x18002eb46  lea     rdx, [rdi+0A8h]; ppMediaSession
0x18002eb4d  call    cs:__imp_MFCreateMediaSession
0x18002eb53  mov     ebx, eax
0x18002eb55  test    eax, eax
0x18002eb57  jns     loc_18002EBE9
0x18002eb5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb64  test    rcx, rcx
0x18002eb67  jnz     short loc_18002EBAA
0x18002eb69  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002eb6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb76  mov     rcx, rax
0x18002eb79  test    rax, rax
0x18002eb7c  jz      short loc_18002EB9C
0x18002eb7e  mov     rax, [rax]
0x18002eb81  mov     edx, 7F0h
0x18002eb86  mov     rax, [rax+8]
0x18002eb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb8f  test    eax, eax
0x18002eb91  jz      short loc_18002EB9C
0x18002eb93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002eb9a  jmp     short loc_18002EBAA
0x18002eb9c  lea     rcx, qword_180069A90; this
0x18002eba3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ebaa  cmp     [rcx+8], r15b
0x18002ebae  jz      short loc_18002EBD1
0x18002ebb0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002ebb5  cmp     [rax+7CCh], ebx
0x18002ebbb  jz      short loc_18002EBD1
0x18002ebbd  mov     r9d, ebx; int
0x18002ebc0  mov     r8d, 355h; int
0x18002ebc6  mov     rdx, r13; char *
0x18002ebc9  mov     rcx, rax; this
0x18002ebcc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002ebd1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ebd6  cmp     al, r12b
0x18002ebd9  jb      loc_18002EEC1
0x18002ebdf  mov     edx, 6Eh ; 'n'
0x18002ebe4  jmp     loc_18002EEA3
0x18002ebe9  mov     rcx, [rdi+0A8h]
0x18002ebf0  lea     rdx, [rdi+2B0h]
0x18002ebf7  xor     r8d, r8d
0x18002ebfa  mov     rax, [rcx]
0x18002ebfd  mov     rax, [rax+20h]
0x18002ec01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec06  mov     ebx, eax
0x18002ec08  test    eax, eax
0x18002ec0a  jns     loc_18002EC9C
0x18002ec10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ec17  test    rcx, rcx
0x18002ec1a  jnz     short loc_18002EC5D
0x18002ec1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002ec22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002ec29  mov     rcx, rax
0x18002ec2c  test    rax, rax
0x18002ec2f  jz      short loc_18002EC4F
0x18002ec31  mov     rax, [rax]
0x18002ec34  mov     edx, 7F0h
0x18002ec39  mov     rax, [rax+8]
  ... truncated ...
```
