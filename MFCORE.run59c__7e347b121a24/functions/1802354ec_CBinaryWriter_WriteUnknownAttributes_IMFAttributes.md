# CBinaryWriter::WriteUnknownAttributes(IMFAttributes *)

- ea: `0x1802354ec`
- end: `0x180235d1f`
- name: `?WriteUnknownAttributes@CBinaryWriter@@QEAAJPEAUIMFAttributes@@@Z`
- size: `2099`
- prototype: `__int64 __fastcall(CBinaryWriter *__hidden this, struct IMFAttributes *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180191ee0`
- `0x1802d5ed0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x18012649c`
- `0x1802354ec`
- `0x180258390`
- `0x180258480`
- `0x180325914`
- `0x180325ef0`
- `0x180326934`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235580`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235651`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235788`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18023581e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802358c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235a2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235af4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235b8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235c20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235580`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235651`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235788`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18023581e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802358c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235a2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235af4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235b8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180235c20`

## string_xrefs

- `0x180235517`: `CBinaryWriter::WriteUnknownAttributes`
- `0x1802357e6`: `CBinaryWriter::WriteUnknownAttributes`
- `0x18023587c`: `CBinaryWriter::WriteUnknownAttributes`
- `0x180235926`: `CBinaryWriter::WriteUnknownAttributes`
- `0x180235abc`: `CBinaryWriter::WriteUnknownAttributes`
- `0x180235b52`: `CBinaryWriter::WriteUnknownAttributes`
- `0x180235be8`: `CBinaryWriter::WriteUnknownAttributes`
- `0x180235c7e`: `CBinaryWriter::WriteUnknownAttributes`

## pseudocode

```c
__int64 __fastcall CBinaryWriter::WriteUnknownAttributes(CBinaryWriter *this, struct IMFAttributes *a2)
{
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *LockStore)(IMFAttributes *); // rax
  struct _GUID *v6; // r13
  unsigned int v7; // esi
  __int64 v8; // rdx
  int Guid; // ebx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  unsigned int i; // r14d
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  unsigned int j; // r14d
  struct IMFAttributesVtbl *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  int (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r8
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  char v62[8]; // [rsp+30h] [rbp-50h] BYREF
  LPUNKNOWN pUnk; // [rsp+38h] [rbp-48h] BYREF
  __int64 v64; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v65; // [rsp+48h] [rbp-38h] BYREF
  int v66; // [rsp+4Ch] [rbp-34h] BYREF
  struct _GUID *v67; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v68; // [rsp+58h] [rbp-28h]
  __int64 v69; // [rsp+5Ch] [rbp-24h]
  struct _GUID v70; // [rsp+68h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v62, "CBinaryWriter::WriteUnknownAttributes", 179);
  lpVtbl = a2->lpVtbl;
  v65 = 0;
  v66 = 0;
  v70 = 0;
  LockStore = lpVtbl->LockStore;
  v6 = 0;
  v67 = 0;
  v7 = 0;
  v69 = 0;
  v68 = 0;
  Guid = ((__int64 (__fastcall *)(struct IMFAttributes *))LockStore)(a2);
  if ( Guid >= 0 )
  {
    Guid = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v65);
    if ( Guid >= 0 )
    {
      for ( i = 0; i < v65; ++i )
      {
        Guid = ((__int64 (__fastcall *)(struct IMFAttributes *, _QWORD, struct _GUID *, _QWORD))a2->lpVtbl->GetItemByIndex)(
                 a2,
                 i,
                 &v70,
                 0);
        if ( Guid < 0 )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != Guid )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CBinaryWriter::WriteUnknownAttributes", 204, Guid);
          }
          if ( g_wppLevels )
          {
            v19 = 25;
            goto LABEL_23;
          }
          goto LABEL_115;
        }
        Guid = ((__int64 (__fastcall *)(struct IMFAttributes *, struct _GUID *, int *))a2->lpVtbl->GetItemType)(
                 a2,
                 &v70,
                 &v66);
        if ( Guid < 0 )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
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
            if ( *((_DWORD *)v28 + 499) != Guid )
              CallStackContext::TraceFailure(v28, "CBinaryWriter::WriteUnknownAttributes", 206, Guid);
          }
          if ( g_wppLevels )
          {
            v19 = 26;
            goto LABEL_23;
          }
          goto LABEL_115;
        }
        if ( v66 == 13 )
        {
          v25 = CTEntryArray<_GUID>::SetSize(&v67, v7 + 1);
          v6 = v67;
          if ( v25 )
            v67[v7] = v70;
          v7 = v68;
        }
      }
      Guid = CBinaryWriter::WriteBool(this, v7);
      if ( Guid >= 0 )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= v7 )
            goto LABEL_115;
          v38 = a2->lpVtbl;
          pUnk = 0;
          v64 = 0;
          Guid = ((__int64 (__fastcall *)(struct IMFAttributes *, struct _GUID *, GUID *, LPUNKNOWN *))v38->GetUnknown)(
                   a2,
                   &v6[j],
                   &IID_IUnknown,
                   &pUnk);
          if ( Guid < 0 )
            break;
          Guid = CBinaryReader::ReadGuid(this, &v6[j]);
          if ( Guid < 0 )
          {
            v55 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42);
              CallStackTracing::s_wpInstance = v56;
              if ( v56
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
              {
                v55 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v55 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v55 + 8) )
            {
              v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
              if ( *((_DWORD *)v57 + 499) != Guid )
                CallStackContext::TraceFailure(v57, "CBinaryWriter::WriteUnknownAttributes", 223, Guid);
            }
            if ( !g_wppLevels )
              goto LABEL_114;
            v51 = 29;
            goto LABEL_113;
          }
          if ( (*(__int64 (__fastcall **)(CBinaryWriter *))(*(_QWORD *)this + 8LL))(this)
            && (v43 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(CBinaryWriter *))(*(_QWORD *)this + 8LL))(this),
                (**v43)(v43, &IID_IMFObjectReferenceStream, &v64) >= 0) )
          {
            Guid = (*(__int64 (__fastcall **)(__int64, GUID *, LPUNKNOWN))(*(_QWORD *)v64 + 24LL))(
                     v64,
                     &IID_IUnknown,
                     pUnk);
            if ( Guid < 0 )
            {
              v46 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45);
                CallStackTracing::s_wpInstance = v47;
                if ( v47
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                {
                  v46 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v46 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v46 + 8) )
              {
                v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                if ( *((_DWORD *)v50 + 499) != Guid )
                  CallStackContext::TraceFailure(v50, "CBinaryWriter::WriteUnknownAttributes", 230, Guid);
              }
              if ( g_wppLevels )
              {
                v51 = 30;
                goto LABEL_113;
              }
              goto LABEL_114;
            }
          }
          else
          {
            Guid = CDCOMInterfaceMashallerHelper::MarshalInterface(this, &IID_IUnknown, pUnk);
            if ( Guid < 0 )
            {
              v52 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48, v49);
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
                if ( *((_DWORD *)v54 + 499) != Guid )
                  CallStackContext::TraceFailure(v54, "CBinaryWriter::WriteUnknownAttributes", 234, Guid);
              }
              if ( g_wppLevels )
              {
                v51 = 31;
                goto LABEL_113;
              }
LABEL_114:
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&pUnk);
              goto LABEL_115;
            }
          }
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&pUnk);
        }
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40);
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( *((_DWORD *)v60 + 499) != Guid )
            CallStackContext::TraceFailure(v60, "CBinaryWriter::WriteUnknownAttributes", 221, Guid);
        }
        if ( !g_wppLevels )
          goto LABEL_114;
        v51 = 28;
LABEL_113:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v51,
          &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
          this,
          Guid);
        goto LABEL_114;
      }
      v34 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v36 + 499) != Guid )
          CallStackContext::TraceFailure(v36, "CBinaryWriter::WriteUnknownAttributes", 214, Guid);
      }
      if ( g_wppLevels )
      {
        v19 = 27;
        goto LABEL_23;
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15);
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
        if ( *((_DWORD *)v18 + 499) != Guid )
          CallStackContext::TraceFailure(v18, "CBinaryWriter::WriteUnknownAttributes", 197, Guid);
      }
      if ( g_wppLevels )
      {
        v19 = 24;
LABEL_23:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids,
          this,
          Guid);
      }
    }
LABEL_115:
    ((void (__fastcall *)(struct IMFAttributes *))a2->lpVtbl->UnlockStore)(a2);
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != Guid )
        CallStackContext::TraceFailure(v13, "CBinaryWriter::WriteUnknownAttributes", 189, Guid);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids, this, Guid);
  }
  operator delete(v6);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v62);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1802354ec  mov     [rsp-38h+arg_10], rbx
0x1802354f1  push    rbp
0x1802354f2  push    rsi
0x1802354f3  push    rdi
0x1802354f4  push    r12
0x1802354f6  push    r13
0x1802354f8  push    r14
0x1802354fa  push    r15
0x1802354fc  mov     rbp, rsp
0x1802354ff  sub     rsp, 80h
0x180235506  mov     rax, cs:__security_cookie
0x18023550d  xor     rax, rsp
0x180235510  mov     [rbp+var_8], rax
0x180235514  mov     r15, rdx
0x180235517  lea     r14, aCbinarywriterW_0; "CBinaryWriter::WriteUnknownAttributes"
0x18023551e  mov     rdi, rcx
0x180235521  mov     rdx, r14; char *
0x180235524  mov     r8d, 0B3h; int
0x18023552a  lea     rcx, [rbp+var_50]; this
0x18023552e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180235533  mov     rax, [r15]
0x180235536  xor     r12d, r12d
0x180235539  xorps   xmm0, xmm0
0x18023553c  mov     [rbp+var_38], r12d
0x180235540  mov     rcx, r15
0x180235543  mov     [rbp+var_34], r12d
0x180235547  movups  [rbp+var_18], xmm0
0x18023554b  mov     rax, [rax+0E0h]
0x180235552  mov     r13d, r12d
0x180235555  mov     [rbp+var_30], r12
0x180235559  mov     esi, r12d
0x18023555c  mov     [rbp+var_24], r12
0x180235560  mov     [rbp+var_28], r12d
0x180235564  call    cs:__guard_dispatch_icall_fptr
0x18023556a  mov     ebx, eax
0x18023556c  test    eax, eax
0x18023556e  jns     loc_180235624
0x180235574  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023557b  test    rcx, rcx
0x18023557e  jnz     short loc_1802355C8
0x180235580  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180235587  nop     dword ptr [rax+rax+00h]
0x18023558c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180235593  mov     rcx, rax
0x180235596  test    rax, rax
0x180235599  jz      short loc_1802355BA
0x18023559b  mov     rax, [rax]
0x18023559e  mov     edx, 7F0h
0x1802355a3  mov     rax, [rax+8]
0x1802355a7  call    cs:__guard_dispatch_icall_fptr
0x1802355ad  test    eax, eax
0x1802355af  jz      short loc_1802355BA
0x1802355b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802355b8  jmp     short loc_1802355C8
0x1802355ba  lea     rcx, qword_1803CE250; this
0x1802355c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802355c8  cmp     [rcx+8], r12b
0x1802355cc  jz      short loc_1802355EF
0x1802355ce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802355d3  cmp     [rax+7CCh], ebx
0x1802355d9  jz      short loc_1802355EF
0x1802355db  mov     r9d, ebx; int
0x1802355de  mov     r8d, 0BDh; int
0x1802355e4  mov     rdx, r14; char *
0x1802355e7  mov     rcx, rax; this
0x1802355ea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802355ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802355f6  jb      loc_180235CE4
0x1802355fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180235603  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x18023560a  mov     edx, 17h
0x18023560f  mov     [rsp+80h+var_60], ebx
0x180235613  mov     r9, rdi
0x180235616  mov     rcx, [rcx+10h]
0x18023561a  call    WPP_SF_qD
0x18023561f  jmp     loc_180235CE4
0x180235624  mov     rax, [r15]
0x180235627  lea     rdx, [rbp+var_38]
0x18023562b  mov     rcx, r15
0x18023562e  mov     rax, [rax+0F0h]
0x180235635  call    cs:__guard_dispatch_icall_fptr
0x18023563b  mov     ebx, eax
0x18023563d  test    eax, eax
0x18023563f  jns     loc_1802356F5
0x180235645  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18023564c  test    rcx, rcx
0x18023564f  jnz     short loc_180235699
0x180235651  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180235658  nop     dword ptr [rax+rax+00h]
0x18023565d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180235664  mov     rcx, rax
0x180235667  test    rax, rax
0x18023566a  jz      short loc_18023568B
0x18023566c  mov     rax, [rax]
0x18023566f  mov     edx, 7F0h
0x180235674  mov     rax, [rax+8]
0x180235678  call    cs:__guard_dispatch_icall_fptr
0x18023567e  test    eax, eax
0x180235680  jz      short loc_18023568B
0x180235682  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180235689  jmp     short loc_180235699
0x18023568b  lea     rcx, qword_1803CE250; this
0x180235692  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180235699  cmp     [rcx+8], r12b
0x18023569d  jz      short loc_1802356C0
0x18023569f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802356a4  cmp     [rax+7CCh], ebx
0x1802356aa  jz      short loc_1802356C0
0x1802356ac  mov     r9d, ebx; int
0x1802356af  mov     r8d, 0C5h; int
0x1802356b5  mov     rdx, r14; char *
0x1802356b8  mov     rcx, rax; this
0x1802356bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802356c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802356c7  jb      loc_180235CD1
0x1802356cd  mov     edx, 18h
0x1802356d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1802356d9  lea     r8, WPP_9f8a26c46d5635c487300a376c0e4004_Traceguids
0x1802356e0  mov     r9, rdi
0x1802356e3  mov     [rsp+80h+var_60], ebx
0x1802356e7  mov     rcx, [rcx+10h]
0x1802356eb  call    WPP_SF_qD
0x1802356f0  jmp     loc_180235CD1
0x1802356f5  mov     r14d, r12d
0x1802356f8  cmp     r14d, [rbp+var_38]
0x1802356fc  jnb     loc_1802358A8
0x180235702  mov     rax, [r15]
0x180235705  lea     r8, [rbp+var_18]
0x180235709  xor     r9d, r9d
0x18023570c  mov     edx, r14d
0x18023570f  mov     rcx, r15
0x180235712  mov     rax, [rax+0F8h]
0x180235719  call    cs:__guard_dispatch_icall_fptr
0x18023571f  mov     ebx, eax
0x180235721  test    eax, eax
0x180235723  js      loc_180235812
0x180235729  mov     rax, [r15]
0x18023572c  lea     r8, [rbp+var_34]
0x180235730  lea     rdx, [rbp+var_18]
0x180235734  mov     rcx, r15
0x180235737  mov     rax, [rax+20h]
0x18023573b  call    cs:__guard_dispatch_icall_fptr
0x180235741  mov     ebx, eax
0x180235743  test    eax, eax
0x180235745  js      short loc_18023577C
0x180235747  cmp     [rbp+var_34], 0Dh
0x18023574b  jnz     short loc_180235774
0x18023574d  lea     edx, [rsi+1]
0x180235750  lea     rcx, [rbp+var_30]
0x180235754  call    ?SetSize@?$CTEntryArray@U_GUID@@@@QEAAHKK@Z; CTEntryArray<_GUID>::SetSize(ulong,ulong)
0x180235759  mov     r13, [rbp+var_30]
0x18023575d  test    eax, eax
0x18023575f  jz      short loc_180235771
0x180235761  movups  xmm0, [rbp+var_18]
0x180235765  mov     eax, esi
0x180235767  add     rax, rax
0x18023576a  movdqu  xmmword ptr [r13+rax*8+0], xmm0
0x180235771  mov     esi, [rbp+var_28]
0x180235774  inc     r14d
0x180235777  jmp     loc_1802356F8
0x18023577c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180235783  test    rcx, rcx
0x180235786  jnz     short loc_1802357D0
0x180235788  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18023578f  nop     dword ptr [rax+rax+00h]
0x180235794  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18023579b  mov     rcx, rax
0x18023579e  test    rax, rax
0x1802357a1  jz      short loc_1802357C2
0x1802357a3  mov     rax, [rax]
0x1802357a6  mov     edx, 7F0h
0x1802357ab  mov     rax, [rax+8]
0x1802357af  call    cs:__guard_dispatch_icall_fptr
0x1802357b5  test    eax, eax
0x1802357b7  jz      short loc_1802357C2
0x1802357b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802357c0  jmp     short loc_1802357D0
0x1802357c2  lea     rcx, qword_1803CE250; this
0x1802357c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802357d0  cmp     [rcx+8], r12b
0x1802357d4  jz      short loc_1802357FB
0x1802357d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802357db  cmp     [rax+7CCh], ebx
0x1802357e1  jz      short loc_1802357FB
0x1802357e3  mov     r9d, ebx; int
0x1802357e6  lea     rdx, aCbinarywriterW_0; "CBinaryWriter::WriteUnknownAttributes"
0x1802357ed  mov     r8d, 0CEh; int
0x1802357f3  mov     rcx, rax; this
0x1802357f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802357fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180235802  jb      loc_180235CD1
0x180235808  mov     edx, 1Ah
0x18023580d  jmp     loc_1802356D2
0x180235812  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180235819  test    rcx, rcx
0x18023581c  jnz     short loc_180235866
0x18023581e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180235825  nop     dword ptr [rax+rax+00h]
0x18023582a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180235831  mov     rcx, rax
0x180235834  test    rax, rax
0x180235837  jz      short loc_180235858
0x180235839  mov     rax, [rax]
0x18023583c  mov     edx, 7F0h
0x180235841  mov     rax, [rax+8]
0x180235845  call    cs:__guard_dispatch_icall_fptr
0x18023584b  test    eax, eax
0x18023584d  jz      short loc_180235858
0x18023584f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180235856  jmp     short loc_180235866
0x180235858  lea     rcx, qword_1803CE250; this
0x18023585f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180235866  cmp     [rcx+8], r12b
0x18023586a  jz      short loc_180235891
0x18023586c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180235871  cmp     [rax+7CCh], ebx
0x180235877  jz      short loc_180235891
0x180235879  mov     r9d, ebx; int
0x18023587c  lea     rdx, aCbinarywriterW_0; "CBinaryWriter::WriteUnknownAttributes"
0x180235883  mov     r8d, 0CCh; int
0x180235889  mov     rcx, rax; this
0x18023588c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180235891  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180235898  jb      loc_180235CD1
0x18023589e  mov     edx, 19h
0x1802358a3  jmp     loc_1802356D2
0x1802358a8  mov     edx, esi; int
0x1802358aa  mov     rcx, rdi; this
0x1802358ad  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x1802358b2  mov     ebx, eax
0x1802358b4  test    eax, eax
0x1802358b6  jns     loc_180235952
0x1802358bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802358c3  test    rcx, rcx
0x1802358c6  jnz     short loc_180235910
0x1802358c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802358cf  nop     dword ptr [rax+rax+00h]
0x1802358d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802358db  mov     rcx, rax
0x1802358de  test    rax, rax
0x1802358e1  jz      short loc_180235902
0x1802358e3  mov     rax, [rax]
0x1802358e6  mov     edx, 7F0h
0x1802358eb  mov     rax, [rax+8]
0x1802358ef  call    cs:__guard_dispatch_icall_fptr
0x1802358f5  test    eax, eax
0x1802358f7  jz      short loc_180235902
0x1802358f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180235900  jmp     short loc_180235910
0x180235902  lea     rcx, qword_1803CE250; this
0x180235909  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180235910  cmp     [rcx+8], r12b
0x180235914  jz      short loc_18023593B
0x180235916  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18023591b  cmp     [rax+7CCh], ebx
0x180235921  jz      short loc_18023593B
0x180235923  mov     r9d, ebx; int
0x180235926  lea     rdx, aCbinarywriterW_0; "CBinaryWriter::WriteUnknownAttributes"
0x18023592d  mov     r8d, 0D6h; int
0x180235933  mov     rcx, rax; this
0x180235936  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18023593b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180235942  jb      loc_180235CD1
0x180235948  mov     edx, 1Bh
0x18023594d  jmp     loc_1802356D2
0x180235952  mov     r14d, r12d
0x180235955  cmp     r14d, esi
0x180235958  jnb     loc_180235CD1
0x18023595e  mov     rax, [r15]
0x180235961  lea     r9, [rbp+pUnk]
0x180235965  mov     [rbp+pUnk], r12
0x180235969  lea     r8, IID_IUnknown
0x180235970  mov     [rbp+var_40], r12
0x180235974  mov     rcx, r15
0x180235977  mov     r12d, r14d
0x18023597a  mov     rax, [rax+88h]
0x180235981  shl     r12, 4
0x180235985  add     r12, r13
0x180235988  mov     rdx, r12
0x18023598b  call    cs:__guard_dispatch_icall_fptr
0x180235991  mov     ebx, eax
0x180235993  test    eax, eax
0x180235995  js      loc_180235C14
0x18023599b  mov     rdx, r12; struct _GUID *
0x18023599e  mov     rcx, rdi; this
0x1802359a1  call    ?ReadGuid@CBinaryReader@@QEAAJAEAU_GUID@@@Z; CBinaryReader::ReadGuid(_GUID &)
0x1802359a6  xor     r12d, r12d
0x1802359a9  mov     ebx, eax
0x1802359ab  test    eax, eax
0x1802359ad  js      loc_180235B7E
0x1802359b3  mov     rax, [rdi]
0x1802359b6  mov     rcx, rdi
0x1802359b9  mov     rax, [rax+8]
0x1802359bd  call    cs:__guard_dispatch_icall_fptr
0x1802359c3  test    rax, rax
0x1802359c6  jz      loc_180235A65
0x1802359cc  mov     rax, [rdi]
0x1802359cf  mov     rcx, rdi
0x1802359d2  mov     rax, [rax+8]
0x1802359d6  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
