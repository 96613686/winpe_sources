# CMediaSession::UpdateOutputTypeUINT64(unsigned __int64,_GUID,unsigned __int64)

- ea: `0x1801e4a70`
- end: `0x1801e5221`
- name: `?UpdateOutputTypeUINT64@CMediaSession@@UEAAJ_KU_GUID@@0@Z`
- size: `1969`
- prototype: `__int64 __fastcall(CMediaSession *__hidden this, unsigned __int64, struct _GUID *__struct_ptr, unsigned __int64)`
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
- `0x1801e4a70`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1801e4e1e`
- `MFPlat!MFCreateMediaType` at `0x1801e4e1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4cd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4d90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4e40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4efa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e506c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e5129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4c1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4cd5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4d90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4e40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4efa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e4fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e506c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e5129`

## string_xrefs

- `0x1801e4aa0`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4baf`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4c7b`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4d33`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4dee`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4e9e`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e4f58`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e5010`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e50ca`: `CMediaSession::UpdateOutputTypeUINT64`
- `0x1801e5187`: `CMediaSession::UpdateOutputTypeUINT64`

## pseudocode

```c
__int64 __fastcall CMediaSession::UpdateOutputTypeUINT64(CMediaSession *this, __int64 a2, struct _GUID *a3, __int64 a4)
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

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMediaSession::UpdateOutputTypeUINT64", 9626);
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
                v15 = ((__int64 (__fastcall *)(IMFMediaType *, struct _GUID *, __int64))ppMFType->lpVtbl->SetUINT64)(
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
                      CallStackContext::TraceFailure(v59, "CMediaSession::UpdateOutputTypeUINT64", 9648, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 778;
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
                      CallStackContext::TraceFailure(v54, "CMediaSession::UpdateOutputTypeUINT64", 9647, v15);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_105;
                  v19 = 777;
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
                    CallStackContext::TraceFailure(v49, "CMediaSession::UpdateOutputTypeUINT64", 9646, v15);
                }
                if ( !g_wppLevels )
                  goto LABEL_105;
                v19 = 776;
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
                  CallStackContext::TraceFailure(v44, "CMediaSession::UpdateOutputTypeUINT64", 9645, v15);
              }
              if ( !g_wppLevels )
                goto LABEL_105;
              v19 = 775;
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
                CallStackContext::TraceFailure(v39, "CMediaSession::UpdateOutputTypeUINT64", 9644, v15);
            }
            if ( !g_wppLevels )
              goto LABEL_105;
            v19 = 774;
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
              CallStackContext::TraceFailure(v34, "CMediaSession::UpdateOutputTypeUINT64", 9642, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_105;
          v19 = 773;
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
            CallStackContext::TraceFailure(v29, "CMediaSession::UpdateOutputTypeUINT64", 9641, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_105;
        v19 = 772;
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
          CallStackContext::TraceFailure(v24, "CMediaSession::UpdateOutputTypeUINT64", 9640, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_105;
      v19 = 771;
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
      CallStackContext::TraceFailure(v17, "CMediaSession::UpdateOutputTypeUINT64", 9637, -1072875854);
  }
  if ( g_wppLevels )
  {
    v18 = (char *)this - 528;
    v19 = 770;
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
0x1801e4a70  push    rbp
0x1801e4a72  push    rbx
0x1801e4a73  push    rsi
0x1801e4a74  push    rdi
0x1801e4a75  push    r12
0x1801e4a77  push    r13
0x1801e4a79  push    r14
0x1801e4a7b  push    r15
0x1801e4a7d  lea     rbp, [rsp-1Fh]
0x1801e4a82  sub     rsp, 88h
0x1801e4a89  mov     rax, cs:__security_cookie
0x1801e4a90  xor     rax, rsp
0x1801e4a93  mov     [rbp+57h+var_50], rax
0x1801e4a97  mov     r15, r8
0x1801e4a9a  mov     r14, rdx
0x1801e4a9d  mov     rsi, rcx
0x1801e4aa0  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4aa7  mov     r8d, 259Ah; int
0x1801e4aad  lea     rcx, [rbp+57h+var_90]; this
0x1801e4ab1  mov     r12, r9
0x1801e4ab4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801e4ab9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801e4ac0  xor     r13d, r13d
0x1801e4ac3  cmp     [rcx+8], r13b
0x1801e4ac7  jz      short loc_1801E4B26
0x1801e4ac9  cmp     [rsi+440h], r13
0x1801e4ad0  jz      short loc_1801E4B26
0x1801e4ad2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4ad7  mov     rcx, [rsi+440h]
0x1801e4ade  mov     rdi, rax
0x1801e4ae1  mov     rdx, [rcx]
0x1801e4ae4  mov     rax, [rdx+128h]
0x1801e4aeb  call    cs:__guard_dispatch_icall_fptr
0x1801e4af1  mov     rcx, [rsi+440h]
0x1801e4af8  mov     ebx, eax
0x1801e4afa  mov     rdx, [rcx]
0x1801e4afd  mov     rax, [rdx+118h]
0x1801e4b04  lea     rdx, [rbp+57h+var_60]
0x1801e4b08  call    cs:__guard_dispatch_icall_fptr
0x1801e4b0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4b15  movups  xmm0, xmmword ptr [rax]
0x1801e4b18  mov     [rdi+7E0h], ebx
0x1801e4b1e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801e4b26  mov     [rbp+57h+var_68], r13
0x1801e4b2a  mov     [rbp+57h+var_70], r13
0x1801e4b2e  mov     [rbp+57h+var_80], r13
0x1801e4b32  mov     [rbp+57h+var_78], r13
0x1801e4b36  mov     [rbp+57h+ppMFType], r13
0x1801e4b3a  cmp     [rsi+1E0h], r13
0x1801e4b41  jnz     loc_1801E4BE2
0x1801e4b47  mov     ebx, 0C00D36B2h
0x1801e4b4c  test    rcx, rcx
0x1801e4b4f  jnz     short loc_1801E4B99
0x1801e4b51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4b58  nop     dword ptr [rax+rax+00h]
0x1801e4b5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4b64  mov     rcx, rax
0x1801e4b67  test    rax, rax
0x1801e4b6a  jz      short loc_1801E4B8B
0x1801e4b6c  mov     rax, [rax]
0x1801e4b6f  mov     edx, 7F0h
0x1801e4b74  mov     rax, [rax+8]
0x1801e4b78  call    cs:__guard_dispatch_icall_fptr
0x1801e4b7e  test    eax, eax
0x1801e4b80  jz      short loc_1801E4B8B
0x1801e4b82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4b89  jmp     short loc_1801E4B99
0x1801e4b8b  lea     rcx, qword_1803CE250; this
0x1801e4b92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4b99  cmp     [rcx+8], r13b
0x1801e4b9d  jz      short loc_1801E4BC4
0x1801e4b9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4ba4  cmp     [rax+7CCh], ebx
0x1801e4baa  jz      short loc_1801E4BC4
0x1801e4bac  mov     r9d, ebx; int
0x1801e4baf  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4bb6  mov     r8d, 25A5h; int
0x1801e4bbc  mov     rcx, rax; this
0x1801e4bbf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4bc4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4bcb  jb      loc_1801E51C8
0x1801e4bd1  lea     r9, [rsi-210h]
0x1801e4bd8  mov     edx, 302h
0x1801e4bdd  jmp     loc_1801E51AD
0x1801e4be2  lea     rdi, [rsi-210h]
0x1801e4be9  mov     rdx, r14
0x1801e4bec  mov     rcx, [rdi+3F0h]
0x1801e4bf3  lea     r8, [rbp+57h+var_68]
0x1801e4bf7  mov     rax, [rcx]
0x1801e4bfa  mov     rax, [rax+140h]
0x1801e4c01  call    cs:__guard_dispatch_icall_fptr
0x1801e4c07  mov     ebx, eax
0x1801e4c09  test    eax, eax
0x1801e4c0b  jns     loc_1801E4CA7
0x1801e4c11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4c18  test    rcx, rcx
0x1801e4c1b  jnz     short loc_1801E4C65
0x1801e4c1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4c24  nop     dword ptr [rax+rax+00h]
0x1801e4c29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4c30  mov     rcx, rax
0x1801e4c33  test    rax, rax
0x1801e4c36  jz      short loc_1801E4C57
0x1801e4c38  mov     rax, [rax]
0x1801e4c3b  mov     edx, 7F0h
0x1801e4c40  mov     rax, [rax+8]
0x1801e4c44  call    cs:__guard_dispatch_icall_fptr
0x1801e4c4a  test    eax, eax
0x1801e4c4c  jz      short loc_1801E4C57
0x1801e4c4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4c55  jmp     short loc_1801E4C65
0x1801e4c57  lea     rcx, qword_1803CE250; this
0x1801e4c5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4c65  cmp     [rcx+8], r13b
0x1801e4c69  jz      short loc_1801E4C90
0x1801e4c6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4c70  cmp     [rax+7CCh], ebx
0x1801e4c76  jz      short loc_1801E4C90
0x1801e4c78  mov     r9d, ebx; int
0x1801e4c7b  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4c82  mov     r8d, 25A8h; int
0x1801e4c88  mov     rcx, rax; this
0x1801e4c8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4c90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4c97  jb      loc_1801E51C8
0x1801e4c9d  mov     edx, 303h
0x1801e4ca2  jmp     loc_1801E51AA
0x1801e4ca7  mov     rcx, [rbp+57h+var_68]
0x1801e4cab  lea     rdx, [rbp+57h+var_70]
0x1801e4caf  mov     rax, [rcx]
0x1801e4cb2  mov     rax, [rax+110h]
0x1801e4cb9  call    cs:__guard_dispatch_icall_fptr
0x1801e4cbf  mov     ebx, eax
0x1801e4cc1  test    eax, eax
0x1801e4cc3  jns     loc_1801E4D5F
0x1801e4cc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4cd0  test    rcx, rcx
0x1801e4cd3  jnz     short loc_1801E4D1D
0x1801e4cd5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4cdc  nop     dword ptr [rax+rax+00h]
0x1801e4ce1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4ce8  mov     rcx, rax
0x1801e4ceb  test    rax, rax
0x1801e4cee  jz      short loc_1801E4D0F
0x1801e4cf0  mov     rax, [rax]
0x1801e4cf3  mov     edx, 7F0h
0x1801e4cf8  mov     rax, [rax+8]
0x1801e4cfc  call    cs:__guard_dispatch_icall_fptr
0x1801e4d02  test    eax, eax
0x1801e4d04  jz      short loc_1801E4D0F
0x1801e4d06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4d0d  jmp     short loc_1801E4D1D
0x1801e4d0f  lea     rcx, qword_1803CE250; this
0x1801e4d16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4d1d  cmp     [rcx+8], r13b
0x1801e4d21  jz      short loc_1801E4D48
0x1801e4d23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4d28  cmp     [rax+7CCh], ebx
0x1801e4d2e  jz      short loc_1801E4D48
0x1801e4d30  mov     r9d, ebx; int
0x1801e4d33  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4d3a  mov     r8d, 25A9h; int
0x1801e4d40  mov     rcx, rax; this
0x1801e4d43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4d48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4d4f  jb      loc_1801E51C8
0x1801e4d55  mov     edx, 304h
0x1801e4d5a  jmp     loc_1801E51AA
0x1801e4d5f  mov     rcx, [rbp+57h+var_70]
0x1801e4d63  lea     r8, [rbp+57h+var_80]
0x1801e4d67  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1801e4d6e  mov     rax, [rcx]
0x1801e4d71  mov     rax, [rax]
0x1801e4d74  call    cs:__guard_dispatch_icall_fptr
0x1801e4d7a  mov     ebx, eax
0x1801e4d7c  test    eax, eax
0x1801e4d7e  jns     loc_1801E4E1A
0x1801e4d84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4d8b  test    rcx, rcx
0x1801e4d8e  jnz     short loc_1801E4DD8
0x1801e4d90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4d97  nop     dword ptr [rax+rax+00h]
0x1801e4d9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4da3  mov     rcx, rax
0x1801e4da6  test    rax, rax
0x1801e4da9  jz      short loc_1801E4DCA
0x1801e4dab  mov     rax, [rax]
0x1801e4dae  mov     edx, 7F0h
0x1801e4db3  mov     rax, [rax+8]
0x1801e4db7  call    cs:__guard_dispatch_icall_fptr
0x1801e4dbd  test    eax, eax
0x1801e4dbf  jz      short loc_1801E4DCA
0x1801e4dc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4dc8  jmp     short loc_1801E4DD8
0x1801e4dca  lea     rcx, qword_1803CE250; this
0x1801e4dd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4dd8  cmp     [rcx+8], r13b
0x1801e4ddc  jz      short loc_1801E4E03
0x1801e4dde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4de3  cmp     [rax+7CCh], ebx
0x1801e4de9  jz      short loc_1801E4E03
0x1801e4deb  mov     r9d, ebx; int
0x1801e4dee  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4df5  mov     r8d, 25AAh; int
0x1801e4dfb  mov     rcx, rax; this
0x1801e4dfe  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4e03  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4e0a  jb      loc_1801E51C8
0x1801e4e10  mov     edx, 305h
0x1801e4e15  jmp     loc_1801E51AA
0x1801e4e1a  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1801e4e1e  call    cs:__imp_MFCreateMediaType
0x1801e4e25  nop     dword ptr [rax+rax+00h]
0x1801e4e2a  mov     ebx, eax
0x1801e4e2c  test    eax, eax
0x1801e4e2e  jns     loc_1801E4ECA
0x1801e4e34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4e3b  test    rcx, rcx
0x1801e4e3e  jnz     short loc_1801E4E88
0x1801e4e40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4e47  nop     dword ptr [rax+rax+00h]
0x1801e4e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4e53  mov     rcx, rax
0x1801e4e56  test    rax, rax
0x1801e4e59  jz      short loc_1801E4E7A
0x1801e4e5b  mov     rax, [rax]
0x1801e4e5e  mov     edx, 7F0h
0x1801e4e63  mov     rax, [rax+8]
0x1801e4e67  call    cs:__guard_dispatch_icall_fptr
0x1801e4e6d  test    eax, eax
0x1801e4e6f  jz      short loc_1801E4E7A
0x1801e4e71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4e78  jmp     short loc_1801E4E88
0x1801e4e7a  lea     rcx, qword_1803CE250; this
0x1801e4e81  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4e88  cmp     [rcx+8], r13b
0x1801e4e8c  jz      short loc_1801E4EB3
0x1801e4e8e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4e93  cmp     [rax+7CCh], ebx
0x1801e4e99  jz      short loc_1801E4EB3
0x1801e4e9b  mov     r9d, ebx; int
0x1801e4e9e  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4ea5  mov     r8d, 25ACh; int
0x1801e4eab  mov     rcx, rax; this
0x1801e4eae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4eb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4eba  jb      loc_1801E51C8
0x1801e4ec0  mov     edx, 306h
0x1801e4ec5  jmp     loc_1801E51AA
0x1801e4eca  mov     rcx, [rbp+57h+var_80]
0x1801e4ece  lea     r8, [rbp+57h+var_78]
0x1801e4ed2  xor     edx, edx
0x1801e4ed4  mov     rax, [rcx]
0x1801e4ed7  mov     rax, [rax+90h]
0x1801e4ede  call    cs:__guard_dispatch_icall_fptr
0x1801e4ee4  mov     ebx, eax
0x1801e4ee6  test    eax, eax
0x1801e4ee8  jns     loc_1801E4F84
0x1801e4eee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4ef5  test    rcx, rcx
0x1801e4ef8  jnz     short loc_1801E4F42
0x1801e4efa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e4f01  nop     dword ptr [rax+rax+00h]
0x1801e4f06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4f0d  mov     rcx, rax
0x1801e4f10  test    rax, rax
0x1801e4f13  jz      short loc_1801E4F34
0x1801e4f15  mov     rax, [rax]
0x1801e4f18  mov     edx, 7F0h
0x1801e4f1d  mov     rax, [rax+8]
0x1801e4f21  call    cs:__guard_dispatch_icall_fptr
0x1801e4f27  test    eax, eax
0x1801e4f29  jz      short loc_1801E4F34
0x1801e4f2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4f32  jmp     short loc_1801E4F42
0x1801e4f34  lea     rcx, qword_1803CE250; this
0x1801e4f3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e4f42  cmp     [rcx+8], r13b
0x1801e4f46  jz      short loc_1801E4F6D
0x1801e4f48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e4f4d  cmp     [rax+7CCh], ebx
0x1801e4f53  jz      short loc_1801E4F6D
0x1801e4f55  mov     r9d, ebx; int
0x1801e4f58  lea     rdx, aCmediasessionU_2; "CMediaSession::UpdateOutputTypeUINT64"
0x1801e4f5f  mov     r8d, 25ADh; int
0x1801e4f65  mov     rcx, rax; this
0x1801e4f68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e4f6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e4f74  jb      loc_1801E51C8
0x1801e4f7a  mov     edx, 307h
0x1801e4f7f  jmp     loc_1801E51AA
0x1801e4f84  mov     rcx, [rbp+57h+var_78]
0x1801e4f88  mov     rdx, [rbp+57h+ppMFType]
0x1801e4f8c  mov     rax, [rcx]
0x1801e4f8f  mov     rax, [rax+100h]
0x1801e4f96  call    cs:__guard_dispatch_icall_fptr
0x1801e4f9c  mov     ebx, eax
0x1801e4f9e  test    eax, eax
0x1801e4fa0  jns     loc_1801E503C
0x1801e4fa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
