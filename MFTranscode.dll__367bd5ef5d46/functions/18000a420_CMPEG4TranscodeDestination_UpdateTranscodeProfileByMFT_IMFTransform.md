# CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT(IMFTransform *)

- ea: `0x18000a420`
- end: `0x18000a93a`
- name: `?UpdateTranscodeProfileByMFT@CMPEG4TranscodeDestination@@MEAAJPEAUIMFTransform@@@Z`
- size: `1306`
- prototype: `__int64 __fastcall(CMPEG4TranscodeDestination *__hidden this, struct IMFTransform *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18000a420`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180045fe0`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a4a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a55b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a607`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a6bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a85b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a4a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a55b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a607`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a6bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000a85b`

## string_xrefs

- `0x18000a444`: `CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT`

## pseudocode

```c
__int64 __fastcall CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT(
        CMPEG4TranscodeDestination *this,
        struct IMFTransform *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  int updated; // ebx
  __int64 *v7; // rcx
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
  _BYTE v32[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v33; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v34; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  __int64 v36; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v32,
    "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT",
    74);
  v4 = *((_QWORD *)this + 1);
  v36 = 0;
  v34 = 0;
  Buf1 = 0;
  pv = 0;
  v33 = 0;
  updated = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, &v34);
  if ( updated >= 0 )
  {
    if ( v34 )
    {
      updated = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, __int64 *))a2->lpVtbl->GetOutputCurrentType)(
                  a2,
                  0,
                  &v36);
      if ( updated >= 0 )
      {
        updated = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v36 + 264LL))(v36, &Buf1);
        if ( updated >= 0 )
        {
          if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) )
          {
            if ( *((_QWORD *)this + 8) )
            {
              if ( (*(int (__fastcall **)(__int64, const GUID *, unsigned int *))(*(_QWORD *)v34 + 112LL))(
                     v34,
                     &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
                     &v33) < 0
                && (*(int (__fastcall **)(__int64, const GUID *, LPVOID *, unsigned int *))(*(_QWORD *)v36 + 128LL))(
                     v36,
                     &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
                     &pv,
                     &v33) >= 0 )
              {
                updated = (*(__int64 (__fastcall **)(__int64, const GUID *, LPVOID, _QWORD))(*(_QWORD *)v34 + 208LL))(
                            v34,
                            &MF_MT_MPEG4_SAMPLE_DESCRIPTION,
                            pv,
                            v33);
                if ( updated >= 0 )
                {
                  updated = CMPEG4TranscodeDestination::UpdateSinkInfo(this);
                  if ( updated < 0 )
                  {
                    v28 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                      CallStackTracing::s_wpInstance = v29;
                      if ( v29
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(
                             v29,
                             2032) )
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
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT",
                          126,
                          updated);
                    }
                    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    {
                      v10 = 19;
                      goto LABEL_71;
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
                    if ( *((_DWORD *)v26 + 499) != updated )
                      CallStackContext::TraceFailure(
                        v26,
                        "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT",
                        121,
                        updated);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v10 = 18;
                    goto LABEL_71;
                  }
                }
              }
            }
            else
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
              updated = -2147418113;
              if ( !CallStackTracing::s_wpInstance )
              {
                v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
                CallStackTracing::s_wpInstance = v21;
                if ( v21
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
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
                if ( *((_DWORD *)v22 + 499) != -2147418113 )
                  CallStackContext::TraceFailure(
                    v22,
                    "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT",
                    108,
                    -2147418113);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 17;
                goto LABEL_71;
              }
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
            if ( *((_DWORD *)v18 + 499) != updated )
              CallStackContext::TraceFailure(
                v18,
                "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT",
                98,
                updated);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 16;
            goto LABEL_71;
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
          if ( *((_DWORD *)v14 + 499) != updated )
            CallStackContext::TraceFailure(v14, "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT", 96, updated);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 15;
          goto LABEL_71;
        }
      }
    }
  }
  else
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
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != updated )
        CallStackContext::TraceFailure(v9, "CMPEG4TranscodeDestination::UpdateTranscodeProfileByMFT", 87, updated);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 14;
LABEL_71:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        WPP_8500b975b1173f2b6163c20b6fddb525_Traceguids,
        this,
        updated);
    }
  }
  CoTaskMemFree(pv);
  pv = 0;
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v34);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v36);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v32);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000a420  mov     [rsp-28h+arg_10], rbx
0x18000a425  push    rbp
0x18000a426  push    rsi
0x18000a427  push    rdi
0x18000a428  push    r14
0x18000a42a  push    r15
0x18000a42c  mov     rbp, rsp
0x18000a42f  sub     rsp, 70h
0x18000a433  mov     rax, cs:__security_cookie
0x18000a43a  xor     rax, rsp
0x18000a43d  mov     [rbp+var_10], rax
0x18000a441  mov     rsi, rdx
0x18000a444  lea     r15, aCmpeg4transcod_0; "CMPEG4TranscodeDestination::UpdateTrans"...
0x18000a44b  mov     rdi, rcx
0x18000a44e  mov     rdx, r15; char *
0x18000a451  mov     r8d, 4Ah ; 'J'; int
0x18000a457  lea     rcx, [rbp+var_40]; this
0x18000a45b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000a460  mov     rcx, [rdi+8]
0x18000a464  lea     rdx, [rbp+var_38]
0x18000a468  xor     r14d, r14d
0x18000a46b  xorps   xmm0, xmm0
0x18000a46e  mov     [rbp+var_28], r14
0x18000a472  mov     [rbp+var_38], r14
0x18000a476  movups  [rbp+Buf1], xmm0
0x18000a47a  mov     [rbp+pv], r14
0x18000a47e  mov     [rbp+var_3C], r14d
0x18000a482  mov     rax, [rcx]
0x18000a485  mov     rax, [rax+30h]
0x18000a489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48e  mov     ebx, eax
0x18000a490  test    eax, eax
0x18000a492  jns     loc_18000A523
0x18000a498  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a49f  test    rcx, rcx
0x18000a4a2  jnz     short loc_18000A4E5
0x18000a4a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a4aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a4b1  mov     rcx, rax
0x18000a4b4  test    rax, rax
0x18000a4b7  jz      short loc_18000A4D7
0x18000a4b9  mov     rax, [rax]
0x18000a4bc  mov     edx, 7F0h
0x18000a4c1  mov     rax, [rax+8]
0x18000a4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ca  test    eax, eax
0x18000a4cc  jz      short loc_18000A4D7
0x18000a4ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a4d5  jmp     short loc_18000A4E5
0x18000a4d7  lea     rcx, qword_180069A90; this
0x18000a4de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a4e5  cmp     [rcx+8], r14b
0x18000a4e9  jz      short loc_18000A50C
0x18000a4eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a4f0  cmp     [rax+7CCh], ebx
0x18000a4f6  jz      short loc_18000A50C
0x18000a4f8  mov     r9d, ebx; int
0x18000a4fb  mov     r8d, 57h ; 'W'; int
0x18000a501  mov     rdx, r15; char *
0x18000a504  mov     rcx, rax; this
0x18000a507  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a50c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a511  cmp     al, 1
0x18000a513  jb      loc_18000A8EF
0x18000a519  mov     edx, 0Eh
0x18000a51e  jmp     loc_18000A8D1
0x18000a523  cmp     [rbp+var_38], r14
0x18000a527  jz      loc_18000A8EF
0x18000a52d  mov     rax, [rsi]
0x18000a530  lea     r8, [rbp+var_28]
0x18000a534  xor     edx, edx
0x18000a536  mov     rcx, rsi
0x18000a539  mov     rax, [rax+90h]
0x18000a540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a545  mov     ebx, eax
0x18000a547  test    eax, eax
0x18000a549  jns     loc_18000A5DA
0x18000a54f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a556  test    rcx, rcx
0x18000a559  jnz     short loc_18000A59C
0x18000a55b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a561  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a568  mov     rcx, rax
0x18000a56b  test    rax, rax
0x18000a56e  jz      short loc_18000A58E
0x18000a570  mov     rax, [rax]
0x18000a573  mov     edx, 7F0h
0x18000a578  mov     rax, [rax+8]
0x18000a57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a581  test    eax, eax
0x18000a583  jz      short loc_18000A58E
0x18000a585  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a58c  jmp     short loc_18000A59C
0x18000a58e  lea     rcx, qword_180069A90; this
0x18000a595  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a59c  cmp     [rcx+8], r14b
0x18000a5a0  jz      short loc_18000A5C3
0x18000a5a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a5a7  cmp     [rax+7CCh], ebx
0x18000a5ad  jz      short loc_18000A5C3
0x18000a5af  mov     r9d, ebx; int
0x18000a5b2  mov     r8d, 60h ; '`'; int
0x18000a5b8  mov     rdx, r15; char *
0x18000a5bb  mov     rcx, rax; this
0x18000a5be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a5c3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a5c8  cmp     al, 1
0x18000a5ca  jb      loc_18000A8EF
0x18000a5d0  mov     edx, 0Fh
0x18000a5d5  jmp     loc_18000A8D1
0x18000a5da  mov     rcx, [rbp+var_28]
0x18000a5de  lea     rdx, [rbp+Buf1]
0x18000a5e2  mov     rax, [rcx]
0x18000a5e5  mov     rax, [rax+108h]
0x18000a5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f1  mov     ebx, eax
0x18000a5f3  test    eax, eax
0x18000a5f5  jns     loc_18000A686
0x18000a5fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a602  test    rcx, rcx
0x18000a605  jnz     short loc_18000A648
0x18000a607  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a60d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a614  mov     rcx, rax
0x18000a617  test    rax, rax
0x18000a61a  jz      short loc_18000A63A
0x18000a61c  mov     rax, [rax]
0x18000a61f  mov     edx, 7F0h
0x18000a624  mov     rax, [rax+8]
0x18000a628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a62d  test    eax, eax
0x18000a62f  jz      short loc_18000A63A
0x18000a631  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a638  jmp     short loc_18000A648
0x18000a63a  lea     rcx, qword_180069A90; this
0x18000a641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a648  cmp     [rcx+8], r14b
0x18000a64c  jz      short loc_18000A66F
0x18000a64e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a653  cmp     [rax+7CCh], ebx
0x18000a659  jz      short loc_18000A66F
0x18000a65b  mov     r9d, ebx; int
0x18000a65e  mov     r8d, 62h ; 'b'; int
0x18000a664  mov     rdx, r15; char *
0x18000a667  mov     rcx, rax; this
0x18000a66a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a66f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a674  cmp     al, 1
0x18000a676  jb      loc_18000A8EF
0x18000a67c  mov     edx, 10h
0x18000a681  jmp     loc_18000A8D1
0x18000a686  mov     r8d, 10h; Size
0x18000a68c  lea     rdx, MFMediaType_Video; Buf2
0x18000a693  lea     rcx, [rbp+Buf1]; Buf1
0x18000a697  call    memcmp_0
0x18000a69c  test    eax, eax
0x18000a69e  jnz     loc_18000A8EF
0x18000a6a4  cmp     [rdi+40h], r14
0x18000a6a8  jnz     loc_18000A73E
0x18000a6ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a6b5  mov     ebx, 8000FFFFh
0x18000a6ba  test    rcx, rcx
0x18000a6bd  jnz     short loc_18000A700
0x18000a6bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a6c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a6cc  mov     rcx, rax
0x18000a6cf  test    rax, rax
0x18000a6d2  jz      short loc_18000A6F2
0x18000a6d4  mov     rax, [rax]
0x18000a6d7  mov     edx, 7F0h
0x18000a6dc  mov     rax, [rax+8]
0x18000a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e5  test    eax, eax
0x18000a6e7  jz      short loc_18000A6F2
0x18000a6e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a6f0  jmp     short loc_18000A700
0x18000a6f2  lea     rcx, qword_180069A90; this
0x18000a6f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a700  cmp     [rcx+8], r14b
0x18000a704  jz      short loc_18000A727
0x18000a706  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a70b  cmp     [rax+7CCh], ebx
0x18000a711  jz      short loc_18000A727
0x18000a713  mov     r9d, ebx; int
0x18000a716  mov     r8d, 6Ch ; 'l'; int
0x18000a71c  mov     rdx, r15; char *
0x18000a71f  mov     rcx, rax; this
0x18000a722  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a727  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a72c  cmp     al, 1
0x18000a72e  jb      loc_18000A8EF
0x18000a734  mov     edx, 11h
0x18000a739  jmp     loc_18000A8D1
0x18000a73e  mov     rcx, [rbp+var_38]
0x18000a742  lea     rsi, MF_MT_MPEG4_SAMPLE_DESCRIPTION
0x18000a749  lea     r8, [rbp+var_3C]
0x18000a74d  mov     rdx, rsi
0x18000a750  mov     rax, [rcx]
0x18000a753  mov     rax, [rax+70h]
0x18000a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75c  test    eax, eax
0x18000a75e  jns     loc_18000A8EF
0x18000a764  mov     rcx, [rbp+var_28]
0x18000a768  lea     r9, [rbp+var_3C]
0x18000a76c  lea     r8, [rbp+pv]
0x18000a770  mov     rdx, rsi
0x18000a773  mov     rax, [rcx]
0x18000a776  mov     rax, [rax+80h]
0x18000a77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a782  test    eax, eax
0x18000a784  js      loc_18000A8EF
0x18000a78a  mov     rcx, [rbp+var_38]
0x18000a78e  mov     rdx, rsi
0x18000a791  mov     r9d, [rbp+var_3C]
0x18000a795  mov     r8, [rbp+pv]
0x18000a799  mov     rax, [rcx]
0x18000a79c  mov     rax, [rax+0D0h]
0x18000a7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a8  mov     ebx, eax
0x18000a7aa  test    eax, eax
0x18000a7ac  jns     loc_18000A83D
0x18000a7b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a7b9  test    rcx, rcx
0x18000a7bc  jnz     short loc_18000A7FF
0x18000a7be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a7c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a7cb  mov     rcx, rax
0x18000a7ce  test    rax, rax
0x18000a7d1  jz      short loc_18000A7F1
0x18000a7d3  mov     rax, [rax]
0x18000a7d6  mov     edx, 7F0h
0x18000a7db  mov     rax, [rax+8]
0x18000a7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e4  test    eax, eax
0x18000a7e6  jz      short loc_18000A7F1
0x18000a7e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a7ef  jmp     short loc_18000A7FF
0x18000a7f1  lea     rcx, qword_180069A90; this
0x18000a7f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a7ff  cmp     [rcx+8], r14b
0x18000a803  jz      short loc_18000A826
0x18000a805  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a80a  cmp     [rax+7CCh], ebx
0x18000a810  jz      short loc_18000A826
0x18000a812  mov     r9d, ebx; int
0x18000a815  mov     r8d, 79h ; 'y'; int
0x18000a81b  mov     rdx, r15; char *
0x18000a81e  mov     rcx, rax; this
0x18000a821  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a826  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a82b  cmp     al, 1
0x18000a82d  jb      loc_18000A8EF
0x18000a833  mov     edx, 12h
0x18000a838  jmp     loc_18000A8D1
0x18000a83d  mov     rcx, rdi; this
0x18000a840  call    ?UpdateSinkInfo@CMPEG4TranscodeDestination@@MEAAJXZ; CMPEG4TranscodeDestination::UpdateSinkInfo(void)
0x18000a845  mov     ebx, eax
0x18000a847  test    eax, eax
0x18000a849  jns     loc_18000A8EF
0x18000a84f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a856  test    rcx, rcx
0x18000a859  jnz     short loc_18000A89C
0x18000a85b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000a861  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a868  mov     rcx, rax
0x18000a86b  test    rax, rax
0x18000a86e  jz      short loc_18000A88E
0x18000a870  mov     rax, [rax]
0x18000a873  mov     edx, 7F0h
0x18000a878  mov     rax, [rax+8]
0x18000a87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a881  test    eax, eax
0x18000a883  jz      short loc_18000A88E
0x18000a885  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a88c  jmp     short loc_18000A89C
0x18000a88e  lea     rcx, qword_180069A90; this
0x18000a895  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000a89c  cmp     [rcx+8], r14b
0x18000a8a0  jz      short loc_18000A8C3
0x18000a8a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000a8a7  cmp     [rax+7CCh], ebx
0x18000a8ad  jz      short loc_18000A8C3
0x18000a8af  mov     r9d, ebx; int
0x18000a8b2  mov     r8d, 7Eh ; '~'; int
0x18000a8b8  mov     rdx, r15; char *
0x18000a8bb  mov     rcx, rax; this
0x18000a8be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000a8c3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000a8c8  cmp     al, 1
0x18000a8ca  jb      short loc_18000A8EF
0x18000a8cc  mov     edx, 13h
0x18000a8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8d8  lea     r8, WPP_8500b975b1173f2b6163c20b6fddb525_Traceguids
0x18000a8df  mov     r9, rdi
0x18000a8e2  mov     [rsp+70h+var_50], ebx
0x18000a8e6  mov     rcx, [rcx+10h]
0x18000a8ea  call    WPP_SF_qd
0x18000a8ef  mov     rcx, [rbp+pv]; pv
0x18000a8f3  call    cs:__imp_CoTaskMemFree
0x18000a8f9  lea     rcx, [rbp+var_38]
  ... truncated ...
```
