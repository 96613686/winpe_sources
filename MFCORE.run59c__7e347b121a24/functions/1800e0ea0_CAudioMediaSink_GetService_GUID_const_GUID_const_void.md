# CAudioMediaSink::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x1800e0ea0`
- end: `0x1800e1567`
- name: `?GetService@CAudioMediaSink@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1735`
- prototype: `int(CAudioMediaSink *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800e0ea0`
- `0x1800e1570`
- `0x1800e247c`
- `0x1800e2590`
- `0x1800ec0e0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e0fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e0fc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e0f4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e0f4a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e11f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1289`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1321`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e13b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1451`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1159`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e11f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1289`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1321`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e13b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800e1451`

## string_xrefs

- `0x1800e0ecb`: `CAudioMediaSink::GetService`
- `0x1800e1131`: `CAudioMediaSink::GetService`
- `0x1800e11ce`: `CAudioMediaSink::GetService`
- `0x1800e1266`: `CAudioMediaSink::GetService`
- `0x1800e12fe`: `CAudioMediaSink::GetService`
- `0x1800e1396`: `CAudioMediaSink::GetService`
- `0x1800e142e`: `CAudioMediaSink::GetService`
- `0x1800e14e4`: `CAudioMediaSink::GetService`

## pseudocode

```c
__int64 __fastcall CAudioMediaSink::GetService(
        CAudioMediaSink *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  __int64 v11; // rdx
  __int64 v12; // r8
  CAudioMediaSink *v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rax
  int Interface; // eax
  int AudStreamSink; // ebx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  CallStackTracing *v26; // rcx
  __int64 v27; // rdx
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
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r8
  _BYTE v55[8]; // [rsp+30h] [rbp-38h] BYREF
  struct CAudStreamSink *v56; // [rsp+38h] [rbp-30h] BYREF
  _BYTE v57[16]; // [rsp+40h] [rbp-28h] BYREF

  v56 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v55, "CAudioMediaSink::GetService", 316);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 296LL))(*((_QWORD *)this + 8));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 8) + 280LL))(
                       *((_QWORD *)this + 8),
                       v57);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this - 2);
  v13 = (CAudioMediaSink *)((char *)this - 744);
  if ( !a4 )
  {
    v26 = CallStackTracing::s_wpInstance;
    AudStreamSink = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v26 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v26 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext(v26);
      if ( *((_DWORD *)v28 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v28, "CAudioMediaSink::GetService", 319, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v27 = 21;
    goto LABEL_98;
  }
  if ( *((_DWORD *)v13 + 158) == 8 )
  {
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    AudStreamSink = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
      if ( *((_DWORD *)v31 + 499) != -1072873851 )
        CallStackContext::TraceFailure(v31, "CAudioMediaSink::GetService", 320, -1072873851);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v27 = 22;
    goto LABEL_98;
  }
  *a4 = 0;
  v14 = *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MF_RATE_CONTROL_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v14 = *(_QWORD *)MF_RATE_CONTROL_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v14 )
  {
    v15 = *(_QWORD *)&IID_IMFRateSupport.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&IID_IMFRateSupport.Data1 == *(_QWORD *)&a3->Data1 )
      v15 = *(_QWORD *)IID_IMFRateSupport.Data4 - *(_QWORD *)a3->Data4;
    if ( v15 )
    {
      AudStreamSink = -2147467262;
      goto LABEL_14;
    }
    Interface = CAudioMediaSink::QueryInterface(v13, a3, a4);
    goto LABEL_13;
  }
  v19 = *(_QWORD *)&MR_POLICY_VOLUME_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MR_POLICY_VOLUME_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v19 = *(_QWORD *)MR_POLICY_VOLUME_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v19 )
  {
    AudStreamSink = CAudioMediaSink::GetAudStreamSink(v13, &v56);
    if ( AudStreamSink >= 0 )
      goto LABEL_33;
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
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
      if ( *((_DWORD *)v34 + 499) != AudStreamSink )
        CallStackContext::TraceFailure(v34, "CAudioMediaSink::GetService", 339, AudStreamSink);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v27 = 23;
LABEL_98:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      &WPP_e5c7a7e2e5b73eae2b8eb536f271e77e_Traceguids,
      v13,
      AudStreamSink);
    goto LABEL_14;
  }
  v20 = *(_QWORD *)&MR_STREAM_VOLUME_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MR_STREAM_VOLUME_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v20 = *(_QWORD *)MR_STREAM_VOLUME_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v20 )
  {
    AudStreamSink = CAudioMediaSink::GetAudStreamSink(v13, &v56);
    if ( AudStreamSink >= 0 )
      goto LABEL_33;
    v35 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48);
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
      if ( *((_DWORD *)v37 + 499) != AudStreamSink )
        CallStackContext::TraceFailure(v37, "CAudioMediaSink::GetService", 347, AudStreamSink);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v27 = 24;
    goto LABEL_98;
  }
  v21 = *(_QWORD *)&MR_AUDIO_POLICY_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MR_AUDIO_POLICY_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v21 = *(_QWORD *)MR_AUDIO_POLICY_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v21 )
  {
    AudStreamSink = CAudioMediaSink::GetAudStreamSink(v13, &v56);
    if ( AudStreamSink >= 0 )
      goto LABEL_33;
    v38 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v49, v50);
      CallStackTracing::s_wpInstance = v39;
      if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v38 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
      if ( *((_DWORD *)v40 + 499) != AudStreamSink )
        CallStackContext::TraceFailure(v40, "CAudioMediaSink::GetService", 355, AudStreamSink);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v27 = 25;
    goto LABEL_98;
  }
  v22 = *(_QWORD *)&MF_CLOCK_RATE_MATCH_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MF_CLOCK_RATE_MATCH_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v22 = *(_QWORD *)MF_CLOCK_RATE_MATCH_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( !v22 )
  {
    AudStreamSink = CAudioMediaSink::GetAudStreamSink(v13, &v56);
    if ( AudStreamSink < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != AudStreamSink )
          CallStackContext::TraceFailure(v43, "CAudioMediaSink::GetService", 363, AudStreamSink);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v27 = 26;
      goto LABEL_98;
    }
LABEL_33:
    Interface = CAudStreamSink::GetService((struct CAudStreamSink *)((char *)v56 + 616), a2, a3, a4);
LABEL_13:
    AudStreamSink = Interface;
    goto LABEL_14;
  }
  v23 = *(_QWORD *)&MR_AUDIO_RENDER_SERVICE.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&MR_AUDIO_RENDER_SERVICE.Data1 == *(_QWORD *)&a2->Data1 )
    v23 = *(_QWORD *)MR_AUDIO_RENDER_SERVICE.Data4 - *(_QWORD *)a2->Data4;
  if ( v23 )
  {
    AudStreamSink = -1072875846;
    goto LABEL_14;
  }
  AudStreamSink = CAudioMediaSink::GetAudStreamSink(v13, &v56);
  if ( AudStreamSink >= 0 )
    goto LABEL_33;
  v44 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54);
    CallStackTracing::s_wpInstance = v45;
    if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v44 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v44 + 8) )
  {
    v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
    if ( *((_DWORD *)v46 + 499) != AudStreamSink )
      CallStackContext::TraceFailure(v46, "CAudioMediaSink::GetService", 380, AudStreamSink);
  }
  if ( g_wppLevels )
  {
    v27 = 27;
    goto LABEL_98;
  }
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)this - 2);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v55);
  return (unsigned int)AudStreamSink;
}

```

## disassembly

```asm
0x1800e0ea0  push    rbp
0x1800e0ea2  push    rbx
0x1800e0ea3  push    rsi
0x1800e0ea4  push    rdi
0x1800e0ea5  push    r12
0x1800e0ea7  push    r13
0x1800e0ea9  push    r14
0x1800e0eab  push    r15
0x1800e0ead  mov     rbp, rsp
0x1800e0eb0  sub     rsp, 68h
0x1800e0eb4  mov     rax, cs:__security_cookie
0x1800e0ebb  xor     rax, rsp
0x1800e0ebe  mov     [rbp+var_18], rax
0x1800e0ec2  mov     r14, r8
0x1800e0ec5  mov     rsi, rdx
0x1800e0ec8  mov     r13, rcx
0x1800e0ecb  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e0ed2  xor     ebx, ebx
0x1800e0ed4  lea     rcx, [rbp+var_38]; this
0x1800e0ed8  mov     r8d, 13Ch; int
0x1800e0ede  mov     [rbp+var_30], rbx
0x1800e0ee2  mov     r15, r9
0x1800e0ee5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800e0eea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e0ef1  cmp     [rcx+8], bl
0x1800e0ef4  jz      short loc_1800E0F43
0x1800e0ef6  cmp     [r13+40h], rbx
0x1800e0efa  jz      short loc_1800E0F43
0x1800e0efc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e0f01  mov     rcx, [r13+40h]
0x1800e0f05  mov     rdi, rax
0x1800e0f08  mov     rdx, [rcx]
0x1800e0f0b  mov     rax, [rdx+128h]
0x1800e0f12  call    cs:__guard_dispatch_icall_fptr
0x1800e0f18  mov     rcx, [r13+40h]
0x1800e0f1c  mov     ebx, eax
0x1800e0f1e  mov     rdx, [rcx]
0x1800e0f21  mov     rax, [rdx+118h]
0x1800e0f28  lea     rdx, [rbp+var_28]
0x1800e0f2c  call    cs:__guard_dispatch_icall_fptr
0x1800e0f32  movups  xmm0, xmmword ptr [rax]
0x1800e0f35  mov     [rdi+7E0h], ebx
0x1800e0f3b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800e0f43  lea     r12, [r13-50h]
0x1800e0f47  mov     rcx, r12; lpCriticalSection
0x1800e0f4a  call    cs:__imp_EnterCriticalSection
0x1800e0f51  nop     dword ptr [rax+rax+00h]
0x1800e0f56  lea     rdi, [r13-2E8h]
0x1800e0f5d  xor     r13d, r13d
0x1800e0f60  test    r15, r15
0x1800e0f63  jz      loc_1800E10E5
0x1800e0f69  cmp     dword ptr [rdi+278h], 8
0x1800e0f70  jz      loc_1800E1148
0x1800e0f76  mov     [r15], r13
0x1800e0f79  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data1
0x1800e0f80  sub     rax, [rsi]
0x1800e0f83  jnz     short loc_1800E0F90
0x1800e0f85  mov     rax, qword ptr cs:MF_RATE_CONTROL_SERVICE.Data4
0x1800e0f8c  sub     rax, [rsi+8]
0x1800e0f90  test    rax, rax
0x1800e0f93  jnz     short loc_1800E0FFD
0x1800e0f95  mov     rax, qword ptr cs:IID_IMFRateSupport.Data1
0x1800e0f9c  sub     rax, [r14]
0x1800e0f9f  jnz     short loc_1800E0FAC
0x1800e0fa1  mov     rax, qword ptr cs:IID_IMFRateSupport.Data4
0x1800e0fa8  sub     rax, [r14+8]
0x1800e0fac  test    rax, rax
0x1800e0faf  jnz     loc_1800E10A7
0x1800e0fb5  mov     r8, r15; void **
0x1800e0fb8  mov     rdx, r14; struct _GUID *
0x1800e0fbb  mov     rcx, rdi; this
0x1800e0fbe  call    ?QueryInterface@CAudioMediaSink@@UEAAJAEBU_GUID@@PEAPEAX@Z; CAudioMediaSink::QueryInterface(_GUID const &,void * *)
0x1800e0fc3  mov     ebx, eax
0x1800e0fc5  mov     rcx, r12; lpCriticalSection
0x1800e0fc8  call    cs:__imp_LeaveCriticalSection
0x1800e0fcf  nop     dword ptr [rax+rax+00h]
0x1800e0fd4  lea     rcx, [rbp+var_38]; this
0x1800e0fd8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800e0fdd  mov     eax, ebx
0x1800e0fdf  mov     rcx, [rbp+var_18]
0x1800e0fe3  xor     rcx, rsp; StackCookie
0x1800e0fe6  call    __security_check_cookie
0x1800e0feb  add     rsp, 68h
0x1800e0fef  pop     r15
0x1800e0ff1  pop     r14
0x1800e0ff3  pop     r13
0x1800e0ff5  pop     r12
0x1800e0ff7  pop     rdi
0x1800e0ff8  pop     rsi
0x1800e0ff9  pop     rbx
0x1800e0ffa  pop     rbp
0x1800e0ffb  retn
0x1800e0ffd  mov     rax, qword ptr cs:MR_POLICY_VOLUME_SERVICE.Data1
0x1800e1004  sub     rax, [rsi]
0x1800e1007  jnz     short loc_1800E1014
0x1800e1009  mov     rax, qword ptr cs:MR_POLICY_VOLUME_SERVICE.Data4
0x1800e1010  sub     rax, [rsi+8]
0x1800e1014  test    rax, rax
0x1800e1017  jz      loc_1800E10B1
0x1800e101d  mov     rax, qword ptr cs:MR_STREAM_VOLUME_SERVICE.Data1
0x1800e1024  sub     rax, [rsi]
0x1800e1027  jnz     short loc_1800E1034
0x1800e1029  mov     rax, qword ptr cs:MR_STREAM_VOLUME_SERVICE.Data4
0x1800e1030  sub     rax, [rsi+8]
0x1800e1034  test    rax, rax
0x1800e1037  jz      loc_1800E14FB
0x1800e103d  mov     rax, qword ptr cs:MR_AUDIO_POLICY_SERVICE.Data1
0x1800e1044  sub     rax, [rsi]
0x1800e1047  jnz     short loc_1800E1054
0x1800e1049  mov     rax, qword ptr cs:MR_AUDIO_POLICY_SERVICE.Data4
0x1800e1050  sub     rax, [rsi+8]
0x1800e1054  test    rax, rax
0x1800e1057  jz      loc_1800E1516
0x1800e105d  mov     rax, qword ptr cs:MF_CLOCK_RATE_MATCH_SERVICE.Data1
0x1800e1064  sub     rax, [rsi]
0x1800e1067  jnz     short loc_1800E1074
0x1800e1069  mov     rax, qword ptr cs:MF_CLOCK_RATE_MATCH_SERVICE.Data4
0x1800e1070  sub     rax, [rsi+8]
0x1800e1074  test    rax, rax
0x1800e1077  jz      loc_1800E1531
0x1800e107d  mov     rax, qword ptr cs:MR_AUDIO_RENDER_SERVICE.Data1
0x1800e1084  sub     rax, [rsi]
0x1800e1087  jnz     short loc_1800E1094
0x1800e1089  mov     rax, qword ptr cs:MR_AUDIO_RENDER_SERVICE.Data4
0x1800e1090  sub     rax, [rsi+8]
0x1800e1094  test    rax, rax
0x1800e1097  jz      loc_1800E154C
0x1800e109d  mov     ebx, 0C00D36BAh
0x1800e10a2  jmp     loc_1800E0FC5
0x1800e10a7  mov     ebx, 80004002h
0x1800e10ac  jmp     loc_1800E0FC5
0x1800e10b1  lea     rdx, [rbp+var_30]; struct CAudStreamSink **
0x1800e10b5  mov     rcx, rdi; this
0x1800e10b8  call    ?GetAudStreamSink@CAudioMediaSink@@AEAAJPEAPEAVCAudStreamSink@@@Z; CAudioMediaSink::GetAudStreamSink(CAudStreamSink * *)
0x1800e10bd  mov     ebx, eax
0x1800e10bf  test    eax, eax
0x1800e10c1  js      loc_1800E11E5
0x1800e10c7  mov     rcx, [rbp+var_30]
0x1800e10cb  mov     r9, r15; void **
0x1800e10ce  add     rcx, 268h; this
0x1800e10d5  mov     r8, r14; struct _GUID *
0x1800e10d8  mov     rdx, rsi; struct _GUID *
0x1800e10db  call    ?GetService@CAudStreamSink@@UEAAJAEBU_GUID@@0PEAPEAX@Z; CAudStreamSink::GetService(_GUID const &,_GUID const &,void * *)
0x1800e10e0  jmp     loc_1800E0FC3
0x1800e10e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e10ec  mov     ebx, 80004003h
0x1800e10f1  test    rcx, rcx
0x1800e10f4  jz      short loc_1800E1113
0x1800e10f6  cmp     [rcx+8], r13b
0x1800e10fa  jnz     short loc_1800E1121
0x1800e10fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1103  jb      loc_1800E0FC5
0x1800e1109  mov     edx, 15h
0x1800e110e  jmp     loc_1800E14A1
0x1800e1113  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800e1118  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e111f  jmp     short loc_1800E10F6
0x1800e1121  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e1126  cmp     [rax+7CCh], ebx
0x1800e112c  jz      short loc_1800E10FC
0x1800e112e  mov     r9d, ebx; int
0x1800e1131  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e1138  mov     r8d, 13Fh; int
0x1800e113e  mov     rcx, rax; this
0x1800e1141  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e1146  jmp     short loc_1800E10FC
0x1800e1148  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e114f  mov     ebx, 0C00D3E85h
0x1800e1154  test    rcx, rcx
0x1800e1157  jnz     short loc_1800E1191
0x1800e1159  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e1160  nop     dword ptr [rax+rax+00h]
0x1800e1165  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e116c  mov     rcx, rax
0x1800e116f  test    rax, rax
0x1800e1172  jz      short loc_1800E11AE
0x1800e1174  mov     rax, [rax]
0x1800e1177  mov     edx, 7F0h
0x1800e117c  mov     rax, [rax+8]
0x1800e1180  call    cs:__guard_dispatch_icall_fptr
0x1800e1186  test    eax, eax
0x1800e1188  jz      short loc_1800E11AE
0x1800e118a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e1191  cmp     [rcx+8], r13b
0x1800e1195  jnz     short loc_1800E11BE
0x1800e1197  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e119e  jb      loc_1800E0FC5
0x1800e11a4  mov     edx, 16h
0x1800e11a9  jmp     loc_1800E14A1
0x1800e11ae  lea     rcx, qword_1803CE250
0x1800e11b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e11bc  jmp     short loc_1800E1191
0x1800e11be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e11c3  cmp     [rax+7CCh], ebx
0x1800e11c9  jz      short loc_1800E1197
0x1800e11cb  mov     r9d, ebx; int
0x1800e11ce  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e11d5  mov     r8d, 140h; int
0x1800e11db  mov     rcx, rax; this
0x1800e11de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e11e3  jmp     short loc_1800E1197
0x1800e11e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e11ec  test    rcx, rcx
0x1800e11ef  jnz     short loc_1800E1229
0x1800e11f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e11f8  nop     dword ptr [rax+rax+00h]
0x1800e11fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1204  mov     rcx, rax
0x1800e1207  test    rax, rax
0x1800e120a  jz      short loc_1800E1246
0x1800e120c  mov     rax, [rax]
0x1800e120f  mov     edx, 7F0h
0x1800e1214  mov     rax, [rax+8]
0x1800e1218  call    cs:__guard_dispatch_icall_fptr
0x1800e121e  test    eax, eax
0x1800e1220  jz      short loc_1800E1246
0x1800e1222  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e1229  cmp     [rcx+8], r13b
0x1800e122d  jnz     short loc_1800E1256
0x1800e122f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1236  jb      loc_1800E0FC5
0x1800e123c  mov     edx, 17h
0x1800e1241  jmp     loc_1800E14A1
0x1800e1246  lea     rcx, qword_1803CE250
0x1800e124d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1254  jmp     short loc_1800E1229
0x1800e1256  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e125b  cmp     [rax+7CCh], ebx
0x1800e1261  jz      short loc_1800E122F
0x1800e1263  mov     r9d, ebx; int
0x1800e1266  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e126d  mov     r8d, 153h; int
0x1800e1273  mov     rcx, rax; this
0x1800e1276  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e127b  jmp     short loc_1800E122F
0x1800e127d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1284  test    rcx, rcx
0x1800e1287  jnz     short loc_1800E12C1
0x1800e1289  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e1290  nop     dword ptr [rax+rax+00h]
0x1800e1295  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e129c  mov     rcx, rax
0x1800e129f  test    rax, rax
0x1800e12a2  jz      short loc_1800E12DE
0x1800e12a4  mov     rax, [rax]
0x1800e12a7  mov     edx, 7F0h
0x1800e12ac  mov     rax, [rax+8]
0x1800e12b0  call    cs:__guard_dispatch_icall_fptr
0x1800e12b6  test    eax, eax
0x1800e12b8  jz      short loc_1800E12DE
0x1800e12ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e12c1  cmp     [rcx+8], r13b
0x1800e12c5  jnz     short loc_1800E12EE
0x1800e12c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e12ce  jb      loc_1800E0FC5
0x1800e12d4  mov     edx, 18h
0x1800e12d9  jmp     loc_1800E14A1
0x1800e12de  lea     rcx, qword_1803CE250
0x1800e12e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e12ec  jmp     short loc_1800E12C1
0x1800e12ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e12f3  cmp     [rax+7CCh], ebx
0x1800e12f9  jz      short loc_1800E12C7
0x1800e12fb  mov     r9d, ebx; int
0x1800e12fe  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e1305  mov     r8d, 15Bh; int
0x1800e130b  mov     rcx, rax; this
0x1800e130e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800e1313  jmp     short loc_1800E12C7
0x1800e1315  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e131c  test    rcx, rcx
0x1800e131f  jnz     short loc_1800E1359
0x1800e1321  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800e1328  nop     dword ptr [rax+rax+00h]
0x1800e132d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1334  mov     rcx, rax
0x1800e1337  test    rax, rax
0x1800e133a  jz      short loc_1800E1376
0x1800e133c  mov     rax, [rax]
0x1800e133f  mov     edx, 7F0h
0x1800e1344  mov     rax, [rax+8]
0x1800e1348  call    cs:__guard_dispatch_icall_fptr
0x1800e134e  test    eax, eax
0x1800e1350  jz      short loc_1800E1376
0x1800e1352  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800e1359  cmp     [rcx+8], r13b
0x1800e135d  jnz     short loc_1800E1386
0x1800e135f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e1366  jb      loc_1800E0FC5
0x1800e136c  mov     edx, 19h
0x1800e1371  jmp     loc_1800E14A1
0x1800e1376  lea     rcx, qword_1803CE250
0x1800e137d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800e1384  jmp     short loc_1800E1359
0x1800e1386  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800e138b  cmp     [rax+7CCh], ebx
0x1800e1391  jz      short loc_1800E135F
0x1800e1393  mov     r9d, ebx; int
0x1800e1396  lea     rdx, aCaudiomediasin_14; "CAudioMediaSink::GetService"
0x1800e139d  mov     r8d, 163h; int
  ... truncated ...
```
