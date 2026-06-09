# CUnCompToUnCompContext::FindOrderedVideoTypeMatchList(ulong,ulong,CTOrderedList<ulong,TypeMatchPair> *)

- ea: `0x1801f4480`
- end: `0x1801f4be4`
- name: `?FindOrderedVideoTypeMatchList@CUnCompToUnCompContext@@AEAAJKKPEAV?$CTOrderedList@KUTypeMatchPair@@@@@Z`
- size: `1892`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18010a65c`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x18010b030`
- `0x1801f4480`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f473e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f48a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f493e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f49ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4a87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4b20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f473e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f48a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f493e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f49ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4a87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801f4b20`

## string_xrefs

- `0x1801f44de`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f47d0`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f486d`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f48ff`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f4998`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f4a44`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f4ae1`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`
- `0x1801f4b7a`: `CUnCompToUnCompContext::FindOrderedVideoTypeMatchList`

## pseudocode

```c
__int64 __fastcall CUnCompToUnCompContext::FindOrderedVideoTypeMatchList(
        _QWORD *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  int v4; // ebx
  __int64 i; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // r8
  __int64 j; // r13
  int v14; // edi
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  int v24; // r8d
  int v25; // ecx
  BOOL v26; // r10d
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r10
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  int v38; // edi
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 *v51; // rcx
  int v52; // edi
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v60[4]; // [rsp+30h] [rbp-30h] BYREF
  int v61; // [rsp+34h] [rbp-2Ch] BYREF
  int v62; // [rsp+38h] [rbp-28h]
  int v63; // [rsp+3Ch] [rbp-24h]
  __int64 v64; // [rsp+40h] [rbp-20h] BYREF
  __int64 v65; // [rsp+48h] [rbp-18h] BYREF
  _DWORD v66[4]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v67; // [rsp+A8h] [rbp+48h]

  v67 = a2;
  v4 = 0;
  v63 = 4 * a3 * a2;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v62 = i;
    if ( (unsigned int)i >= a2 )
      break;
    v65 = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v60,
      "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList",
      439);
    v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(*a1 + 8 * i);
    if ( !v9 )
    {
      v56 = (__int64 *)CallStackTracing::s_wpInstance;
      v52 = -2147467261;
      v4 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList",
            439,
            -2147467261);
      }
      if ( g_wppLevels )
      {
        v55 = 40;
LABEL_117:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, a1, v52);
      }
LABEL_118:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v60);
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v65);
      return (unsigned int)v4;
    }
    v4 = (**v9)(v9, &IID_IMFVideoMediaType, &v65);
    if ( (*(int (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v65 + 24LL))(v65, &MF_MT_PALETTE, 0) < 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 304LL))(v65);
      if ( v11 )
      {
        for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
        {
          v64 = 0;
          v14 = 10 * a3 * (v67 - i) + 1;
          v15 = a1[3];
          v61 = v14;
          v16 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v15 + 8 * j);
          if ( !v16 )
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
            v38 = -2147467261;
            v4 = -2147467261;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != -2147467261 )
                CallStackContext::TraceFailure(
                  v47,
                  "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList",
                  467,
                  -2147467261);
            }
            if ( !g_wppLevels )
              goto LABEL_86;
            v41 = 42;
LABEL_85:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v41,
              &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids,
              a1,
              v38);
            goto LABEL_86;
          }
          v4 = (**v16)(v16, &IID_IMFVideoMediaType, &v64);
          if ( v4 < 0 )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
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
              if ( *((_DWORD *)v44 + 499) != v4 )
                CallStackContext::TraceFailure(v44, "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList", 469, v4);
            }
            if ( g_wppLevels )
            {
              v36 = 43;
LABEL_54:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v36,
                &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids,
                a1,
                v4);
            }
LABEL_86:
            ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
            goto LABEL_87;
          }
          if ( (*(int (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v64 + 24LL))(v64, &MF_MT_PALETTE, 0) >= 0 )
          {
            LODWORD(i) = v62;
          }
          else
          {
            v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 304LL))(v64);
            v22 = v19;
            if ( !v19 )
            {
              v37 = (__int64 *)CallStackTracing::s_wpInstance;
              v38 = -1072875852;
              v4 = -1072875852;
              if ( !CallStackTracing::s_wpInstance )
              {
                v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
                CallStackTracing::s_wpInstance = v39;
                if ( v39
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
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
                v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                if ( *((_DWORD *)v40 + 499) != -1072875852 )
                  CallStackContext::TraceFailure(
                    v40,
                    "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList",
                    482,
                    -1072875852);
              }
              if ( !g_wppLevels )
                goto LABEL_86;
              v41 = 44;
              goto LABEL_85;
            }
            v23 = *(_QWORD *)(v11 + 120) - *(_QWORD *)(v19 + 120);
            if ( !v23 )
              v23 = *(_QWORD *)(v11 + 128) - *(_QWORD *)(v22 + 128);
            if ( v23 )
            {
              v24 = 1;
            }
            else
            {
              v14 += v63;
              v24 = 0;
              v61 = v14;
            }
            v25 = *(_DWORD *)(v22 + 12);
            v26 = !v25 || *(_DWORD *)(v11 + 8) == *(_DWORD *)(v22 + 8) && *(_DWORD *)(v11 + 12) == v25;
            if ( !*(_DWORD *)(v22 + 20)
              || !*(_DWORD *)(v11 + 20)
              || (v27 = 0,
                  *(unsigned int *)(v11 + 20) * (unsigned __int64)*(unsigned int *)(v22 + 16) == *(unsigned int *)(v22 + 20)
                                                                                               * (unsigned __int64)*(unsigned int *)(v11 + 16)) )
            {
              v27 = 1;
            }
            if ( v26 && v27 )
            {
              v14 += 2;
              v61 = v14;
            }
            else
            {
              v24 |= 2u;
            }
            if ( *(_DWORD *)(v22 + 52)
              && *(_DWORD *)(v11 + 52)
              && ((v28 = HIDWORD(*(_QWORD *)(v11 + 48)),
                   v29 = v28 * HIDWORD(*(_QWORD *)(v22 + 48)),
                   v30 = 1000
                       * (HIDWORD(*(_QWORD *)(v22 + 48)) * *(unsigned int *)(v11 + 48)
                        - v28 * *(unsigned int *)(v22 + 48)),
                   v30 < -v29)
               || v30 > v29) )
            {
              v24 |= 4u;
            }
            else
            {
              v61 = ++v14;
            }
            if ( *(_DWORD *)(v22 + 28) == *(_DWORD *)(v11 + 28) )
              v61 = v14 + 1;
            else
              v24 |= 0x10u;
            LODWORD(i) = v62;
            v66[2] = v24;
            v66[0] = v62;
            v66[1] = j;
            if ( !(unsigned int)CTOrderedList<unsigned long,TypeMatchPair>::AddEntry(a4, &v61, v66) )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
              v4 = -2147024882;
              if ( !CallStackTracing::s_wpInstance )
              {
                v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
                CallStackTracing::s_wpInstance = v34;
                if ( v34
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
                {
                  v33 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v33 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v33 + 8) )
              {
                v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                if ( *((_DWORD *)v35 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(
                    v35,
                    "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList",
                    548,
                    -2147024882);
              }
              if ( g_wppLevels )
              {
                v36 = 45;
                goto LABEL_54;
              }
              goto LABEL_86;
            }
          }
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
        }
        if ( v4 >= 0 )
          goto LABEL_47;
LABEL_87:
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
          CallStackTracing::s_wpInstance = v49;
          if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
          {
            v48 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v48 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
          if ( *((_DWORD *)v50 + 499) != v4 )
            CallStackContext::TraceFailure(v50, "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList", 551, v4);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids, a1, v4);
        goto LABEL_118;
      }
      v51 = (__int64 *)CallStackTracing::s_wpInstance;
      v52 = -1072875852;
      v4 = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v51 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v51 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
        if ( *((_DWORD *)v54 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v54, "CUnCompToUnCompContext::FindOrderedVideoTypeMatchList", 453, -1072875852);
      }
      if ( g_wppLevels )
      {
        v55 = 41;
        goto LABEL_117;
      }
      goto LABEL_118;
    }
LABEL_47:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v60);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v65);
    a2 = v67;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801f4480  mov     rax, rsp
0x1801f4483  mov     [rax+8], rbx
0x1801f4487  mov     [rax+20h], r9
0x1801f448b  mov     [rax+18h], r8d
0x1801f448f  mov     [rax+10h], edx
0x1801f4492  push    rbp
0x1801f4493  push    rsi
0x1801f4494  push    rdi
0x1801f4495  push    r12
0x1801f4497  push    r13
0x1801f4499  push    r14
0x1801f449b  push    r15
0x1801f449d  mov     rbp, rsp
0x1801f44a0  sub     rsp, 60h
0x1801f44a4  mov     eax, edx
0x1801f44a6  lea     r14, qword_1803CE250
0x1801f44ad  imul    eax, r8d
0x1801f44b1  lea     r12, WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids
0x1801f44b8  xor     ebx, ebx
0x1801f44ba  mov     r15, rcx
0x1801f44bd  shl     eax, 2
0x1801f44c0  mov     [rbp+var_24], eax
0x1801f44c3  xor     edi, edi
0x1801f44c5  mov     [rbp+var_28], edi
0x1801f44c8  cmp     edi, edx
0x1801f44ca  jnb     loc_1801F4BC9
0x1801f44d0  mov     r8d, 1B7h; int
0x1801f44d6  mov     [rbp+var_18], 0
0x1801f44de  lea     rdx, aCuncomptouncom_4; "CUnCompToUnCompContext::FindOrderedVide"...
0x1801f44e5  lea     rcx, [rbp+var_30]; this
0x1801f44e9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801f44ee  mov     rax, [r15]
0x1801f44f1  mov     rcx, [rax+rdi*8]
0x1801f44f5  test    rcx, rcx
0x1801f44f8  jz      loc_1801F4B0D
0x1801f44fe  mov     rax, [rcx]
0x1801f4501  lea     r8, [rbp+var_18]
0x1801f4505  lea     rdx, IID_IMFVideoMediaType
0x1801f450c  mov     rax, [rax]
0x1801f450f  call    cs:__guard_dispatch_icall_fptr
0x1801f4515  mov     rcx, [rbp+var_18]
0x1801f4519  xor     r8d, r8d
0x1801f451c  mov     ebx, eax
0x1801f451e  mov     rdx, [rcx]
0x1801f4521  mov     rax, [rdx+18h]
0x1801f4525  lea     rdx, MF_MT_PALETTE
0x1801f452c  call    cs:__guard_dispatch_icall_fptr
0x1801f4532  test    eax, eax
0x1801f4534  jns     loc_1801F4794
0x1801f453a  mov     rcx, [rbp+var_18]
0x1801f453e  mov     rax, [rcx]
0x1801f4541  mov     rax, [rax+130h]
0x1801f4548  call    cs:__guard_dispatch_icall_fptr
0x1801f454e  mov     rsi, rax
0x1801f4551  test    rax, rax
0x1801f4554  jz      loc_1801F4A74
0x1801f455a  xor     r13d, r13d
0x1801f455d  mov     ecx, [rbp+arg_10]
0x1801f4560  lea     r14, qword_1803CE250
0x1801f4567  lea     r12, WPP_1c3761fd7999351ac55a8474b3c7752b_Traceguids
0x1801f456e  cmp     r13d, ecx
0x1801f4571  jnb     loc_1801F478C
0x1801f4577  mov     eax, [rbp+arg_8]
0x1801f457a  sub     eax, edi
0x1801f457c  mov     [rbp+var_20], 0
0x1801f4584  imul    eax, ecx
0x1801f4587  lea     eax, [rax+rax*4]
0x1801f458a  lea     edi, ds:1[rax*2]
0x1801f4591  mov     rax, [r15+18h]
0x1801f4595  mov     [rbp+var_2C], edi
0x1801f4598  mov     rcx, [rax+r13*8]
0x1801f459c  test    rcx, rcx
0x1801f459f  jz      loc_1801F492B
0x1801f45a5  mov     rax, [rcx]
0x1801f45a8  lea     r8, [rbp+var_20]
0x1801f45ac  lea     rdx, IID_IMFVideoMediaType
0x1801f45b3  mov     rax, [rax]
0x1801f45b6  call    cs:__guard_dispatch_icall_fptr
0x1801f45bc  mov     ebx, eax
0x1801f45be  test    eax, eax
0x1801f45c0  js      loc_1801F4899
0x1801f45c6  mov     rcx, [rbp+var_20]
0x1801f45ca  lea     rdx, MF_MT_PALETTE
0x1801f45d1  xor     r8d, r8d
0x1801f45d4  mov     rax, [rcx]
0x1801f45d7  mov     rax, [rax+18h]
0x1801f45db  call    cs:__guard_dispatch_icall_fptr
0x1801f45e1  test    eax, eax
0x1801f45e3  jns     loc_1801F4778
0x1801f45e9  mov     rcx, [rbp+var_20]
0x1801f45ed  mov     rax, [rcx]
0x1801f45f0  mov     rax, [rax+130h]
0x1801f45f7  call    cs:__guard_dispatch_icall_fptr
0x1801f45fd  xor     r11d, r11d
0x1801f4600  mov     r9, rax
0x1801f4603  test    rax, rax
0x1801f4606  jz      loc_1801F4800
0x1801f460c  mov     rax, [rsi+78h]
0x1801f4610  sub     rax, [r9+78h]
0x1801f4614  jnz     short loc_1801F4624
0x1801f4616  mov     rax, [rsi+80h]
0x1801f461d  sub     rax, [r9+80h]
0x1801f4624  test    rax, rax
0x1801f4627  jnz     short loc_1801F4634
0x1801f4629  add     edi, [rbp+var_24]
0x1801f462c  mov     r8d, r11d
0x1801f462f  mov     [rbp+var_2C], edi
0x1801f4632  jmp     short loc_1801F463A
0x1801f4634  mov     r8d, 1
0x1801f463a  mov     ecx, [r9+0Ch]
0x1801f463e  test    ecx, ecx
0x1801f4640  jz      short loc_1801F4655
0x1801f4642  mov     eax, [r9+8]
0x1801f4646  cmp     [rsi+8], eax
0x1801f4649  jnz     short loc_1801F4650
0x1801f464b  cmp     [rsi+0Ch], ecx
0x1801f464e  jz      short loc_1801F4655
0x1801f4650  mov     r10d, r11d
0x1801f4653  jmp     short loc_1801F465B
0x1801f4655  mov     r10d, 1
0x1801f465b  cmp     [r9+14h], r11d
0x1801f465f  jz      short loc_1801F4685
0x1801f4661  cmp     [rsi+14h], r11d
0x1801f4665  jz      short loc_1801F4685
0x1801f4667  mov     eax, [r9+14h]
0x1801f466b  mov     edx, [rsi+10h]
0x1801f466e  mov     ecx, [r9+10h]
0x1801f4672  imul    rdx, rax
0x1801f4676  mov     eax, [rsi+14h]
0x1801f4679  imul    rcx, rax
0x1801f467d  mov     eax, r11d
0x1801f4680  cmp     rcx, rdx
0x1801f4683  jnz     short loc_1801F468A
0x1801f4685  mov     eax, 1
0x1801f468a  test    r10d, r10d
0x1801f468d  jz      short loc_1801F469B
0x1801f468f  test    eax, eax
0x1801f4691  jz      short loc_1801F469B
0x1801f4693  add     edi, 2
0x1801f4696  mov     [rbp+var_2C], edi
0x1801f4699  jmp     short loc_1801F469F
0x1801f469b  or      r8d, 2
0x1801f469f  cmp     [r9+34h], r11d
0x1801f46a3  jz      short loc_1801F46F1
0x1801f46a5  cmp     [rsi+34h], r11d
0x1801f46a9  jz      short loc_1801F46F1
0x1801f46ab  mov     rax, [r9+30h]
0x1801f46af  mov     ecx, [rsi+30h]
0x1801f46b2  mov     rdx, [rsi+30h]
0x1801f46b6  shr     rax, 20h
0x1801f46ba  imul    rcx, rax
0x1801f46be  mov     r10, rax
0x1801f46c1  shr     rdx, 20h
0x1801f46c5  mov     eax, [r9+30h]
0x1801f46c9  imul    rax, rdx
0x1801f46cd  imul    r10, rdx
0x1801f46d1  sub     rcx, rax
0x1801f46d4  imul    rdx, rcx, 3E8h
0x1801f46db  mov     rax, r10
0x1801f46de  neg     rax
0x1801f46e1  cmp     rdx, rax
0x1801f46e4  jl      short loc_1801F46EB
0x1801f46e6  cmp     rdx, r10
0x1801f46e9  jle     short loc_1801F46F1
0x1801f46eb  or      r8d, 4
0x1801f46ef  jmp     short loc_1801F46F6
0x1801f46f1  inc     edi
0x1801f46f3  mov     [rbp+var_2C], edi
0x1801f46f6  mov     eax, [rsi+1Ch]
0x1801f46f9  cmp     [r9+1Ch], eax
0x1801f46fd  jnz     short loc_1801F4706
0x1801f46ff  inc     edi
0x1801f4701  mov     [rbp+var_2C], edi
0x1801f4704  jmp     short loc_1801F470A
0x1801f4706  or      r8d, 10h
0x1801f470a  mov     edi, [rbp+var_28]
0x1801f470d  lea     rdx, [rbp+var_2C]
0x1801f4711  mov     rcx, [rbp+arg_18]
0x1801f4715  mov     [rbp+var_8], r8d
0x1801f4719  lea     r8, [rbp+var_10]
0x1801f471d  mov     [rbp+var_10], edi
0x1801f4720  mov     [rbp+var_C], r13d
0x1801f4724  call    ?AddEntry@?$CTOrderedList@KUTypeMatchPair@@@@QEAAHAEBKAEBUTypeMatchPair@@@Z; CTOrderedList<ulong,TypeMatchPair>::AddEntry(ulong const &,TypeMatchPair const &)
0x1801f4729  test    eax, eax
0x1801f472b  jnz     short loc_1801F477B
0x1801f472d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4734  mov     ebx, 8007000Eh
0x1801f4739  test    rcx, rcx
0x1801f473c  jnz     short loc_1801F47BA
0x1801f473e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f4745  nop     dword ptr [rax+rax+00h]
0x1801f474a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4751  mov     rcx, rax
0x1801f4754  test    rax, rax
0x1801f4757  jz      short loc_1801F47B0
0x1801f4759  mov     rax, [rax]
0x1801f475c  mov     edx, 7F0h
0x1801f4761  mov     rax, [rax+8]
0x1801f4765  call    cs:__guard_dispatch_icall_fptr
0x1801f476b  test    eax, eax
0x1801f476d  jz      short loc_1801F47B0
0x1801f476f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4776  jmp     short loc_1801F47BA
0x1801f4778  mov     edi, [rbp+var_28]
0x1801f477b  lea     rcx, [rbp+var_20]
0x1801f477f  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801f4784  inc     r13d
0x1801f4787  jmp     loc_1801F455D
0x1801f478c  test    ebx, ebx
0x1801f478e  js      loc_1801F49DE
0x1801f4794  lea     rcx, [rbp+var_30]; this
0x1801f4798  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801f479d  lea     rcx, [rbp+var_18]
0x1801f47a1  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1801f47a6  mov     edx, [rbp+arg_8]
0x1801f47a9  inc     edi
0x1801f47ab  jmp     loc_1801F44C5
0x1801f47b0  mov     rcx, r14; this
0x1801f47b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f47ba  cmp     byte ptr [rcx+8], 0
0x1801f47be  jz      short loc_1801F47E5
0x1801f47c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f47c5  cmp     [rax+7CCh], ebx
0x1801f47cb  jz      short loc_1801F47E5
0x1801f47cd  mov     r9d, ebx; int
0x1801f47d0  lea     rdx, aCuncomptouncom_4; "CUnCompToUnCompContext::FindOrderedVide"...
0x1801f47d7  mov     r8d, 224h; int
0x1801f47dd  mov     rcx, rax; this
0x1801f47e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f47e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f47ec  jb      loc_1801F49D5
0x1801f47f2  mov     edx, 2Dh ; '-'
0x1801f47f7  mov     [rsp+60h+var_40], ebx
0x1801f47fb  jmp     loc_1801F49BF
0x1801f4800  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4807  mov     edi, 0C00D36B4h
0x1801f480c  mov     ebx, edi
0x1801f480e  test    rcx, rcx
0x1801f4811  jnz     short loc_1801F4857
0x1801f4813  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f481a  nop     dword ptr [rax+rax+00h]
0x1801f481f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4826  mov     rcx, rax
0x1801f4829  test    rax, rax
0x1801f482c  jz      short loc_1801F484D
0x1801f482e  mov     rax, [rax]
0x1801f4831  mov     edx, 7F0h
0x1801f4836  mov     rax, [rax+8]
0x1801f483a  call    cs:__guard_dispatch_icall_fptr
0x1801f4840  test    eax, eax
0x1801f4842  jz      short loc_1801F484D
0x1801f4844  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f484b  jmp     short loc_1801F4857
0x1801f484d  mov     rcx, r14; this
0x1801f4850  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f4857  cmp     byte ptr [rcx+8], 0
0x1801f485b  jz      short loc_1801F4882
0x1801f485d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f4862  cmp     [rax+7CCh], edi
0x1801f4868  jz      short loc_1801F4882
0x1801f486a  mov     r9d, edi; int
0x1801f486d  lea     rdx, aCuncomptouncom_4; "CUnCompToUnCompContext::FindOrderedVide"...
0x1801f4874  mov     r8d, 1E2h; int
0x1801f487a  mov     rcx, rax; this
0x1801f487d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f4882  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f4889  jb      loc_1801F49D5
0x1801f488f  mov     edx, 2Ch ; ','
0x1801f4894  jmp     loc_1801F49BB
0x1801f4899  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f48a0  test    rcx, rcx
0x1801f48a3  jnz     short loc_1801F48E9
0x1801f48a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801f48ac  nop     dword ptr [rax+rax+00h]
0x1801f48b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f48b8  mov     rcx, rax
0x1801f48bb  test    rax, rax
0x1801f48be  jz      short loc_1801F48DF
0x1801f48c0  mov     rax, [rax]
0x1801f48c3  mov     edx, 7F0h
0x1801f48c8  mov     rax, [rax+8]
0x1801f48cc  call    cs:__guard_dispatch_icall_fptr
0x1801f48d2  test    eax, eax
0x1801f48d4  jz      short loc_1801F48DF
0x1801f48d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f48dd  jmp     short loc_1801F48E9
0x1801f48df  mov     rcx, r14; this
0x1801f48e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801f48e9  cmp     byte ptr [rcx+8], 0
0x1801f48ed  jz      short loc_1801F4914
0x1801f48ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801f48f4  cmp     [rax+7CCh], ebx
0x1801f48fa  jz      short loc_1801F4914
0x1801f48fc  mov     r9d, ebx; int
0x1801f48ff  lea     rdx, aCuncomptouncom_4; "CUnCompToUnCompContext::FindOrderedVide"...
0x1801f4906  mov     r8d, 1D5h; int
0x1801f490c  mov     rcx, rax; this
0x1801f490f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801f4914  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801f491b  jb      loc_1801F49D5
  ... truncated ...
```
