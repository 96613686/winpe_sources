# CMediaSession::UpdateOutputTypeGUID(unsigned __int64,_GUID,_GUID)

- ea: `0x1801dcfc0`
- end: `0x1801dd771`
- name: `?UpdateOutputTypeGUID@CMediaSession@@UEAAJ_KU_GUID@@U2@@Z`
- size: `1969`
- prototype: `__int64 __fastcall(CMediaSession *__hidden this, unsigned __int64, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
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
- `0x1801dcfc0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFCreateMediaType` at `0x1801dd36e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd0a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd16d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd2e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd390`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801dd679`

## string_xrefs

- `0x1801dcff0`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd0ff`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd1cb`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd283`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd33e`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd3ee`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd4a8`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd560`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd61a`: `CMediaSession::UpdateOutputTypeGUID`
- `0x1801dd6d7`: `CMediaSession::UpdateOutputTypeGUID`

## pseudocode

```c
__int64 __fastcall CMediaSession::UpdateOutputTypeGUID(
        CMediaSession *this,
        __int64 a2,
        struct _GUID *a3,
        struct _GUID *a4)
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

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMediaSession::UpdateOutputTypeGUID", 9562);
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
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, struct _GUID *, struct _GUID *))ppMFType->lpVtbl->SetGUID)(
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
                      CallStackContext::TraceFailure(v59, "CMediaSession::UpdateOutputTypeGUID", 9584, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 760;
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
                      CallStackContext::TraceFailure(v54, "CMediaSession::UpdateOutputTypeGUID", 9583, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 759;
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
                    CallStackContext::TraceFailure(v49, "CMediaSession::UpdateOutputTypeGUID", 9582, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_105;
                v19 = 758;
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
                  CallStackContext::TraceFailure(v44, "CMediaSession::UpdateOutputTypeGUID", 9581, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_105;
              v19 = 757;
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
                CallStackContext::TraceFailure(v39, "CMediaSession::UpdateOutputTypeGUID", 9580, v15);
            }
            if ( !g_wppLevels )
              goto LABEL_105;
            v19 = 756;
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
              CallStackContext::TraceFailure(v34, "CMediaSession::UpdateOutputTypeGUID", 9578, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_105;
          v19 = 755;
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
            CallStackContext::TraceFailure(v29, "CMediaSession::UpdateOutputTypeGUID", 9577, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_105;
        v19 = 754;
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
          CallStackContext::TraceFailure(v24, "CMediaSession::UpdateOutputTypeGUID", 9576, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v19 = 753;
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
      CallStackContext::TraceFailure(v17, "CMediaSession::UpdateOutputTypeGUID", 9573, -1072875854);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 528;
    v19 = 752;
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
0x1801dcfc0  push    rbp
0x1801dcfc2  push    rbx
0x1801dcfc3  push    rsi
0x1801dcfc4  push    rdi
0x1801dcfc5  push    r12
0x1801dcfc7  push    r13
0x1801dcfc9  push    r14
0x1801dcfcb  push    r15
0x1801dcfcd  lea     rbp, [rsp-1Fh]
0x1801dcfd2  sub     rsp, 88h
0x1801dcfd9  mov     rax, cs:__security_cookie
0x1801dcfe0  xor     rax, rsp
0x1801dcfe3  mov     [rbp+57h+var_50], rax
0x1801dcfe7  mov     r15, r8
0x1801dcfea  mov     r14, rdx
0x1801dcfed  mov     rsi, rcx
0x1801dcff0  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dcff7  mov     r8d, 255Ah; int
0x1801dcffd  lea     rcx, [rbp+57h+var_90]; this
0x1801dd001  mov     r12, r9
0x1801dd004  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801dd009  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801dd010  xor     r13d, r13d
0x1801dd013  cmp     [rcx+8], r13b
0x1801dd017  jz      short loc_1801DD076
0x1801dd019  cmp     [rsi+440h], r13
0x1801dd020  jz      short loc_1801DD076
0x1801dd022  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd027  mov     rcx, [rsi+440h]
0x1801dd02e  mov     rdi, rax
0x1801dd031  mov     rdx, [rcx]
0x1801dd034  mov     rax, [rdx+128h]
0x1801dd03b  call    cs:__guard_dispatch_icall_fptr
0x1801dd041  mov     rcx, [rsi+440h]
0x1801dd048  mov     ebx, eax
0x1801dd04a  mov     rdx, [rcx]
0x1801dd04d  mov     rax, [rdx+118h]
0x1801dd054  lea     rdx, [rbp+57h+var_60]
0x1801dd058  call    cs:__guard_dispatch_icall_fptr
0x1801dd05e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd065  movups  xmm0, xmmword ptr [rax]
0x1801dd068  mov     [rdi+7E0h], ebx
0x1801dd06e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801dd076  mov     [rbp+57h+var_68], r13
0x1801dd07a  mov     [rbp+57h+var_70], r13
0x1801dd07e  mov     [rbp+57h+var_80], r13
0x1801dd082  mov     [rbp+57h+var_78], r13
0x1801dd086  mov     [rbp+57h+ppMFType], r13
0x1801dd08a  cmp     [rsi+1E0h], r13
0x1801dd091  jnz     loc_1801DD132
0x1801dd097  mov     ebx, 0C00D36B2h
0x1801dd09c  test    rcx, rcx
0x1801dd09f  jnz     short loc_1801DD0E9
0x1801dd0a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd0a8  nop     dword ptr [rax+rax+00h]
0x1801dd0ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd0b4  mov     rcx, rax
0x1801dd0b7  test    rax, rax
0x1801dd0ba  jz      short loc_1801DD0DB
0x1801dd0bc  mov     rax, [rax]
0x1801dd0bf  mov     edx, 7F0h
0x1801dd0c4  mov     rax, [rax+8]
0x1801dd0c8  call    cs:__guard_dispatch_icall_fptr
0x1801dd0ce  test    eax, eax
0x1801dd0d0  jz      short loc_1801DD0DB
0x1801dd0d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd0d9  jmp     short loc_1801DD0E9
0x1801dd0db  lea     rcx, qword_1803CE250; this
0x1801dd0e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd0e9  cmp     [rcx+8], r13b
0x1801dd0ed  jz      short loc_1801DD114
0x1801dd0ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd0f4  cmp     [rax+7CCh], ebx
0x1801dd0fa  jz      short loc_1801DD114
0x1801dd0fc  mov     r9d, ebx; int
0x1801dd0ff  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd106  mov     r8d, 2565h; int
0x1801dd10c  mov     rcx, rax; this
0x1801dd10f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd114  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd11b  jb      loc_1801DD718
0x1801dd121  lea     r9, [rsi-210h]
0x1801dd128  mov     edx, 2F0h
0x1801dd12d  jmp     loc_1801DD6FD
0x1801dd132  lea     rdi, [rsi-210h]
0x1801dd139  mov     rdx, r14
0x1801dd13c  mov     rcx, [rdi+3F0h]
0x1801dd143  lea     r8, [rbp+57h+var_68]
0x1801dd147  mov     rax, [rcx]
0x1801dd14a  mov     rax, [rax+140h]
0x1801dd151  call    cs:__guard_dispatch_icall_fptr
0x1801dd157  mov     ebx, eax
0x1801dd159  test    eax, eax
0x1801dd15b  jns     loc_1801DD1F7
0x1801dd161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd168  test    rcx, rcx
0x1801dd16b  jnz     short loc_1801DD1B5
0x1801dd16d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd174  nop     dword ptr [rax+rax+00h]
0x1801dd179  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd180  mov     rcx, rax
0x1801dd183  test    rax, rax
0x1801dd186  jz      short loc_1801DD1A7
0x1801dd188  mov     rax, [rax]
0x1801dd18b  mov     edx, 7F0h
0x1801dd190  mov     rax, [rax+8]
0x1801dd194  call    cs:__guard_dispatch_icall_fptr
0x1801dd19a  test    eax, eax
0x1801dd19c  jz      short loc_1801DD1A7
0x1801dd19e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd1a5  jmp     short loc_1801DD1B5
0x1801dd1a7  lea     rcx, qword_1803CE250; this
0x1801dd1ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd1b5  cmp     [rcx+8], r13b
0x1801dd1b9  jz      short loc_1801DD1E0
0x1801dd1bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd1c0  cmp     [rax+7CCh], ebx
0x1801dd1c6  jz      short loc_1801DD1E0
0x1801dd1c8  mov     r9d, ebx; int
0x1801dd1cb  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd1d2  mov     r8d, 2568h; int
0x1801dd1d8  mov     rcx, rax; this
0x1801dd1db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd1e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd1e7  jb      loc_1801DD718
0x1801dd1ed  mov     edx, 2F1h
0x1801dd1f2  jmp     loc_1801DD6FA
0x1801dd1f7  mov     rcx, [rbp+57h+var_68]
0x1801dd1fb  lea     rdx, [rbp+57h+var_70]
0x1801dd1ff  mov     rax, [rcx]
0x1801dd202  mov     rax, [rax+110h]
0x1801dd209  call    cs:__guard_dispatch_icall_fptr
0x1801dd20f  mov     ebx, eax
0x1801dd211  test    eax, eax
0x1801dd213  jns     loc_1801DD2AF
0x1801dd219  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd220  test    rcx, rcx
0x1801dd223  jnz     short loc_1801DD26D
0x1801dd225  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd22c  nop     dword ptr [rax+rax+00h]
0x1801dd231  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd238  mov     rcx, rax
0x1801dd23b  test    rax, rax
0x1801dd23e  jz      short loc_1801DD25F
0x1801dd240  mov     rax, [rax]
0x1801dd243  mov     edx, 7F0h
0x1801dd248  mov     rax, [rax+8]
0x1801dd24c  call    cs:__guard_dispatch_icall_fptr
0x1801dd252  test    eax, eax
0x1801dd254  jz      short loc_1801DD25F
0x1801dd256  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd25d  jmp     short loc_1801DD26D
0x1801dd25f  lea     rcx, qword_1803CE250; this
0x1801dd266  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd26d  cmp     [rcx+8], r13b
0x1801dd271  jz      short loc_1801DD298
0x1801dd273  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd278  cmp     [rax+7CCh], ebx
0x1801dd27e  jz      short loc_1801DD298
0x1801dd280  mov     r9d, ebx; int
0x1801dd283  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd28a  mov     r8d, 2569h; int
0x1801dd290  mov     rcx, rax; this
0x1801dd293  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd298  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd29f  jb      loc_1801DD718
0x1801dd2a5  mov     edx, 2F2h
0x1801dd2aa  jmp     loc_1801DD6FA
0x1801dd2af  mov     rcx, [rbp+57h+var_70]
0x1801dd2b3  lea     r8, [rbp+57h+var_80]
0x1801dd2b7  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1801dd2be  mov     rax, [rcx]
0x1801dd2c1  mov     rax, [rax]
0x1801dd2c4  call    cs:__guard_dispatch_icall_fptr
0x1801dd2ca  mov     ebx, eax
0x1801dd2cc  test    eax, eax
0x1801dd2ce  jns     loc_1801DD36A
0x1801dd2d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd2db  test    rcx, rcx
0x1801dd2de  jnz     short loc_1801DD328
0x1801dd2e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd2e7  nop     dword ptr [rax+rax+00h]
0x1801dd2ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd2f3  mov     rcx, rax
0x1801dd2f6  test    rax, rax
0x1801dd2f9  jz      short loc_1801DD31A
0x1801dd2fb  mov     rax, [rax]
0x1801dd2fe  mov     edx, 7F0h
0x1801dd303  mov     rax, [rax+8]
0x1801dd307  call    cs:__guard_dispatch_icall_fptr
0x1801dd30d  test    eax, eax
0x1801dd30f  jz      short loc_1801DD31A
0x1801dd311  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd318  jmp     short loc_1801DD328
0x1801dd31a  lea     rcx, qword_1803CE250; this
0x1801dd321  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd328  cmp     [rcx+8], r13b
0x1801dd32c  jz      short loc_1801DD353
0x1801dd32e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd333  cmp     [rax+7CCh], ebx
0x1801dd339  jz      short loc_1801DD353
0x1801dd33b  mov     r9d, ebx; int
0x1801dd33e  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd345  mov     r8d, 256Ah; int
0x1801dd34b  mov     rcx, rax; this
0x1801dd34e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd353  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd35a  jb      loc_1801DD718
0x1801dd360  mov     edx, 2F3h
0x1801dd365  jmp     loc_1801DD6FA
0x1801dd36a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801dd36e  call    cs:__imp_MFCreateMediaType
0x1801dd375  nop     dword ptr [rax+rax+00h]
0x1801dd37a  mov     ebx, eax
0x1801dd37c  test    eax, eax
0x1801dd37e  jns     loc_1801DD41A
0x1801dd384  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd38b  test    rcx, rcx
0x1801dd38e  jnz     short loc_1801DD3D8
0x1801dd390  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd397  nop     dword ptr [rax+rax+00h]
0x1801dd39c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd3a3  mov     rcx, rax
0x1801dd3a6  test    rax, rax
0x1801dd3a9  jz      short loc_1801DD3CA
0x1801dd3ab  mov     rax, [rax]
0x1801dd3ae  mov     edx, 7F0h
0x1801dd3b3  mov     rax, [rax+8]
0x1801dd3b7  call    cs:__guard_dispatch_icall_fptr
0x1801dd3bd  test    eax, eax
0x1801dd3bf  jz      short loc_1801DD3CA
0x1801dd3c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd3c8  jmp     short loc_1801DD3D8
0x1801dd3ca  lea     rcx, qword_1803CE250; this
0x1801dd3d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd3d8  cmp     [rcx+8], r13b
0x1801dd3dc  jz      short loc_1801DD403
0x1801dd3de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd3e3  cmp     [rax+7CCh], ebx
0x1801dd3e9  jz      short loc_1801DD403
0x1801dd3eb  mov     r9d, ebx; int
0x1801dd3ee  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd3f5  mov     r8d, 256Ch; int
0x1801dd3fb  mov     rcx, rax; this
0x1801dd3fe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd403  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd40a  jb      loc_1801DD718
0x1801dd410  mov     edx, 2F4h
0x1801dd415  jmp     loc_1801DD6FA
0x1801dd41a  mov     rcx, [rbp+57h+var_80]
0x1801dd41e  lea     r8, [rbp+57h+var_78]
0x1801dd422  xor     edx, edx
0x1801dd424  mov     rax, [rcx]
0x1801dd427  mov     rax, [rax+90h]
0x1801dd42e  call    cs:__guard_dispatch_icall_fptr
0x1801dd434  mov     ebx, eax
0x1801dd436  test    eax, eax
0x1801dd438  jns     loc_1801DD4D4
0x1801dd43e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd445  test    rcx, rcx
0x1801dd448  jnz     short loc_1801DD492
0x1801dd44a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801dd451  nop     dword ptr [rax+rax+00h]
0x1801dd456  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd45d  mov     rcx, rax
0x1801dd460  test    rax, rax
0x1801dd463  jz      short loc_1801DD484
0x1801dd465  mov     rax, [rax]
0x1801dd468  mov     edx, 7F0h
0x1801dd46d  mov     rax, [rax+8]
0x1801dd471  call    cs:__guard_dispatch_icall_fptr
0x1801dd477  test    eax, eax
0x1801dd479  jz      short loc_1801DD484
0x1801dd47b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd482  jmp     short loc_1801DD492
0x1801dd484  lea     rcx, qword_1803CE250; this
0x1801dd48b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801dd492  cmp     [rcx+8], r13b
0x1801dd496  jz      short loc_1801DD4BD
0x1801dd498  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801dd49d  cmp     [rax+7CCh], ebx
0x1801dd4a3  jz      short loc_1801DD4BD
0x1801dd4a5  mov     r9d, ebx; int
0x1801dd4a8  lea     rdx, aCmediasessionU_5; "CMediaSession::UpdateOutputTypeGUID"
0x1801dd4af  mov     r8d, 256Dh; int
0x1801dd4b5  mov     rcx, rax; this
0x1801dd4b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801dd4bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801dd4c4  jb      loc_1801DD718
0x1801dd4ca  mov     edx, 2F5h
0x1801dd4cf  jmp     loc_1801DD6FA
0x1801dd4d4  mov     rcx, [rbp+57h+var_78]
0x1801dd4d8  mov     rdx, [rbp+57h+ppMFType]
0x1801dd4dc  mov     rax, [rcx]
0x1801dd4df  mov     rax, [rax+100h]
0x1801dd4e6  call    cs:__guard_dispatch_icall_fptr
0x1801dd4ec  mov     ebx, eax
0x1801dd4ee  test    eax, eax
0x1801dd4f0  jns     loc_1801DD58C
0x1801dd4f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
