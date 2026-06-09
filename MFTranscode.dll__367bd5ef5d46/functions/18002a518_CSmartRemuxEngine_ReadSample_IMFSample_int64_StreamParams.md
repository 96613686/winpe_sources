# CSmartRemuxEngine::_ReadSample(IMFSample * *,__int64 *,StreamParams * *)

- ea: `0x18002a518`
- end: `0x18002a93e`
- name: `?_ReadSample@CSmartRemuxEngine@@IEAAJPEAPEAUIMFSample@@PEA_JPEAPEAUStreamParams@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this, struct IMFSample **, __int64 *, struct StreamParams **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001f5b8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a320`
- `0x18001a330`
- `0x18001c240`
- `0x18001c280`
- `0x18002a518`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a5b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a69e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a763`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a861`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a5b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a69e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a763`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a861`

## string_xrefs

- `0x18002a534`: `CSmartRemuxEngine::_ReadSample`
- `0x18002a60f`: `CSmartRemuxEngine::_ReadSample`
- `0x18002a6f5`: `CSmartRemuxEngine::_ReadSample`
- `0x18002a7ba`: `CSmartRemuxEngine::_ReadSample`
- `0x18002a8b8`: `CSmartRemuxEngine::_ReadSample`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_ReadSample(
        CSmartRemuxEngine *this,
        struct IMFSample **a2,
        __int64 *a3,
        struct StreamParams **a4)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  struct StreamParams *v24; // r14
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rax
  _QWORD v33[2]; // [rsp+40h] [rbp-10h] BYREF
  char v34; // [rsp+90h] [rbp+40h] BYREF
  int v35; // [rsp+98h] [rbp+48h] BYREF
  int v36; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v34, "CSmartRemuxEngine::_ReadSample", 1761);
  *a2 = 0;
  v8 = (__int64 *)*((_QWORD *)this + 4);
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v33[0] = 0;
  v9 = *v8;
  *a3 = 0;
  *a4 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, int *, int *, __int64 *, _QWORD *))(v9 + 72))(
          v8,
          4294967294LL,
          0,
          &v36,
          &v35,
          &v37,
          v33);
  if ( v11 >= 0 )
  {
    if ( (v35 & 1) != 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 225, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this);
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CSmartRemuxEngine::_ReadSample", 1782, -2147467259);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 226;
        goto LABEL_12;
      }
    }
    else
    {
      if ( (v35 & 0x34) == 0 )
      {
        v24 = (CSmartRemuxEngine *)((char *)this + 96);
        if ( v36 != *((_DWORD *)this + 24) )
          v24 = (CSmartRemuxEngine *)((char *)this + 128);
        if ( *((_BYTE *)v24 + 20) )
          goto LABEL_61;
        if ( (v35 & 2) != 0 )
        {
          *((_BYTE *)v24 + 20) = 1;
          goto LABEL_61;
        }
        v25 = v37;
        if ( (v35 & 0x100) != 0 )
        {
          v26 = *((_QWORD *)this + 32);
          if ( v37 >= v26 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 5) + 56LL))(
                    *((_QWORD *)this + 5),
                    *((unsigned int *)v24 + 1),
                    v37 - v26);
            if ( v11 < 0 )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                CallStackTracing::s_wpInstance = v29;
                if ( v29
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
                v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                if ( *((_DWORD *)v30 + 499) != v11 )
                  CallStackContext::TraceFailure(v30, "CSmartRemuxEngine::_ReadSample", 1813, v11);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v15 = 229;
                goto LABEL_12;
              }
              goto LABEL_61;
            }
            v31 = *((_QWORD *)this + 25);
            v25 = v37;
            if ( v31 <= v37 - *((_QWORD *)this + 32) )
              v31 = v37 - *((_QWORD *)this + 32);
            *((_QWORD *)this + 25) = v31;
          }
        }
        *a2 = (struct IMFSample *)v33[0];
        v33[0] = 0;
        *a3 = v25;
        *a4 = v24;
        goto LABEL_61;
      }
      if ( _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel() )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 227, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this);
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -1072875778;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != -1072875778 )
          CallStackContext::TraceFailure(v23, "CSmartRemuxEngine::_ReadSample", 1791, -1072875778);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v15 = 228;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
      if ( *((_DWORD *)v14 + 499) != v11 )
        CallStackContext::TraceFailure(v14, "CSmartRemuxEngine::_ReadSample", 1777, v11);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v15 = 224;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v11);
    }
  }
LABEL_61:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v33);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002a518  push    rbp
0x18002a51a  push    rbx
0x18002a51b  push    rdi
0x18002a51c  push    r12
0x18002a51e  push    r13
0x18002a520  push    r14
0x18002a522  push    r15
0x18002a524  mov     rbp, rsp
0x18002a527  sub     rsp, 50h
0x18002a52b  mov     r12, r8
0x18002a52e  mov     r13, rdx
0x18002a531  mov     rdi, rcx
0x18002a534  lea     rdx, aCsmartremuxeng_6; "CSmartRemuxEngine::_ReadSample"
0x18002a53b  mov     r8d, 6E1h; int
0x18002a541  lea     rcx, [rbp+arg_0]; this
0x18002a545  mov     r15, r9
0x18002a548  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002a54d  xor     r14d, r14d
0x18002a550  lea     rdx, [rbp+var_10]
0x18002a554  mov     [rsp+50h+var_20], rdx
0x18002a559  lea     r9, [rbp+arg_10]
0x18002a55d  mov     [r13+0], r14
0x18002a561  lea     rdx, [rbp+arg_18]
0x18002a565  mov     rcx, [rdi+20h]
0x18002a569  xor     r8d, r8d
0x18002a56c  mov     [rsp+50h+var_28], rdx
0x18002a571  lea     rdx, [rbp+arg_8]
0x18002a575  mov     [rbp+arg_10], r14d
0x18002a579  mov     [rbp+arg_8], r14d
0x18002a57d  mov     [rbp+arg_18], r14
0x18002a581  mov     [rbp+var_10], r14
0x18002a585  mov     rax, [rcx]
0x18002a588  mov     [rsp+50h+var_30], rdx
0x18002a58d  mov     edx, 0FFFFFFFEh
0x18002a592  mov     [r12], r14
0x18002a596  mov     [r15], r14
0x18002a599  mov     rax, [rax+48h]
0x18002a59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5a2  mov     ebx, eax
0x18002a5a4  test    eax, eax
0x18002a5a6  jns     loc_18002A659
0x18002a5ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5b3  test    rcx, rcx
0x18002a5b6  jnz     short loc_18002A5F9
0x18002a5b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a5be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5c5  mov     rcx, rax
0x18002a5c8  test    rax, rax
0x18002a5cb  jz      short loc_18002A5EB
0x18002a5cd  mov     rax, [rax]
0x18002a5d0  mov     edx, 7F0h
0x18002a5d5  mov     rax, [rax+8]
0x18002a5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5de  test    eax, eax
0x18002a5e0  jz      short loc_18002A5EB
0x18002a5e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5e9  jmp     short loc_18002A5F9
0x18002a5eb  lea     rcx, qword_180069A90; this
0x18002a5f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a5f9  cmp     [rcx+8], r14b
0x18002a5fd  jz      short loc_18002A624
0x18002a5ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a604  cmp     [rax+7CCh], ebx
0x18002a60a  jz      short loc_18002A624
0x18002a60c  mov     r9d, ebx; int
0x18002a60f  lea     rdx, aCsmartremuxeng_6; "CSmartRemuxEngine::_ReadSample"
0x18002a616  mov     r8d, 6F1h; int
0x18002a61c  mov     rcx, rax; this
0x18002a61f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a624  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a629  cmp     al, 1
0x18002a62b  jb      loc_18002A91A
0x18002a631  mov     edx, 0E0h
0x18002a636  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a63d  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002a644  mov     r9, rdi
0x18002a647  mov     dword ptr [rsp+50h+var_30], ebx
0x18002a64b  mov     rcx, [rcx+10h]
0x18002a64f  call    WPP_SF_qd
0x18002a654  jmp     loc_18002A91A
0x18002a659  mov     ecx, [rbp+arg_8]
0x18002a65c  test    cl, 1
0x18002a65f  jz      loc_18002A721
0x18002a665  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x18002a66a  cmp     al, 1
0x18002a66c  jb      short loc_18002A68D
0x18002a66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a675  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002a67c  mov     edx, 0E1h
0x18002a681  mov     r9, rdi
0x18002a684  mov     rcx, [rcx+38h]
0x18002a688  call    WPP_SF_q
0x18002a68d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a694  mov     ebx, 80004005h
0x18002a699  test    rcx, rcx
0x18002a69c  jnz     short loc_18002A6DF
0x18002a69e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a6a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6ab  mov     rcx, rax
0x18002a6ae  test    rax, rax
0x18002a6b1  jz      short loc_18002A6D1
0x18002a6b3  mov     rax, [rax]
0x18002a6b6  mov     edx, 7F0h
0x18002a6bb  mov     rax, [rax+8]
0x18002a6bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6c4  test    eax, eax
0x18002a6c6  jz      short loc_18002A6D1
0x18002a6c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6cf  jmp     short loc_18002A6DF
0x18002a6d1  lea     rcx, qword_180069A90; this
0x18002a6d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6df  cmp     [rcx+8], r14b
0x18002a6e3  jz      short loc_18002A70A
0x18002a6e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a6ea  cmp     [rax+7CCh], ebx
0x18002a6f0  jz      short loc_18002A70A
0x18002a6f2  mov     r9d, ebx; int
0x18002a6f5  lea     rdx, aCsmartremuxeng_6; "CSmartRemuxEngine::_ReadSample"
0x18002a6fc  mov     r8d, 6F6h; int
0x18002a702  mov     rcx, rax; this
0x18002a705  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a70a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a70f  cmp     al, 1
0x18002a711  jb      loc_18002A91A
0x18002a717  mov     edx, 0E2h
0x18002a71c  jmp     loc_18002A636
0x18002a721  test    cl, 34h
0x18002a724  jz      loc_18002A7E6
0x18002a72a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PIPELINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PIPELINE::GetLevel(void)
0x18002a72f  cmp     al, 1
0x18002a731  jb      short loc_18002A752
0x18002a733  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a73a  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002a741  mov     edx, 0E3h
0x18002a746  mov     r9, rdi
0x18002a749  mov     rcx, [rcx+38h]
0x18002a74d  call    WPP_SF_q
0x18002a752  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a759  mov     ebx, 0C00D36FEh
0x18002a75e  test    rcx, rcx
0x18002a761  jnz     short loc_18002A7A4
0x18002a763  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a769  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a770  mov     rcx, rax
0x18002a773  test    rax, rax
0x18002a776  jz      short loc_18002A796
0x18002a778  mov     rax, [rax]
0x18002a77b  mov     edx, 7F0h
0x18002a780  mov     rax, [rax+8]
0x18002a784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a789  test    eax, eax
0x18002a78b  jz      short loc_18002A796
0x18002a78d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a794  jmp     short loc_18002A7A4
0x18002a796  lea     rcx, qword_180069A90; this
0x18002a79d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a7a4  cmp     [rcx+8], r14b
0x18002a7a8  jz      short loc_18002A7CF
0x18002a7aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a7af  cmp     [rax+7CCh], ebx
0x18002a7b5  jz      short loc_18002A7CF
0x18002a7b7  mov     r9d, ebx; int
0x18002a7ba  lea     rdx, aCsmartremuxeng_6; "CSmartRemuxEngine::_ReadSample"
0x18002a7c1  mov     r8d, 6FFh; int
0x18002a7c7  mov     rcx, rax; this
0x18002a7ca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a7cf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a7d4  cmp     al, 1
0x18002a7d6  jb      loc_18002A91A
0x18002a7dc  mov     edx, 0E4h
0x18002a7e1  jmp     loc_18002A636
0x18002a7e6  lea     r14, [rdi+60h]
0x18002a7ea  mov     eax, [r14]
0x18002a7ed  cmp     [rbp+arg_10], eax
0x18002a7f0  jz      short loc_18002A7F9
0x18002a7f2  lea     r14, [rdi+80h]
0x18002a7f9  cmp     byte ptr [r14+14h], 0
0x18002a7fe  jnz     loc_18002A91A
0x18002a804  test    cl, 2
0x18002a807  jz      short loc_18002A813
0x18002a809  mov     byte ptr [r14+14h], 1
0x18002a80e  jmp     loc_18002A91A
0x18002a813  mov     rdx, [rbp+arg_18]
0x18002a817  bt      ecx, 8
0x18002a81b  jnb     loc_18002A903
0x18002a821  mov     r8, [rdi+100h]
0x18002a828  cmp     rdx, r8
0x18002a82b  jl      loc_18002A903
0x18002a831  mov     rcx, [rdi+28h]
0x18002a835  sub     rdx, r8
0x18002a838  mov     r8, rdx
0x18002a83b  mov     edx, [r14+4]
0x18002a83f  mov     rax, [rcx]
0x18002a842  mov     rax, [rax+38h]
0x18002a846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a84b  mov     ebx, eax
0x18002a84d  test    eax, eax
0x18002a84f  jns     loc_18002A8E0
0x18002a855  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a85c  test    rcx, rcx
0x18002a85f  jnz     short loc_18002A8A2
0x18002a861  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a867  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a86e  mov     rcx, rax
0x18002a871  test    rax, rax
0x18002a874  jz      short loc_18002A894
0x18002a876  mov     rax, [rax]
0x18002a879  mov     edx, 7F0h
0x18002a87e  mov     rax, [rax+8]
0x18002a882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a887  test    eax, eax
0x18002a889  jz      short loc_18002A894
0x18002a88b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a892  jmp     short loc_18002A8A2
0x18002a894  lea     rcx, qword_180069A90; this
0x18002a89b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8a2  cmp     byte ptr [rcx+8], 0
0x18002a8a6  jz      short loc_18002A8CD
0x18002a8a8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a8ad  cmp     [rax+7CCh], ebx
0x18002a8b3  jz      short loc_18002A8CD
0x18002a8b5  mov     r9d, ebx; int
0x18002a8b8  lea     rdx, aCsmartremuxeng_6; "CSmartRemuxEngine::_ReadSample"
0x18002a8bf  mov     r8d, 715h; int
0x18002a8c5  mov     rcx, rax; this
0x18002a8c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a8cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002a8d2  cmp     al, 1
0x18002a8d4  jb      short loc_18002A91A
0x18002a8d6  mov     edx, 0E5h
0x18002a8db  jmp     loc_18002A636
0x18002a8e0  mov     rax, [rdi+0C8h]
0x18002a8e7  mov     rdx, [rbp+arg_18]
0x18002a8eb  mov     rcx, rdx
0x18002a8ee  sub     rcx, [rdi+100h]
0x18002a8f5  cmp     rax, rcx
0x18002a8f8  cmovle  rax, rcx
0x18002a8fc  mov     [rdi+0C8h], rax
0x18002a903  mov     rcx, [rbp+var_10]
0x18002a907  mov     [r13+0], rcx
0x18002a90b  mov     [rbp+var_10], 0
0x18002a913  mov     [r12], rdx
0x18002a917  mov     [r15], r14
0x18002a91a  lea     rcx, [rbp+var_10]
0x18002a91e  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18002a923  lea     rcx, [rbp+arg_0]; this
0x18002a927  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002a92c  mov     eax, ebx
0x18002a92e  add     rsp, 50h
0x18002a932  pop     r15
0x18002a934  pop     r14
0x18002a936  pop     r13
0x18002a938  pop     r12
0x18002a93a  pop     rdi
0x18002a93b  pop     rbx
0x18002a93c  pop     rbp
0x18002a93d  retn
```
