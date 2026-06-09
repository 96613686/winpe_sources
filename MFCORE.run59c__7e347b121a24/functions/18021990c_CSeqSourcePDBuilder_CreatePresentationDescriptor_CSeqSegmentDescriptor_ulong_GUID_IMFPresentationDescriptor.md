# CSeqSourcePDBuilder::CreatePresentationDescriptor(CSeqSegmentDescriptor *,ulong,_GUID *,IMFPresentationDescriptor * *)

- ea: `0x18021990c`
- end: `0x18021a303`
- name: `?CreatePresentationDescriptor@CSeqSourcePDBuilder@@QEAAJPEAVCSeqSegmentDescriptor@@KPEAU_GUID@@PEAPEAUIMFPresentationDescriptor@@@Z`
- size: `2551`
- prototype: `__int64 __usercall@<rax>(CSeqSourcePDBuilder *__hidden this@<rcx>, struct CSeqSegmentDescriptor *@<rdx>, unsigned int@<r8d>, struct _GUID *@<r9>, struct IMFPresentationDescriptor **)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180129be4`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d16c`
- `0x180050d6c`
- `0x18005a3d4`
- `0x1800ec0e0`
- `0x18016082c`
- `0x18018cdf0`
- `0x1801cecb0`
- `0x1801d9cd8`
- `0x1801f302c`
- `0x1801fa3ac`
- `0x18021990c`
- `0x1802b7058`
- `0x1802b720c`
- `0x1802bb158`
- `0x1802bceb4`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFCreatePresentationDescriptor` at `0x18021a023`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18021a023`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219988`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219a46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219af1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219cbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219de8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219e9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a048`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a12c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219988`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219a46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219af1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219cbc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219d52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219de8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219e9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180219f3a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a048`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a12c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021a210`

## string_xrefs

- `0x180219946`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x180219d1a`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x180219db0`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x180219e46`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x180219efb`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x180219f98`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x18021a0a6`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x18021a18a`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`
- `0x18021a26e`: `CSeqSourcePDBuilder::CreatePresentationDescriptor`

## pseudocode

```c
__int64 __fastcall CSeqSourcePDBuilder::CreatePresentationDescriptor(
        CSeqSourcePDBuilder *this,
        struct CSeqSegmentDescriptor *a2,
        unsigned int a3,
        struct _GUID *a4,
        struct IMFPresentationDescriptor **ppPresentationDescriptor)
{
  struct IUnknown *v5; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v10; // rcx
  HRESULT PDWrap; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // edi
  struct IMFMediaSource *Source; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  struct IUnknown *v29; // r12
  CSeqSourceWrap *SourceWrap; // rax
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
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  DWORD v55; // ebx
  struct IMFPresentationDescriptor **v56; // r12
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  struct CSeqPresentationContext *v62; // rdi
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CSeqPresentationContext *v74; // [rsp+30h] [rbp-40h] BYREF
  __int64 v75; // [rsp+38h] [rbp-38h] BYREF
  __int128 v76; // [rsp+40h] [rbp-30h] BYREF
  IMFStreamDescriptor **apStreamDescriptors; // [rsp+50h] [rbp-20h] BYREF
  DWORD cStreamDescriptors; // [rsp+58h] [rbp-18h]
  __int64 v79; // [rsp+5Ch] [rbp-14h]
  __int64 v80; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v81; // [rsp+C0h] [rbp+50h] BYREF
  struct IUnknown *v82; // [rsp+C8h] [rbp+58h] BYREF

  v81 = a3;
  v5 = 0;
  v74 = 0;
  v82 = 0;
  apStreamDescriptors = 0;
  v79 = 0;
  cStreamDescriptors = 0;
  v80 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v81,
    "CSeqSourcePDBuilder::CreatePresentationDescriptor",
    48);
  if ( *(_QWORD *)this )
  {
    if ( ppPresentationDescriptor )
    {
      PDWrap = CSeqSourcePDBuilder::CreatePresentationContext(this, a2, &v74);
      if ( PDWrap >= 0 )
      {
        v23 = *((_QWORD *)a2 + 7);
        v24 = *((_DWORD *)a2 + 10);
        v25 = 0;
        v80 = v23;
        v81 = v24;
        while ( 1 )
        {
          if ( v25 >= v24 )
          {
            v55 = cStreamDescriptors;
            if ( (unsigned __int8)byte_1803CECE9 >= 8u )
              WPP_SF_qDD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                19,
                &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
                this,
                cStreamDescriptors,
                (int)v23 / 10000);
            v56 = ppPresentationDescriptor;
            PDWrap = MFCreatePresentationDescriptor(v55, apStreamDescriptors, ppPresentationDescriptor);
            if ( PDWrap >= 0 )
            {
              ((void (__fastcall *)(struct IMFPresentationDescriptor *, const IID *, __int64))(*v56)->lpVtbl->SetUINT64)(
                *v56,
                &MF_PD_DURATION,
                v80);
              v62 = v74;
              PDWrap = ((__int64 (__fastcall *)(struct IMFPresentationDescriptor *, __int64, struct CSeqPresentationContext *))(*v56)->lpVtbl->SetUnknown)(
                         *v56,
                         *(_QWORD *)this + 144LL,
                         v74);
              if ( PDWrap >= 0 )
              {
                v75 = 0;
                v82 = 0;
                v76 = 0;
                CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::GetFirstPosition((char *)v62 + 48, &v76);
                while ( (_QWORD)v76 )
                {
                  CTBucketHash<IUnknown *,IUnknown *>::GetNext((char *)v62 + 48, &v76, &v75, &v82);
                  PDWrap = CSeqPDWrap::CopySelectionToPD((CSeqPDWrap *)v82, *v56);
                  if ( PDWrap < 0 )
                  {
                    v70 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69);
                      CallStackTracing::s_wpInstance = v71;
                      if ( v71
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(
                             v71,
                             2032) )
                      {
                        v70 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v70 = &qword_1803CE250;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                      }
                    }
                    if ( *((_BYTE *)v70 + 8) )
                    {
                      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
                      if ( *((_DWORD *)ThreadRelativeContext + 499) != PDWrap )
                        CallStackContext::TraceFailure(
                          ThreadRelativeContext,
                          "CSeqSourcePDBuilder::CreatePresentationDescriptor",
                          136,
                          PDWrap);
                    }
                    if ( g_wppLevels )
                    {
                      v42 = 22;
                      goto LABEL_138;
                    }
                    goto LABEL_139;
                  }
                }
              }
              else
              {
                v65 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63, v64);
                  CallStackTracing::s_wpInstance = v66;
                  if ( v66
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
                  {
                    v65 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v65 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v65 + 8) )
                {
                  v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
                  if ( *((_DWORD *)v67 + 499) != PDWrap )
                    CallStackContext::TraceFailure(
                      v67,
                      "CSeqSourcePDBuilder::CreatePresentationDescriptor",
                      123,
                      PDWrap);
                }
                if ( g_wppLevels )
                {
                  v42 = 21;
                  goto LABEL_138;
                }
              }
            }
            else
            {
              v59 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58);
                CallStackTracing::s_wpInstance = v60;
                if ( v60
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                {
                  v59 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v59 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v59 + 8) )
              {
                v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
                if ( *((_DWORD *)v61 + 499) != PDWrap )
                  CallStackContext::TraceFailure(v61, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 116, PDWrap);
              }
              if ( g_wppLevels )
              {
                v42 = 20;
                goto LABEL_138;
              }
            }
            goto LABEL_139;
          }
          if ( v5 )
          {
            ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
            v5 = 0;
            v82 = 0;
          }
          Source = CSeqSegmentDescriptor::GetSource(a2, v25);
          v29 = (struct IUnknown *)Source;
          if ( !Source )
          {
            v52 = (__int64 *)CallStackTracing::s_wpInstance;
            PDWrap = -1072875845;
            if ( !CallStackTracing::s_wpInstance )
            {
              v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
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
              if ( *((_DWORD *)v54 + 499) != -1072875845 )
                CallStackContext::TraceFailure(
                  v54,
                  "CSeqSourcePDBuilder::CreatePresentationDescriptor",
                  85,
                  -1072875845);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
                this,
                -1072875845);
            goto LABEL_139;
          }
          SourceWrap = CSeqSourceCache::FindSourceWrap((CSeqSourceCache *)(*(_QWORD *)this + 288LL), Source);
          if ( !SourceWrap )
            break;
          PDWrap = CSeqSourceWrap::GetPDWrap(SourceWrap, (struct CSeqPDWrap **)&v82);
          if ( PDWrap < 0 )
          {
            v46 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
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
              v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
              if ( *((_DWORD *)v48 + 499) != PDWrap )
                CallStackContext::TraceFailure(v48, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 90, PDWrap);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
                this,
                PDWrap);
            v5 = v82;
            goto LABEL_139;
          }
          v5 = v82;
          PDWrap = CSeqPDWrap::CopyStreamDescriptors(v82, &apStreamDescriptors);
          if ( PDWrap < 0 )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
              CallStackTracing::s_wpInstance = v44;
              if ( v44
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
              {
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v43 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v43 + 8) )
            {
              v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
              if ( *((_DWORD *)v45 + 499) != PDWrap )
                CallStackContext::TraceFailure(v45, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 92, PDWrap);
            }
            if ( !g_wppLevels )
              goto LABEL_139;
            v42 = 16;
LABEL_138:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v42,
              &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
              this,
              PDWrap);
            goto LABEL_139;
          }
          if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
            WPP_SF_qqq(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              17,
              &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
              this,
              v29,
              v5);
          PDWrap = CSeqObjectCache::AddObject((struct CSeqPresentationContext *)((char *)v74 + 48), v29, v5);
          if ( PDWrap < 0 )
          {
            v39 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38);
              CallStackTracing::s_wpInstance = v40;
              if ( v40
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
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
              if ( *((_DWORD *)v41 + 499) != PDWrap )
                CallStackContext::TraceFailure(v41, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 99, PDWrap);
            }
            if ( !g_wppLevels )
              goto LABEL_139;
            v42 = 18;
            goto LABEL_138;
          }
          LODWORD(v23) = v80;
          if ( !v80 && !v25 )
          {
            (*((void (__fastcall **)(struct IUnknownVtbl *, const IID *, __int64 *))v5[5].lpVtbl->QueryInterface + 8))(
              v5[5].lpVtbl,
              &MF_PD_DURATION,
              &v80);
            LODWORD(v23) = v80;
          }
          v24 = v81;
          ++v25;
        }
        v49 = (__int64 *)CallStackTracing::s_wpInstance;
        PDWrap = -1072864850;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != -1072864850 )
            CallStackContext::TraceFailure(v51, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 88, -1072864850);
        }
        if ( g_wppLevels )
        {
          v42 = 14;
          goto LABEL_138;
        }
LABEL_139:
        if ( v5 )
          ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
      }
      else
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
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
          v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)v22 + 499) != PDWrap )
            CallStackContext::TraceFailure(v22, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 54, PDWrap);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
            this,
            PDWrap);
      }
      if ( v74 )
        (*(void (__fastcall **)(struct CSeqPresentationContext *))(*(_QWORD *)v74 + 16LL))(v74);
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      PDWrap = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v17, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 49, -1072875845);
      }
      if ( g_wppLevels )
      {
        v14 = 11;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    PDWrap = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v13 + 499) != -1072875845 )
        CallStackContext::TraceFailure(v13, "CSeqSourcePDBuilder::CreatePresentationDescriptor", 48, -1072875845);
    }
    if ( g_wppLevels )
    {
      v14 = 10;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids,
        this,
        -1072875845);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v81);
  CSeqObjectArray<IMFStreamDescriptor>::~CSeqObjectArray<IMFStreamDescriptor>(&apStreamDescriptors);
  return (unsigned int)PDWrap;
}

```

## disassembly

```asm
0x18021990c  mov     [rsp-38h+arg_8], rbx
0x180219911  mov     [rsp-38h+arg_18], r9
0x180219916  mov     [rsp-38h+arg_10], r8d
0x18021991b  push    rbp
0x18021991c  push    rsi
0x18021991d  push    rdi
0x18021991e  push    r12
0x180219920  push    r13
0x180219922  push    r14
0x180219924  push    r15
0x180219926  mov     rbp, rsp
0x180219929  sub     rsp, 70h
0x18021992d  xor     r15d, r15d
0x180219930  mov     [rbp+var_40], 0
0x180219938  mov     r13, rdx
0x18021993b  mov     [rbp+arg_18], r15
0x18021993f  mov     r14, rcx
0x180219942  mov     [rbp+apStreamDescriptors], r15
0x180219946  lea     rsi, aCseqsourcepdbu; "CSeqSourcePDBuilder::CreatePresentation"...
0x18021994d  mov     [rbp+var_14], r15
0x180219951  lea     r12d, [r15+30h]
0x180219955  mov     [rbp+cStreamDescriptors], r15d
0x180219959  mov     r8d, r12d; int
0x18021995c  mov     [rbp+arg_0], r15
0x180219960  mov     rdx, rsi; char *
0x180219963  lea     rcx, [rbp+arg_10]; this
0x180219967  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18021996c  cmp     [r14], r15
0x18021996f  jnz     loc_180219A29
0x180219975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021997c  mov     edi, 0C00D36BBh
0x180219981  mov     ebx, edi
0x180219983  test    rcx, rcx
0x180219986  jnz     short loc_1802199D0
0x180219988  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18021998f  nop     dword ptr [rax+rax+00h]
0x180219994  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021999b  mov     rcx, rax
0x18021999e  test    rax, rax
0x1802199a1  jz      short loc_1802199C2
0x1802199a3  mov     rax, [rax]
0x1802199a6  mov     edx, 7F0h
0x1802199ab  mov     rax, [rax+8]
0x1802199af  call    cs:__guard_dispatch_icall_fptr
0x1802199b5  test    eax, eax
0x1802199b7  jz      short loc_1802199C2
0x1802199b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802199c0  jmp     short loc_1802199D0
0x1802199c2  lea     rcx, qword_1803CE250; this
0x1802199c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802199d0  cmp     [rcx+8], r15b
0x1802199d4  jz      short loc_1802199F4
0x1802199d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802199db  cmp     [rax+7CCh], edi
0x1802199e1  jz      short loc_1802199F4
0x1802199e3  mov     r9d, edi; int
0x1802199e6  mov     r8d, r12d; int
0x1802199e9  mov     rdx, rsi; char *
0x1802199ec  mov     rcx, rax; this
0x1802199ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1802199f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1802199fb  jb      loc_18021A2D6
0x180219a01  mov     edx, 0Ah
0x180219a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180219a0d  lea     r8, WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids
0x180219a14  mov     r9, r14
0x180219a17  mov     dword ptr [rsp+70h+var_50], edi
0x180219a1b  mov     rcx, [rcx+10h]
0x180219a1f  call    WPP_SF_qD
0x180219a24  jmp     loc_18021A2D6
0x180219a29  cmp     [rbp+ppPresentationDescriptor], r15
0x180219a2d  jnz     loc_180219ACC
0x180219a33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219a3a  mov     edi, 0C00D36BBh
0x180219a3f  mov     ebx, edi
0x180219a41  test    rcx, rcx
0x180219a44  jnz     short loc_180219A8E
0x180219a46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180219a4d  nop     dword ptr [rax+rax+00h]
0x180219a52  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180219a59  mov     rcx, rax
0x180219a5c  test    rax, rax
0x180219a5f  jz      short loc_180219A80
0x180219a61  mov     rax, [rax]
0x180219a64  mov     edx, 7F0h
0x180219a69  mov     rax, [rax+8]
0x180219a6d  call    cs:__guard_dispatch_icall_fptr
0x180219a73  test    eax, eax
0x180219a75  jz      short loc_180219A80
0x180219a77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219a7e  jmp     short loc_180219A8E
0x180219a80  lea     rcx, qword_1803CE250; this
0x180219a87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180219a8e  cmp     [rcx+8], r15b
0x180219a92  jz      short loc_180219AB5
0x180219a94  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180219a99  cmp     [rax+7CCh], edi
0x180219a9f  jz      short loc_180219AB5
0x180219aa1  mov     r9d, edi; int
0x180219aa4  mov     r8d, 31h ; '1'; int
0x180219aaa  mov     rdx, rsi; char *
0x180219aad  mov     rcx, rax; this
0x180219ab0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180219ab5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180219abc  jb      loc_18021A2D6
0x180219ac2  mov     edx, 0Bh
0x180219ac7  jmp     loc_180219A06
0x180219acc  lea     r8, [rbp+var_40]; struct CSeqPresentationContext **
0x180219ad0  mov     rdx, r13; struct CSeqSegmentDescriptor *
0x180219ad3  mov     rcx, r14; this
0x180219ad6  call    ?CreatePresentationContext@CSeqSourcePDBuilder@@IEAAJPEAVCSeqSegmentDescriptor@@PEAPEAVCSeqPresentationContext@@@Z; CSeqSourcePDBuilder::CreatePresentationContext(CSeqSegmentDescriptor *,CSeqPresentationContext * *)
0x180219adb  mov     ebx, eax
0x180219add  test    eax, eax
0x180219adf  jns     loc_180219B95
0x180219ae5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219aec  test    rcx, rcx
0x180219aef  jnz     short loc_180219B39
0x180219af1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180219af8  nop     dword ptr [rax+rax+00h]
0x180219afd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180219b04  mov     rcx, rax
0x180219b07  test    rax, rax
0x180219b0a  jz      short loc_180219B2B
0x180219b0c  mov     rax, [rax]
0x180219b0f  mov     edx, 7F0h
0x180219b14  mov     rax, [rax+8]
0x180219b18  call    cs:__guard_dispatch_icall_fptr
0x180219b1e  test    eax, eax
0x180219b20  jz      short loc_180219B2B
0x180219b22  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219b29  jmp     short loc_180219B39
0x180219b2b  lea     rcx, qword_1803CE250; this
0x180219b32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180219b39  cmp     [rcx+8], r15b
0x180219b3d  jz      short loc_180219B60
0x180219b3f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180219b44  cmp     [rax+7CCh], ebx
0x180219b4a  jz      short loc_180219B60
0x180219b4c  mov     r9d, ebx; int
0x180219b4f  mov     r8d, 36h ; '6'; int
0x180219b55  mov     rdx, rsi; char *
0x180219b58  mov     rcx, rax; this
0x180219b5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180219b60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180219b67  jb      loc_18021A2C0
0x180219b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180219b74  lea     r8, WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids
0x180219b7b  mov     edx, 0Ch
0x180219b80  mov     dword ptr [rsp+70h+var_50], ebx
0x180219b84  mov     r9, r14
0x180219b87  mov     rcx, [rcx+10h]
0x180219b8b  call    WPP_SF_qD
0x180219b90  jmp     loc_18021A2C0
0x180219b95  mov     rcx, [r13+38h]
0x180219b99  lea     rsi, WPP_87009a61730b3df9de449d01e97cbc6a_Traceguids
0x180219ba0  mov     eax, [r13+28h]
0x180219ba4  xor     edi, edi
0x180219ba6  mov     [rbp+arg_0], rcx
0x180219baa  mov     [rbp+arg_10], eax
0x180219bad  cmp     edi, eax
0x180219baf  jnb     loc_180219FC8
0x180219bb5  test    r15, r15
0x180219bb8  jz      short loc_180219BD1
0x180219bba  mov     rax, [r15]
0x180219bbd  mov     rcx, r15
0x180219bc0  mov     rax, [rax+10h]
0x180219bc4  call    cs:__guard_dispatch_icall_fptr
0x180219bca  xor     r15d, r15d
0x180219bcd  mov     [rbp+arg_18], r15
0x180219bd1  mov     edx, edi; unsigned int
0x180219bd3  mov     rcx, r13; this
0x180219bd6  call    ?GetSource@CSeqSegmentDescriptor@@QEAAPEAUIMFMediaSource@@K@Z; CSeqSegmentDescriptor::GetSource(ulong)
0x180219bdb  mov     r12, rax
0x180219bde  test    rax, rax
0x180219be1  jz      loc_180219F27
0x180219be7  mov     rcx, [r14]
0x180219bea  mov     rdx, rax; struct IMFMediaSource *
0x180219bed  add     rcx, 120h; this
0x180219bf4  call    ?FindSourceWrap@CSeqSourceCache@@QEAAPEAVCSeqSourceWrap@@PEAUIMFMediaSource@@@Z; CSeqSourceCache::FindSourceWrap(IMFMediaSource *)
0x180219bf9  test    rax, rax
0x180219bfc  jz      loc_180219E8C
0x180219c02  lea     rdx, [rbp+arg_18]; struct CSeqPDWrap **
0x180219c06  mov     rcx, rax; this
0x180219c09  call    ?GetPDWrap@CSeqSourceWrap@@QEAAJPEAPEAVCSeqPDWrap@@@Z; CSeqSourceWrap::GetPDWrap(CSeqPDWrap * *)
0x180219c0e  mov     ebx, eax
0x180219c10  test    eax, eax
0x180219c12  js      loc_180219DDC
0x180219c18  mov     r15, [rbp+arg_18]
0x180219c1c  lea     rdx, [rbp+apStreamDescriptors]
0x180219c20  mov     rcx, r15
0x180219c23  call    ?CopyStreamDescriptors@CSeqPDWrap@@QEAAJAEAV?$CSeqObjectArray@UIMFStreamDescriptor@@@@@Z; CSeqPDWrap::CopyStreamDescriptors(CSeqObjectArray<IMFStreamDescriptor> &)
0x180219c28  mov     ebx, eax
0x180219c2a  test    eax, eax
0x180219c2c  js      loc_180219D46
0x180219c32  cmp     cs:byte_1803CECE9, 10h
0x180219c39  jb      short loc_180219C60
0x180219c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180219c42  mov     edx, 11h
0x180219c47  mov     [rsp+70h+var_48], r15
0x180219c4c  mov     r9, r14
0x180219c4f  mov     r8, rsi
0x180219c52  mov     [rsp+70h+var_50], r12
0x180219c57  mov     rcx, [rcx+38h]
0x180219c5b  call    WPP_SF_qqq
0x180219c60  mov     rcx, [rbp+var_40]
0x180219c64  mov     r8, r15; struct IUnknown *
0x180219c67  add     rcx, 30h ; '0'; this
0x180219c6b  mov     rdx, r12; struct IUnknown *
0x180219c6e  call    ?AddObject@CSeqObjectCache@@QEAAJPEAUIUnknown@@0@Z; CSeqObjectCache::AddObject(IUnknown *,IUnknown *)
0x180219c73  mov     ebx, eax
0x180219c75  test    eax, eax
0x180219c77  js      short loc_180219CB0
0x180219c79  mov     rcx, [rbp+arg_0]
0x180219c7d  test    rcx, rcx
0x180219c80  jnz     short loc_180219CA6
0x180219c82  test    edi, edi
0x180219c84  jnz     short loc_180219CA6
0x180219c86  mov     rcx, [r15+28h]
0x180219c8a  lea     r8, [rbp+arg_0]
0x180219c8e  lea     rdx, MF_PD_DURATION
0x180219c95  mov     rax, [rcx]
0x180219c98  mov     rax, [rax+40h]
0x180219c9c  call    cs:__guard_dispatch_icall_fptr
0x180219ca2  mov     rcx, [rbp+arg_0]
0x180219ca6  mov     eax, [rbp+arg_10]
0x180219ca9  inc     edi
0x180219cab  jmp     loc_180219BAD
0x180219cb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219cb7  test    rcx, rcx
0x180219cba  jnz     short loc_180219D04
0x180219cbc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180219cc3  nop     dword ptr [rax+rax+00h]
0x180219cc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180219ccf  mov     rcx, rax
0x180219cd2  test    rax, rax
0x180219cd5  jz      short loc_180219CF6
0x180219cd7  mov     rax, [rax]
0x180219cda  mov     edx, 7F0h
0x180219cdf  mov     rax, [rax+8]
0x180219ce3  call    cs:__guard_dispatch_icall_fptr
0x180219ce9  test    eax, eax
0x180219ceb  jz      short loc_180219CF6
0x180219ced  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219cf4  jmp     short loc_180219D04
0x180219cf6  lea     rcx, qword_1803CE250; this
0x180219cfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180219d04  cmp     byte ptr [rcx+8], 0
0x180219d08  jz      short loc_180219D2F
0x180219d0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180219d0f  cmp     [rax+7CCh], ebx
0x180219d15  jz      short loc_180219D2F
0x180219d17  mov     r9d, ebx; int
0x180219d1a  lea     rdx, aCseqsourcepdbu; "CSeqSourcePDBuilder::CreatePresentation"...
0x180219d21  mov     r8d, 63h ; 'c'; int
0x180219d27  mov     rcx, rax; this
0x180219d2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180219d2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180219d36  jb      loc_18021A2AB
0x180219d3c  mov     edx, 12h
0x180219d41  jmp     loc_18021A291
0x180219d46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219d4d  test    rcx, rcx
0x180219d50  jnz     short loc_180219D9A
0x180219d52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180219d59  nop     dword ptr [rax+rax+00h]
0x180219d5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180219d65  mov     rcx, rax
0x180219d68  test    rax, rax
0x180219d6b  jz      short loc_180219D8C
0x180219d6d  mov     rax, [rax]
0x180219d70  mov     edx, 7F0h
0x180219d75  mov     rax, [rax+8]
0x180219d79  call    cs:__guard_dispatch_icall_fptr
0x180219d7f  test    eax, eax
0x180219d81  jz      short loc_180219D8C
0x180219d83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219d8a  jmp     short loc_180219D9A
0x180219d8c  lea     rcx, qword_1803CE250; this
0x180219d93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180219d9a  cmp     byte ptr [rcx+8], 0
0x180219d9e  jz      short loc_180219DC5
0x180219da0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180219da5  cmp     [rax+7CCh], ebx
0x180219dab  jz      short loc_180219DC5
0x180219dad  mov     r9d, ebx; int
0x180219db0  lea     rdx, aCseqsourcepdbu; "CSeqSourcePDBuilder::CreatePresentation"...
0x180219db7  mov     r8d, 5Ch ; '\'; int
0x180219dbd  mov     rcx, rax; this
0x180219dc0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180219dc5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180219dcc  jb      loc_18021A2AB
0x180219dd2  mov     edx, 10h
0x180219dd7  jmp     loc_18021A291
0x180219ddc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180219de3  test    rcx, rcx
0x180219de6  jnz     short loc_180219E30
0x180219de8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180219def  nop     dword ptr [rax+rax+00h]
0x180219df4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180219dfb  mov     rcx, rax
  ... truncated ...
```
