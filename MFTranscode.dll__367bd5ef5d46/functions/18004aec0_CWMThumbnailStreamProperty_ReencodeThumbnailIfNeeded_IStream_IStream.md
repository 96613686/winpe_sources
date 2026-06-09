# CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(IStream *,IStream * *)

- ea: `0x18004aec0`
- end: `0x18004b8f8`
- name: `?ReencodeThumbnailIfNeeded@CWMThumbnailStreamProperty@@AEAAJPEAUIStream@@PEAPEAU2@@Z`
- size: `2616`
- prototype: `int(CWMThumbnailStreamProperty *__hidden this, struct IStream *, struct IStream **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004d1e0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x1800170b4`
- `0x1800174c0`
- `0x18001c280`
- `0x18004aec0`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004b0c9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18004b0c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004af6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004af6b`

## pseudocode

```c
__int64 __fastcall CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded(
        CWMThumbnailStreamProperty *this,
        struct IStream *a2,
        struct IStream **a3)
{
  HRESULT StreamOnHGlobal; // edi
  CallStackTracing *v7; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  CallStackTracing *v14; // rcx
  struct CallStackContext *v15; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  _BYTE v47[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v48; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v50; // [rsp+44h] [rbp-45h] BYREF
  __int64 v51; // [rsp+48h] [rbp-41h] BYREF
  __int64 v52; // [rsp+50h] [rbp-39h] BYREF
  __int64 v53; // [rsp+58h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-29h] BYREF
  __int64 v55; // [rsp+68h] [rbp-21h] BYREF
  __int64 v56; // [rsp+70h] [rbp-19h] BYREF
  __int64 v57; // [rsp+78h] [rbp-11h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-9h] BYREF
  GUID v59; // [rsp+90h] [rbp+7h] BYREF

  *a3 = 0;
  ppv = 0;
  v53 = 0;
  v51 = 0;
  v57 = 0;
  v52 = 0;
  v59 = GUID_WICPixelFormat24bppRGB;
  v48 = 0;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v56 = 0;
  v55 = 0;
  v50 = 0;
  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v47,
    "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
    727);
  StreamOnHGlobal = CoCreateInstance(
                      &CLSID_WICImagingFactory2,
                      0,
                      0x17u,
                      &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                      &ppv);
  if ( StreamOnHGlobal < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          727,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 66;
    goto LABEL_154;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
                      ppv,
                      a2,
                      &GUID_VendorMicrosoft,
                      0,
                      &v53);
  if ( StreamOnHGlobal < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v11 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v11,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          729,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 67;
    goto LABEL_154;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v53 + 40LL))(v53, &Buf1);
  if ( StreamOnHGlobal < 0 )
  {
    v12 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v13 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v13,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          731,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 68;
    goto LABEL_154;
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  if ( StreamOnHGlobal < 0 )
  {
    v14 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v14 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v14);
      if ( *((_DWORD *)v15 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v15,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          733,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 69;
    goto LABEL_154;
  }
  if ( !memcmp_0(&Buf1, &GUID_ContainerFormatJpeg, 0x10u) )
  {
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( *((_DWORD *)v39 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v39,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            788,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 81;
      goto LABEL_154;
    }
    StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, _QWORD, _QWORD))a2->lpVtbl->CopyTo)(
                        a2,
                        *a3,
                        -1,
                        0,
                        0);
    if ( StreamOnHGlobal < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v40 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( *((_DWORD *)v41 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v41,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            789,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 82;
      goto LABEL_154;
    }
  }
  else
  {
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 104LL))(v53, 0, &v52);
    if ( StreamOnHGlobal < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v16 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( *((_DWORD *)v17 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v17,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            737,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 70;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v52 + 24LL))(
                        v52,
                        &v50,
                        &v49);
    if ( StreamOnHGlobal < 0 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v18 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( *((_DWORD *)v19 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v19,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            739,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 71;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(
                        ppv,
                        &GUID_ContainerFormatJpeg,
                        &GUID_VendorMicrosoft,
                        &v51);
    if ( StreamOnHGlobal < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v20 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v21 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v21,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            746,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 72;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v51 + 24LL))(v51, *a3, 2);
    if ( StreamOnHGlobal < 0 )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v22 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( *((_DWORD *)v23 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v23,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            751,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 73;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v51 + 80LL))(
                        v51,
                        &v48,
                        &v55);
    if ( StreamOnHGlobal < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( *((_DWORD *)v25 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v25,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            753,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 74;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 24LL))(v48, v55);
    if ( StreamOnHGlobal < 0 )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( *((_DWORD *)v27 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v27,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            755,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 75;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 32LL))(v48, v50, v49);
    if ( StreamOnHGlobal < 0 )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v28 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v28);
        if ( *((_DWORD *)v29 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v29,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            757,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 76;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v48 + 48LL))(v48, &v59);
    if ( StreamOnHGlobal < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v30 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext(v30);
        if ( *((_DWORD *)v31 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v31,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            770,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 77;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 88LL))(v48, v52, 0);
    if ( StreamOnHGlobal < 0 )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v32 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(v32);
        if ( *((_DWORD *)v33 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v33,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            772,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 78;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 96LL))(v48);
    if ( StreamOnHGlobal < 0 )
    {
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v34 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext(v34);
        if ( *((_DWORD *)v35 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v35,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            774,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 79;
      goto LABEL_154;
    }
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 88LL))(v51);
    if ( StreamOnHGlobal < 0 )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext(v36);
        if ( *((_DWORD *)v37 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(
            v37,
            "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
            776,
            StreamOnHGlobal);
      }
      if ( !g_wppLevels )
        goto LABEL_155;
      v9 = 80;
      goto LABEL_154;
    }
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))(*a3)->lpVtbl->Seek)(*a3, 0, 0, 0);
  if ( StreamOnHGlobal < 0 )
  {
    v42 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v42 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( *((_DWORD *)v43 + 499) != StreamOnHGlobal )
        CallStackContext::TraceFailure(
          v43,
          "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded",
          795,
          StreamOnHGlobal);
    }
    if ( !g_wppLevels )
      goto LABEL_155;
    v9 = 83;
    goto LABEL_154;
  }
  StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
  if ( StreamOnHGlobal >= 0 )
    goto LABEL_157;
  v44 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v44 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v44 + 8) )
  {
    v45 = CallStackTracing::GetThreadRelativeContext(v44);
    if ( *((_DWORD *)v45 + 499) != StreamOnHGlobal )
      CallStackContext::TraceFailure(v45, "CWMThumbnailStreamProperty::ReencodeThumbnailIfNeeded", 801, StreamOnHGlobal);
  }
  if ( g_wppLevels )
  {
    v9 = 84;
LABEL_154:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
      this,
      StreamOnHGlobal);
  }
LABEL_155:
  if ( *a3 )
  {
    ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
    *a3 = 0;
  }
LABEL_157:
  operator delete(0);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v47);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v55);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v48);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v52);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v57);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v51);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v53);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18004aec0  push    rbp
0x18004aec2  push    rbx
0x18004aec3  push    rdi
0x18004aec4  push    r12
0x18004aec6  push    r13
0x18004aec8  push    r14
0x18004aeca  push    r15
0x18004aecc  lea     rbp, [rsp-27h]
0x18004aed1  sub     rsp, 0B0h
0x18004aed8  mov     rax, cs:__security_cookie
0x18004aedf  xor     rax, rsp
0x18004aee2  mov     [rbp+57h+var_40], rax
0x18004aee6  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004aeed  xor     r13d, r13d
0x18004aef0  mov     r12, r8
0x18004aef3  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x18004aefa  mov     [r8], r13
0x18004aefd  lea     rbx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004af04  mov     r15, rdx
0x18004af07  mov     [rbp+57h+var_80], r13
0x18004af0b  mov     r14, rcx
0x18004af0e  mov     [rbp+57h+var_88], r13
0x18004af12  mov     r8d, 2D7h; int
0x18004af18  mov     [rbp+57h+var_98], r13
0x18004af1c  mov     rdx, rbx; char *
0x18004af1f  mov     [rbp+57h+var_68], r13
0x18004af23  lea     rcx, [rbp+57h+var_B0]; this
0x18004af27  mov     [rbp+57h+var_90], r13
0x18004af2b  movdqu  [rbp+57h+var_50], xmm0
0x18004af30  mov     [rbp+57h+var_A8], r13
0x18004af34  movdqu  [rbp+57h+Buf1], xmm1
0x18004af39  mov     [rbp+57h+var_70], r13
0x18004af3d  mov     [rbp+57h+var_78], r13
0x18004af41  mov     [rbp+57h+var_9C], r13d
0x18004af45  mov     [rbp+57h+var_A0], r13d
0x18004af49  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004af4e  lea     rax, [rbp+57h+var_80]
0x18004af52  xor     edx, edx; pUnkOuter
0x18004af54  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18004af5b  mov     [rsp+0E0h+ppv], rax; ppv
0x18004af60  lea     r8d, [r13+17h]; dwClsContext
0x18004af64  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18004af6b  call    cs:__imp_CoCreateInstance
0x18004af71  mov     edi, eax
0x18004af73  test    eax, eax
0x18004af75  jns     short loc_18004AFCD
0x18004af77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af7e  test    rcx, rcx
0x18004af81  jnz     short loc_18004AF8F
0x18004af83  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004af88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004af8f  cmp     [rcx+8], r13b
0x18004af93  jz      short loc_18004AFB6
0x18004af95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004af9a  cmp     [rax+7CCh], edi
0x18004afa0  jz      short loc_18004AFB6
0x18004afa2  mov     r9d, edi; int
0x18004afa5  mov     r8d, 2D7h; int
0x18004afab  mov     rdx, rbx; char *
0x18004afae  mov     rcx, rax; this
0x18004afb1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004afb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004afbd  jb      loc_18004B866
0x18004afc3  mov     edx, 42h ; 'B'
0x18004afc8  jmp     loc_18004B848
0x18004afcd  mov     rcx, [rbp+57h+var_80]
0x18004afd1  lea     rdx, [rbp+57h+var_88]
0x18004afd5  mov     [rsp+0E0h+ppv], rdx
0x18004afda  lea     r8, GUID_VendorMicrosoft
0x18004afe1  xor     r9d, r9d
0x18004afe4  mov     rdx, r15
0x18004afe7  mov     rax, [rcx]
0x18004afea  mov     rax, [rax+20h]
0x18004afee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aff3  mov     edi, eax
0x18004aff5  test    eax, eax
0x18004aff7  jns     short loc_18004B04F
0x18004aff9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b000  test    rcx, rcx
0x18004b003  jnz     short loc_18004B011
0x18004b005  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b00a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b011  cmp     [rcx+8], r13b
0x18004b015  jz      short loc_18004B038
0x18004b017  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b01c  cmp     [rax+7CCh], edi
0x18004b022  jz      short loc_18004B038
0x18004b024  mov     r9d, edi; int
0x18004b027  mov     r8d, 2D9h; int
0x18004b02d  mov     rdx, rbx; char *
0x18004b030  mov     rcx, rax; this
0x18004b033  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b038  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b03f  jb      loc_18004B866
0x18004b045  mov     edx, 43h ; 'C'
0x18004b04a  jmp     loc_18004B848
0x18004b04f  mov     rcx, [rbp+57h+var_88]
0x18004b053  lea     rdx, [rbp+57h+Buf1]
0x18004b057  mov     rax, [rcx]
0x18004b05a  mov     rax, [rax+28h]
0x18004b05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b063  mov     edi, eax
0x18004b065  test    eax, eax
0x18004b067  jns     short loc_18004B0BF
0x18004b069  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b070  test    rcx, rcx
0x18004b073  jnz     short loc_18004B081
0x18004b075  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b07a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b081  cmp     [rcx+8], r13b
0x18004b085  jz      short loc_18004B0A8
0x18004b087  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b08c  cmp     [rax+7CCh], edi
0x18004b092  jz      short loc_18004B0A8
0x18004b094  mov     r9d, edi; int
0x18004b097  mov     r8d, 2DBh; int
0x18004b09d  mov     rdx, rbx; char *
0x18004b0a0  mov     rcx, rax; this
0x18004b0a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b0a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b0af  jb      loc_18004B866
0x18004b0b5  mov     edx, 44h ; 'D'
0x18004b0ba  jmp     loc_18004B848
0x18004b0bf  mov     r8, r12; ppstm
0x18004b0c2  mov     edx, 1; fDeleteOnRelease
0x18004b0c7  xor     ecx, ecx; hGlobal
0x18004b0c9  call    cs:__imp_CreateStreamOnHGlobal
0x18004b0cf  mov     edi, eax
0x18004b0d1  test    eax, eax
0x18004b0d3  jns     short loc_18004B12B
0x18004b0d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b0dc  test    rcx, rcx
0x18004b0df  jnz     short loc_18004B0ED
0x18004b0e1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b0e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b0ed  cmp     [rcx+8], r13b
0x18004b0f1  jz      short loc_18004B114
0x18004b0f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b0f8  cmp     [rax+7CCh], edi
0x18004b0fe  jz      short loc_18004B114
0x18004b100  mov     r9d, edi; int
0x18004b103  mov     r8d, 2DDh; int
0x18004b109  mov     rdx, rbx; char *
0x18004b10c  mov     rcx, rax; this
0x18004b10f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b114  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b11b  jb      loc_18004B866
0x18004b121  mov     edx, 45h ; 'E'
0x18004b126  jmp     loc_18004B848
0x18004b12b  mov     r8d, 10h; Size
0x18004b131  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x18004b138  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18004b13c  mov     rbx, r13
0x18004b13f  call    memcmp_0
0x18004b144  test    eax, eax
0x18004b146  jz      loc_18004B668
0x18004b14c  mov     rcx, [rbp+57h+var_88]
0x18004b150  lea     r8, [rbp+57h+var_90]
0x18004b154  xor     edx, edx
0x18004b156  mov     rax, [rcx]
0x18004b159  mov     rax, [rax+68h]
0x18004b15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b162  mov     edi, eax
0x18004b164  test    eax, eax
0x18004b166  jns     short loc_18004B1C2
0x18004b168  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b16f  test    rcx, rcx
0x18004b172  jnz     short loc_18004B180
0x18004b174  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b179  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b180  cmp     [rcx+8], r13b
0x18004b184  jz      short loc_18004B1AB
0x18004b186  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b18b  cmp     [rax+7CCh], edi
0x18004b191  jz      short loc_18004B1AB
0x18004b193  mov     r9d, edi; int
0x18004b196  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004b19d  mov     r8d, 2E1h; int
0x18004b1a3  mov     rcx, rax; this
0x18004b1a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b1ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b1b2  jb      loc_18004B866
0x18004b1b8  mov     edx, 46h ; 'F'
0x18004b1bd  jmp     loc_18004B848
0x18004b1c2  mov     rcx, [rbp+57h+var_90]
0x18004b1c6  lea     r8, [rbp+57h+var_A0]
0x18004b1ca  lea     rdx, [rbp+57h+var_9C]
0x18004b1ce  mov     rax, [rcx]
0x18004b1d1  mov     rax, [rax+18h]
0x18004b1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1da  mov     edi, eax
0x18004b1dc  test    eax, eax
0x18004b1de  jns     short loc_18004B23A
0x18004b1e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b1e7  test    rcx, rcx
0x18004b1ea  jnz     short loc_18004B1F8
0x18004b1ec  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b1f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b1f8  cmp     [rcx+8], r13b
0x18004b1fc  jz      short loc_18004B223
0x18004b1fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b203  cmp     [rax+7CCh], edi
0x18004b209  jz      short loc_18004B223
0x18004b20b  mov     r9d, edi; int
0x18004b20e  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004b215  mov     r8d, 2E3h; int
0x18004b21b  mov     rcx, rax; this
0x18004b21e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b223  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b22a  jb      loc_18004B866
0x18004b230  mov     edx, 47h ; 'G'
0x18004b235  jmp     loc_18004B848
0x18004b23a  mov     rcx, [rbp+57h+var_80]
0x18004b23e  lea     r9, [rbp+57h+var_98]
0x18004b242  lea     r8, GUID_VendorMicrosoft
0x18004b249  lea     rdx, GUID_ContainerFormatJpeg
0x18004b250  mov     rax, [rcx]
0x18004b253  mov     rax, [rax+40h]
0x18004b257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b25c  mov     edi, eax
0x18004b25e  test    eax, eax
0x18004b260  jns     short loc_18004B2BC
0x18004b262  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b269  test    rcx, rcx
0x18004b26c  jnz     short loc_18004B27A
0x18004b26e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b273  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b27a  cmp     [rcx+8], r13b
0x18004b27e  jz      short loc_18004B2A5
0x18004b280  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b285  cmp     [rax+7CCh], edi
0x18004b28b  jz      short loc_18004B2A5
0x18004b28d  mov     r9d, edi; int
0x18004b290  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004b297  mov     r8d, 2EAh; int
0x18004b29d  mov     rcx, rax; this
0x18004b2a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b2a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b2ac  jb      loc_18004B866
0x18004b2b2  mov     edx, 48h ; 'H'
0x18004b2b7  jmp     loc_18004B848
0x18004b2bc  mov     rcx, [rbp+57h+var_98]
0x18004b2c0  mov     r8d, 2
0x18004b2c6  mov     rdx, [r12]
0x18004b2ca  mov     rax, [rcx]
0x18004b2cd  mov     rax, [rax+18h]
0x18004b2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2d6  mov     edi, eax
0x18004b2d8  test    eax, eax
0x18004b2da  jns     short loc_18004B336
0x18004b2dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2e3  test    rcx, rcx
0x18004b2e6  jnz     short loc_18004B2F4
0x18004b2e8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b2ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b2f4  cmp     [rcx+8], r13b
0x18004b2f8  jz      short loc_18004B31F
0x18004b2fa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b2ff  cmp     [rax+7CCh], edi
0x18004b305  jz      short loc_18004B31F
0x18004b307  mov     r9d, edi; int
0x18004b30a  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004b311  mov     r8d, 2EFh; int
0x18004b317  mov     rcx, rax; this
0x18004b31a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b31f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b326  jb      loc_18004B866
0x18004b32c  mov     edx, 49h ; 'I'
0x18004b331  jmp     loc_18004B848
0x18004b336  mov     rcx, [rbp+57h+var_98]
0x18004b33a  lea     r8, [rbp+57h+var_78]
0x18004b33e  lea     rdx, [rbp+57h+var_A8]
0x18004b342  mov     rax, [rcx]
0x18004b345  mov     rax, [rax+50h]
0x18004b349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b34e  mov     edi, eax
0x18004b350  test    eax, eax
0x18004b352  jns     short loc_18004B3AE
0x18004b354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b35b  test    rcx, rcx
0x18004b35e  jnz     short loc_18004B36C
0x18004b360  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004b365  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b36c  cmp     [rcx+8], r13b
0x18004b370  jz      short loc_18004B397
0x18004b372  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b377  cmp     [rax+7CCh], edi
0x18004b37d  jz      short loc_18004B397
0x18004b37f  mov     r9d, edi; int
0x18004b382  lea     rdx, aCwmthumbnailst; "CWMThumbnailStreamProperty::ReencodeThu"...
0x18004b389  mov     r8d, 2F1h; int
0x18004b38f  mov     rcx, rax; this
0x18004b392  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b397  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b39e  jb      loc_18004B866
0x18004b3a4  mov     edx, 4Ah ; 'J'
0x18004b3a9  jmp     loc_18004B848
0x18004b3ae  mov     rcx, [rbp+57h+var_A8]
0x18004b3b2  mov     rdx, [rbp+57h+var_78]
0x18004b3b6  mov     rax, [rcx]
  ... truncated ...
```
