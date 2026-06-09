# CDShowWrapper::SetupThreadpoolWait(void)

- ea: `0x18003221c`
- end: `0x180032567`
- name: `?SetupThreadpoolWait@CDShowWrapper@@IEAAJXZ`
- size: `843`
- prototype: `__int64 __fastcall(CDShowWrapper *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180030060`
- `0x1800802fc`
- `0x180083858`
- `0x180084e00`
- `0x180097eb0`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18003221c`
- `0x180032988`
- `0x180032a50`
- `0x180051ce4`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180032510`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180032510`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800323ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003247d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800322f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800323ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003247d`

## string_xrefs

- `0x18003225b`: `CDShowWrapper::SetupThreadpoolWait`
- `0x180032350`: `CDShowWrapper::SetupThreadpoolWait`
- `0x180032427`: `CDShowWrapper::SetupThreadpoolWait`
- `0x1800324da`: `CDShowWrapper::SetupThreadpoolWait`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::SetupThreadpoolWait(CDShowWrapper *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int128 v4; // xmm0
  int v5; // ebx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  _BYTE v17[8]; // [rsp+30h] [rbp-48h] BYREF
  void *v18; // [rsp+38h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-38h] BYREF
  HANDLE h; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-28h] BYREF

  v19 = 0;
  h = 0;
  v18 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v17, "CDShowWrapper::SetupThreadpoolWait", 2161);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v4 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 60) + 280LL))(
                      *((_QWORD *)this + 60),
                      v21);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
    *((_OWORD *)ThreadRelativeContext + 125) = v4;
  }
  v5 = CGITPtr::Get((CDShowWrapper *)((char *)this + 48), &GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770, &v18);
  if ( v5 >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v18)(v18, &IID_IMediaEventEx, &v19);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v19 + 56LL))(v19, &h);
      if ( v5 >= 0 )
      {
        SetThreadpoolWait(*((PTP_WAIT *)this + 52), h, 0);
      }
      else
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( *((_DWORD *)v15 + 499) != v5 )
            CallStackContext::TraceFailure(v15, "CDShowWrapper::SetupThreadpoolWait", 2164, v5);
        }
        if ( g_wppLevels )
        {
          v9 = 180;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v10 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v10);
        if ( *((_DWORD *)v12 + 499) != v5 )
          CallStackContext::TraceFailure(v12, "CDShowWrapper::SetupThreadpoolWait", 2162, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 179;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v6 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CDShowWrapper::SetupThreadpoolWait", 2161, v5);
    }
    if ( g_wppLevels )
    {
      v9 = 178;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v17);
  if ( v18 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003221c  push    rbp
0x18003221e  push    rbx
0x18003221f  push    rsi
0x180032220  push    rdi
0x180032221  mov     rbp, rsp
0x180032224  sub     rsp, 78h
0x180032228  mov     rax, cs:__security_cookie
0x18003222f  xor     rax, rsp
0x180032232  mov     [rbp+var_18], rax
0x180032236  mov     rsi, rcx
0x180032239  mov     [rbp+var_38], 0
0x180032241  lea     rcx, [rbp+var_48]; this
0x180032245  mov     [rbp+h], 0
0x18003224d  mov     r8d, 871h; int
0x180032253  mov     [rbp+var_40], 0
0x18003225b  lea     rdx, aCdshowwrapperS_9; "CDShowWrapper::SetupThreadpoolWait"
0x180032262  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180032267  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003226e  cmp     byte ptr [rcx+8], 0
0x180032272  jz      short loc_1800322C9
0x180032274  cmp     qword ptr [rsi+1E0h], 0
0x18003227c  jz      short loc_1800322C9
0x18003227e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032283  mov     rcx, [rsi+1E0h]
0x18003228a  mov     rdi, rax
0x18003228d  mov     rdx, [rcx]
0x180032290  mov     rax, [rdx+128h]
0x180032297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003229c  mov     rcx, [rsi+1E0h]
0x1800322a3  mov     ebx, eax
0x1800322a5  mov     rdx, [rcx]
0x1800322a8  mov     rax, [rdx+118h]
0x1800322af  lea     rdx, [rbp+var_28]
0x1800322b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800322b8  movups  xmm0, xmmword ptr [rax]
0x1800322bb  mov     [rdi+7E0h], ebx
0x1800322c1  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800322c9  lea     rcx, [rsi+30h]; this
0x1800322cd  lea     r8, [rbp+var_40]; void **
0x1800322d1  lea     rdx, _GUID_56a868a9_0ad4_11ce_b03a_0020af0ba770; struct _GUID *
0x1800322d8  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x1800322dd  mov     ebx, eax
0x1800322df  test    eax, eax
0x1800322e1  jns     loc_18003239A
0x1800322e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800322ee  test    rcx, rcx
0x1800322f1  jnz     short loc_18003233A
0x1800322f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800322fa  nop     dword ptr [rax+rax+00h]
0x1800322ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032306  mov     rcx, rax
0x180032309  test    rax, rax
0x18003230c  jz      short loc_18003232C
0x18003230e  mov     rax, [rax]
0x180032311  mov     edx, 7F0h
0x180032316  mov     rax, [rax+8]
0x18003231a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003231f  test    eax, eax
0x180032321  jz      short loc_18003232C
0x180032323  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003232a  jmp     short loc_18003233A
0x18003232c  lea     rcx, qword_1800EB130; this
0x180032333  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003233a  cmp     byte ptr [rcx+8], 0
0x18003233e  jz      short loc_180032365
0x180032340  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032345  cmp     [rax+7CCh], ebx
0x18003234b  jz      short loc_180032365
0x18003234d  mov     r9d, ebx; int
0x180032350  lea     rdx, aCdshowwrapperS_9; "CDShowWrapper::SetupThreadpoolWait"
0x180032357  mov     r8d, 871h; int
0x18003235d  mov     rcx, rax; this
0x180032360  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032365  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003236c  jb      loc_18003251C
0x180032372  mov     edx, 0B2h
0x180032377  mov     rcx, cs:WPP_GLOBAL_Control
0x18003237e  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180032385  mov     r9, rsi
0x180032388  mov     [rsp+78h+var_58], ebx
0x18003238c  mov     rcx, [rcx+10h]
0x180032390  call    WPP_SF_qD
0x180032395  jmp     loc_18003251C
0x18003239a  mov     rcx, [rbp+var_40]
0x18003239e  lea     r8, [rbp+var_38]
0x1800323a2  lea     rdx, IID_IMediaEventEx
0x1800323a9  mov     rax, [rcx]
0x1800323ac  mov     rax, [rax]
0x1800323af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323b4  mov     ebx, eax
0x1800323b6  test    eax, eax
0x1800323b8  jns     loc_180032453
0x1800323be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800323c5  test    rcx, rcx
0x1800323c8  jnz     short loc_180032411
0x1800323ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800323d1  nop     dword ptr [rax+rax+00h]
0x1800323d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800323dd  mov     rcx, rax
0x1800323e0  test    rax, rax
0x1800323e3  jz      short loc_180032403
0x1800323e5  mov     rax, [rax]
0x1800323e8  mov     edx, 7F0h
0x1800323ed  mov     rax, [rax+8]
0x1800323f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323f6  test    eax, eax
0x1800323f8  jz      short loc_180032403
0x1800323fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032401  jmp     short loc_180032411
0x180032403  lea     rcx, qword_1800EB130; this
0x18003240a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032411  cmp     byte ptr [rcx+8], 0
0x180032415  jz      short loc_18003243C
0x180032417  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003241c  cmp     [rax+7CCh], ebx
0x180032422  jz      short loc_18003243C
0x180032424  mov     r9d, ebx; int
0x180032427  lea     rdx, aCdshowwrapperS_9; "CDShowWrapper::SetupThreadpoolWait"
0x18003242e  mov     r8d, 872h; int
0x180032434  mov     rcx, rax; this
0x180032437  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003243c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032443  jb      loc_18003251C
0x180032449  mov     edx, 0B3h
0x18003244e  jmp     loc_180032377
0x180032453  mov     rcx, [rbp+var_38]
0x180032457  lea     rdx, [rbp+h]
0x18003245b  mov     rax, [rcx]
0x18003245e  mov     rax, [rax+38h]
0x180032462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032467  mov     ebx, eax
0x180032469  test    eax, eax
0x18003246b  jns     loc_180032502
0x180032471  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032478  test    rcx, rcx
0x18003247b  jnz     short loc_1800324C4
0x18003247d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032484  nop     dword ptr [rax+rax+00h]
0x180032489  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032490  mov     rcx, rax
0x180032493  test    rax, rax
0x180032496  jz      short loc_1800324B6
0x180032498  mov     rax, [rax]
0x18003249b  mov     edx, 7F0h
0x1800324a0  mov     rax, [rax+8]
0x1800324a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a9  test    eax, eax
0x1800324ab  jz      short loc_1800324B6
0x1800324ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800324b4  jmp     short loc_1800324C4
0x1800324b6  lea     rcx, qword_1800EB130; this
0x1800324bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800324c4  cmp     byte ptr [rcx+8], 0
0x1800324c8  jz      short loc_1800324EF
0x1800324ca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800324cf  cmp     [rax+7CCh], ebx
0x1800324d5  jz      short loc_1800324EF
0x1800324d7  mov     r9d, ebx; int
0x1800324da  lea     rdx, aCdshowwrapperS_9; "CDShowWrapper::SetupThreadpoolWait"
0x1800324e1  mov     r8d, 874h; int
0x1800324e7  mov     rcx, rax; this
0x1800324ea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800324ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800324f6  jb      short loc_18003251C
0x1800324f8  mov     edx, 0B4h
0x1800324fd  jmp     loc_180032377
0x180032502  mov     rdx, [rbp+h]; h
0x180032506  xor     r8d, r8d; pftTimeout
0x180032509  mov     rcx, [rsi+1A0h]; pwa
0x180032510  call    cs:__imp_SetThreadpoolWait
0x180032517  nop     dword ptr [rax+rax+00h]
0x18003251c  lea     rcx, [rbp+var_48]; this
0x180032520  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180032525  mov     rcx, [rbp+var_40]
0x180032529  test    rcx, rcx
0x18003252c  jz      short loc_18003253A
0x18003252e  mov     rax, [rcx]
0x180032531  mov     rax, [rax+10h]
0x180032535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003253a  mov     rcx, [rbp+var_38]
0x18003253e  test    rcx, rcx
0x180032541  jz      short loc_18003254F
0x180032543  mov     rax, [rcx]
0x180032546  mov     rax, [rax+10h]
0x18003254a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003254f  mov     eax, ebx
0x180032551  mov     rcx, [rbp+var_18]
0x180032555  xor     rcx, rsp; StackCookie
0x180032558  call    __security_check_cookie
0x18003255d  add     rsp, 78h
0x180032561  pop     rdi
0x180032562  pop     rsi
0x180032563  pop     rbx
0x180032564  pop     rbp
0x180032565  retn
```
