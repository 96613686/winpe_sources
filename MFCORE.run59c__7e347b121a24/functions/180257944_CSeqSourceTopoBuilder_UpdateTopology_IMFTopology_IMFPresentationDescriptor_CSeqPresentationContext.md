# CSeqSourceTopoBuilder::UpdateTopology(IMFTopology *,IMFPresentationDescriptor *,CSeqPresentationContext *)

- ea: `0x180257944`
- end: `0x18025829a`
- name: `?UpdateTopology@CSeqSourceTopoBuilder@@QEAAJPEAUIMFTopology@@PEAUIMFPresentationDescriptor@@PEAVCSeqPresentationContext@@@Z`
- size: `2390`
- prototype: `__int64 __fastcall(CSeqSourceTopoBuilder *__hidden this, struct IMFTopology *, struct IMFPresentationDescriptor *, struct CSeqPresentationContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801a43fc`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x180067eec`
- `0x1800953e4`
- `0x1800ec0e0`
- `0x1801d2aac`
- `0x180257944`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802579d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257a84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257ccb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257d61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257df7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257e8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257f23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257fb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025804f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802580e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025817b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802579d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257a84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257ccb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257d61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257df7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257e8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257f23`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180257fb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025804f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802580e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18025817b`

## string_xrefs

- `0x18025795b`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180257d29`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180257dbf`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180257e55`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180257eeb`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180257f81`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180258017`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x1802580ad`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x180258143`: `CSeqSourceTopoBuilder::UpdateTopology`
- `0x1802581d9`: `CSeqSourceTopoBuilder::UpdateTopology`

## pseudocode

```c
__int64 __fastcall CSeqSourceTopoBuilder::UpdateTopology(
        CSeqSourceTopoBuilder *this,
        struct IMFTopology *a2,
        struct IMFPresentationDescriptor *a3,
        struct CSeqPresentationContext *a4)
{
  __int64 v8; // rdx
  int NewSD; // ebx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned int i; // esi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
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
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  unsigned int v67; // [rsp+30h] [rbp-48h] BYREF
  __int64 v68; // [rsp+38h] [rbp-40h] BYREF
  __int64 v69; // [rsp+40h] [rbp-38h] BYREF
  struct IMFStreamDescriptor *v70; // [rsp+48h] [rbp-30h] BYREF
  struct IMFStreamDescriptor *v71; // [rsp+50h] [rbp-28h] BYREF
  struct IMFMediaSource *v72; // [rsp+58h] [rbp-20h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-18h] BYREF
  _QWORD v74[2]; // [rsp+68h] [rbp-10h] BYREF
  char v75; // [rsp+C8h] [rbp+50h] BYREF

  v74[0] = 0;
  v73 = 0;
  v68 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v69 = 0;
  v67 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v75, "CSeqSourceTopoBuilder::UpdateTopology", 111);
  NewSD = ((__int64 (__fastcall *)(struct IMFTopology *, _QWORD *))a2->lpVtbl->GetSourceNodeCollection)(a2, v74);
  if ( NewSD < 0 )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != NewSD )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSeqSourceTopoBuilder::UpdateTopology", 111, NewSD);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v14 = 15;
LABEL_125:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_263c1318004232a04081619c54e6cc2d_Traceguids, this, NewSD);
LABEL_126:
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, &WPP_263c1318004232a04081619c54e6cc2d_Traceguids, this, NewSD);
    goto LABEL_128;
  }
  NewSD = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v74[0] + 24LL))(v74[0], &v67);
  if ( NewSD < 0 )
  {
    v17 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != NewSD )
        CallStackContext::TraceFailure(v19, "CSeqSourceTopoBuilder::UpdateTopology", 113, NewSD);
    }
    if ( !g_wppLevels )
      goto LABEL_126;
    v14 = 16;
    goto LABEL_125;
  }
  for ( i = 0; i < v67; ++i )
  {
    ComSmartPtr<CPMPStreamStub>::operator=(&v73, 0);
    NewSD = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v74[0] + 32LL))(v74[0], i, &v73);
    if ( NewSD < 0 )
    {
      v63 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != NewSD )
          CallStackContext::TraceFailure(v65, "CSeqSourceTopoBuilder::UpdateTopology", 118, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 17;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ComSmartPtr<CPMPStreamStub>::operator=(&v68, 0);
    NewSD = (**v73)(v73, &IID_IMFTopologyNode, &v68);
    if ( NewSD < 0 )
    {
      v60 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
        CallStackTracing::s_wpInstance = v61;
        if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
        {
          v60 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v60 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v60 + 8) )
      {
        v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
        if ( *((_DWORD *)v62 + 499) != NewSD )
          CallStackContext::TraceFailure(v62, "CSeqSourceTopoBuilder::UpdateTopology", 122, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 18;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ComSmartPtr<IMFStreamDescriptor>::operator=(&v72);
    NewSD = (*(__int64 (__fastcall **)(__int64, const IID *, GUID *, struct IMFMediaSource **))(*(_QWORD *)v68 + 136LL))(
              v68,
              &MF_TOPONODE_SOURCE,
              &IID_IMFMediaSource,
              &v72);
    if ( NewSD < 0 )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
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
        if ( *((_DWORD *)v59 + 499) != NewSD )
          CallStackContext::TraceFailure(v59, "CSeqSourceTopoBuilder::UpdateTopology", 127, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 19;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ComSmartPtr<IMFStreamDescriptor>::operator=(&v71);
    NewSD = (*(__int64 (__fastcall **)(__int64, const IID *, GUID *, struct IMFStreamDescriptor **))(*(_QWORD *)v68 + 136LL))(
              v68,
              &MF_TOPONODE_STREAM_DESCRIPTOR,
              &IID_IMFStreamDescriptor,
              &v71);
    if ( NewSD < 0 )
    {
      v54 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
        CallStackTracing::s_wpInstance = v55;
        if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v54 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v54 + 8) )
      {
        v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
        if ( *((_DWORD *)v56 + 499) != NewSD )
          CallStackContext::TraceFailure(v56, "CSeqSourceTopoBuilder::UpdateTopology", 132, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 20;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ComSmartPtr<IMFStreamDescriptor>::operator=(&v70);
    NewSD = CSeqSourceTopoBuilder::FindNewSD(this, a4, v72, v71, &v70);
    if ( NewSD < 0 )
    {
      v51 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
        CallStackTracing::s_wpInstance = v52;
        if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
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
        v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
        if ( *((_DWORD *)v53 + 499) != NewSD )
          CallStackContext::TraceFailure(v53, "CSeqSourceTopoBuilder::UpdateTopology", 138, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 21;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    ComSmartPtr<CPMPStreamStub>::operator=(&v69, 0);
    NewSD = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this)(*(_QWORD *)this, &IID_IUnknown, &v69);
    if ( NewSD < 0 )
    {
      v48 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
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
        if ( *((_DWORD *)v50 + 499) != NewSD )
          CallStackContext::TraceFailure(v50, "CSeqSourceTopoBuilder::UpdateTopology", 143, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 22;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    NewSD = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v68 + 216LL))(
              v68,
              &MF_TOPONODE_SOURCE,
              v69);
    if ( NewSD < 0 )
    {
      v45 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
        CallStackTracing::s_wpInstance = v46;
        if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
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
        if ( *((_DWORD *)v47 + 499) != NewSD )
          CallStackContext::TraceFailure(v47, "CSeqSourceTopoBuilder::UpdateTopology", 146, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 23;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    NewSD = (*(__int64 (__fastcall **)(__int64, const IID *, struct IMFPresentationDescriptor *))(*(_QWORD *)v68 + 216LL))(
              v68,
              &MF_TOPONODE_PRESENTATION_DESCRIPTOR,
              a3);
    if ( NewSD < 0 )
    {
      v42 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
        CallStackTracing::s_wpInstance = v43;
        if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
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
        if ( *((_DWORD *)v44 + 499) != NewSD )
          CallStackContext::TraceFailure(v44, "CSeqSourceTopoBuilder::UpdateTopology", 148, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 24;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
    NewSD = (*(__int64 (__fastcall **)(__int64, const IID *, struct IMFStreamDescriptor *))(*(_QWORD *)v68 + 216LL))(
              v68,
              &MF_TOPONODE_STREAM_DESCRIPTOR,
              v70);
    if ( NewSD < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != NewSD )
          CallStackContext::TraceFailure(v41, "CSeqSourceTopoBuilder::UpdateTopology", 150, NewSD);
      }
      if ( g_wppLevels )
      {
        v14 = 25;
        goto LABEL_125;
      }
      goto LABEL_126;
    }
  }
LABEL_128:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v75);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v69);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v70);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v71);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v72);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v68);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v73);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v74);
  return (unsigned int)NewSD;
}

```

## disassembly

```asm
0x180257944  push    rbp
0x180257946  push    rbx
0x180257947  push    rsi
0x180257948  push    rdi
0x180257949  push    r12
0x18025794b  push    r13
0x18025794d  push    r14
0x18025794f  push    r15
0x180257951  mov     rbp, rsp
0x180257954  sub     rsp, 78h
0x180257958  xor     r12d, r12d
0x18025795b  lea     rsi, aCseqsourcetopo_1; "CSeqSourceTopoBuilder::UpdateTopology"
0x180257962  mov     r15, r8
0x180257965  mov     [rbp+var_10], r12
0x180257969  mov     rbx, rdx
0x18025796c  mov     [rbp+var_18], r12
0x180257970  mov     rdi, rcx
0x180257973  mov     [rbp+var_40], r12
0x180257977  lea     r8d, [r12+6Fh]; int
0x18025797c  mov     [rbp+var_20], r12
0x180257980  mov     rdx, rsi; char *
0x180257983  mov     [rbp+var_28], r12
0x180257987  lea     rcx, [rbp+arg_8]; this
0x18025798b  mov     [rbp+var_30], r12
0x18025798f  mov     r14, r9
0x180257992  mov     [rbp+var_38], r12
0x180257996  mov     [rbp+var_48], r12d
0x18025799a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18025799f  mov     rax, [rbx]
0x1802579a2  lea     rdx, [rbp+var_10]
0x1802579a6  mov     rcx, rbx
0x1802579a9  mov     rax, [rax+148h]
0x1802579b0  call    cs:__guard_dispatch_icall_fptr
0x1802579b6  lea     r13, WPP_263c1318004232a04081619c54e6cc2d_Traceguids
0x1802579bd  mov     ebx, eax
0x1802579bf  test    eax, eax
0x1802579c1  jns     loc_180257A59
0x1802579c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802579ce  test    rcx, rcx
0x1802579d1  jnz     short loc_180257A1B
0x1802579d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802579da  nop     dword ptr [rax+rax+00h]
0x1802579df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802579e6  mov     rcx, rax
0x1802579e9  test    rax, rax
0x1802579ec  jz      short loc_180257A0D
0x1802579ee  mov     rax, [rax]
0x1802579f1  mov     edx, 7F0h
0x1802579f6  mov     rax, [rax+8]
0x1802579fa  call    cs:__guard_dispatch_icall_fptr
0x180257a00  test    eax, eax
0x180257a02  jz      short loc_180257A0D
0x180257a04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257a0b  jmp     short loc_180257A1B
0x180257a0d  lea     rcx, qword_1803CE250; this
0x180257a14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180257a1b  cmp     [rcx+8], r12b
0x180257a1f  jz      short loc_180257A42
0x180257a21  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180257a26  cmp     [rax+7CCh], ebx
0x180257a2c  jz      short loc_180257A42
0x180257a2e  mov     r9d, ebx; int
0x180257a31  mov     r8d, 6Fh ; 'o'; int
0x180257a37  mov     rdx, rsi; char *
0x180257a3a  mov     rcx, rax; this
0x180257a3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180257a42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180257a49  jb      loc_180258216
0x180257a4f  mov     edx, 0Fh
0x180257a54  jmp     loc_1802581FC
0x180257a59  mov     rcx, [rbp+var_10]
0x180257a5d  lea     rdx, [rbp+var_48]
0x180257a61  mov     rax, [rcx]
0x180257a64  mov     rax, [rax+18h]
0x180257a68  call    cs:__guard_dispatch_icall_fptr
0x180257a6e  mov     ebx, eax
0x180257a70  test    eax, eax
0x180257a72  jns     loc_180257B0A
0x180257a78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257a7f  test    rcx, rcx
0x180257a82  jnz     short loc_180257ACC
0x180257a84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180257a8b  nop     dword ptr [rax+rax+00h]
0x180257a90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180257a97  mov     rcx, rax
0x180257a9a  test    rax, rax
0x180257a9d  jz      short loc_180257ABE
0x180257a9f  mov     rax, [rax]
0x180257aa2  mov     edx, 7F0h
0x180257aa7  mov     rax, [rax+8]
0x180257aab  call    cs:__guard_dispatch_icall_fptr
0x180257ab1  test    eax, eax
0x180257ab3  jz      short loc_180257ABE
0x180257ab5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257abc  jmp     short loc_180257ACC
0x180257abe  lea     rcx, qword_1803CE250; this
0x180257ac5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180257acc  cmp     [rcx+8], r12b
0x180257ad0  jz      short loc_180257AF3
0x180257ad2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180257ad7  cmp     [rax+7CCh], ebx
0x180257add  jz      short loc_180257AF3
0x180257adf  mov     r9d, ebx; int
0x180257ae2  mov     r8d, 71h ; 'q'; int
0x180257ae8  mov     rdx, rsi; char *
0x180257aeb  mov     rcx, rax; this
0x180257aee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180257af3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180257afa  jb      loc_180258216
0x180257b00  mov     edx, 10h
0x180257b05  jmp     loc_1802581FC
0x180257b0a  mov     esi, r12d
0x180257b0d  cmp     esi, [rbp+var_48]
0x180257b10  jnb     loc_18025823E
0x180257b16  xor     edx, edx
0x180257b18  lea     rcx, [rbp+var_18]
0x180257b1c  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180257b21  mov     rcx, [rbp+var_10]
0x180257b25  lea     r8, [rbp+var_18]
0x180257b29  mov     edx, esi
0x180257b2b  mov     rax, [rcx]
0x180257b2e  mov     rax, [rax+20h]
0x180257b32  call    cs:__guard_dispatch_icall_fptr
0x180257b38  mov     ebx, eax
0x180257b3a  test    eax, eax
0x180257b3c  js      loc_18025816F
0x180257b42  xor     edx, edx
0x180257b44  lea     rcx, [rbp+var_40]
0x180257b48  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180257b4d  mov     rcx, [rbp+var_18]
0x180257b51  lea     r8, [rbp+var_40]
0x180257b55  lea     rdx, IID_IMFTopologyNode
0x180257b5c  mov     rax, [rcx]
0x180257b5f  mov     rax, [rax]
0x180257b62  call    cs:__guard_dispatch_icall_fptr
0x180257b68  mov     ebx, eax
0x180257b6a  test    eax, eax
0x180257b6c  js      loc_1802580D9
0x180257b72  lea     rcx, [rbp+var_20]
0x180257b76  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x180257b7b  mov     rcx, [rbp+var_40]
0x180257b7f  lea     r9, [rbp+var_20]
0x180257b83  lea     r8, IID_IMFMediaSource
0x180257b8a  lea     rdx, MF_TOPONODE_SOURCE
0x180257b91  mov     rax, [rcx]
0x180257b94  mov     rax, [rax+88h]
0x180257b9b  call    cs:__guard_dispatch_icall_fptr
0x180257ba1  mov     ebx, eax
0x180257ba3  test    eax, eax
0x180257ba5  js      loc_180258043
0x180257bab  lea     rcx, [rbp+var_28]
0x180257baf  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x180257bb4  mov     rcx, [rbp+var_40]
0x180257bb8  lea     r9, [rbp+var_28]
0x180257bbc  lea     r8, IID_IMFStreamDescriptor
0x180257bc3  lea     rdx, MF_TOPONODE_STREAM_DESCRIPTOR
0x180257bca  mov     rax, [rcx]
0x180257bcd  mov     rax, [rax+88h]
0x180257bd4  call    cs:__guard_dispatch_icall_fptr
0x180257bda  mov     ebx, eax
0x180257bdc  test    eax, eax
0x180257bde  js      loc_180257FAD
0x180257be4  lea     rcx, [rbp+var_30]
0x180257be8  call    ??4?$ComSmartPtr@UIMFStreamDescriptor@@@@QEAAPEAUIMFStreamDescriptor@@PEAU1@@Z; ComSmartPtr<IMFStreamDescriptor>::operator=(IMFStreamDescriptor *)
0x180257bed  mov     r9, [rbp+var_28]; struct IMFStreamDescriptor *
0x180257bf1  lea     rax, [rbp+var_30]
0x180257bf5  mov     r8, [rbp+var_20]; struct IMFMediaSource *
0x180257bf9  mov     rdx, r14; struct CSeqPresentationContext *
0x180257bfc  mov     rcx, rdi; this
0x180257bff  mov     [rsp+78h+var_58], rax; struct IMFStreamDescriptor **
0x180257c04  call    ?FindNewSD@CSeqSourceTopoBuilder@@QEAAJPEAVCSeqPresentationContext@@PEAUIMFMediaSource@@PEAUIMFStreamDescriptor@@PEAPEAU4@@Z; CSeqSourceTopoBuilder::FindNewSD(CSeqPresentationContext *,IMFMediaSource *,IMFStreamDescriptor *,IMFStreamDescriptor * *)
0x180257c09  mov     ebx, eax
0x180257c0b  test    eax, eax
0x180257c0d  js      loc_180257F17
0x180257c13  xor     edx, edx
0x180257c15  lea     rcx, [rbp+var_38]
0x180257c19  call    ??4?$ComSmartPtr@VCPMPStreamStub@@@@QEAAPEAVCPMPStreamStub@@PEAV1@@Z; ComSmartPtr<CPMPStreamStub>::operator=(CPMPStreamStub *)
0x180257c1e  mov     rcx, [rdi]
0x180257c21  lea     r8, [rbp+var_38]
0x180257c25  lea     rdx, IID_IUnknown
0x180257c2c  mov     rax, [rcx]
0x180257c2f  mov     rax, [rax]
0x180257c32  call    cs:__guard_dispatch_icall_fptr
0x180257c38  mov     ebx, eax
0x180257c3a  test    eax, eax
0x180257c3c  js      loc_180257E81
0x180257c42  mov     rcx, [rbp+var_40]
0x180257c46  lea     rdx, MF_TOPONODE_SOURCE
0x180257c4d  mov     r8, [rbp+var_38]
0x180257c51  mov     rax, [rcx]
0x180257c54  mov     rax, [rax+0D8h]
0x180257c5b  call    cs:__guard_dispatch_icall_fptr
0x180257c61  mov     ebx, eax
0x180257c63  test    eax, eax
0x180257c65  js      loc_180257DEB
0x180257c6b  mov     rcx, [rbp+var_40]
0x180257c6f  lea     rdx, MF_TOPONODE_PRESENTATION_DESCRIPTOR
0x180257c76  mov     r8, r15
0x180257c79  mov     rax, [rcx]
0x180257c7c  mov     rax, [rax+0D8h]
0x180257c83  call    cs:__guard_dispatch_icall_fptr
0x180257c89  mov     ebx, eax
0x180257c8b  test    eax, eax
0x180257c8d  js      loc_180257D55
0x180257c93  mov     rcx, [rbp+var_40]
0x180257c97  lea     rdx, MF_TOPONODE_STREAM_DESCRIPTOR
0x180257c9e  mov     r8, [rbp+var_30]
0x180257ca2  mov     rax, [rcx]
0x180257ca5  mov     rax, [rax+0D8h]
0x180257cac  call    cs:__guard_dispatch_icall_fptr
0x180257cb2  mov     ebx, eax
0x180257cb4  test    eax, eax
0x180257cb6  js      short loc_180257CBF
0x180257cb8  inc     esi
0x180257cba  jmp     loc_180257B0D
0x180257cbf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257cc6  test    rcx, rcx
0x180257cc9  jnz     short loc_180257D13
0x180257ccb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180257cd2  nop     dword ptr [rax+rax+00h]
0x180257cd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180257cde  mov     rcx, rax
0x180257ce1  test    rax, rax
0x180257ce4  jz      short loc_180257D05
0x180257ce6  mov     rax, [rax]
0x180257ce9  mov     edx, 7F0h
0x180257cee  mov     rax, [rax+8]
0x180257cf2  call    cs:__guard_dispatch_icall_fptr
0x180257cf8  test    eax, eax
0x180257cfa  jz      short loc_180257D05
0x180257cfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257d03  jmp     short loc_180257D13
0x180257d05  lea     rcx, qword_1803CE250; this
0x180257d0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180257d13  cmp     [rcx+8], r12b
0x180257d17  jz      short loc_180257D3E
0x180257d19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180257d1e  cmp     [rax+7CCh], ebx
0x180257d24  jz      short loc_180257D3E
0x180257d26  mov     r9d, ebx; int
0x180257d29  lea     rdx, aCseqsourcetopo_1; "CSeqSourceTopoBuilder::UpdateTopology"
0x180257d30  mov     r8d, 96h; int
0x180257d36  mov     rcx, rax; this
0x180257d39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180257d3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180257d45  jb      loc_180258216
0x180257d4b  mov     edx, 19h
0x180257d50  jmp     loc_1802581FC
0x180257d55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257d5c  test    rcx, rcx
0x180257d5f  jnz     short loc_180257DA9
0x180257d61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180257d68  nop     dword ptr [rax+rax+00h]
0x180257d6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180257d74  mov     rcx, rax
0x180257d77  test    rax, rax
0x180257d7a  jz      short loc_180257D9B
0x180257d7c  mov     rax, [rax]
0x180257d7f  mov     edx, 7F0h
0x180257d84  mov     rax, [rax+8]
0x180257d88  call    cs:__guard_dispatch_icall_fptr
0x180257d8e  test    eax, eax
0x180257d90  jz      short loc_180257D9B
0x180257d92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257d99  jmp     short loc_180257DA9
0x180257d9b  lea     rcx, qword_1803CE250; this
0x180257da2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180257da9  cmp     [rcx+8], r12b
0x180257dad  jz      short loc_180257DD4
0x180257daf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180257db4  cmp     [rax+7CCh], ebx
0x180257dba  jz      short loc_180257DD4
0x180257dbc  mov     r9d, ebx; int
0x180257dbf  lea     rdx, aCseqsourcetopo_1; "CSeqSourceTopoBuilder::UpdateTopology"
0x180257dc6  mov     r8d, 94h; int
0x180257dcc  mov     rcx, rax; this
0x180257dcf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180257dd4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180257ddb  jb      loc_180258216
0x180257de1  mov     edx, 18h
0x180257de6  jmp     loc_1802581FC
0x180257deb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257df2  test    rcx, rcx
0x180257df5  jnz     short loc_180257E3F
0x180257df7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180257dfe  nop     dword ptr [rax+rax+00h]
0x180257e03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180257e0a  mov     rcx, rax
0x180257e0d  test    rax, rax
0x180257e10  jz      short loc_180257E31
0x180257e12  mov     rax, [rax]
0x180257e15  mov     edx, 7F0h
0x180257e1a  mov     rax, [rax+8]
0x180257e1e  call    cs:__guard_dispatch_icall_fptr
0x180257e24  test    eax, eax
0x180257e26  jz      short loc_180257E31
0x180257e28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180257e2f  jmp     short loc_180257E3F
0x180257e31  lea     rcx, qword_1803CE250; this
0x180257e38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
