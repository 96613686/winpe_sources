# CMediaSession::UpdateInputTypeUINT32(unsigned __int64,_GUID,uint)

- ea: `0x1801fbb90`
- end: `0x1801fc33e`
- name: `?UpdateInputTypeUINT32@CMediaSession@@UEAAJ_KU_GUID@@I@Z`
- size: `1966`
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
- `0x1801fbb90`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801fbf3e`
- `MFPlat!MFCreateMediaType` at `0x1801fbf3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbc71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbd3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbdf5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbeb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbf60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc01a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc0d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc18c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc246`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbc71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbd3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbdf5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbeb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fbf60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc01a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc0d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc18c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801fc246`

## string_xrefs

- `0x1801fbbc0`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fbccf`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fbd9b`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fbe53`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fbf0e`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fbfbe`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fc078`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fc130`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fc1ea`: `CMediaSession::UpdateInputTypeUINT32`
- `0x1801fc2a4`: `CMediaSession::UpdateInputTypeUINT32`

## pseudocode

```c
__int64 __fastcall CMediaSession::UpdateInputTypeUINT32(
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

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMediaSession::UpdateInputTypeUINT32", 9499);
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
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v63 + 136LL))(v63, 0, &v64);
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
                  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, IMFMediaType *, _QWORD))(*(_QWORD *)v63 + 120LL))(
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
                      CallStackContext::TraceFailure(v59, "CMediaSession::UpdateInputTypeUINT32", 9521, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 742;
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
                      CallStackContext::TraceFailure(v54, "CMediaSession::UpdateInputTypeUINT32", 9520, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 741;
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
                    CallStackContext::TraceFailure(v49, "CMediaSession::UpdateInputTypeUINT32", 9519, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_105;
                v19 = 740;
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
                  CallStackContext::TraceFailure(v44, "CMediaSession::UpdateInputTypeUINT32", 9518, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_105;
              v19 = 739;
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
                CallStackContext::TraceFailure(v39, "CMediaSession::UpdateInputTypeUINT32", 9517, v15);
            }
            if ( !g_wppLevels )
              goto LABEL_105;
            v19 = 738;
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
              CallStackContext::TraceFailure(v34, "CMediaSession::UpdateInputTypeUINT32", 9515, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_105;
          v19 = 737;
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
            CallStackContext::TraceFailure(v29, "CMediaSession::UpdateInputTypeUINT32", 9514, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_105;
        v19 = 736;
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
          CallStackContext::TraceFailure(v24, "CMediaSession::UpdateInputTypeUINT32", 9513, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v19 = 735;
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
      CallStackContext::TraceFailure(v17, "CMediaSession::UpdateInputTypeUINT32", 9510, -1072875854);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 528;
    v19 = 734;
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
0x1801fbb90  push    rbp
0x1801fbb92  push    rbx
0x1801fbb93  push    rsi
0x1801fbb94  push    rdi
0x1801fbb95  push    r12
0x1801fbb97  push    r13
0x1801fbb99  push    r14
0x1801fbb9b  push    r15
0x1801fbb9d  lea     rbp, [rsp-1Fh]
0x1801fbba2  sub     rsp, 88h
0x1801fbba9  mov     rax, cs:__security_cookie
0x1801fbbb0  xor     rax, rsp
0x1801fbbb3  mov     [rbp+57h+var_50], rax
0x1801fbbb7  mov     r15, r8
0x1801fbbba  mov     r14, rdx
0x1801fbbbd  mov     rsi, rcx
0x1801fbbc0  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbbc7  mov     r8d, 251Bh; int
0x1801fbbcd  lea     rcx, [rbp+57h+var_90]; this
0x1801fbbd1  mov     r12d, r9d
0x1801fbbd4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801fbbd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801fbbe0  xor     r13d, r13d
0x1801fbbe3  cmp     [rcx+8], r13b
0x1801fbbe7  jz      short loc_1801FBC46
0x1801fbbe9  cmp     [rsi+440h], r13
0x1801fbbf0  jz      short loc_1801FBC46
0x1801fbbf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbbf7  mov     rcx, [rsi+440h]
0x1801fbbfe  mov     rdi, rax
0x1801fbc01  mov     rdx, [rcx]
0x1801fbc04  mov     rax, [rdx+128h]
0x1801fbc0b  call    cs:__guard_dispatch_icall_fptr
0x1801fbc11  mov     rcx, [rsi+440h]
0x1801fbc18  mov     ebx, eax
0x1801fbc1a  mov     rdx, [rcx]
0x1801fbc1d  mov     rax, [rdx+118h]
0x1801fbc24  lea     rdx, [rbp+57h+var_60]
0x1801fbc28  call    cs:__guard_dispatch_icall_fptr
0x1801fbc2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbc35  movups  xmm0, xmmword ptr [rax]
0x1801fbc38  mov     [rdi+7E0h], ebx
0x1801fbc3e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801fbc46  mov     [rbp+57h+var_68], r13
0x1801fbc4a  mov     [rbp+57h+var_70], r13
0x1801fbc4e  mov     [rbp+57h+var_80], r13
0x1801fbc52  mov     [rbp+57h+var_78], r13
0x1801fbc56  mov     [rbp+57h+ppMFType], r13
0x1801fbc5a  cmp     [rsi+1E0h], r13
0x1801fbc61  jnz     loc_1801FBD02
0x1801fbc67  mov     ebx, 0C00D36B2h
0x1801fbc6c  test    rcx, rcx
0x1801fbc6f  jnz     short loc_1801FBCB9
0x1801fbc71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fbc78  nop     dword ptr [rax+rax+00h]
0x1801fbc7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbc84  mov     rcx, rax
0x1801fbc87  test    rax, rax
0x1801fbc8a  jz      short loc_1801FBCAB
0x1801fbc8c  mov     rax, [rax]
0x1801fbc8f  mov     edx, 7F0h
0x1801fbc94  mov     rax, [rax+8]
0x1801fbc98  call    cs:__guard_dispatch_icall_fptr
0x1801fbc9e  test    eax, eax
0x1801fbca0  jz      short loc_1801FBCAB
0x1801fbca2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbca9  jmp     short loc_1801FBCB9
0x1801fbcab  lea     rcx, qword_1803CE250; this
0x1801fbcb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbcb9  cmp     [rcx+8], r13b
0x1801fbcbd  jz      short loc_1801FBCE4
0x1801fbcbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbcc4  cmp     [rax+7CCh], ebx
0x1801fbcca  jz      short loc_1801FBCE4
0x1801fbccc  mov     r9d, ebx; int
0x1801fbccf  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbcd6  mov     r8d, 2526h; int
0x1801fbcdc  mov     rcx, rax; this
0x1801fbcdf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fbce4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fbceb  jb      loc_1801FC2E5
0x1801fbcf1  lea     r9, [rsi-210h]
0x1801fbcf8  mov     edx, 2DEh
0x1801fbcfd  jmp     loc_1801FC2CA
0x1801fbd02  lea     rdi, [rsi-210h]
0x1801fbd09  mov     rdx, r14
0x1801fbd0c  mov     rcx, [rdi+3F0h]
0x1801fbd13  lea     r8, [rbp+57h+var_68]
0x1801fbd17  mov     rax, [rcx]
0x1801fbd1a  mov     rax, [rax+140h]
0x1801fbd21  call    cs:__guard_dispatch_icall_fptr
0x1801fbd27  mov     ebx, eax
0x1801fbd29  test    eax, eax
0x1801fbd2b  jns     loc_1801FBDC7
0x1801fbd31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbd38  test    rcx, rcx
0x1801fbd3b  jnz     short loc_1801FBD85
0x1801fbd3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fbd44  nop     dword ptr [rax+rax+00h]
0x1801fbd49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbd50  mov     rcx, rax
0x1801fbd53  test    rax, rax
0x1801fbd56  jz      short loc_1801FBD77
0x1801fbd58  mov     rax, [rax]
0x1801fbd5b  mov     edx, 7F0h
0x1801fbd60  mov     rax, [rax+8]
0x1801fbd64  call    cs:__guard_dispatch_icall_fptr
0x1801fbd6a  test    eax, eax
0x1801fbd6c  jz      short loc_1801FBD77
0x1801fbd6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbd75  jmp     short loc_1801FBD85
0x1801fbd77  lea     rcx, qword_1803CE250; this
0x1801fbd7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbd85  cmp     [rcx+8], r13b
0x1801fbd89  jz      short loc_1801FBDB0
0x1801fbd8b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbd90  cmp     [rax+7CCh], ebx
0x1801fbd96  jz      short loc_1801FBDB0
0x1801fbd98  mov     r9d, ebx; int
0x1801fbd9b  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbda2  mov     r8d, 2529h; int
0x1801fbda8  mov     rcx, rax; this
0x1801fbdab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fbdb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fbdb7  jb      loc_1801FC2E5
0x1801fbdbd  mov     edx, 2DFh
0x1801fbdc2  jmp     loc_1801FC2C7
0x1801fbdc7  mov     rcx, [rbp+57h+var_68]
0x1801fbdcb  lea     rdx, [rbp+57h+var_70]
0x1801fbdcf  mov     rax, [rcx]
0x1801fbdd2  mov     rax, [rax+110h]
0x1801fbdd9  call    cs:__guard_dispatch_icall_fptr
0x1801fbddf  mov     ebx, eax
0x1801fbde1  test    eax, eax
0x1801fbde3  jns     loc_1801FBE7F
0x1801fbde9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbdf0  test    rcx, rcx
0x1801fbdf3  jnz     short loc_1801FBE3D
0x1801fbdf5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fbdfc  nop     dword ptr [rax+rax+00h]
0x1801fbe01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbe08  mov     rcx, rax
0x1801fbe0b  test    rax, rax
0x1801fbe0e  jz      short loc_1801FBE2F
0x1801fbe10  mov     rax, [rax]
0x1801fbe13  mov     edx, 7F0h
0x1801fbe18  mov     rax, [rax+8]
0x1801fbe1c  call    cs:__guard_dispatch_icall_fptr
0x1801fbe22  test    eax, eax
0x1801fbe24  jz      short loc_1801FBE2F
0x1801fbe26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbe2d  jmp     short loc_1801FBE3D
0x1801fbe2f  lea     rcx, qword_1803CE250; this
0x1801fbe36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbe3d  cmp     [rcx+8], r13b
0x1801fbe41  jz      short loc_1801FBE68
0x1801fbe43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbe48  cmp     [rax+7CCh], ebx
0x1801fbe4e  jz      short loc_1801FBE68
0x1801fbe50  mov     r9d, ebx; int
0x1801fbe53  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbe5a  mov     r8d, 252Ah; int
0x1801fbe60  mov     rcx, rax; this
0x1801fbe63  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fbe68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fbe6f  jb      loc_1801FC2E5
0x1801fbe75  mov     edx, 2E0h
0x1801fbe7a  jmp     loc_1801FC2C7
0x1801fbe7f  mov     rcx, [rbp+57h+var_70]
0x1801fbe83  lea     r8, [rbp+57h+var_80]
0x1801fbe87  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1801fbe8e  mov     rax, [rcx]
0x1801fbe91  mov     rax, [rax]
0x1801fbe94  call    cs:__guard_dispatch_icall_fptr
0x1801fbe9a  mov     ebx, eax
0x1801fbe9c  test    eax, eax
0x1801fbe9e  jns     loc_1801FBF3A
0x1801fbea4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbeab  test    rcx, rcx
0x1801fbeae  jnz     short loc_1801FBEF8
0x1801fbeb0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fbeb7  nop     dword ptr [rax+rax+00h]
0x1801fbebc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbec3  mov     rcx, rax
0x1801fbec6  test    rax, rax
0x1801fbec9  jz      short loc_1801FBEEA
0x1801fbecb  mov     rax, [rax]
0x1801fbece  mov     edx, 7F0h
0x1801fbed3  mov     rax, [rax+8]
0x1801fbed7  call    cs:__guard_dispatch_icall_fptr
0x1801fbedd  test    eax, eax
0x1801fbedf  jz      short loc_1801FBEEA
0x1801fbee1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbee8  jmp     short loc_1801FBEF8
0x1801fbeea  lea     rcx, qword_1803CE250; this
0x1801fbef1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbef8  cmp     [rcx+8], r13b
0x1801fbefc  jz      short loc_1801FBF23
0x1801fbefe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbf03  cmp     [rax+7CCh], ebx
0x1801fbf09  jz      short loc_1801FBF23
0x1801fbf0b  mov     r9d, ebx; int
0x1801fbf0e  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbf15  mov     r8d, 252Bh; int
0x1801fbf1b  mov     rcx, rax; this
0x1801fbf1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fbf23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fbf2a  jb      loc_1801FC2E5
0x1801fbf30  mov     edx, 2E1h
0x1801fbf35  jmp     loc_1801FC2C7
0x1801fbf3a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801fbf3e  call    cs:__imp_MFCreateMediaType
0x1801fbf45  nop     dword ptr [rax+rax+00h]
0x1801fbf4a  mov     ebx, eax
0x1801fbf4c  test    eax, eax
0x1801fbf4e  jns     loc_1801FBFEA
0x1801fbf54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbf5b  test    rcx, rcx
0x1801fbf5e  jnz     short loc_1801FBFA8
0x1801fbf60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fbf67  nop     dword ptr [rax+rax+00h]
0x1801fbf6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbf73  mov     rcx, rax
0x1801fbf76  test    rax, rax
0x1801fbf79  jz      short loc_1801FBF9A
0x1801fbf7b  mov     rax, [rax]
0x1801fbf7e  mov     edx, 7F0h
0x1801fbf83  mov     rax, [rax+8]
0x1801fbf87  call    cs:__guard_dispatch_icall_fptr
0x1801fbf8d  test    eax, eax
0x1801fbf8f  jz      short loc_1801FBF9A
0x1801fbf91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbf98  jmp     short loc_1801FBFA8
0x1801fbf9a  lea     rcx, qword_1803CE250; this
0x1801fbfa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fbfa8  cmp     [rcx+8], r13b
0x1801fbfac  jz      short loc_1801FBFD3
0x1801fbfae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fbfb3  cmp     [rax+7CCh], ebx
0x1801fbfb9  jz      short loc_1801FBFD3
0x1801fbfbb  mov     r9d, ebx; int
0x1801fbfbe  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fbfc5  mov     r8d, 252Dh; int
0x1801fbfcb  mov     rcx, rax; this
0x1801fbfce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fbfd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fbfda  jb      loc_1801FC2E5
0x1801fbfe0  mov     edx, 2E2h
0x1801fbfe5  jmp     loc_1801FC2C7
0x1801fbfea  mov     rcx, [rbp+57h+var_80]
0x1801fbfee  lea     r8, [rbp+57h+var_78]
0x1801fbff2  xor     edx, edx
0x1801fbff4  mov     rax, [rcx]
0x1801fbff7  mov     rax, [rax+88h]
0x1801fbffe  call    cs:__guard_dispatch_icall_fptr
0x1801fc004  mov     ebx, eax
0x1801fc006  test    eax, eax
0x1801fc008  jns     loc_1801FC0A4
0x1801fc00e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fc015  test    rcx, rcx
0x1801fc018  jnz     short loc_1801FC062
0x1801fc01a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801fc021  nop     dword ptr [rax+rax+00h]
0x1801fc026  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fc02d  mov     rcx, rax
0x1801fc030  test    rax, rax
0x1801fc033  jz      short loc_1801FC054
0x1801fc035  mov     rax, [rax]
0x1801fc038  mov     edx, 7F0h
0x1801fc03d  mov     rax, [rax+8]
0x1801fc041  call    cs:__guard_dispatch_icall_fptr
0x1801fc047  test    eax, eax
0x1801fc049  jz      short loc_1801FC054
0x1801fc04b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fc052  jmp     short loc_1801FC062
0x1801fc054  lea     rcx, qword_1803CE250; this
0x1801fc05b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801fc062  cmp     [rcx+8], r13b
0x1801fc066  jz      short loc_1801FC08D
0x1801fc068  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801fc06d  cmp     [rax+7CCh], ebx
0x1801fc073  jz      short loc_1801FC08D
0x1801fc075  mov     r9d, ebx; int
0x1801fc078  lea     rdx, aCmediasessionU_4; "CMediaSession::UpdateInputTypeUINT32"
0x1801fc07f  mov     r8d, 252Eh; int
0x1801fc085  mov     rcx, rax; this
0x1801fc088  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801fc08d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801fc094  jb      loc_1801FC2E5
0x1801fc09a  mov     edx, 2E3h
0x1801fc09f  jmp     loc_1801FC2C7
0x1801fc0a4  mov     rcx, [rbp+57h+var_78]
0x1801fc0a8  mov     rdx, [rbp+57h+ppMFType]
0x1801fc0ac  mov     rax, [rcx]
0x1801fc0af  mov     rax, [rax+100h]
0x1801fc0b6  call    cs:__guard_dispatch_icall_fptr
0x1801fc0bc  mov     ebx, eax
0x1801fc0be  test    eax, eax
0x1801fc0c0  jns     loc_1801FC15C
0x1801fc0c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
