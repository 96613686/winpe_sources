# CMediaSession::UpdateInputTypeGUID(unsigned __int64,_GUID,_GUID)

- ea: `0x1801b2c40`
- end: `0x1801b33ee`
- name: `?UpdateInputTypeGUID@CMediaSession@@UEAAJ_KU_GUID@@U2@@Z`
- size: `1966`
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
- `0x1801b2c40`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801b2fee`
- `MFPlat!MFCreateMediaType` at `0x1801b2fee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2d21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2ded`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2ea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2f60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b3010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b30ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b3182`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b323c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b32f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2d21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2ded`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2ea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b2f60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b3010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b30ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b3182`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b323c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801b32f6`

## string_xrefs

- `0x1801b2c70`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b2d7f`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b2e4b`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b2f03`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b2fbe`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b306e`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b3128`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b31e0`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b329a`: `CMediaSession::UpdateInputTypeGUID`
- `0x1801b3354`: `CMediaSession::UpdateInputTypeGUID`

## pseudocode

```c
__int64 __fastcall CMediaSession::UpdateInputTypeGUID(
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

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMediaSession::UpdateInputTypeGUID", 9467);
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
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, struct _GUID *, struct _GUID *))ppMFType->lpVtbl->SetGUID)(
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
                      CallStackContext::TraceFailure(v59, "CMediaSession::UpdateInputTypeGUID", 9489, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 733;
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
                      CallStackContext::TraceFailure(v54, "CMediaSession::UpdateInputTypeGUID", 9488, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 732;
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
                    CallStackContext::TraceFailure(v49, "CMediaSession::UpdateInputTypeGUID", 9487, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_105;
                v19 = 731;
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
                  CallStackContext::TraceFailure(v44, "CMediaSession::UpdateInputTypeGUID", 9486, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_105;
              v19 = 730;
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
                CallStackContext::TraceFailure(v39, "CMediaSession::UpdateInputTypeGUID", 9485, v15);
            }
            if ( !g_wppLevels )
              goto LABEL_105;
            v19 = 729;
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
              CallStackContext::TraceFailure(v34, "CMediaSession::UpdateInputTypeGUID", 9483, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_105;
          v19 = 728;
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
            CallStackContext::TraceFailure(v29, "CMediaSession::UpdateInputTypeGUID", 9482, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_105;
        v19 = 727;
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
          CallStackContext::TraceFailure(v24, "CMediaSession::UpdateInputTypeGUID", 9481, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v19 = 726;
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
      CallStackContext::TraceFailure(v17, "CMediaSession::UpdateInputTypeGUID", 9478, -1072875854);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 528;
    v19 = 725;
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
0x1801b2c40  push    rbp
0x1801b2c42  push    rbx
0x1801b2c43  push    rsi
0x1801b2c44  push    rdi
0x1801b2c45  push    r12
0x1801b2c47  push    r13
0x1801b2c49  push    r14
0x1801b2c4b  push    r15
0x1801b2c4d  lea     rbp, [rsp-1Fh]
0x1801b2c52  sub     rsp, 88h
0x1801b2c59  mov     rax, cs:__security_cookie
0x1801b2c60  xor     rax, rsp
0x1801b2c63  mov     [rbp+57h+var_50], rax
0x1801b2c67  mov     r15, r8
0x1801b2c6a  mov     r14, rdx
0x1801b2c6d  mov     rsi, rcx
0x1801b2c70  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b2c77  mov     r8d, 24FBh; int
0x1801b2c7d  lea     rcx, [rbp+57h+var_90]; this
0x1801b2c81  mov     r12, r9
0x1801b2c84  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801b2c89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801b2c90  xor     r13d, r13d
0x1801b2c93  cmp     [rcx+8], r13b
0x1801b2c97  jz      short loc_1801B2CF6
0x1801b2c99  cmp     [rsi+440h], r13
0x1801b2ca0  jz      short loc_1801B2CF6
0x1801b2ca2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b2ca7  mov     rcx, [rsi+440h]
0x1801b2cae  mov     rdi, rax
0x1801b2cb1  mov     rdx, [rcx]
0x1801b2cb4  mov     rax, [rdx+128h]
0x1801b2cbb  call    cs:__guard_dispatch_icall_fptr
0x1801b2cc1  mov     rcx, [rsi+440h]
0x1801b2cc8  mov     ebx, eax
0x1801b2cca  mov     rdx, [rcx]
0x1801b2ccd  mov     rax, [rdx+118h]
0x1801b2cd4  lea     rdx, [rbp+57h+var_60]
0x1801b2cd8  call    cs:__guard_dispatch_icall_fptr
0x1801b2cde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2ce5  movups  xmm0, xmmword ptr [rax]
0x1801b2ce8  mov     [rdi+7E0h], ebx
0x1801b2cee  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801b2cf6  mov     [rbp+57h+var_68], r13
0x1801b2cfa  mov     [rbp+57h+var_70], r13
0x1801b2cfe  mov     [rbp+57h+var_80], r13
0x1801b2d02  mov     [rbp+57h+var_78], r13
0x1801b2d06  mov     [rbp+57h+ppMFType], r13
0x1801b2d0a  cmp     [rsi+1E0h], r13
0x1801b2d11  jnz     loc_1801B2DB2
0x1801b2d17  mov     ebx, 0C00D36B2h
0x1801b2d1c  test    rcx, rcx
0x1801b2d1f  jnz     short loc_1801B2D69
0x1801b2d21  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b2d28  nop     dword ptr [rax+rax+00h]
0x1801b2d2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2d34  mov     rcx, rax
0x1801b2d37  test    rax, rax
0x1801b2d3a  jz      short loc_1801B2D5B
0x1801b2d3c  mov     rax, [rax]
0x1801b2d3f  mov     edx, 7F0h
0x1801b2d44  mov     rax, [rax+8]
0x1801b2d48  call    cs:__guard_dispatch_icall_fptr
0x1801b2d4e  test    eax, eax
0x1801b2d50  jz      short loc_1801B2D5B
0x1801b2d52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2d59  jmp     short loc_1801B2D69
0x1801b2d5b  lea     rcx, qword_1803CE250; this
0x1801b2d62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2d69  cmp     [rcx+8], r13b
0x1801b2d6d  jz      short loc_1801B2D94
0x1801b2d6f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b2d74  cmp     [rax+7CCh], ebx
0x1801b2d7a  jz      short loc_1801B2D94
0x1801b2d7c  mov     r9d, ebx; int
0x1801b2d7f  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b2d86  mov     r8d, 2506h; int
0x1801b2d8c  mov     rcx, rax; this
0x1801b2d8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b2d94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b2d9b  jb      loc_1801B3395
0x1801b2da1  lea     r9, [rsi-210h]
0x1801b2da8  mov     edx, 2D5h
0x1801b2dad  jmp     loc_1801B337A
0x1801b2db2  lea     rdi, [rsi-210h]
0x1801b2db9  mov     rdx, r14
0x1801b2dbc  mov     rcx, [rdi+3F0h]
0x1801b2dc3  lea     r8, [rbp+57h+var_68]
0x1801b2dc7  mov     rax, [rcx]
0x1801b2dca  mov     rax, [rax+140h]
0x1801b2dd1  call    cs:__guard_dispatch_icall_fptr
0x1801b2dd7  mov     ebx, eax
0x1801b2dd9  test    eax, eax
0x1801b2ddb  jns     loc_1801B2E77
0x1801b2de1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2de8  test    rcx, rcx
0x1801b2deb  jnz     short loc_1801B2E35
0x1801b2ded  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b2df4  nop     dword ptr [rax+rax+00h]
0x1801b2df9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2e00  mov     rcx, rax
0x1801b2e03  test    rax, rax
0x1801b2e06  jz      short loc_1801B2E27
0x1801b2e08  mov     rax, [rax]
0x1801b2e0b  mov     edx, 7F0h
0x1801b2e10  mov     rax, [rax+8]
0x1801b2e14  call    cs:__guard_dispatch_icall_fptr
0x1801b2e1a  test    eax, eax
0x1801b2e1c  jz      short loc_1801B2E27
0x1801b2e1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2e25  jmp     short loc_1801B2E35
0x1801b2e27  lea     rcx, qword_1803CE250; this
0x1801b2e2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2e35  cmp     [rcx+8], r13b
0x1801b2e39  jz      short loc_1801B2E60
0x1801b2e3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b2e40  cmp     [rax+7CCh], ebx
0x1801b2e46  jz      short loc_1801B2E60
0x1801b2e48  mov     r9d, ebx; int
0x1801b2e4b  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b2e52  mov     r8d, 2509h; int
0x1801b2e58  mov     rcx, rax; this
0x1801b2e5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b2e60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b2e67  jb      loc_1801B3395
0x1801b2e6d  mov     edx, 2D6h
0x1801b2e72  jmp     loc_1801B3377
0x1801b2e77  mov     rcx, [rbp+57h+var_68]
0x1801b2e7b  lea     rdx, [rbp+57h+var_70]
0x1801b2e7f  mov     rax, [rcx]
0x1801b2e82  mov     rax, [rax+110h]
0x1801b2e89  call    cs:__guard_dispatch_icall_fptr
0x1801b2e8f  mov     ebx, eax
0x1801b2e91  test    eax, eax
0x1801b2e93  jns     loc_1801B2F2F
0x1801b2e99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2ea0  test    rcx, rcx
0x1801b2ea3  jnz     short loc_1801B2EED
0x1801b2ea5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b2eac  nop     dword ptr [rax+rax+00h]
0x1801b2eb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2eb8  mov     rcx, rax
0x1801b2ebb  test    rax, rax
0x1801b2ebe  jz      short loc_1801B2EDF
0x1801b2ec0  mov     rax, [rax]
0x1801b2ec3  mov     edx, 7F0h
0x1801b2ec8  mov     rax, [rax+8]
0x1801b2ecc  call    cs:__guard_dispatch_icall_fptr
0x1801b2ed2  test    eax, eax
0x1801b2ed4  jz      short loc_1801B2EDF
0x1801b2ed6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2edd  jmp     short loc_1801B2EED
0x1801b2edf  lea     rcx, qword_1803CE250; this
0x1801b2ee6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2eed  cmp     [rcx+8], r13b
0x1801b2ef1  jz      short loc_1801B2F18
0x1801b2ef3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b2ef8  cmp     [rax+7CCh], ebx
0x1801b2efe  jz      short loc_1801B2F18
0x1801b2f00  mov     r9d, ebx; int
0x1801b2f03  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b2f0a  mov     r8d, 250Ah; int
0x1801b2f10  mov     rcx, rax; this
0x1801b2f13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b2f18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b2f1f  jb      loc_1801B3395
0x1801b2f25  mov     edx, 2D7h
0x1801b2f2a  jmp     loc_1801B3377
0x1801b2f2f  mov     rcx, [rbp+57h+var_70]
0x1801b2f33  lea     r8, [rbp+57h+var_80]
0x1801b2f37  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1801b2f3e  mov     rax, [rcx]
0x1801b2f41  mov     rax, [rax]
0x1801b2f44  call    cs:__guard_dispatch_icall_fptr
0x1801b2f4a  mov     ebx, eax
0x1801b2f4c  test    eax, eax
0x1801b2f4e  jns     loc_1801B2FEA
0x1801b2f54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2f5b  test    rcx, rcx
0x1801b2f5e  jnz     short loc_1801B2FA8
0x1801b2f60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b2f67  nop     dword ptr [rax+rax+00h]
0x1801b2f6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2f73  mov     rcx, rax
0x1801b2f76  test    rax, rax
0x1801b2f79  jz      short loc_1801B2F9A
0x1801b2f7b  mov     rax, [rax]
0x1801b2f7e  mov     edx, 7F0h
0x1801b2f83  mov     rax, [rax+8]
0x1801b2f87  call    cs:__guard_dispatch_icall_fptr
0x1801b2f8d  test    eax, eax
0x1801b2f8f  jz      short loc_1801B2F9A
0x1801b2f91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2f98  jmp     short loc_1801B2FA8
0x1801b2f9a  lea     rcx, qword_1803CE250; this
0x1801b2fa1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b2fa8  cmp     [rcx+8], r13b
0x1801b2fac  jz      short loc_1801B2FD3
0x1801b2fae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b2fb3  cmp     [rax+7CCh], ebx
0x1801b2fb9  jz      short loc_1801B2FD3
0x1801b2fbb  mov     r9d, ebx; int
0x1801b2fbe  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b2fc5  mov     r8d, 250Bh; int
0x1801b2fcb  mov     rcx, rax; this
0x1801b2fce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b2fd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b2fda  jb      loc_1801B3395
0x1801b2fe0  mov     edx, 2D8h
0x1801b2fe5  jmp     loc_1801B3377
0x1801b2fea  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801b2fee  call    cs:__imp_MFCreateMediaType
0x1801b2ff5  nop     dword ptr [rax+rax+00h]
0x1801b2ffa  mov     ebx, eax
0x1801b2ffc  test    eax, eax
0x1801b2ffe  jns     loc_1801B309A
0x1801b3004  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b300b  test    rcx, rcx
0x1801b300e  jnz     short loc_1801B3058
0x1801b3010  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b3017  nop     dword ptr [rax+rax+00h]
0x1801b301c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b3023  mov     rcx, rax
0x1801b3026  test    rax, rax
0x1801b3029  jz      short loc_1801B304A
0x1801b302b  mov     rax, [rax]
0x1801b302e  mov     edx, 7F0h
0x1801b3033  mov     rax, [rax+8]
0x1801b3037  call    cs:__guard_dispatch_icall_fptr
0x1801b303d  test    eax, eax
0x1801b303f  jz      short loc_1801B304A
0x1801b3041  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b3048  jmp     short loc_1801B3058
0x1801b304a  lea     rcx, qword_1803CE250; this
0x1801b3051  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b3058  cmp     [rcx+8], r13b
0x1801b305c  jz      short loc_1801B3083
0x1801b305e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b3063  cmp     [rax+7CCh], ebx
0x1801b3069  jz      short loc_1801B3083
0x1801b306b  mov     r9d, ebx; int
0x1801b306e  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b3075  mov     r8d, 250Dh; int
0x1801b307b  mov     rcx, rax; this
0x1801b307e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b3083  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b308a  jb      loc_1801B3395
0x1801b3090  mov     edx, 2D9h
0x1801b3095  jmp     loc_1801B3377
0x1801b309a  mov     rcx, [rbp+57h+var_80]
0x1801b309e  lea     r8, [rbp+57h+var_78]
0x1801b30a2  xor     edx, edx
0x1801b30a4  mov     rax, [rcx]
0x1801b30a7  mov     rax, [rax+88h]
0x1801b30ae  call    cs:__guard_dispatch_icall_fptr
0x1801b30b4  mov     ebx, eax
0x1801b30b6  test    eax, eax
0x1801b30b8  jns     loc_1801B3154
0x1801b30be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b30c5  test    rcx, rcx
0x1801b30c8  jnz     short loc_1801B3112
0x1801b30ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801b30d1  nop     dword ptr [rax+rax+00h]
0x1801b30d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b30dd  mov     rcx, rax
0x1801b30e0  test    rax, rax
0x1801b30e3  jz      short loc_1801B3104
0x1801b30e5  mov     rax, [rax]
0x1801b30e8  mov     edx, 7F0h
0x1801b30ed  mov     rax, [rax+8]
0x1801b30f1  call    cs:__guard_dispatch_icall_fptr
0x1801b30f7  test    eax, eax
0x1801b30f9  jz      short loc_1801B3104
0x1801b30fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b3102  jmp     short loc_1801B3112
0x1801b3104  lea     rcx, qword_1803CE250; this
0x1801b310b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801b3112  cmp     [rcx+8], r13b
0x1801b3116  jz      short loc_1801B313D
0x1801b3118  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801b311d  cmp     [rax+7CCh], ebx
0x1801b3123  jz      short loc_1801B313D
0x1801b3125  mov     r9d, ebx; int
0x1801b3128  lea     rdx, aCmediasessionU_0; "CMediaSession::UpdateInputTypeGUID"
0x1801b312f  mov     r8d, 250Eh; int
0x1801b3135  mov     rcx, rax; this
0x1801b3138  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801b313d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801b3144  jb      loc_1801B3395
0x1801b314a  mov     edx, 2DAh
0x1801b314f  jmp     loc_1801B3377
0x1801b3154  mov     rcx, [rbp+57h+var_78]
0x1801b3158  mov     rdx, [rbp+57h+ppMFType]
0x1801b315c  mov     rax, [rcx]
0x1801b315f  mov     rax, [rax+100h]
0x1801b3166  call    cs:__guard_dispatch_icall_fptr
0x1801b316c  mov     ebx, eax
0x1801b316e  test    eax, eax
0x1801b3170  jns     loc_1801B320C
0x1801b3176  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
