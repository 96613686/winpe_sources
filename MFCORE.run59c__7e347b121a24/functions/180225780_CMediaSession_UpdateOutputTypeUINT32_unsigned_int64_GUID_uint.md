# CMediaSession::UpdateOutputTypeUINT32(unsigned __int64,_GUID,uint)

- ea: `0x180225780`
- end: `0x180225f31`
- name: `?UpdateOutputTypeUINT32@CMediaSession@@UEAAJ_KU_GUID@@I@Z`
- size: `1969`
- prototype: `__int64 __fastcall(CMediaSession *__hidden this, unsigned __int64, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x180225780`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180225b2e`
- `MFPlat!MFCreateMediaType` at `0x180225b2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225861`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022592d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802259e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225aa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225b50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225c0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225cc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225d7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225e39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225861`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18022592d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802259e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225aa0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225b50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225c0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225cc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225d7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180225e39`

## string_xrefs

- `0x1802257b0`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x1802258bf`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x18022598b`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225a43`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225afe`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225bae`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225c68`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225d20`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225dda`: `CMediaSession::UpdateOutputTypeUINT32`
- `0x180225e97`: `CMediaSession::UpdateOutputTypeUINT32`

## pseudocode

```c
__int64 __fastcall CMediaSession::UpdateOutputTypeUINT32(
        CMediaSession *this,
        __int64 a2,
        struct _GUID *a3,
        unsigned int a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  HRESULT v15; // ebx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  _BYTE v61[8]; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-31h] BYREF
  __int64 v63; // [rsp+40h] [rbp-29h] BYREF
  __int64 v64; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v65)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  __int64 v66; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v67[16]; // [rsp+60h] [rbp-9h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMediaSession::UpdateOutputTypeUINT32", 9594);
  v10 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 136) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 136) + 296LL))(*((_QWORD *)this + 136));
    v13 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 136) + 280LL))(
                        *((_QWORD *)this + 136),
                        v67);
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v14 = *v13;
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  v66 = 0;
  v65 = 0;
  v63 = 0;
  v64 = 0;
  ppMFType = 0;
  if ( *((_QWORD *)this + 60) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 60) + 320LL))(
            *((_QWORD *)this + 60),
            a2,
            &v66);
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v66 + 272LL))(
              v66,
              &v65);
      if ( v15 >= 0 )
      {
        v15 = (**v65)(v65, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &v63);
        if ( v15 >= 0 )
        {
          v15 = MFCreateMediaType(&ppMFType);
          if ( v15 >= 0 )
          {
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 144LL))(v63, 0, &v64);
            if ( v15 >= 0 )
            {
              v15 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v64 + 256LL))(v64, ppMFType);
              if ( v15 >= 0 )
              {
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, struct _GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
                        ppMFType,
                        a3,
                        a4);
                if ( v15 >= 0 )
                {
                  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v63 + 128LL))(
                          v63,
                          0,
                          ppMFType,
                          0);
                  if ( v15 >= 0 )
                    goto LABEL_105;
                  v57 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
                    CallStackTracing::s_wpInstance = v58;
                    if ( v58
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
                    {
                      v57 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v57 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v57 + 8) )
                  {
                    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
                    if ( *((_DWORD *)v59 + 499) != v15 )
                      CallStackContext::TraceFailure(v59, "CMediaSession::UpdateOutputTypeUINT32", 9616, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 769;
                }
                else
                {
                  v52 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51);
                    CallStackTracing::s_wpInstance = v53;
                    if ( v53
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                    {
                      v52 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v52 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v52 + 8) )
                  {
                    v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                    if ( *((_DWORD *)v54 + 499) != v15 )
                      CallStackContext::TraceFailure(v54, "CMediaSession::UpdateOutputTypeUINT32", 9615, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 768;
                }
              }
              else
              {
                v47 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46);
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != v15 )
                    CallStackContext::TraceFailure(v49, "CMediaSession::UpdateOutputTypeUINT32", 9614, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_105;
                v19 = 767;
              }
            }
            else
            {
              v42 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41);
                CallStackTracing::s_wpInstance = v43;
                if ( v43
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
                {
                  v42 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v42 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v42 + 8) )
              {
                v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
                if ( *((_DWORD *)v44 + 499) != v15 )
                  CallStackContext::TraceFailure(v44, "CMediaSession::UpdateOutputTypeUINT32", 9613, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_105;
              v19 = 766;
            }
          }
          else
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
              if ( *((_DWORD *)v39 + 499) != v15 )
                CallStackContext::TraceFailure(v39, "CMediaSession::UpdateOutputTypeUINT32", 9612, v15);
            }
            if ( !g_wppLevels )
              goto LABEL_105;
            v19 = 765;
          }
        }
        else
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v15 )
              CallStackContext::TraceFailure(v34, "CMediaSession::UpdateOutputTypeUINT32", 9610, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_105;
          v19 = 764;
        }
      }
      else
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v15 )
            CallStackContext::TraceFailure(v29, "CMediaSession::UpdateOutputTypeUINT32", 9609, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_105;
        v19 = 763;
      }
    }
    else
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != v15 )
          CallStackContext::TraceFailure(v24, "CMediaSession::UpdateOutputTypeUINT32", 9608, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v19 = 762;
    }
    v18 = (char *)this - 528;
    goto LABEL_104;
  }
  v15 = -1072875854;
  if ( !v10 )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v10 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
    if ( *((_DWORD *)v17 + 499) != -1072875854 )
      CallStackContext::TraceFailure(v17, "CMediaSession::UpdateOutputTypeUINT32", 9605, -1072875854);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 528;
    v19 = 761;
LABEL_104:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, v18, v15);
  }
LABEL_105:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFType);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v63);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v65);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v66);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180225780  push    rbp
0x180225782  push    rbx
0x180225783  push    rsi
0x180225784  push    rdi
0x180225785  push    r12
0x180225787  push    r13
0x180225789  push    r14
0x18022578b  push    r15
0x18022578d  lea     rbp, [rsp-1Fh]
0x180225792  sub     rsp, 88h
0x180225799  mov     rax, cs:__security_cookie
0x1802257a0  xor     rax, rsp
0x1802257a3  mov     [rbp+57h+var_50], rax
0x1802257a7  mov     r15, r8
0x1802257aa  mov     r14, rdx
0x1802257ad  mov     rsi, rcx
0x1802257b0  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x1802257b7  mov     r8d, 257Ah; int
0x1802257bd  lea     rcx, [rbp+57h+var_90]; this
0x1802257c1  mov     r12d, r9d
0x1802257c4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802257c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1802257d0  xor     r13d, r13d
0x1802257d3  cmp     [rcx+8], r13b
0x1802257d7  jz      short loc_180225836
0x1802257d9  cmp     [rsi+440h], r13
0x1802257e0  jz      short loc_180225836
0x1802257e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802257e7  mov     rcx, [rsi+440h]
0x1802257ee  mov     rdi, rax
0x1802257f1  mov     rdx, [rcx]
0x1802257f4  mov     rax, [rdx+128h]
0x1802257fb  call    cs:__guard_dispatch_icall_fptr
0x180225801  mov     rcx, [rsi+440h]
0x180225808  mov     ebx, eax
0x18022580a  mov     rdx, [rcx]
0x18022580d  mov     rax, [rdx+118h]
0x180225814  lea     rdx, [rbp+57h+var_60]
0x180225818  call    cs:__guard_dispatch_icall_fptr
0x18022581e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225825  movups  xmm0, xmmword ptr [rax]
0x180225828  mov     [rdi+7E0h], ebx
0x18022582e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180225836  mov     [rbp+57h+var_68], r13
0x18022583a  mov     [rbp+57h+var_70], r13
0x18022583e  mov     [rbp+57h+var_80], r13
0x180225842  mov     [rbp+57h+var_78], r13
0x180225846  mov     [rbp+57h+ppMFType], r13
0x18022584a  cmp     [rsi+1E0h], r13
0x180225851  jnz     loc_1802258F2
0x180225857  mov     ebx, 0C00D36B2h
0x18022585c  test    rcx, rcx
0x18022585f  jnz     short loc_1802258A9
0x180225861  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180225868  nop     dword ptr [rax+rax+00h]
0x18022586d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180225874  mov     rcx, rax
0x180225877  test    rax, rax
0x18022587a  jz      short loc_18022589B
0x18022587c  mov     rax, [rax]
0x18022587f  mov     edx, 7F0h
0x180225884  mov     rax, [rax+8]
0x180225888  call    cs:__guard_dispatch_icall_fptr
0x18022588e  test    eax, eax
0x180225890  jz      short loc_18022589B
0x180225892  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225899  jmp     short loc_1802258A9
0x18022589b  lea     rcx, qword_1803CE250; this
0x1802258a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802258a9  cmp     [rcx+8], r13b
0x1802258ad  jz      short loc_1802258D4
0x1802258af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802258b4  cmp     [rax+7CCh], ebx
0x1802258ba  jz      short loc_1802258D4
0x1802258bc  mov     r9d, ebx; int
0x1802258bf  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x1802258c6  mov     r8d, 2585h; int
0x1802258cc  mov     rcx, rax; this
0x1802258cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802258d4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802258db  jb      loc_180225ED8
0x1802258e1  lea     r9, [rsi-210h]
0x1802258e8  mov     edx, 2F9h
0x1802258ed  jmp     loc_180225EBD
0x1802258f2  lea     rdi, [rsi-210h]
0x1802258f9  mov     rdx, r14
0x1802258fc  mov     rcx, [rdi+3F0h]
0x180225903  lea     r8, [rbp+57h+var_68]
0x180225907  mov     rax, [rcx]
0x18022590a  mov     rax, [rax+140h]
0x180225911  call    cs:__guard_dispatch_icall_fptr
0x180225917  mov     ebx, eax
0x180225919  test    eax, eax
0x18022591b  jns     loc_1802259B7
0x180225921  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225928  test    rcx, rcx
0x18022592b  jnz     short loc_180225975
0x18022592d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180225934  nop     dword ptr [rax+rax+00h]
0x180225939  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180225940  mov     rcx, rax
0x180225943  test    rax, rax
0x180225946  jz      short loc_180225967
0x180225948  mov     rax, [rax]
0x18022594b  mov     edx, 7F0h
0x180225950  mov     rax, [rax+8]
0x180225954  call    cs:__guard_dispatch_icall_fptr
0x18022595a  test    eax, eax
0x18022595c  jz      short loc_180225967
0x18022595e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225965  jmp     short loc_180225975
0x180225967  lea     rcx, qword_1803CE250; this
0x18022596e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180225975  cmp     [rcx+8], r13b
0x180225979  jz      short loc_1802259A0
0x18022597b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180225980  cmp     [rax+7CCh], ebx
0x180225986  jz      short loc_1802259A0
0x180225988  mov     r9d, ebx; int
0x18022598b  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x180225992  mov     r8d, 2588h; int
0x180225998  mov     rcx, rax; this
0x18022599b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802259a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802259a7  jb      loc_180225ED8
0x1802259ad  mov     edx, 2FAh
0x1802259b2  jmp     loc_180225EBA
0x1802259b7  mov     rcx, [rbp+57h+var_68]
0x1802259bb  lea     rdx, [rbp+57h+var_70]
0x1802259bf  mov     rax, [rcx]
0x1802259c2  mov     rax, [rax+110h]
0x1802259c9  call    cs:__guard_dispatch_icall_fptr
0x1802259cf  mov     ebx, eax
0x1802259d1  test    eax, eax
0x1802259d3  jns     loc_180225A6F
0x1802259d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802259e0  test    rcx, rcx
0x1802259e3  jnz     short loc_180225A2D
0x1802259e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802259ec  nop     dword ptr [rax+rax+00h]
0x1802259f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802259f8  mov     rcx, rax
0x1802259fb  test    rax, rax
0x1802259fe  jz      short loc_180225A1F
0x180225a00  mov     rax, [rax]
0x180225a03  mov     edx, 7F0h
0x180225a08  mov     rax, [rax+8]
0x180225a0c  call    cs:__guard_dispatch_icall_fptr
0x180225a12  test    eax, eax
0x180225a14  jz      short loc_180225A1F
0x180225a16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225a1d  jmp     short loc_180225A2D
0x180225a1f  lea     rcx, qword_1803CE250; this
0x180225a26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180225a2d  cmp     [rcx+8], r13b
0x180225a31  jz      short loc_180225A58
0x180225a33  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180225a38  cmp     [rax+7CCh], ebx
0x180225a3e  jz      short loc_180225A58
0x180225a40  mov     r9d, ebx; int
0x180225a43  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x180225a4a  mov     r8d, 2589h; int
0x180225a50  mov     rcx, rax; this
0x180225a53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180225a58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180225a5f  jb      loc_180225ED8
0x180225a65  mov     edx, 2FBh
0x180225a6a  jmp     loc_180225EBA
0x180225a6f  mov     rcx, [rbp+57h+var_70]
0x180225a73  lea     r8, [rbp+57h+var_80]
0x180225a77  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x180225a7e  mov     rax, [rcx]
0x180225a81  mov     rax, [rax]
0x180225a84  call    cs:__guard_dispatch_icall_fptr
0x180225a8a  mov     ebx, eax
0x180225a8c  test    eax, eax
0x180225a8e  jns     loc_180225B2A
0x180225a94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225a9b  test    rcx, rcx
0x180225a9e  jnz     short loc_180225AE8
0x180225aa0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180225aa7  nop     dword ptr [rax+rax+00h]
0x180225aac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180225ab3  mov     rcx, rax
0x180225ab6  test    rax, rax
0x180225ab9  jz      short loc_180225ADA
0x180225abb  mov     rax, [rax]
0x180225abe  mov     edx, 7F0h
0x180225ac3  mov     rax, [rax+8]
0x180225ac7  call    cs:__guard_dispatch_icall_fptr
0x180225acd  test    eax, eax
0x180225acf  jz      short loc_180225ADA
0x180225ad1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225ad8  jmp     short loc_180225AE8
0x180225ada  lea     rcx, qword_1803CE250; this
0x180225ae1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180225ae8  cmp     [rcx+8], r13b
0x180225aec  jz      short loc_180225B13
0x180225aee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180225af3  cmp     [rax+7CCh], ebx
0x180225af9  jz      short loc_180225B13
0x180225afb  mov     r9d, ebx; int
0x180225afe  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x180225b05  mov     r8d, 258Ah; int
0x180225b0b  mov     rcx, rax; this
0x180225b0e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180225b13  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180225b1a  jb      loc_180225ED8
0x180225b20  mov     edx, 2FCh
0x180225b25  jmp     loc_180225EBA
0x180225b2a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180225b2e  call    cs:__imp_MFCreateMediaType
0x180225b35  nop     dword ptr [rax+rax+00h]
0x180225b3a  mov     ebx, eax
0x180225b3c  test    eax, eax
0x180225b3e  jns     loc_180225BDA
0x180225b44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225b4b  test    rcx, rcx
0x180225b4e  jnz     short loc_180225B98
0x180225b50  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180225b57  nop     dword ptr [rax+rax+00h]
0x180225b5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180225b63  mov     rcx, rax
0x180225b66  test    rax, rax
0x180225b69  jz      short loc_180225B8A
0x180225b6b  mov     rax, [rax]
0x180225b6e  mov     edx, 7F0h
0x180225b73  mov     rax, [rax+8]
0x180225b77  call    cs:__guard_dispatch_icall_fptr
0x180225b7d  test    eax, eax
0x180225b7f  jz      short loc_180225B8A
0x180225b81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225b88  jmp     short loc_180225B98
0x180225b8a  lea     rcx, qword_1803CE250; this
0x180225b91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180225b98  cmp     [rcx+8], r13b
0x180225b9c  jz      short loc_180225BC3
0x180225b9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180225ba3  cmp     [rax+7CCh], ebx
0x180225ba9  jz      short loc_180225BC3
0x180225bab  mov     r9d, ebx; int
0x180225bae  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x180225bb5  mov     r8d, 258Ch; int
0x180225bbb  mov     rcx, rax; this
0x180225bbe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180225bc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180225bca  jb      loc_180225ED8
0x180225bd0  mov     edx, 2FDh
0x180225bd5  jmp     loc_180225EBA
0x180225bda  mov     rcx, [rbp+57h+var_80]
0x180225bde  lea     r8, [rbp+57h+var_78]
0x180225be2  xor     edx, edx
0x180225be4  mov     rax, [rcx]
0x180225be7  mov     rax, [rax+90h]
0x180225bee  call    cs:__guard_dispatch_icall_fptr
0x180225bf4  mov     ebx, eax
0x180225bf6  test    eax, eax
0x180225bf8  jns     loc_180225C94
0x180225bfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225c05  test    rcx, rcx
0x180225c08  jnz     short loc_180225C52
0x180225c0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180225c11  nop     dword ptr [rax+rax+00h]
0x180225c16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180225c1d  mov     rcx, rax
0x180225c20  test    rax, rax
0x180225c23  jz      short loc_180225C44
0x180225c25  mov     rax, [rax]
0x180225c28  mov     edx, 7F0h
0x180225c2d  mov     rax, [rax+8]
0x180225c31  call    cs:__guard_dispatch_icall_fptr
0x180225c37  test    eax, eax
0x180225c39  jz      short loc_180225C44
0x180225c3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180225c42  jmp     short loc_180225C52
0x180225c44  lea     rcx, qword_1803CE250; this
0x180225c4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180225c52  cmp     [rcx+8], r13b
0x180225c56  jz      short loc_180225C7D
0x180225c58  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180225c5d  cmp     [rax+7CCh], ebx
0x180225c63  jz      short loc_180225C7D
0x180225c65  mov     r9d, ebx; int
0x180225c68  lea     rdx, aCmediasessionU; "CMediaSession::UpdateOutputTypeUINT32"
0x180225c6f  mov     r8d, 258Dh; int
0x180225c75  mov     rcx, rax; this
0x180225c78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180225c7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180225c84  jb      loc_180225ED8
0x180225c8a  mov     edx, 2FEh
0x180225c8f  jmp     loc_180225EBA
0x180225c94  mov     rcx, [rbp+57h+var_78]
0x180225c98  mov     rdx, [rbp+57h+ppMFType]
0x180225c9c  mov     rax, [rcx]
0x180225c9f  mov     rax, [rax+100h]
0x180225ca6  call    cs:__guard_dispatch_icall_fptr
0x180225cac  mov     ebx, eax
0x180225cae  test    eax, eax
0x180225cb0  jns     loc_180225D4C
0x180225cb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
