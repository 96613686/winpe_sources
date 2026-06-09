# CDShowWrapper::SetupMFBytestreamSource(IBaseFilter * *,int *,int *)

- ea: `0x180032d8c`
- end: `0x180033796`
- name: `?SetupMFBytestreamSource@CDShowWrapper@@IEAAJPEAPEAUIBaseFilter@@PEAH1@Z`
- size: `2570`
- prototype: `int(CDShowWrapper *__hidden this, struct IBaseFilter **, int *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180030060`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032988`
- `0x180032a50`
- `0x180032d8c`
- `0x18003379c`
- `0x18004b664`
- `0x180051ce4`
- `0x180053934`
- `0x180074160`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032e76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032e76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033028`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800330fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033202`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003337a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033572`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033625`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f6f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033028`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800330fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033202`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003337a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033572`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033625`

## pseudocode

```c
__int64 __fastcall CDShowWrapper::SetupMFBytestreamSource(
        CDShowWrapper *this,
        struct IBaseFilter **a2,
        int *a3,
        int *a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  int v11; // edi
  HRESULT IsRequired; // ebx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CGITPtr *v23; // rcx
  CallStackTracing *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  bool v27; // zf
  __int64 (__fastcall *v28)(LPVOID, GUID *, __int64 *); // rax
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rax
  __int64 v33; // r10
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  CDShowWrapper *v45; // rcx
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  struct IBaseFilter *v52; // rax
  _BYTE v54[8]; // [rsp+30h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-41h] BYREF
  struct IBaseFilter *v56; // [rsp+40h] [rbp-39h] BYREF
  __int64 v57; // [rsp+48h] [rbp-31h] BYREF
  __int64 v58; // [rsp+50h] [rbp-29h] BYREF
  __int64 v59; // [rsp+58h] [rbp-21h] BYREF
  struct IPin *v60; // [rsp+60h] [rbp-19h] BYREF
  __int64 v61; // [rsp+68h] [rbp-11h] BYREF
  void *v62[2]; // [rsp+70h] [rbp-9h] BYREF

  v61 = 0;
  v60 = 0;
  ppv = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v58 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v54, "CDShowWrapper::SetupMFBytestreamSource", 5064);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 60) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 60) + 296LL))(*((_QWORD *)this + 60));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 60) + 280LL))(
                       *((_QWORD *)this + 60),
                       v62);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  v11 = 1;
  IsRequired = CoCreateInstance(&CLSID_MFSourceFilter, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
  if ( IsRequired >= 0 )
  {
    IsRequired = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IBaseFilter **))ppv)(
                   ppv,
                   &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770,
                   &v56);
    if ( IsRequired >= 0 )
    {
      IsRequired = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                     ppv,
                     &GUID_7bb552d6_cbd8_42cc_bc1a_7b87a0a3a969,
                     &v59);
      if ( IsRequired >= 0 )
      {
        v23 = (CGITPtr *)(*((_QWORD *)this + 1) + 208LL);
        v62[0] = 0;
        CGITPtr::Get(v23, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, v62);
        IsRequired = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v59 + 24LL))(v59, v62[0]);
        if ( IsRequired < 0 )
        {
          v24 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = CallStackTracing::GetThreadRelativeContext(v24);
            if ( *((_DWORD *)v26 + 499) != IsRequired )
              CallStackContext::TraceFailure(v26, "CDShowWrapper::SetupMFBytestreamSource", 5073, IsRequired);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              456,
              &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
              this,
              IsRequired);
          ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v62);
          goto LABEL_131;
        }
        if ( v62[0] )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v62[0] + 16LL))(v62[0]);
        v27 = (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty((char *)this + 16) == 0;
        v28 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
        if ( v27 )
        {
          IsRequired = v28(ppv, &GUID_56a868a6_0ad4_11ce_b03a_0020af0ba770, &v58);
          if ( IsRequired < 0 )
          {
            v29 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              v31 = CallStackTracing::GetThreadRelativeContext(v29);
              if ( *((_DWORD *)v31 + 499) != IsRequired )
                CallStackContext::TraceFailure(v31, "CDShowWrapper::SetupMFBytestreamSource", 5078, IsRequired);
            }
            if ( g_wppLevels )
            {
              v16 = 457;
              goto LABEL_15;
            }
            goto LABEL_131;
          }
          v32 = CMFBaseStringT<unsigned short>::PContents((char *)this + 16);
          IsRequired = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 24LL))(v33, v32, 0);
          if ( IsRequired < 0 )
          {
            v34 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext(v34);
              if ( *((_DWORD *)v36 + 499) != IsRequired )
                CallStackContext::TraceFailure(v36, "CDShowWrapper::SetupMFBytestreamSource", 5079, IsRequired);
            }
            if ( g_wppLevels )
            {
              v16 = 458;
              goto LABEL_15;
            }
            goto LABEL_131;
          }
        }
        else
        {
          IsRequired = v28(ppv, &GUID_00f5e896_8813_44e3_8789_7e520e0de873, &v57);
          if ( IsRequired < 0 )
          {
            v37 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              v39 = CallStackTracing::GetThreadRelativeContext(v37);
              if ( *((_DWORD *)v39 + 499) != IsRequired )
                CallStackContext::TraceFailure(v39, "CDShowWrapper::SetupMFBytestreamSource", 5083, IsRequired);
            }
            if ( g_wppLevels )
            {
              v16 = 459;
              goto LABEL_15;
            }
            goto LABEL_131;
          }
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 96LL))(v57, 0);
          IsRequired = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 80LL))(v57, *((_QWORD *)this + 5));
          if ( IsRequired < 0 )
          {
            v40 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v41;
              if ( v41
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
              {
                v40 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v40 + 8) )
            {
              v42 = CallStackTracing::GetThreadRelativeContext(v40);
              if ( *((_DWORD *)v42 + 499) != IsRequired )
                CallStackContext::TraceFailure(v42, "CDShowWrapper::SetupMFBytestreamSource", 5086, IsRequired);
            }
            if ( g_wppLevels )
            {
              v16 = 460;
              goto LABEL_15;
            }
            goto LABEL_131;
          }
        }
        IsRequired = ((__int64 (__fastcall *)(struct IBaseFilter *, __int64 *))v56->lpVtbl->EnumPins)(v56, &v61);
        if ( IsRequired >= 0 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IPin **, _QWORD))(*(_QWORD *)v61 + 24LL))(
                 v61,
                 1,
                 &v60,
                 0) )
          {
            v46 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            IsRequired = -2147418113;
            if ( *((_BYTE *)v46 + 8) )
            {
              v48 = CallStackTracing::GetThreadRelativeContext(v46);
              if ( *((_DWORD *)v48 + 499) != -2147418113 )
                CallStackContext::TraceFailure(v48, "CDShowWrapper::SetupMFBytestreamSource", 5094, -2147418113);
            }
            if ( g_wppLevels )
            {
              v16 = 462;
              goto LABEL_15;
            }
          }
          else
          {
            IsRequired = CDShowWrapper::PushModeIsRequired(v45, v60, a4);
            if ( IsRequired >= 0 )
            {
              if ( !*a4 && !(unsigned int)CMFBaseStringT<unsigned short>::IsEmpty((char *)this + 16) )
                v11 = 0;
              v52 = v56;
              *a3 = v11;
              *a2 = v52;
              v56 = 0;
            }
            else
            {
              v49 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v49 + 8) )
              {
                v51 = CallStackTracing::GetThreadRelativeContext(v49);
                if ( *((_DWORD *)v51 + 499) != IsRequired )
                  CallStackContext::TraceFailure(v51, "CDShowWrapper::SetupMFBytestreamSource", 5096, IsRequired);
              }
              if ( g_wppLevels )
              {
                v16 = 463;
                goto LABEL_15;
              }
            }
          }
        }
        else
        {
          v43 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v43 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext(v43);
            if ( *((_DWORD *)v44 + 499) != IsRequired )
              CallStackContext::TraceFailure(v44, "CDShowWrapper::SetupMFBytestreamSource", 5089, IsRequired);
          }
          if ( g_wppLevels )
          {
            v16 = 461;
            goto LABEL_15;
          }
        }
        goto LABEL_131;
      }
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v22 + 499) != IsRequired )
          CallStackContext::TraceFailure(v22, "CDShowWrapper::SetupMFBytestreamSource", 5068, IsRequired);
      }
      if ( g_wppLevels )
      {
        v16 = 455;
        goto LABEL_15;
      }
    }
    else
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v19 + 499) != IsRequired )
          CallStackContext::TraceFailure(v19, "CDShowWrapper::SetupMFBytestreamSource", 5066, IsRequired);
      }
      if ( g_wppLevels )
      {
        v16 = 454;
        goto LABEL_15;
      }
    }
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
      if ( *((_DWORD *)v15 + 499) != IsRequired )
        CallStackContext::TraceFailure(v15, "CDShowWrapper::SetupMFBytestreamSource", 5064, IsRequired);
    }
    if ( g_wppLevels )
    {
      v16 = 453;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids,
        this,
        IsRequired);
    }
  }
LABEL_131:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v54);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  if ( v59 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  if ( v56 )
    ((void (__fastcall *)(struct IBaseFilter *))v56->lpVtbl->Release)(v56);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v60 )
    ((void (__fastcall *)(struct IPin *))v60->lpVtbl->Release)(v60);
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  return (unsigned int)IsRequired;
}

```

## disassembly

```asm
0x180032d8c  push    rbp
0x180032d8e  push    rbx
0x180032d8f  push    rsi
0x180032d90  push    rdi
0x180032d91  push    r12
0x180032d93  push    r13
0x180032d95  push    r14
0x180032d97  push    r15
0x180032d99  lea     rbp, [rsp-1Fh]
0x180032d9e  sub     rsp, 98h
0x180032da5  mov     rax, cs:__security_cookie
0x180032dac  xor     rax, rsp
0x180032daf  mov     [rbp+57h+var_50], rax
0x180032db3  xor     r14d, r14d
0x180032db6  mov     r13, r8
0x180032db9  mov     r12, rdx
0x180032dbc  mov     [rbp+57h+var_68], r14
0x180032dc0  mov     rsi, rcx
0x180032dc3  mov     [rbp+57h+var_70], r14
0x180032dc7  mov     r8d, 13C8h; int
0x180032dcd  mov     [rbp+57h+var_98], r14
0x180032dd1  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x180032dd8  mov     [rbp+57h+var_90], r14
0x180032ddc  lea     rcx, [rbp+57h+var_A0]; this
0x180032de0  mov     [rbp+57h+var_88], r14
0x180032de4  mov     [rbp+57h+var_78], r14
0x180032de8  mov     r15, r9
0x180032deb  mov     [rbp+57h+var_80], r14
0x180032def  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180032df4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032dfb  cmp     [rcx+8], r14b
0x180032dff  jz      short loc_180032E55
0x180032e01  cmp     [rsi+1E0h], r14
0x180032e08  jz      short loc_180032E55
0x180032e0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032e0f  mov     rcx, [rsi+1E0h]
0x180032e16  mov     rdi, rax
0x180032e19  mov     rdx, [rcx]
0x180032e1c  mov     rax, [rdx+128h]
0x180032e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e28  mov     rcx, [rsi+1E0h]
0x180032e2f  mov     ebx, eax
0x180032e31  mov     rdx, [rcx]
0x180032e34  mov     rax, [rdx+118h]
0x180032e3b  lea     rdx, [rbp+57h+var_60]
0x180032e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e44  movups  xmm0, xmmword ptr [rax]
0x180032e47  mov     [rdi+7E0h], ebx
0x180032e4d  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180032e55  lea     rax, [rbp+57h+var_98]
0x180032e59  mov     edi, 1
0x180032e5e  mov     r8d, edi; dwClsContext
0x180032e61  mov     [rsp+0D0h+ppv], rax; ppv
0x180032e66  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180032e6d  xor     edx, edx; pUnkOuter
0x180032e6f  lea     rcx, CLSID_MFSourceFilter; rclsid
0x180032e76  call    cs:__imp_CoCreateInstance
0x180032e7d  nop     dword ptr [rax+rax+00h]
0x180032e82  mov     ebx, eax
0x180032e84  test    eax, eax
0x180032e86  jns     loc_180032F3F
0x180032e8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e93  test    rcx, rcx
0x180032e96  jnz     short loc_180032EDF
0x180032e98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032e9f  nop     dword ptr [rax+rax+00h]
0x180032ea4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032eab  mov     rcx, rax
0x180032eae  test    rax, rax
0x180032eb1  jz      short loc_180032ED1
0x180032eb3  mov     rax, [rax]
0x180032eb6  mov     edx, 7F0h
0x180032ebb  mov     rax, [rax+8]
0x180032ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ec4  test    eax, eax
0x180032ec6  jz      short loc_180032ED1
0x180032ec8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032ecf  jmp     short loc_180032EDF
0x180032ed1  lea     rcx, qword_1800EB130; this
0x180032ed8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032edf  cmp     [rcx+8], r14b
0x180032ee3  jz      short loc_180032F0A
0x180032ee5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032eea  cmp     [rax+7CCh], ebx
0x180032ef0  jz      short loc_180032F0A
0x180032ef2  mov     r9d, ebx; int
0x180032ef5  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x180032efc  mov     r8d, 13C8h; int
0x180032f02  mov     rcx, rax; this
0x180032f05  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032f0a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180032f11  jb      loc_1800336D7
0x180032f17  mov     edx, 1C5h
0x180032f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f23  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180032f2a  mov     r9, rsi
0x180032f2d  mov     dword ptr [rsp+0D0h+ppv], ebx
0x180032f31  mov     rcx, [rcx+10h]
0x180032f35  call    WPP_SF_qD
0x180032f3a  jmp     loc_1800336D7
0x180032f3f  mov     rcx, [rbp+57h+var_98]
0x180032f43  lea     r8, [rbp+57h+var_90]
0x180032f47  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x180032f4e  mov     rax, [rcx]
0x180032f51  mov     rax, [rax]
0x180032f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f59  mov     ebx, eax
0x180032f5b  test    eax, eax
0x180032f5d  jns     loc_180032FF8
0x180032f63  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f6a  test    rcx, rcx
0x180032f6d  jnz     short loc_180032FB6
0x180032f6f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032f76  nop     dword ptr [rax+rax+00h]
0x180032f7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f82  mov     rcx, rax
0x180032f85  test    rax, rax
0x180032f88  jz      short loc_180032FA8
0x180032f8a  mov     rax, [rax]
0x180032f8d  mov     edx, 7F0h
0x180032f92  mov     rax, [rax+8]
0x180032f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f9b  test    eax, eax
0x180032f9d  jz      short loc_180032FA8
0x180032f9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032fa6  jmp     short loc_180032FB6
0x180032fa8  lea     rcx, qword_1800EB130; this
0x180032faf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032fb6  cmp     [rcx+8], r14b
0x180032fba  jz      short loc_180032FE1
0x180032fbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032fc1  cmp     [rax+7CCh], ebx
0x180032fc7  jz      short loc_180032FE1
0x180032fc9  mov     r9d, ebx; int
0x180032fcc  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x180032fd3  mov     r8d, 13CAh; int
0x180032fd9  mov     rcx, rax; this
0x180032fdc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032fe1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180032fe8  jb      loc_1800336D7
0x180032fee  mov     edx, 1C6h
0x180032ff3  jmp     loc_180032F1C
0x180032ff8  mov     rcx, [rbp+57h+var_98]
0x180032ffc  lea     r8, [rbp+57h+var_78]
0x180033000  lea     rdx, _GUID_7bb552d6_cbd8_42cc_bc1a_7b87a0a3a969
0x180033007  mov     rax, [rcx]
0x18003300a  mov     rax, [rax]
0x18003300d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033012  mov     ebx, eax
0x180033014  test    eax, eax
0x180033016  jns     loc_1800330B1
0x18003301c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033023  test    rcx, rcx
0x180033026  jnz     short loc_18003306F
0x180033028  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003302f  nop     dword ptr [rax+rax+00h]
0x180033034  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003303b  mov     rcx, rax
0x18003303e  test    rax, rax
0x180033041  jz      short loc_180033061
0x180033043  mov     rax, [rax]
0x180033046  mov     edx, 7F0h
0x18003304b  mov     rax, [rax+8]
0x18003304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033054  test    eax, eax
0x180033056  jz      short loc_180033061
0x180033058  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003305f  jmp     short loc_18003306F
0x180033061  lea     rcx, qword_1800EB130; this
0x180033068  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003306f  cmp     [rcx+8], r14b
0x180033073  jz      short loc_18003309A
0x180033075  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003307a  cmp     [rax+7CCh], ebx
0x180033080  jz      short loc_18003309A
0x180033082  mov     r9d, ebx; int
0x180033085  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x18003308c  mov     r8d, 13CCh; int
0x180033092  mov     rcx, rax; this
0x180033095  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003309a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800330a1  jb      loc_1800336D7
0x1800330a7  mov     edx, 1C7h
0x1800330ac  jmp     loc_180032F1C
0x1800330b1  mov     rcx, [rsi+8]
0x1800330b5  lea     r8, [rbp+57h+var_60]; void **
0x1800330b9  add     rcx, 0D0h; this
0x1800330c0  mov     [rbp+57h+var_60], r14
0x1800330c4  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; struct _GUID *
0x1800330cb  call    ?Get@CGITPtr@@QEAAJAEBU_GUID@@PEAPEAX@Z; CGITPtr::Get(_GUID const &,void * *)
0x1800330d0  mov     rcx, [rbp+57h+var_78]
0x1800330d4  mov     rdx, [rbp+57h+var_60]
0x1800330d8  mov     rax, [rcx]
0x1800330db  mov     rax, [rax+18h]
0x1800330df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330e4  mov     ebx, eax
0x1800330e6  test    eax, eax
0x1800330e8  jns     loc_1800331A6
0x1800330ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800330f5  test    rcx, rcx
0x1800330f8  jnz     short loc_180033141
0x1800330fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033101  nop     dword ptr [rax+rax+00h]
0x180033106  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003310d  mov     rcx, rax
0x180033110  test    rax, rax
0x180033113  jz      short loc_180033133
0x180033115  mov     rax, [rax]
0x180033118  mov     edx, 7F0h
0x18003311d  mov     rax, [rax+8]
0x180033121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033126  test    eax, eax
0x180033128  jz      short loc_180033133
0x18003312a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033131  jmp     short loc_180033141
0x180033133  lea     rcx, qword_1800EB130; this
0x18003313a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033141  cmp     [rcx+8], r14b
0x180033145  jz      short loc_18003316C
0x180033147  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003314c  cmp     [rax+7CCh], ebx
0x180033152  jz      short loc_18003316C
0x180033154  mov     r9d, ebx; int
0x180033157  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x18003315e  mov     r8d, 13D1h; int
0x180033164  mov     rcx, rax; this
0x180033167  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003316c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180033173  jb      short loc_180033198
0x180033175  mov     rcx, cs:WPP_GLOBAL_Control
0x18003317c  lea     r8, WPP_8e8a43b2e5013e25304950bf1ec57b49_Traceguids
0x180033183  mov     edx, 1C8h
0x180033188  mov     dword ptr [rsp+0D0h+ppv], ebx
0x18003318c  mov     r9, rsi
0x18003318f  mov     rcx, [rcx+10h]
0x180033193  call    WPP_SF_qD
0x180033198  lea     rcx, [rbp+57h+var_60]; void *
0x18003319c  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x1800331a1  jmp     loc_1800336D7
0x1800331a6  mov     rcx, [rbp+57h+var_60]
0x1800331aa  test    rcx, rcx
0x1800331ad  jz      short loc_1800331BB
0x1800331af  mov     rax, [rcx]
0x1800331b2  mov     rax, [rax+10h]
0x1800331b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331bb  lea     r14, [rsi+10h]
0x1800331bf  mov     rcx, r14
0x1800331c2  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x1800331c7  mov     rcx, [rbp+57h+var_98]
0x1800331cb  test    eax, eax
0x1800331cd  mov     rax, [rcx]
0x1800331d0  mov     rax, [rax]
0x1800331d3  jnz     loc_180033351
0x1800331d9  lea     r8, [rbp+57h+var_80]
0x1800331dd  lea     rdx, _GUID_56a868a6_0ad4_11ce_b03a_0020af0ba770
0x1800331e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331e9  mov     ebx, eax
0x1800331eb  test    eax, eax
0x1800331ed  jns     loc_18003328B
0x1800331f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800331fa  xor     r14d, r14d
0x1800331fd  test    rcx, rcx
0x180033200  jnz     short loc_180033249
0x180033202  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033209  nop     dword ptr [rax+rax+00h]
0x18003320e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033215  mov     rcx, rax
0x180033218  test    rax, rax
0x18003321b  jz      short loc_18003323B
0x18003321d  mov     rax, [rax]
0x180033220  mov     edx, 7F0h
0x180033225  mov     rax, [rax+8]
0x180033229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003322e  test    eax, eax
0x180033230  jz      short loc_18003323B
0x180033232  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033239  jmp     short loc_180033249
0x18003323b  lea     rcx, qword_1800EB130; this
0x180033242  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033249  cmp     [rcx+8], r14b
0x18003324d  jz      short loc_180033274
0x18003324f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033254  cmp     [rax+7CCh], ebx
0x18003325a  jz      short loc_180033274
0x18003325c  mov     r9d, ebx; int
0x18003325f  lea     rdx, aCdshowwrapperS_1; "CDShowWrapper::SetupMFBytestreamSource"
0x180033266  mov     r8d, 13D6h; int
0x18003326c  mov     rcx, rax; this
0x18003326f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033274  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18003327b  jb      loc_1800336D7
0x180033281  mov     edx, 1C9h
0x180033286  jmp     loc_180032F1C
0x18003328b  mov     r10, [rbp+57h+var_80]
0x18003328f  mov     rcx, r14
0x180033292  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180033297  mov     rdx, [r10]
0x18003329a  xor     r8d, r8d
0x18003329d  mov     rcx, r10
0x1800332a0  mov     r9, [rdx+18h]
  ... truncated ...
```
