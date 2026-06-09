# CMFPropVariant::InsertElement(ulong,tagPROPVARIANT const *)

- ea: `0x180245bc8`
- end: `0x180246342`
- name: `?InsertElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z`
- size: `1914`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801cd57c`

## callees

- `0x18002c9ac`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18019d300`
- `0x1801c1658`
- `0x1801c32c0`
- `0x1802115c8`
- `0x180245bc8`
- `0x180258480`
- `0x1802592a0`
- `0x1802796b8`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180245fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180246306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180245fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180246306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180245ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180245ed7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245c5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245d20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245e3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245f00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18024600f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802460dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180246187`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180246264`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245c5d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245d20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245e3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180245f00`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18024600f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802460dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180246187`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180246264`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::InsertElement(CMFPropVariant *this, unsigned int a2, PROPVARIANT *a3)
{
  __int16 v4; // cx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rcx
  int VarTypeSize; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CMFPropVariant *v13; // r8
  __int16 v14; // r10
  unsigned int ElementCount; // r15d
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int16 v21; // cx
  __int16 v22; // dx
  const void **v23; // r14
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  int v29; // r12d
  size_t v30; // rcx
  char *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  char *v34; // rbx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  PROPVARIANT *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  const void *v44; // r8
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
  char v61[8]; // [rsp+30h] [rbp-40h] BYREF
  size_t Size; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvarDest[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v66; // [rsp+60h] [rbp-10h]

  pvarSrc = a3;
  LODWORD(Size) = 0;
  v4 = *(_WORD *)this;
  Src = 0;
  v66 = 0;
  *(_OWORD *)pvarDest = 0;
  if ( (v4 & 0x1000) != 0 || !*(_WORD *)this )
  {
    ElementCount = CMFPropVariant::GetElementCount(this);
    if ( this == v13 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1991);
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      VarTypeSize = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::InsertElement", 1991, -2147467261);
      }
      if ( g_wppLevels )
      {
        v12 = 130;
        goto LABEL_106;
      }
    }
    else
    {
      v21 = *(_WORD *)v13;
      if ( !*(_WORD *)v13
        || *(_WORD *)this && (v22 = *(_WORD *)this & 0xFFF, v22 != 12) && (v21 & 0xFFF) != v22
        || ElementCount < a2 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1998);
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
        VarTypeSize = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
          CallStackTracing::s_wpInstance = v58;
          if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
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
          if ( *((_DWORD *)v59 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v59, "CMFPropVariant::InsertElement", 1998, -2147024809);
        }
        if ( g_wppLevels )
        {
          v12 = 131;
          goto LABEL_106;
        }
        goto LABEL_107;
      }
      v23 = (const void **)((char *)this + 16);
      if ( !*(_WORD *)this )
      {
        *((_DWORD *)this + 2) = 0;
        *v23 = 0;
        *(_WORD *)this = v14 | v21 & 0xFFF;
      }
      VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, (unsigned int *)&Size);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 2015);
      if ( VarTypeSize >= 0 )
      {
        v29 = Size;
        v30 = (unsigned int)Size * (ElementCount + 1);
        Size = v30;
        v31 = (char *)CoTaskMemAlloc(v30);
        v34 = v31;
        if ( v31 )
        {
          memset_0(v31, 0, Size);
          if ( a2 )
            memcpy_0(v34, *v23, v29 * a2);
          if ( ElementCount > a2 )
            memcpy_0(&v34[v29 * (a2 + 1)], (char *)*v23 + v29 * a2, v29 * (ElementCount - a2));
          CoTaskMemFree((LPVOID)*v23);
          v38 = pvarSrc;
          ++*((_DWORD *)this + 2);
          *v23 = v34;
          VarTypeSize = CMFPropVariant::Copy(pvarDest, v38);
          if ( VarTypeSize >= 0 )
          {
            if ( (*(_WORD *)this & 0xFFF) == 0xC )
            {
              v44 = pvarDest;
            }
            else
            {
              VarTypeSize = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)pvarDest, 0, &Src);
              if ( VarTypeSize < 0 )
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
                  if ( *((_DWORD *)v49 + 499) != VarTypeSize )
                    CallStackContext::TraceFailure(v49, "CMFPropVariant::InsertElement", 2086, VarTypeSize);
                }
                if ( g_wppLevels )
                {
                  v12 = 135;
                  goto LABEL_106;
                }
                goto LABEL_107;
              }
              v44 = Src;
            }
            VarTypeSize = CMFPropVariant::SetElementData(this, a2, v44);
            if ( VarTypeSize >= 0 )
            {
              if ( (*(_WORD *)this & 0xFFF) == 0xC || LOWORD(pvarDest[0]) != 72 )
              {
                *(_OWORD *)pvarDest = 0;
                v66 = 0;
              }
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
                if ( *((_DWORD *)v54 + 499) != VarTypeSize )
                  CallStackContext::TraceFailure(v54, "CMFPropVariant::InsertElement", 2093, VarTypeSize);
              }
              if ( g_wppLevels )
              {
                v12 = 136;
                goto LABEL_106;
              }
            }
            goto LABEL_107;
          }
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40);
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
            if ( *((_DWORD *)v43 + 499) != VarTypeSize )
              CallStackContext::TraceFailure(v43, "CMFPropVariant::InsertElement", 2068, VarTypeSize);
          }
          if ( g_wppLevels )
          {
            v12 = 134;
            goto LABEL_106;
          }
        }
        else
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          VarTypeSize = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
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
            if ( *((_DWORD *)v37 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v37, "CMFPropVariant::InsertElement", 2021, -2147024882);
          }
          if ( g_wppLevels )
          {
            v12 = 133;
            goto LABEL_106;
          }
        }
      }
      else
      {
        v26 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
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
          if ( *((_DWORD *)v28 + 499) != VarTypeSize )
            CallStackContext::TraceFailure(v28, "CMFPropVariant::InsertElement", 2015, VarTypeSize);
        }
        if ( g_wppLevels )
        {
          v12 = 132;
          goto LABEL_106;
        }
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1978);
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v11 + 499) != -1072875796 )
        CallStackContext::TraceFailure(v11, "CMFPropVariant::InsertElement", 1978, -1072875796);
    }
    if ( g_wppLevels )
    {
      v12 = 129;
LABEL_106:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        VarTypeSize);
    }
  }
LABEL_107:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
  CoTaskMemFree(0);
  CMFPropVariant::Clear(pvarDest);
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x180245bc8  mov     [rsp-38h+arg_18], rbx
0x180245bcd  push    rbp
0x180245bce  push    rsi
0x180245bcf  push    rdi
0x180245bd0  push    r12
0x180245bd2  push    r13
0x180245bd4  push    r14
0x180245bd6  push    r15
0x180245bd8  mov     rbp, rsp
0x180245bdb  sub     rsp, 70h
0x180245bdf  mov     rax, cs:__security_cookie
0x180245be6  xor     rax, rsp
0x180245be9  mov     [rbp+var_8], rax
0x180245bed  xor     r12d, r12d
0x180245bf0  mov     [rbp+pvarSrc], r8
0x180245bf4  mov     rdi, rcx
0x180245bf7  mov     dword ptr [rbp+Size], r12d
0x180245bfb  movzx   ecx, word ptr [rcx]
0x180245bfe  xor     eax, eax
0x180245c00  mov     r10d, 1000h
0x180245c06  mov     [rbp+Src], r12
0x180245c0a  and     cx, r10w
0x180245c0e  mov     [rbp+var_10], rax
0x180245c12  xorps   xmm0, xmm0
0x180245c15  mov     r13d, edx
0x180245c18  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180245c1c  cmp     r12w, cx
0x180245c20  jnz     loc_180245CDF
0x180245c26  cmp     r12w, [rdi]
0x180245c2a  jz      loc_180245CDF
0x180245c30  mov     r14d, 7BAh
0x180245c36  lea     rsi, aCmfpropvariant_7; "CMFPropVariant::InsertElement"
0x180245c3d  mov     r8d, r14d; int
0x180245c40  lea     rcx, [rbp+var_40]; this
0x180245c44  mov     rdx, rsi; char *
0x180245c47  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180245c4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245c53  mov     ebx, 0C00D36ECh
0x180245c58  test    rcx, rcx
0x180245c5b  jnz     short loc_180245CA4
0x180245c5d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180245c64  nop     dword ptr [rax+rax+00h]
0x180245c69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180245c70  mov     rcx, rax
0x180245c73  test    rax, rax
0x180245c76  jz      short loc_180245C96
0x180245c78  mov     rax, [rax]
0x180245c7b  lea     edx, [r14+36h]
0x180245c7f  mov     rax, [rax+8]
0x180245c83  call    cs:__guard_dispatch_icall_fptr
0x180245c89  test    eax, eax
0x180245c8b  jz      short loc_180245C96
0x180245c8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245c94  jmp     short loc_180245CA4
0x180245c96  lea     rcx, qword_1803CE250; this
0x180245c9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180245ca4  cmp     [rcx+8], r12b
0x180245ca8  jz      short loc_180245CC8
0x180245caa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180245caf  cmp     [rax+7CCh], ebx
0x180245cb5  jz      short loc_180245CC8
0x180245cb7  mov     r9d, ebx; int
0x180245cba  mov     r8d, r14d; int
0x180245cbd  mov     rdx, rsi; char *
0x180245cc0  mov     rcx, rax; this
0x180245cc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180245cc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180245ccf  jb      loc_1802462FB
0x180245cd5  mov     edx, 81h
0x180245cda  jmp     loc_1802462DD
0x180245cdf  mov     rcx, rdi; this
0x180245ce2  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180245ce7  mov     r15d, eax
0x180245cea  cmp     rdi, r8
0x180245ced  jnz     loc_180245DA2
0x180245cf3  mov     r14d, 7C7h
0x180245cf9  lea     rsi, aCmfpropvariant_7; "CMFPropVariant::InsertElement"
0x180245d00  mov     r8d, r14d; int
0x180245d03  lea     rcx, [rbp+var_40]; this
0x180245d07  mov     rdx, rsi; char *
0x180245d0a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180245d0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245d16  mov     ebx, 80004003h
0x180245d1b  test    rcx, rcx
0x180245d1e  jnz     short loc_180245D67
0x180245d20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180245d27  nop     dword ptr [rax+rax+00h]
0x180245d2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180245d33  mov     rcx, rax
0x180245d36  test    rax, rax
0x180245d39  jz      short loc_180245D59
0x180245d3b  mov     rax, [rax]
0x180245d3e  lea     edx, [r14+29h]
0x180245d42  mov     rax, [rax+8]
0x180245d46  call    cs:__guard_dispatch_icall_fptr
0x180245d4c  test    eax, eax
0x180245d4e  jz      short loc_180245D59
0x180245d50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245d57  jmp     short loc_180245D67
0x180245d59  lea     rcx, qword_1803CE250; this
0x180245d60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180245d67  cmp     [rcx+8], r12b
0x180245d6b  jz      short loc_180245D8B
0x180245d6d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180245d72  cmp     [rax+7CCh], ebx
0x180245d78  jz      short loc_180245D8B
0x180245d7a  mov     r9d, ebx; int
0x180245d7d  mov     r8d, r14d; int
0x180245d80  mov     rdx, rsi; char *
0x180245d83  mov     rcx, rax; this
0x180245d86  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180245d8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180245d92  jb      loc_1802462FB
0x180245d98  mov     edx, 82h
0x180245d9d  jmp     loc_1802462DD
0x180245da2  movzx   ecx, word ptr [r8]
0x180245da6  cmp     r12w, cx
0x180245daa  jz      loc_180246237
0x180245db0  mov     r8d, 0FFFh
0x180245db6  mov     r9d, 0Ch
0x180245dbc  cmp     r12w, [rdi]
0x180245dc0  jz      short loc_180245DDF
0x180245dc2  movzx   edx, word ptr [rdi]
0x180245dc5  and     dx, r8w
0x180245dc9  cmp     r9w, dx
0x180245dcd  jz      short loc_180245DDF
0x180245dcf  movzx   eax, cx
0x180245dd2  and     ax, r8w
0x180245dd6  cmp     ax, dx
0x180245dd9  jnz     loc_180246237
0x180245ddf  cmp     r15d, r13d
0x180245de2  jb      loc_180246237
0x180245de8  lea     r14, [rdi+10h]
0x180245dec  cmp     r12w, [rdi]
0x180245df0  jnz     short loc_180245E04
0x180245df2  and     cx, r8w
0x180245df6  mov     [rdi+8], r12d
0x180245dfa  or      cx, r10w
0x180245dfe  mov     [r14], r12
0x180245e01  mov     [rdi], cx
0x180245e04  lea     rdx, [rbp+Size]; unsigned int *
0x180245e08  mov     rcx, rdi; struct CMFPropVariant *
0x180245e0b  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180245e10  lea     rsi, aCmfpropvariant_7; "CMFPropVariant::InsertElement"
0x180245e17  mov     r8d, 7DFh; int
0x180245e1d  mov     rdx, rsi; char *
0x180245e20  lea     rcx, [rbp+var_40]; this
0x180245e24  mov     ebx, eax
0x180245e26  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180245e2b  test    ebx, ebx
0x180245e2d  jns     loc_180245EC5
0x180245e33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245e3a  test    rcx, rcx
0x180245e3d  jnz     short loc_180245E87
0x180245e3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180245e46  nop     dword ptr [rax+rax+00h]
0x180245e4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180245e52  mov     rcx, rax
0x180245e55  test    rax, rax
0x180245e58  jz      short loc_180245E79
0x180245e5a  mov     rax, [rax]
0x180245e5d  mov     edx, 7F0h
0x180245e62  mov     rax, [rax+8]
0x180245e66  call    cs:__guard_dispatch_icall_fptr
0x180245e6c  test    eax, eax
0x180245e6e  jz      short loc_180245E79
0x180245e70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245e77  jmp     short loc_180245E87
0x180245e79  lea     rcx, qword_1803CE250; this
0x180245e80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180245e87  cmp     [rcx+8], r12b
0x180245e8b  jz      short loc_180245EAE
0x180245e8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180245e92  cmp     [rax+7CCh], ebx
0x180245e98  jz      short loc_180245EAE
0x180245e9a  mov     r9d, ebx; int
0x180245e9d  mov     r8d, 7DFh; int
0x180245ea3  mov     rdx, rsi; char *
0x180245ea6  mov     rcx, rax; this
0x180245ea9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180245eae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180245eb5  jb      loc_1802462FB
0x180245ebb  mov     edx, 84h
0x180245ec0  jmp     loc_1802462DD
0x180245ec5  mov     r12d, dword ptr [rbp+Size]
0x180245ec9  lea     eax, [r15+1]
0x180245ecd  imul    eax, r12d
0x180245ed1  mov     ecx, eax; cb
0x180245ed3  mov     [rbp+Size], rax
0x180245ed7  call    cs:__imp_CoTaskMemAlloc
0x180245ede  nop     dword ptr [rax+rax+00h]
0x180245ee3  mov     rbx, rax
0x180245ee6  test    rax, rax
0x180245ee9  jnz     loc_180245F86
0x180245eef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245ef6  mov     ebx, 8007000Eh
0x180245efb  test    rcx, rcx
0x180245efe  jnz     short loc_180245F48
0x180245f00  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180245f07  nop     dword ptr [rax+rax+00h]
0x180245f0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180245f13  mov     rcx, rax
0x180245f16  test    rax, rax
0x180245f19  jz      short loc_180245F3A
0x180245f1b  mov     rax, [rax]
0x180245f1e  mov     edx, 7F0h
0x180245f23  mov     rax, [rax+8]
0x180245f27  call    cs:__guard_dispatch_icall_fptr
0x180245f2d  test    eax, eax
0x180245f2f  jz      short loc_180245F3A
0x180245f31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180245f38  jmp     short loc_180245F48
0x180245f3a  lea     rcx, qword_1803CE250; this
0x180245f41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180245f48  cmp     byte ptr [rcx+8], 0
0x180245f4c  jz      short loc_180245F6F
0x180245f4e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180245f53  cmp     [rax+7CCh], ebx
0x180245f59  jz      short loc_180245F6F
0x180245f5b  mov     r9d, ebx; int
0x180245f5e  mov     r8d, 7E5h; int
0x180245f64  mov     rdx, rsi; char *
0x180245f67  mov     rcx, rax; this
0x180245f6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180245f6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180245f76  jb      loc_1802462FB
0x180245f7c  mov     edx, 85h
0x180245f81  jmp     loc_1802462DD
0x180245f86  mov     r8, [rbp+Size]; Size
0x180245f8a  xor     edx, edx; Val
0x180245f8c  mov     rcx, rbx; void *
0x180245f8f  call    memset_0
0x180245f94  test    r13d, r13d
0x180245f97  jz      short loc_180245FAB
0x180245f99  mov     rdx, [r14]; Src
0x180245f9c  mov     r8d, r13d
0x180245f9f  imul    r8d, r12d; Size
0x180245fa3  mov     rcx, rbx; void *
0x180245fa6  call    memcpy_0
0x180245fab  cmp     r15d, r13d
0x180245fae  jbe     short loc_180245FD4
0x180245fb0  sub     r15d, r13d
0x180245fb3  lea     ecx, [r13+1]
0x180245fb7  mov     edx, r13d
0x180245fba  imul    r15d, r12d
0x180245fbe  imul    edx, r12d
0x180245fc2  imul    ecx, r12d
0x180245fc6  mov     r8d, r15d; Size
0x180245fc9  add     rdx, [r14]; Src
0x180245fcc  add     rcx, rbx; void *
0x180245fcf  call    memcpy_0
0x180245fd4  mov     rcx, [r14]; pv
0x180245fd7  call    cs:__imp_CoTaskMemFree
0x180245fde  nop     dword ptr [rax+rax+00h]
0x180245fe3  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x180245fe7  lea     rcx, [rbp+pvarDest]; pvarDest
0x180245feb  inc     dword ptr [rdi+8]
0x180245fee  xor     r15d, r15d
0x180245ff1  mov     [r14], rbx
0x180245ff4  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180245ff9  mov     ebx, eax
0x180245ffb  test    eax, eax
0x180245ffd  jns     loc_180246095
0x180246003  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18024600a  test    rcx, rcx
0x18024600d  jnz     short loc_180246057
0x18024600f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180246016  nop     dword ptr [rax+rax+00h]
0x18024601b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180246022  mov     rcx, rax
0x180246025  test    rax, rax
0x180246028  jz      short loc_180246049
0x18024602a  mov     rax, [rax]
0x18024602d  mov     edx, 7F0h
0x180246032  mov     rax, [rax+8]
0x180246036  call    cs:__guard_dispatch_icall_fptr
0x18024603c  test    eax, eax
0x18024603e  jz      short loc_180246049
0x180246040  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180246047  jmp     short loc_180246057
0x180246049  lea     rcx, qword_1803CE250; this
0x180246050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180246057  cmp     [rcx+8], r15b
0x18024605b  jz      short loc_18024607E
0x18024605d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180246062  cmp     [rax+7CCh], ebx
0x180246068  jz      short loc_18024607E
0x18024606a  mov     r9d, ebx; int
0x18024606d  mov     r8d, 814h; int
0x180246073  mov     rdx, rsi; char *
0x180246076  mov     rcx, rax; this
0x180246079  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18024607e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180246085  jb      loc_1802462FB
0x18024608b  mov     edx, 86h
0x180246090  jmp     loc_1802462DD
0x180246095  movzx   eax, word ptr [rdi]
0x180246098  mov     r14d, 0FFFh
0x18024609e  and     ax, r14w
0x1802460a2  mov     r12d, 0Ch
  ... truncated ...
```
