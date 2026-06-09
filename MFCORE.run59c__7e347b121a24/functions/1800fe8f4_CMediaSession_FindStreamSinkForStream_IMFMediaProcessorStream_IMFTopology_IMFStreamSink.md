# CMediaSession::FindStreamSinkForStream(IMFMediaProcessorStream *,IMFTopology *,IMFStreamSink * *)

- ea: `0x1800fe8f4`
- end: `0x1800ff0e3`
- name: `?FindStreamSinkForStream@CMediaSession@@AEAAJPEAUIMFMediaProcessorStream@@PEAUIMFTopology@@PEAPEAUIMFStreamSink@@@Z`
- size: `2031`
- prototype: `__int64 __fastcall(CMediaSession *__hidden this, struct IMFMediaProcessorStream *, struct IMFTopology *, struct IMFStreamSink **)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800fe35c`
- `0x180290074`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800717b4`
- `0x1800ec0e0`
- `0x1800fe8f4`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800feb65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800febe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fecb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fed48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fede0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fee78`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800feb65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800febe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fecb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fed48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fede0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fee78`

## string_xrefs

- `0x1800fe924`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fec5f`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fec8a`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fed25`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fedbd`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fee55`: `CMediaSession::FindStreamSinkForStream`
- `0x1800feeed`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fef18`: `CMediaSession::FindStreamSinkForStream`
- `0x1800fef46`: `CMediaSession::FindStreamSinkForStream`

## pseudocode

```c
__int64 __fastcall CMediaSession::FindStreamSinkForStream(
        CMediaSession *this,
        struct IMFMediaProcessorStream *a2,
        struct IMFTopology *a3,
        struct IMFStreamSink **a4)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct IMFMediaProcessorStream *, __int64 *); // rax
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r8
  CallStackTracing *v13; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int16 i; // r14
  CallStackTracing *v18; // rcx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v41; // ebx
  __int128 v42; // xmm0
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  _BYTE v47[4]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 v48; // [rsp+34h] [rbp-35h] BYREF
  __int64 v49; // [rsp+38h] [rbp-31h] BYREF
  __int64 v50; // [rsp+40h] [rbp-29h] BYREF
  __int64 v51; // [rsp+48h] [rbp-21h] BYREF
  __int64 v52; // [rsp+50h] [rbp-19h] BYREF
  __int64 v53; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v54[16]; // [rsp+60h] [rbp-9h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v47, "CMediaSession::FindStreamSinkForStream", 6058);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 202) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 202) + 296LL))(*((_QWORD *)this + 202));
    v42 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 202) + 280LL))(
                       *((_QWORD *)this + 202),
                       v54);
    *((_DWORD *)ThreadRelativeContext + 504) = v41;
    *((_OWORD *)ThreadRelativeContext + 125) = v42;
  }
  v8 = *(_QWORD *)a2;
  v52 = 0;
  v50 = 0;
  v49 = 0;
  v9 = *(__int64 (__fastcall **)(struct IMFMediaProcessorStream *, __int64 *))(v8 + 56);
  v51 = 0;
  v48 = 0;
  v53 = 0;
  v11 = v9(a2, &v52);
  if ( v11 < 0 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
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
      if ( *((_DWORD *)v24 + 499) != v11 )
        CallStackContext::TraceFailure(v24, "CMediaSession::FindStreamSinkForStream", 6072, v11);
    }
    if ( g_wppLevels )
    {
      v19 = 456;
      goto LABEL_37;
    }
  }
  else
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 457, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, this, v52);
    v11 = ((__int64 (__fastcall *)(struct IMFTopology *, GUID *, __int64 *))a3->lpVtbl->QueryInterface)(
            a3,
            &IID_IMFTopologyPriv,
            &v50);
    if ( v11 < 0 )
    {
      v13 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v13 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v13);
        if ( *((_DWORD *)v25 + 499) != v11 )
          CallStackContext::TraceFailure(v25, "CMediaSession::FindStreamSinkForStream", 6082, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_10;
      v19 = 458;
LABEL_37:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, this, v11);
      goto LABEL_10;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v50 + 24LL))(v50, &v48);
    if ( v11 < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != v11 )
          CallStackContext::TraceFailure(v28, "CMediaSession::FindStreamSinkForStream", 6084, v11);
      }
      if ( g_wppLevels )
      {
        v19 = 459;
        goto LABEL_37;
      }
    }
    else
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 460, &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids, this, v48);
      for ( i = 0; ; ++i )
      {
        if ( i >= v48 )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          v11 = -2147467259;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v39 + 499) != -2147467259 )
              CallStackContext::TraceFailure(v39, "CMediaSession::FindStreamSinkForStream", 6126, -2147467259);
          }
          if ( g_wppLevels )
          {
            v19 = 466;
            goto LABEL_37;
          }
          goto LABEL_10;
        }
        if ( v49 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          v49 = 0;
        }
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v50 + 32LL))(v50, i, &v49);
        if ( v11 < 0 )
        {
          v18 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v18 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext(v18);
            if ( *((_DWORD *)v38 + 499) != v11 )
              CallStackContext::TraceFailure(v38, "CMediaSession::FindStreamSinkForStream", 6095, v11);
          }
          if ( g_wppLevels )
          {
            v19 = 461;
            goto LABEL_37;
          }
          goto LABEL_10;
        }
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 288LL))(v49, &v53);
        if ( v11 < 0 )
          break;
        if ( v53 == v52 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 272LL))(v49, &v51);
          if ( v11 < 0 )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)v31 + 499) != v11 )
                CallStackContext::TraceFailure(v31, "CMediaSession::FindStreamSinkForStream", 6104, v11);
            }
            if ( g_wppLevels )
            {
              v19 = 463;
              goto LABEL_37;
            }
          }
          else
          {
            v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMFStreamSink **))v51)(
                    v51,
                    &IID_IMFStreamSink,
                    a4);
            if ( v11 < 0 )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
                if ( *((_DWORD *)v34 + 499) != v11 )
                  CallStackContext::TraceFailure(v34, "CMediaSession::FindStreamSinkForStream", 6107, v11);
              }
              if ( g_wppLevels )
              {
                v19 = 464;
                goto LABEL_37;
              }
            }
            else if ( (unsigned __int8)byte_1803CECE9 >= 8u )
            {
              WPP_SF_qqD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                465,
                &WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids,
                this,
                *a4,
                v53);
            }
          }
          goto LABEL_10;
        }
      }
      v35 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != v11 )
          CallStackContext::TraceFailure(v37, "CMediaSession::FindStreamSinkForStream", 6097, v11);
      }
      if ( g_wppLevels )
      {
        v19 = 462;
        goto LABEL_37;
      }
    }
  }
LABEL_10:
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800fe8f4  push    rbp
0x1800fe8f6  push    rbx
0x1800fe8f7  push    rsi
0x1800fe8f8  push    rdi
0x1800fe8f9  push    r12
0x1800fe8fb  push    r13
0x1800fe8fd  push    r14
0x1800fe8ff  push    r15
0x1800fe901  lea     rbp, [rsp-1Fh]
0x1800fe906  sub     rsp, 88h
0x1800fe90d  mov     rax, cs:__security_cookie
0x1800fe914  xor     rax, rsp
0x1800fe917  mov     [rbp+57h+var_50], rax
0x1800fe91b  mov     r15, r8
0x1800fe91e  mov     r14, rdx
0x1800fe921  mov     rsi, rcx
0x1800fe924  lea     rdx, aCmediasessionF_0; "CMediaSession::FindStreamSinkForStream"
0x1800fe92b  mov     r8d, 17AAh; int
0x1800fe931  lea     rcx, [rbp+57h+var_90]; this
0x1800fe935  mov     r12, r9
0x1800fe938  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800fe93d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800fe944  xor     r13d, r13d
0x1800fe947  cmp     [rcx+8], r13b
0x1800fe94b  jnz     loc_1800FEF60
0x1800fe951  mov     rax, [r14]
0x1800fe954  lea     rdx, [rbp+57h+var_70]
0x1800fe958  mov     rcx, r14
0x1800fe95b  mov     [rbp+57h+var_70], r13
0x1800fe95f  mov     [rbp+57h+var_80], r13
0x1800fe963  mov     [rbp+57h+var_88], r13
0x1800fe967  mov     rax, [rax+38h]
0x1800fe96b  mov     [rbp+57h+var_78], r13
0x1800fe96f  mov     [rbp+57h+var_8C], r13w
0x1800fe974  mov     [rbp+57h+var_68], r13
0x1800fe978  call    cs:__guard_dispatch_icall_fptr
0x1800fe97e  mov     ebx, eax
0x1800fe980  test    eax, eax
0x1800fe982  js      loc_1800FEBD7
0x1800fe988  cmp     cs:byte_1803CECE9, 8
0x1800fe98f  lea     rdi, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x1800fe996  jnb     loc_1800FEFC5
0x1800fe99c  mov     rax, [r15]
0x1800fe99f  lea     r8, [rbp+57h+var_80]
0x1800fe9a3  lea     rdx, IID_IMFTopologyPriv
0x1800fe9aa  mov     rcx, r15
0x1800fe9ad  mov     rax, [rax]
0x1800fe9b0  call    cs:__guard_dispatch_icall_fptr
0x1800fe9b6  mov     ebx, eax
0x1800fe9b8  test    eax, eax
0x1800fe9ba  jns     short loc_1800FEA36
0x1800fe9bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800fe9c3  test    rcx, rcx
0x1800fe9c6  jz      loc_1800FEBA2
0x1800fe9cc  cmp     [rcx+8], r13b
0x1800fe9d0  jnz     loc_1800FEC76
0x1800fe9d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fe9dd  jnb     loc_1800FEFEC
0x1800fe9e3  mov     rcx, [rbp+57h+var_80]
0x1800fe9e7  test    rcx, rcx
0x1800fe9ea  jnz     loc_1800FF0A1
0x1800fe9f0  mov     rcx, [rbp+57h+var_88]
0x1800fe9f4  test    rcx, rcx
0x1800fe9f7  jnz     loc_1800FF0B7
0x1800fe9fd  mov     rcx, [rbp+57h+var_78]
0x1800fea01  test    rcx, rcx
0x1800fea04  jnz     loc_1800FF0CD
0x1800fea0a  lea     rcx, [rbp+57h+var_90]; this
0x1800fea0e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800fea13  mov     eax, ebx
0x1800fea15  mov     rcx, [rbp+57h+var_50]
0x1800fea19  xor     rcx, rsp; StackCookie
0x1800fea1c  call    __security_check_cookie
0x1800fea21  add     rsp, 88h
0x1800fea28  pop     r15
0x1800fea2a  pop     r14
0x1800fea2c  pop     r13
0x1800fea2e  pop     r12
0x1800fea30  pop     rdi
0x1800fea31  pop     rsi
0x1800fea32  pop     rbx
0x1800fea33  pop     rbp
0x1800fea34  retn
0x1800fea36  mov     rcx, [rbp+57h+var_80]
0x1800fea3a  lea     rdx, [rbp+57h+var_8C]
0x1800fea3e  mov     rax, [rcx]
0x1800fea41  mov     rax, [rax+18h]
0x1800fea45  call    cs:__guard_dispatch_icall_fptr
0x1800fea4b  mov     ebx, eax
0x1800fea4d  test    eax, eax
0x1800fea4f  js      loc_1800FECA4
0x1800fea55  cmp     cs:byte_1803CECE9, 8
0x1800fea5c  jnb     loc_1800FEFF6
0x1800fea62  mov     r14d, r13d
0x1800fea65  cmp     r14w, [rbp+57h+var_8C]
0x1800fea6a  jnb     loc_1800FEB03
0x1800fea70  mov     rcx, [rbp+57h+var_88]
0x1800fea74  test    rcx, rcx
0x1800fea77  jnz     loc_1800FEB4F
0x1800fea7d  mov     rcx, [rbp+57h+var_80]
0x1800fea81  lea     r8, [rbp+57h+var_88]
0x1800fea85  movzx   edx, r14w
0x1800fea89  mov     rax, [rcx]
0x1800fea8c  mov     rax, [rax+20h]
0x1800fea90  call    cs:__guard_dispatch_icall_fptr
0x1800fea96  mov     ebx, eax
0x1800fea98  test    eax, eax
0x1800fea9a  jns     short loc_1800FEACA
0x1800fea9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800feaa3  test    rcx, rcx
0x1800feaa6  jz      loc_1800FEBB3
0x1800feaac  cmp     [rcx+8], r13b
0x1800feab0  jnz     loc_1800FEF04
0x1800feab6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800feabd  jb      loc_1800FE9E3
0x1800feac3  mov     edx, 1CDh
0x1800feac8  jmp     short loc_1800FEB30
0x1800feaca  mov     rcx, [rbp+57h+var_88]
0x1800feace  lea     rdx, [rbp+57h+var_68]
0x1800fead2  mov     rax, [rcx]
0x1800fead5  mov     rax, [rax+120h]
0x1800feadc  call    cs:__guard_dispatch_icall_fptr
0x1800feae2  mov     ebx, eax
0x1800feae4  test    eax, eax
0x1800feae6  js      loc_1800FEE6C
0x1800feaec  mov     rax, [rbp+57h+var_70]
0x1800feaf0  cmp     [rbp+57h+var_68], rax
0x1800feaf4  jz      loc_1800FF01E
0x1800feafa  inc     r14w
0x1800feafe  jmp     loc_1800FEA65
0x1800feb03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800feb0a  mov     ebx, 80004005h
0x1800feb0f  test    rcx, rcx
0x1800feb12  jz      short loc_1800FEB65
0x1800feb14  cmp     [rcx+8], r13b
0x1800feb18  jnz     loc_1800FEF32
0x1800feb1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800feb25  jb      loc_1800FE9E3
0x1800feb2b  mov     edx, 1D2h
0x1800feb30  mov     r8, rdi
0x1800feb33  mov     rcx, cs:WPP_GLOBAL_Control
0x1800feb3a  mov     r9, rsi
0x1800feb3d  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800feb41  mov     rcx, [rcx+10h]
0x1800feb45  call    WPP_SF_qD
0x1800feb4a  jmp     loc_1800FE9E3
0x1800feb4f  mov     rax, [rcx]
0x1800feb52  mov     rax, [rax+10h]
0x1800feb56  call    cs:__guard_dispatch_icall_fptr
0x1800feb5c  mov     [rbp+57h+var_88], r13
0x1800feb60  jmp     loc_1800FEA7D
0x1800feb65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800feb6c  nop     dword ptr [rax+rax+00h]
0x1800feb71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800feb78  mov     rcx, rax
0x1800feb7b  test    rax, rax
0x1800feb7e  jz      short loc_1800FEBC4
0x1800feb80  mov     rax, [rax]
0x1800feb83  mov     edx, 7F0h
0x1800feb88  mov     rax, [rax+8]
0x1800feb8c  call    cs:__guard_dispatch_icall_fptr
0x1800feb92  test    eax, eax
0x1800feb94  jz      short loc_1800FEBC4
0x1800feb96  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800feb9d  jmp     loc_1800FEB14
0x1800feba2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800feba7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800febae  jmp     loc_1800FE9CC
0x1800febb3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800febb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800febbf  jmp     loc_1800FEAAC
0x1800febc4  lea     rcx, qword_1803CE250
0x1800febcb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800febd2  jmp     loc_1800FEB14
0x1800febd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800febde  test    rcx, rcx
0x1800febe1  jnz     short loc_1800FEC1B
0x1800febe3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800febea  nop     dword ptr [rax+rax+00h]
0x1800febef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800febf6  mov     rcx, rax
0x1800febf9  test    rax, rax
0x1800febfc  jz      short loc_1800FEC3F
0x1800febfe  mov     rax, [rax]
0x1800fec01  mov     edx, 7F0h
0x1800fec06  mov     rax, [rax+8]
0x1800fec0a  call    cs:__guard_dispatch_icall_fptr
0x1800fec10  test    eax, eax
0x1800fec12  jz      short loc_1800FEC3F
0x1800fec14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800fec1b  cmp     [rcx+8], r13b
0x1800fec1f  jnz     short loc_1800FEC4F
0x1800fec21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fec28  jb      loc_1800FE9E3
0x1800fec2e  mov     edx, 1C8h
0x1800fec33  lea     r8, WPP_99df56b8d925385f4040ffb74e86ce6f_Traceguids
0x1800fec3a  jmp     loc_1800FEB33
0x1800fec3f  lea     rcx, qword_1803CE250
0x1800fec46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fec4d  jmp     short loc_1800FEC1B
0x1800fec4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fec54  cmp     [rax+7CCh], ebx
0x1800fec5a  jz      short loc_1800FEC21
0x1800fec5c  mov     r9d, ebx; int
0x1800fec5f  lea     rdx, aCmediasessionF_0; "CMediaSession::FindStreamSinkForStream"
0x1800fec66  mov     r8d, 17B8h; int
0x1800fec6c  mov     rcx, rax; this
0x1800fec6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fec74  jmp     short loc_1800FEC21
0x1800fec76  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fec7b  cmp     [rax+7CCh], ebx
0x1800fec81  jz      loc_1800FE9D6
0x1800fec87  mov     r9d, ebx; int
0x1800fec8a  lea     rdx, aCmediasessionF_0; "CMediaSession::FindStreamSinkForStream"
0x1800fec91  mov     r8d, 17C2h; int
0x1800fec97  mov     rcx, rax; this
0x1800fec9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fec9f  jmp     loc_1800FE9D6
0x1800feca4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fecab  test    rcx, rcx
0x1800fecae  jnz     short loc_1800FECE8
0x1800fecb0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fecb7  nop     dword ptr [rax+rax+00h]
0x1800fecbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fecc3  mov     rcx, rax
0x1800fecc6  test    rax, rax
0x1800fecc9  jz      short loc_1800FED05
0x1800feccb  mov     rax, [rax]
0x1800fecce  mov     edx, 7F0h
0x1800fecd3  mov     rax, [rax+8]
0x1800fecd7  call    cs:__guard_dispatch_icall_fptr
0x1800fecdd  test    eax, eax
0x1800fecdf  jz      short loc_1800FED05
0x1800fece1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800fece8  cmp     [rcx+8], r13b
0x1800fecec  jnz     short loc_1800FED15
0x1800fecee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fecf5  jb      loc_1800FE9E3
0x1800fecfb  mov     edx, 1CBh
0x1800fed00  jmp     loc_1800FEB30
0x1800fed05  lea     rcx, qword_1803CE250
0x1800fed0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fed13  jmp     short loc_1800FECE8
0x1800fed15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fed1a  cmp     [rax+7CCh], ebx
0x1800fed20  jz      short loc_1800FECEE
0x1800fed22  mov     r9d, ebx; int
0x1800fed25  lea     rdx, aCmediasessionF_0; "CMediaSession::FindStreamSinkForStream"
0x1800fed2c  mov     r8d, 17C4h; int
0x1800fed32  mov     rcx, rax; this
0x1800fed35  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fed3a  jmp     short loc_1800FECEE
0x1800fed3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fed43  test    rcx, rcx
0x1800fed46  jnz     short loc_1800FED80
0x1800fed48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fed4f  nop     dword ptr [rax+rax+00h]
0x1800fed54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fed5b  mov     rcx, rax
0x1800fed5e  test    rax, rax
0x1800fed61  jz      short loc_1800FED9D
0x1800fed63  mov     rax, [rax]
0x1800fed66  mov     edx, 7F0h
0x1800fed6b  mov     rax, [rax+8]
0x1800fed6f  call    cs:__guard_dispatch_icall_fptr
0x1800fed75  test    eax, eax
0x1800fed77  jz      short loc_1800FED9D
0x1800fed79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800fed80  cmp     [rcx+8], r13b
0x1800fed84  jnz     short loc_1800FEDAD
0x1800fed86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fed8d  jb      loc_1800FE9E3
0x1800fed93  mov     edx, 1CFh
0x1800fed98  jmp     loc_1800FEB30
0x1800fed9d  lea     rcx, qword_1803CE250
0x1800feda4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fedab  jmp     short loc_1800FED80
0x1800fedad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fedb2  cmp     [rax+7CCh], ebx
0x1800fedb8  jz      short loc_1800FED86
0x1800fedba  mov     r9d, ebx; int
0x1800fedbd  lea     rdx, aCmediasessionF_0; "CMediaSession::FindStreamSinkForStream"
0x1800fedc4  mov     r8d, 17D8h; int
0x1800fedca  mov     rcx, rax; this
0x1800fedcd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fedd2  jmp     short loc_1800FED86
0x1800fedd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800feddb  test    rcx, rcx
0x1800fedde  jnz     short loc_1800FEE18
0x1800fede0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fede7  nop     dword ptr [rax+rax+00h]
0x1800fedec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fedf3  mov     rcx, rax
0x1800fedf6  test    rax, rax
0x1800fedf9  jz      short loc_1800FEE35
0x1800fedfb  mov     rax, [rax]
0x1800fedfe  mov     edx, 7F0h
0x1800fee03  mov     rax, [rax+8]
0x1800fee07  call    cs:__guard_dispatch_icall_fptr
0x1800fee0d  test    eax, eax
  ... truncated ...
```
