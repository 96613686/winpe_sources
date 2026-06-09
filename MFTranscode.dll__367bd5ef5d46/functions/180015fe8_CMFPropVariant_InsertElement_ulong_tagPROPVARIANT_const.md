# CMFPropVariant::InsertElement(ulong,tagPROPVARIANT const *)

- ea: `0x180015fe8`
- end: `0x180016717`
- name: `?InsertElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z`
- size: `1839`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011f08`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800085a0`
- `0x1800115b0`
- `0x180015fe8`
- `0x1800174c0`
- `0x180017e20`
- `0x18001a330`
- `0x18001c280`
- `0x18004f410`
- `0x180057904`
- `0x180058310`
- `0x180058610`
- `0x1800588b8`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800163d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800163d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800162e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001607d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016139`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016305`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016407`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800164cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016571`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001607d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016139`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016251`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016305`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016407`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800164cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016571`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016647`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::InsertElement(CMFPropVariant *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int16 v4; // cx
  __int64 v6; // rdx
  __int64 *v7; // rcx
  int VarTypeSize; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CMFPropVariant *v12; // r8
  __int16 v13; // r10
  unsigned int ElementCount; // r15d
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int16 v19; // cx
  __int16 v20; // dx
  const void **v21; // r14
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  int v26; // r12d
  size_t v27; // rcx
  char *v28; // rax
  __int64 v29; // rdx
  char *v30; // rbx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  PROPVARIANT *v34; // rdx
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  const void *p_pvarDest; // r8
  __int64 v40; // rdx
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  char v53[8]; // [rsp+30h] [rbp-40h] BYREF
  size_t Size; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+48h] [rbp-28h]
  PROPVARIANT pvarDest; // [rsp+50h] [rbp-20h] BYREF

  pvarSrc = a3;
  LODWORD(Size) = 0;
  v4 = *(_WORD *)this;
  Src = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( (v4 & 0x1000) != 0 || !*(_WORD *)this )
  {
    ElementCount = CMFPropVariant::GetElementCount(this);
    if ( this == v12 )
    {
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1991);
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      VarTypeSize = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::InsertElement", 1991, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 130;
        goto LABEL_106;
      }
    }
    else
    {
      v19 = *(_WORD *)v12;
      if ( !*(_WORD *)v12
        || *(_WORD *)this && (v20 = *(_WORD *)this & 0xFFF, v20 != 12) && (v19 & 0xFFF) != v20
        || ElementCount < a2 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1998);
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        VarTypeSize = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v51, "CMFPropVariant::InsertElement", 1998, -2147024809);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 131;
          goto LABEL_106;
        }
        goto LABEL_107;
      }
      v21 = (const void **)((char *)this + 16);
      if ( !*(_WORD *)this )
      {
        *((_DWORD *)this + 2) = 0;
        *v21 = 0;
        *(_WORD *)this = v13 | v19 & 0xFFF;
      }
      VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, (unsigned int *)&Size);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 2015);
      if ( VarTypeSize >= 0 )
      {
        v26 = Size;
        v27 = (unsigned int)Size * (ElementCount + 1);
        Size = v27;
        v28 = (char *)CoTaskMemAlloc(v27);
        v30 = v28;
        if ( v28 )
        {
          memset_0(v28, 0, Size);
          if ( a2 )
            memcpy_0(v30, *v21, v26 * a2);
          if ( ElementCount > a2 )
            memcpy_0(&v30[v26 * (a2 + 1)], (char *)*v21 + v26 * a2, v26 * (ElementCount - a2));
          CoTaskMemFree((LPVOID)*v21);
          v34 = pvarSrc;
          ++*((_DWORD *)this + 2);
          *v21 = v30;
          VarTypeSize = CMFPropVariant::Copy(&pvarDest, v34);
          if ( VarTypeSize >= 0 )
          {
            if ( (*(_WORD *)this & 0xFFF) == 0xC )
            {
              p_pvarDest = &pvarDest;
            }
            else
            {
              VarTypeSize = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)&pvarDest, 0, &Src);
              if ( VarTypeSize < 0 )
              {
                v41 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40);
                  CallStackTracing::s_wpInstance = v42;
                  if ( v42
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                  {
                    v41 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v41 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v41 + 8) )
                {
                  v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
                  if ( *((_DWORD *)v43 + 499) != VarTypeSize )
                    CallStackContext::TraceFailure(v43, "CMFPropVariant::InsertElement", 2086, VarTypeSize);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v11 = 135;
                  goto LABEL_106;
                }
                goto LABEL_107;
              }
              p_pvarDest = Src;
            }
            VarTypeSize = CMFPropVariant::SetElementData(this, a2, p_pvarDest);
            if ( VarTypeSize >= 0 )
            {
              if ( (*(_WORD *)this & 0xFFF) == 0xC || pvarDest.vt != 72 )
                memset(&pvarDest, 0, sizeof(pvarDest));
            }
            else
            {
              v45 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
                CallStackTracing::s_wpInstance = v46;
                if ( v46
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                {
                  v45 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v45 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v45 + 8) )
              {
                v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                if ( *((_DWORD *)v47 + 499) != VarTypeSize )
                  CallStackContext::TraceFailure(v47, "CMFPropVariant::InsertElement", 2093, VarTypeSize);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v11 = 136;
                goto LABEL_106;
              }
            }
            goto LABEL_107;
          }
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != VarTypeSize )
              CallStackContext::TraceFailure(v38, "CMFPropVariant::InsertElement", 2068, VarTypeSize);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 134;
            goto LABEL_106;
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          VarTypeSize = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v33, "CMFPropVariant::InsertElement", 2021, -2147024882);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v11 = 133;
            goto LABEL_106;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != VarTypeSize )
            CallStackContext::TraceFailure(v25, "CMFPropVariant::InsertElement", 2015, VarTypeSize);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 132;
          goto LABEL_106;
        }
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CMFPropVariant::InsertElement", 1978);
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    VarTypeSize = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -1072875796 )
        CallStackContext::TraceFailure(v10, "CMFPropVariant::InsertElement", 1978, -1072875796);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 129;
LABEL_106:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        VarTypeSize);
    }
  }
LABEL_107:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  CoTaskMemFree(0);
  CMFPropVariant::Clear(&pvarDest);
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x180015fe8  mov     [rsp-38h+arg_18], rbx
0x180015fed  push    rbp
0x180015fee  push    rsi
0x180015fef  push    rdi
0x180015ff0  push    r12
0x180015ff2  push    r13
0x180015ff4  push    r14
0x180015ff6  push    r15
0x180015ff8  mov     rbp, rsp
0x180015ffb  sub     rsp, 70h
0x180015fff  mov     rax, cs:__security_cookie
0x180016006  xor     rax, rsp
0x180016009  mov     [rbp+var_8], rax
0x18001600d  xor     r12d, r12d
0x180016010  mov     [rbp+pvarSrc], r8
0x180016014  mov     rdi, rcx
0x180016017  mov     dword ptr [rbp+Size], r12d
0x18001601b  movzx   ecx, word ptr [rcx]
0x18001601e  xor     eax, eax
0x180016020  mov     r10d, 1000h
0x180016026  mov     [rbp+Src], r12
0x18001602a  and     cx, r10w
0x18001602e  mov     qword ptr [rbp+pvarDest+10h], rax
0x180016032  xorps   xmm0, xmm0
0x180016035  mov     r13d, edx
0x180016038  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18001603c  cmp     r12w, cx
0x180016040  jnz     loc_1800160F8
0x180016046  cmp     r12w, [rdi]
0x18001604a  jz      loc_1800160F8
0x180016050  mov     r14d, 7BAh
0x180016056  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::InsertElement"
0x18001605d  mov     r8d, r14d; int
0x180016060  lea     rcx, [rbp+var_40]; this
0x180016064  mov     rdx, rsi; char *
0x180016067  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001606c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016073  mov     ebx, 0C00D36ECh
0x180016078  test    rcx, rcx
0x18001607b  jnz     short loc_1800160BD
0x18001607d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016083  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001608a  mov     rcx, rax
0x18001608d  test    rax, rax
0x180016090  jz      short loc_1800160AF
0x180016092  mov     rax, [rax]
0x180016095  lea     edx, [r14+36h]
0x180016099  mov     rax, [rax+8]
0x18001609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160a2  test    eax, eax
0x1800160a4  jz      short loc_1800160AF
0x1800160a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800160ad  jmp     short loc_1800160BD
0x1800160af  lea     rcx, qword_180069A90; this
0x1800160b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800160bd  cmp     [rcx+8], r12b
0x1800160c1  jz      short loc_1800160E1
0x1800160c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800160c8  cmp     [rax+7CCh], ebx
0x1800160ce  jz      short loc_1800160E1
0x1800160d0  mov     r9d, ebx; int
0x1800160d3  mov     r8d, r14d; int
0x1800160d6  mov     rdx, rsi; char *
0x1800160d9  mov     rcx, rax; this
0x1800160dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800160e1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800160e6  cmp     al, 1
0x1800160e8  jb      loc_1800166D7
0x1800160ee  mov     edx, 81h
0x1800160f3  jmp     loc_1800166B9
0x1800160f8  mov     rcx, rdi; this
0x1800160fb  call    ?GetElementCount@CMFPropVariant@@QEBAKXZ; CMFPropVariant::GetElementCount(void)
0x180016100  mov     r15d, eax
0x180016103  cmp     rdi, r8
0x180016106  jnz     loc_1800161B4
0x18001610c  mov     r14d, 7C7h
0x180016112  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::InsertElement"
0x180016119  mov     r8d, r14d; int
0x18001611c  lea     rcx, [rbp+var_40]; this
0x180016120  mov     rdx, rsi; char *
0x180016123  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016128  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001612f  mov     ebx, 80004003h
0x180016134  test    rcx, rcx
0x180016137  jnz     short loc_180016179
0x180016139  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001613f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016146  mov     rcx, rax
0x180016149  test    rax, rax
0x18001614c  jz      short loc_18001616B
0x18001614e  mov     rax, [rax]
0x180016151  lea     edx, [r14+29h]
0x180016155  mov     rax, [rax+8]
0x180016159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001615e  test    eax, eax
0x180016160  jz      short loc_18001616B
0x180016162  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016169  jmp     short loc_180016179
0x18001616b  lea     rcx, qword_180069A90; this
0x180016172  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016179  cmp     [rcx+8], r12b
0x18001617d  jz      short loc_18001619D
0x18001617f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016184  cmp     [rax+7CCh], ebx
0x18001618a  jz      short loc_18001619D
0x18001618c  mov     r9d, ebx; int
0x18001618f  mov     r8d, r14d; int
0x180016192  mov     rdx, rsi; char *
0x180016195  mov     rcx, rax; this
0x180016198  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001619d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800161a2  cmp     al, 1
0x1800161a4  jb      loc_1800166D7
0x1800161aa  mov     edx, 82h
0x1800161af  jmp     loc_1800166B9
0x1800161b4  movzx   ecx, word ptr [r8]
0x1800161b8  cmp     r12w, cx
0x1800161bc  jz      loc_18001661A
0x1800161c2  mov     r8d, 0FFFh
0x1800161c8  mov     r9d, 0Ch
0x1800161ce  cmp     r12w, [rdi]
0x1800161d2  jz      short loc_1800161F1
0x1800161d4  movzx   edx, word ptr [rdi]
0x1800161d7  and     dx, r8w
0x1800161db  cmp     r9w, dx
0x1800161df  jz      short loc_1800161F1
0x1800161e1  movzx   eax, cx
0x1800161e4  and     ax, r8w
0x1800161e8  cmp     ax, dx
0x1800161eb  jnz     loc_18001661A
0x1800161f1  cmp     r15d, r13d
0x1800161f4  jb      loc_18001661A
0x1800161fa  lea     r14, [rdi+10h]
0x1800161fe  cmp     r12w, [rdi]
0x180016202  jnz     short loc_180016216
0x180016204  and     cx, r8w
0x180016208  mov     [rdi+8], r12d
0x18001620c  or      cx, r10w
0x180016210  mov     [r14], r12
0x180016213  mov     [rdi], cx
0x180016216  lea     rdx, [rbp+Size]; unsigned int *
0x18001621a  mov     rcx, rdi; struct CMFPropVariant *
0x18001621d  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180016222  lea     rsi, aCmfpropvariant_6; "CMFPropVariant::InsertElement"
0x180016229  mov     r8d, 7DFh; int
0x18001622f  mov     rdx, rsi; char *
0x180016232  lea     rcx, [rbp+var_40]; this
0x180016236  mov     ebx, eax
0x180016238  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001623d  test    ebx, ebx
0x18001623f  jns     loc_1800162D0
0x180016245  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001624c  test    rcx, rcx
0x18001624f  jnz     short loc_180016292
0x180016251  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001625e  mov     rcx, rax
0x180016261  test    rax, rax
0x180016264  jz      short loc_180016284
0x180016266  mov     rax, [rax]
0x180016269  mov     edx, 7F0h
0x18001626e  mov     rax, [rax+8]
0x180016272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016277  test    eax, eax
0x180016279  jz      short loc_180016284
0x18001627b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016282  jmp     short loc_180016292
0x180016284  lea     rcx, qword_180069A90; this
0x18001628b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016292  cmp     [rcx+8], r12b
0x180016296  jz      short loc_1800162B9
0x180016298  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001629d  cmp     [rax+7CCh], ebx
0x1800162a3  jz      short loc_1800162B9
0x1800162a5  mov     r9d, ebx; int
0x1800162a8  mov     r8d, 7DFh; int
0x1800162ae  mov     rdx, rsi; char *
0x1800162b1  mov     rcx, rax; this
0x1800162b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800162b9  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800162be  cmp     al, 1
0x1800162c0  jb      loc_1800166D7
0x1800162c6  mov     edx, 84h
0x1800162cb  jmp     loc_1800166B9
0x1800162d0  mov     r12d, dword ptr [rbp+Size]
0x1800162d4  lea     eax, [r15+1]
0x1800162d8  imul    eax, r12d
0x1800162dc  mov     ecx, eax; cb
0x1800162de  mov     [rbp+Size], rax
0x1800162e2  call    cs:__imp_CoTaskMemAlloc
0x1800162e8  mov     rbx, rax
0x1800162eb  test    rax, rax
0x1800162ee  jnz     loc_180016384
0x1800162f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800162fb  mov     ebx, 8007000Eh
0x180016300  test    rcx, rcx
0x180016303  jnz     short loc_180016346
0x180016305  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001630b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016312  mov     rcx, rax
0x180016315  test    rax, rax
0x180016318  jz      short loc_180016338
0x18001631a  mov     rax, [rax]
0x18001631d  mov     edx, 7F0h
0x180016322  mov     rax, [rax+8]
0x180016326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001632b  test    eax, eax
0x18001632d  jz      short loc_180016338
0x18001632f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016336  jmp     short loc_180016346
0x180016338  lea     rcx, qword_180069A90; this
0x18001633f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016346  cmp     byte ptr [rcx+8], 0
0x18001634a  jz      short loc_18001636D
0x18001634c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016351  cmp     [rax+7CCh], ebx
0x180016357  jz      short loc_18001636D
0x180016359  mov     r9d, ebx; int
0x18001635c  mov     r8d, 7E5h; int
0x180016362  mov     rdx, rsi; char *
0x180016365  mov     rcx, rax; this
0x180016368  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001636d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016372  cmp     al, 1
0x180016374  jb      loc_1800166D7
0x18001637a  mov     edx, 85h
0x18001637f  jmp     loc_1800166B9
0x180016384  mov     r8, [rbp+Size]; Size
0x180016388  xor     edx, edx; Val
0x18001638a  mov     rcx, rbx; void *
0x18001638d  call    memset_0
0x180016392  test    r13d, r13d
0x180016395  jz      short loc_1800163A9
0x180016397  mov     rdx, [r14]; Src
0x18001639a  mov     r8d, r13d
0x18001639d  imul    r8d, r12d; Size
0x1800163a1  mov     rcx, rbx; void *
0x1800163a4  call    memcpy_0
0x1800163a9  cmp     r15d, r13d
0x1800163ac  jbe     short loc_1800163D2
0x1800163ae  sub     r15d, r13d
0x1800163b1  lea     ecx, [r13+1]
0x1800163b5  mov     edx, r13d
0x1800163b8  imul    r15d, r12d
0x1800163bc  imul    edx, r12d
0x1800163c0  imul    ecx, r12d
0x1800163c4  mov     r8d, r15d; Size
0x1800163c7  add     rdx, [r14]; Src
0x1800163ca  add     rcx, rbx; void *
0x1800163cd  call    memcpy_0
0x1800163d2  mov     rcx, [r14]; pv
0x1800163d5  call    cs:__imp_CoTaskMemFree
0x1800163db  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x1800163df  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800163e3  inc     dword ptr [rdi+8]
0x1800163e6  xor     r15d, r15d
0x1800163e9  mov     [r14], rbx
0x1800163ec  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x1800163f1  mov     ebx, eax
0x1800163f3  test    eax, eax
0x1800163f5  jns     loc_180016486
0x1800163fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016402  test    rcx, rcx
0x180016405  jnz     short loc_180016448
0x180016407  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001640d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016414  mov     rcx, rax
0x180016417  test    rax, rax
0x18001641a  jz      short loc_18001643A
0x18001641c  mov     rax, [rax]
0x18001641f  mov     edx, 7F0h
0x180016424  mov     rax, [rax+8]
0x180016428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001642d  test    eax, eax
0x18001642f  jz      short loc_18001643A
0x180016431  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016438  jmp     short loc_180016448
0x18001643a  lea     rcx, qword_180069A90; this
0x180016441  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016448  cmp     [rcx+8], r15b
0x18001644c  jz      short loc_18001646F
0x18001644e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016453  cmp     [rax+7CCh], ebx
0x180016459  jz      short loc_18001646F
0x18001645b  mov     r9d, ebx; int
0x18001645e  mov     r8d, 814h; int
0x180016464  mov     rdx, rsi; char *
0x180016467  mov     rcx, rax; this
0x18001646a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001646f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016474  cmp     al, 1
0x180016476  jb      loc_1800166D7
0x18001647c  mov     edx, 86h
0x180016481  jmp     loc_1800166B9
0x180016486  movzx   eax, word ptr [rdi]
0x180016489  mov     r14d, 0FFFh
0x18001648f  and     ax, r14w
0x180016493  mov     r12d, 0Ch
0x180016499  cmp     r12w, ax
0x18001649d  jnz     short loc_1800164A8
  ... truncated ...
```
