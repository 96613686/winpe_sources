# CPolicyEngine::TryToReloadGRL(IMFInputTrustAuthority *,_MFPOLICYMANAGER_ACTION,ulong)

- ea: `0x1802a995c`
- end: `0x1802aa116`
- name: `?TryToReloadGRL@CPolicyEngine@@IEAAJPEAUIMFInputTrustAuthority@@W4_MFPOLICYMANAGER_ACTION@@K@Z`
- size: `1978`
- prototype: `__int64 __fastcall(CPolicyEngine *__hidden this, struct IMFInputTrustAuthority *, enum _MFPOLICYMANAGER_ACTION, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802a7bc0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x18006b388`
- `0x1800ec0e0`
- `0x1802035b4`
- `0x180258480`
- `0x1802a37a4`
- `0x1802a995c`
- `0x1802aa11c`
- `0x1803145a8`
- `0x180314774`
- `0x180314e50`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802aa0dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1802aa0dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a9cad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a9cad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a9c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a9c8e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1802a9ccd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1802a9ccd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9a4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9bc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9d6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9e20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9ec5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9f7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802aa00e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9a4f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9b0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9bc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9d6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9e20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9ec5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802a9f7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802aa00e`

## pseudocode

```c
__int64 __fastcall CPolicyEngine::TryToReloadGRL(
        CPolicyEngine *this,
        struct IMFInputTrustAuthority *a2,
        unsigned int a3,
        int a4)
{
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rdx
  CPEAuthHandShake *v35; // rcx
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
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  _BYTE v54[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v55; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v59[4]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v62[80]; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+E0h] [rbp-20h] BYREF

  v55 = 0;
  v57 = 0;
  v59[0] = 0;
  v59[2] = 0;
  CMIGStateInfo::CMIGStateInfo((CMIGStateInfo *)v62);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v54, "CPolicyEngine::TryToReloadGRL", 1892);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 151, &WPP_6fd5af56dfe53a28ce4a59031bd7494d_Traceguids, this);
  v8 = ((__int64 (__fastcall *)(struct IMFInputTrustAuthority *, _QWORD, __int64 *))a2->lpVtbl->GetPolicy)(a2, a3, &v57);
  v11 = v8;
  if ( (Microsoft_Windows_MFEnableBits & 8) != 0 )
    McTemplateU0qqtd_EventWriteTransfer(v57 != 0, (unsigned int)&IMFInputTrustAuthority_GetPolicy, a4, a3, v57 != 0, v8);
  if ( v11 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CPolicyEngine::TryToReloadGRL", 1901, v11);
    }
    if ( g_wppLevels )
    {
      v15 = 152;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_6fd5af56dfe53a28ce4a59031bd7494d_Traceguids, this, v11);
      goto LABEL_106;
    }
    goto LABEL_106;
  }
  if ( v57 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 280LL))(v57, &v55);
    if ( v11 < 0 )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != v11 )
          CallStackContext::TraceFailure(v23, "CPolicyEngine::TryToReloadGRL", 1910, v11);
      }
      if ( g_wppLevels )
      {
        v15 = 154;
        goto LABEL_16;
      }
      goto LABEL_106;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 155, &WPP_6fd5af56dfe53a28ce4a59031bd7494d_Traceguids, this, v55);
    v56 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Media.Protection.Internal.ActivatePendingGrl",
           0x34u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v56 = 0;
    v58 = 0;
    v11 = RoActivateInstance(string, &v58);
    if ( v11 >= 0 )
    {
      v26 = memcmp_0(&GUID_4882a30b_d618_4c19_bbc7_1207d567a678, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
      v27 = v58;
      if ( !v26 )
      {
        v56 = v58;
LABEL_48:
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 48LL))(v27, v55);
        if ( v11 >= 0 )
        {
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
          v11 = CPEAuthHandShake::Init((CPEAuthHandShake *)v59, (struct CMIGStateInfo *)v62);
          if ( v11 >= 0 )
          {
            v11 = CPEAuthHandShake::ReloadGRL(v35, (struct CMIGStateInfo *)v62);
            if ( v11 >= 0 )
            {
              if ( g_FalseStatement == 1 )
              {
                v11 = CPEAuthHandShake::KernelStateInquiry((CPEAuthHandShake *)v59, (struct CMIGStateInfo *)v62);
                if ( v11 < 0 )
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
                    if ( *((_DWORD *)v49 + 499) != v11 )
                      CallStackContext::TraceFailure(v49, "CPolicyEngine::TryToReloadGRL", 1942, v11);
                  }
                  if ( g_wppLevels )
                  {
                    v15 = 160;
                    goto LABEL_16;
                  }
                }
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
                if ( *((_DWORD *)v44 + 499) != v11 )
                  CallStackContext::TraceFailure(v44, "CPolicyEngine::TryToReloadGRL", 1936, v11);
              }
              if ( g_wppLevels )
              {
                v15 = 159;
                goto LABEL_16;
              }
            }
          }
          else
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v36);
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
              if ( *((_DWORD *)v39 + 499) != v11 )
                CallStackContext::TraceFailure(v39, "CPolicyEngine::TryToReloadGRL", 1935, v11);
            }
            if ( g_wppLevels )
            {
              v15 = 158;
              goto LABEL_16;
            }
          }
          goto LABEL_106;
        }
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v11 )
            CallStackContext::TraceFailure(v32, "CPolicyEngine::TryToReloadGRL", 1925, v11);
        }
        if ( !g_wppLevels )
        {
LABEL_105:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
          goto LABEL_106;
        }
        v33 = 157;
LABEL_104:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_6fd5af56dfe53a28ce4a59031bd7494d_Traceguids, this, v11);
        goto LABEL_105;
      }
      v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v58)(
              v58,
              &GUID_4882a30b_d618_4c19_bbc7_1207d567a678,
              &v56);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      if ( v11 >= 0 )
      {
        v27 = v56;
        goto LABEL_48;
      }
    }
    v50 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v52 + 499) != v11 )
        CallStackContext::TraceFailure(v52, "CPolicyEngine::TryToReloadGRL", 1924, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_105;
    v33 = 156;
    goto LABEL_104;
  }
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  v11 = -1072860833;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != -1072860833 )
      CallStackContext::TraceFailure(v18, "CPolicyEngine::TryToReloadGRL", 1908, -1072860833);
  }
  if ( g_wppLevels )
  {
    v15 = 153;
    goto LABEL_16;
  }
LABEL_106:
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v54);
  DeleteCriticalSection(&CriticalSection);
  CPEAuthHandShake::Close((CPEAuthHandShake *)v59);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1802a995c  push    rbp
0x1802a995e  push    rbx
0x1802a995f  push    rsi
0x1802a9960  push    rdi
0x1802a9961  push    r12
0x1802a9963  push    r13
0x1802a9965  push    r14
0x1802a9967  push    r15
0x1802a9969  lea     rbp, [rsp-28h]
0x1802a996e  sub     rsp, 128h
0x1802a9975  mov     rax, cs:__security_cookie
0x1802a997c  xor     rax, rsp
0x1802a997f  mov     [rbp+60h+var_50], rax
0x1802a9983  xor     r15d, r15d
0x1802a9986  mov     rdi, rcx
0x1802a9989  lea     rcx, [rbp+60h+var_D0]; this
0x1802a998d  mov     [rsp+160h+var_12C], r15d
0x1802a9992  mov     [rsp+160h+var_120], r15
0x1802a9997  mov     r14d, r9d
0x1802a999a  mov     [rsp+160h+var_110], r15
0x1802a999f  mov     esi, r8d
0x1802a99a2  mov     [rsp+160h+var_100], r15
0x1802a99a7  mov     rbx, rdx
0x1802a99aa  call    ??0CMIGStateInfo@@QEAA@XZ; CMIGStateInfo::CMIGStateInfo(void)
0x1802a99af  lea     r13, aCpolicyengineT; "CPolicyEngine::TryToReloadGRL"
0x1802a99b6  mov     r8d, 764h; int
0x1802a99bc  mov     rdx, r13; char *
0x1802a99bf  lea     rcx, [rsp+160h+var_130]; this
0x1802a99c4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802a99c9  cmp     cs:byte_1803CECE9, 8
0x1802a99d0  lea     r12, WPP_6fd5af56dfe53a28ce4a59031bd7494d_Traceguids
0x1802a99d7  jb      short loc_1802A99F4
0x1802a99d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1802a99e0  mov     edx, 97h
0x1802a99e5  mov     r9, rdi
0x1802a99e8  mov     r8, r12
0x1802a99eb  mov     rcx, [rcx+38h]
0x1802a99ef  call    WPP_SF_q
0x1802a99f4  mov     rax, [rbx]
0x1802a99f7  lea     r8, [rsp+160h+var_120]
0x1802a99fc  mov     edx, esi
0x1802a99fe  mov     rcx, rbx
0x1802a9a01  mov     rax, [rax+28h]
0x1802a9a05  call    cs:__guard_dispatch_icall_fptr
0x1802a9a0b  test    cs:Microsoft_Windows_MFEnableBits, 8
0x1802a9a12  mov     ebx, eax
0x1802a9a14  jz      short loc_1802A9A3B
0x1802a9a16  cmp     [rsp+160h+var_120], r15
0x1802a9a1b  lea     rdx, IMFInputTrustAuthority_GetPolicy
0x1802a9a22  mov     ecx, r15d
0x1802a9a25  mov     [rsp+160h+var_138], eax
0x1802a9a29  setnz   cl
0x1802a9a2c  mov     r9d, esi
0x1802a9a2f  mov     r8d, r14d
0x1802a9a32  mov     [rsp+160h+var_140], ecx
0x1802a9a36  call    McTemplateU0qqtd_EventWriteTransfer
0x1802a9a3b  test    ebx, ebx
0x1802a9a3d  jns     loc_1802A9AEF
0x1802a9a43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9a4a  test    rcx, rcx
0x1802a9a4d  jnz     short loc_1802A9A97
0x1802a9a4f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802a9a56  nop     dword ptr [rax+rax+00h]
0x1802a9a5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9a62  mov     rcx, rax
0x1802a9a65  test    rax, rax
0x1802a9a68  jz      short loc_1802A9A89
0x1802a9a6a  mov     rax, [rax]
0x1802a9a6d  mov     edx, 7F0h
0x1802a9a72  mov     rax, [rax+8]
0x1802a9a76  call    cs:__guard_dispatch_icall_fptr
0x1802a9a7c  test    eax, eax
0x1802a9a7e  jz      short loc_1802A9A89
0x1802a9a80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9a87  jmp     short loc_1802A9A97
0x1802a9a89  lea     rcx, qword_1803CE250; this
0x1802a9a90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9a97  cmp     [rcx+8], r15b
0x1802a9a9b  jz      short loc_1802A9ABE
0x1802a9a9d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802a9aa2  cmp     [rax+7CCh], ebx
0x1802a9aa8  jz      short loc_1802A9ABE
0x1802a9aaa  mov     r9d, ebx; int
0x1802a9aad  mov     r8d, 76Dh; int
0x1802a9ab3  mov     rdx, r13; char *
0x1802a9ab6  mov     rcx, rax; this
0x1802a9ab9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802a9abe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802a9ac5  jb      loc_1802AA0B3
0x1802a9acb  mov     edx, 98h
0x1802a9ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x1802a9ad7  mov     r9, rdi
0x1802a9ada  mov     r8, r12
0x1802a9add  mov     [rsp+160h+var_140], ebx
0x1802a9ae1  mov     rcx, [rcx+10h]
0x1802a9ae5  call    WPP_SF_qD
0x1802a9aea  jmp     loc_1802AA0B3
0x1802a9aef  cmp     [rsp+160h+var_120], r15
0x1802a9af4  jnz     loc_1802A9B91
0x1802a9afa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9b01  mov     ebx, 0C00D715Fh
0x1802a9b06  test    rcx, rcx
0x1802a9b09  jnz     short loc_1802A9B53
0x1802a9b0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802a9b12  nop     dword ptr [rax+rax+00h]
0x1802a9b17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9b1e  mov     rcx, rax
0x1802a9b21  test    rax, rax
0x1802a9b24  jz      short loc_1802A9B45
0x1802a9b26  mov     rax, [rax]
0x1802a9b29  mov     edx, 7F0h
0x1802a9b2e  mov     rax, [rax+8]
0x1802a9b32  call    cs:__guard_dispatch_icall_fptr
0x1802a9b38  test    eax, eax
0x1802a9b3a  jz      short loc_1802A9B45
0x1802a9b3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9b43  jmp     short loc_1802A9B53
0x1802a9b45  lea     rcx, qword_1803CE250; this
0x1802a9b4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9b53  cmp     [rcx+8], r15b
0x1802a9b57  jz      short loc_1802A9B7A
0x1802a9b59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802a9b5e  cmp     [rax+7CCh], ebx
0x1802a9b64  jz      short loc_1802A9B7A
0x1802a9b66  mov     r9d, ebx; int
0x1802a9b69  mov     r8d, 774h; int
0x1802a9b6f  mov     rdx, r13; char *
0x1802a9b72  mov     rcx, rax; this
0x1802a9b75  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802a9b7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802a9b81  jb      loc_1802AA0B3
0x1802a9b87  mov     edx, 99h
0x1802a9b8c  jmp     loc_1802A9AD0
0x1802a9b91  mov     rcx, [rsp+160h+var_120]
0x1802a9b96  lea     rdx, [rsp+160h+var_12C]
0x1802a9b9b  mov     rax, [rcx]
0x1802a9b9e  mov     rax, [rax+118h]
0x1802a9ba5  call    cs:__guard_dispatch_icall_fptr
0x1802a9bab  mov     ebx, eax
0x1802a9bad  test    eax, eax
0x1802a9baf  jns     loc_1802A9C47
0x1802a9bb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9bbc  test    rcx, rcx
0x1802a9bbf  jnz     short loc_1802A9C09
0x1802a9bc1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802a9bc8  nop     dword ptr [rax+rax+00h]
0x1802a9bcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9bd4  mov     rcx, rax
0x1802a9bd7  test    rax, rax
0x1802a9bda  jz      short loc_1802A9BFB
0x1802a9bdc  mov     rax, [rax]
0x1802a9bdf  mov     edx, 7F0h
0x1802a9be4  mov     rax, [rax+8]
0x1802a9be8  call    cs:__guard_dispatch_icall_fptr
0x1802a9bee  test    eax, eax
0x1802a9bf0  jz      short loc_1802A9BFB
0x1802a9bf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9bf9  jmp     short loc_1802A9C09
0x1802a9bfb  lea     rcx, qword_1803CE250; this
0x1802a9c02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9c09  cmp     [rcx+8], r15b
0x1802a9c0d  jz      short loc_1802A9C30
0x1802a9c0f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802a9c14  cmp     [rax+7CCh], ebx
0x1802a9c1a  jz      short loc_1802A9C30
0x1802a9c1c  mov     r9d, ebx; int
0x1802a9c1f  mov     r8d, 776h; int
0x1802a9c25  mov     rdx, r13; char *
0x1802a9c28  mov     rcx, rax; this
0x1802a9c2b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802a9c30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802a9c37  jb      loc_1802AA0B3
0x1802a9c3d  mov     edx, 9Ah
0x1802a9c42  jmp     loc_1802A9AD0
0x1802a9c47  cmp     cs:byte_1803CECE9, 10h
0x1802a9c4e  jb      short loc_1802A9C73
0x1802a9c50  mov     rcx, cs:WPP_GLOBAL_Control
0x1802a9c57  mov     edx, 9Bh
0x1802a9c5c  mov     eax, [rsp+160h+var_12C]
0x1802a9c60  mov     r9, rdi
0x1802a9c63  mov     r8, r12
0x1802a9c66  mov     [rsp+160h+var_140], eax
0x1802a9c6a  mov     rcx, [rcx+38h]
0x1802a9c6e  call    WPP_SF_qD
0x1802a9c73  lea     r9, [rsp+160h+string]; string
0x1802a9c78  mov     [rsp+160h+var_128], r15
0x1802a9c7d  lea     r8, [rsp+160h+hstringHeader]; hstringHeader
0x1802a9c82  mov     edx, 34h ; '4'; length
0x1802a9c87  lea     rcx, ?RuntimeClass_Windows_Media_Protection_Internal_ActivatePendingGrl@@3QBGB; "Windows.Media.Protection.Internal.Activ"...
0x1802a9c8e  call    cs:__imp_WindowsCreateStringReference
0x1802a9c95  nop     dword ptr [rax+rax+00h]
0x1802a9c9a  test    eax, eax
0x1802a9c9c  jns     short loc_1802A9CB9
0x1802a9c9e  xor     r9d, r9d; lpArguments
0x1802a9ca1  xor     r8d, r8d; nNumberOfArguments
0x1802a9ca4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1802a9ca9  lea     edx, [r9+1]; dwExceptionFlags
0x1802a9cad  call    cs:__imp_RaiseException
0x1802a9cb4  nop     dword ptr [rax+rax+00h]
0x1802a9cb9  mov     rcx, [rsp+160h+string]
0x1802a9cbe  lea     rdx, [rsp+160h+var_118]
0x1802a9cc3  mov     [rsp+160h+var_128], r15
0x1802a9cc8  mov     [rsp+160h+var_118], r15
0x1802a9ccd  call    cs:__imp_RoActivateInstance
0x1802a9cd4  nop     dword ptr [rax+rax+00h]
0x1802a9cd9  mov     ebx, eax
0x1802a9cdb  test    eax, eax
0x1802a9cdd  js      loc_1802AA002
0x1802a9ce3  mov     r8d, 10h; Size
0x1802a9ce9  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1802a9cf0  lea     rcx, _GUID_4882a30b_d618_4c19_bbc7_1207d567a678; Buf1
0x1802a9cf7  call    memcmp_0
0x1802a9cfc  mov     rcx, [rsp+160h+var_118]
0x1802a9d01  test    eax, eax
0x1802a9d03  jnz     short loc_1802A9D0C
0x1802a9d05  mov     [rsp+160h+var_128], rcx
0x1802a9d0a  jmp     short loc_1802A9D45
0x1802a9d0c  mov     rax, [rcx]
0x1802a9d0f  lea     r8, [rsp+160h+var_128]
0x1802a9d14  lea     rdx, _GUID_4882a30b_d618_4c19_bbc7_1207d567a678
0x1802a9d1b  mov     rax, [rax]
0x1802a9d1e  call    cs:__guard_dispatch_icall_fptr
0x1802a9d24  mov     rcx, [rsp+160h+var_118]
0x1802a9d29  mov     ebx, eax
0x1802a9d2b  mov     rax, [rcx]
0x1802a9d2e  mov     rax, [rax+10h]
0x1802a9d32  call    cs:__guard_dispatch_icall_fptr
0x1802a9d38  test    ebx, ebx
0x1802a9d3a  js      loc_1802AA002
0x1802a9d40  mov     rcx, [rsp+160h+var_128]
0x1802a9d45  mov     rax, [rcx]
0x1802a9d48  mov     edx, [rsp+160h+var_12C]
0x1802a9d4c  mov     rax, [rax+30h]
0x1802a9d50  call    cs:__guard_dispatch_icall_fptr
0x1802a9d56  mov     ebx, eax
0x1802a9d58  test    eax, eax
0x1802a9d5a  jns     loc_1802A9DF2
0x1802a9d60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9d67  test    rcx, rcx
0x1802a9d6a  jnz     short loc_1802A9DB4
0x1802a9d6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802a9d73  nop     dword ptr [rax+rax+00h]
0x1802a9d78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9d7f  mov     rcx, rax
0x1802a9d82  test    rax, rax
0x1802a9d85  jz      short loc_1802A9DA6
0x1802a9d87  mov     rax, [rax]
0x1802a9d8a  mov     edx, 7F0h
0x1802a9d8f  mov     rax, [rax+8]
0x1802a9d93  call    cs:__guard_dispatch_icall_fptr
0x1802a9d99  test    eax, eax
0x1802a9d9b  jz      short loc_1802A9DA6
0x1802a9d9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9da4  jmp     short loc_1802A9DB4
0x1802a9da6  lea     rcx, qword_1803CE250; this
0x1802a9dad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9db4  cmp     [rcx+8], r15b
0x1802a9db8  jz      short loc_1802A9DDB
0x1802a9dba  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802a9dbf  cmp     [rax+7CCh], ebx
0x1802a9dc5  jz      short loc_1802A9DDB
0x1802a9dc7  mov     r9d, ebx; int
0x1802a9dca  mov     r8d, 785h; int
0x1802a9dd0  mov     rdx, r13; char *
0x1802a9dd3  mov     rcx, rax; this
0x1802a9dd6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802a9ddb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802a9de2  jb      loc_1802AA0A9
0x1802a9de8  mov     edx, 9Dh
0x1802a9ded  jmp     loc_1802AA08F
0x1802a9df2  lea     rcx, [rsp+160h+var_128]
0x1802a9df7  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1802a9dfc  lea     rdx, [rbp+60h+var_D0]; struct CMIGStateInfo *
0x1802a9e00  lea     rcx, [rsp+160h+var_110]; this
0x1802a9e05  call    ?Init@CPEAuthHandShake@@QEAAJPEAVCMIGStateInfo@@@Z; CPEAuthHandShake::Init(CMIGStateInfo *)
0x1802a9e0a  mov     ebx, eax
0x1802a9e0c  test    eax, eax
0x1802a9e0e  jns     loc_1802A9EA6
0x1802a9e14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9e1b  test    rcx, rcx
0x1802a9e1e  jnz     short loc_1802A9E68
0x1802a9e20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802a9e27  nop     dword ptr [rax+rax+00h]
0x1802a9e2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9e33  mov     rcx, rax
0x1802a9e36  test    rax, rax
0x1802a9e39  jz      short loc_1802A9E5A
0x1802a9e3b  mov     rax, [rax]
0x1802a9e3e  mov     edx, 7F0h
0x1802a9e43  mov     rax, [rax+8]
0x1802a9e47  call    cs:__guard_dispatch_icall_fptr
0x1802a9e4d  test    eax, eax
0x1802a9e4f  jz      short loc_1802A9E5A
0x1802a9e51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9e58  jmp     short loc_1802A9E68
0x1802a9e5a  lea     rcx, qword_1803CE250; this
0x1802a9e61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802a9e68  cmp     [rcx+8], r15b
0x1802a9e6c  jz      short loc_1802A9E8F
0x1802a9e6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
