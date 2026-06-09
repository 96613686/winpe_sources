# CRawImageReader::GetExifMetadata(IStream * *,bool *)

- ea: `0x1800a98c0`
- end: `0x1800aa7dd`
- name: `?GetExifMetadata@CRawImageReader@@UEAAJPEAPEAUIStream@@PEA_N@Z`
- size: `3869`
- prototype: `__int64 __fastcall(CRawImageReader *__hidden this, struct IStream **, bool *)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180002040`
- `0x1800020a0`
- `0x1800020f0`
- `0x1800023a0`
- `0x180002590`
- `0x180002a00`
- `0x18009b9e4`
- `0x18009c44c`
- `0x18009e8b8`
- `0x1800a34f8`
- `0x1800a98c0`
- `0x1800ae338`
- `0x1800ae6b8`
- `0x1800af3f0`
- `0x1800afeb8`
- `0x1800aff40`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9dfb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9dfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9e8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa78f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a9e8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aa78f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a99ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a99ad`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a9e9f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a9e9f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a9dbf`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a9dbf`

## string_xrefs

- `0x1800a99d4`: `CRawImageReader::VerifyImageOpened`
- `0x1800a9a53`: `CRawImageReader::VerifyImageOpened`
- `0x1800a9ac0`: `avcore\mf\rawimage\rawimagereader\RawImageReader.h`
- `0x1800a9902`: `CRawImageReader::GetExifMetadata`
- `0x1800a998c`: `CRawImageReader::GetExifMetadata`
- `0x1800a9b9e`: `CRawImageReader::GetExifMetadata`
- `0x1800a9e7b`: `CRawImageReader::GetExifMetadata`
- `0x1800aa77c`: `CRawImageReader::GetExifMetadata`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRawImageReader::GetExifMetadata(CRawImageReader *this, struct IStream **a2, bool *a3)
{
  int *v6; // r9
  struct CallStackContext *ThreadRelativeContext; // rbx
  int v8; // edi
  unsigned int *v9; // r13
  int *v10; // r9
  struct CallStackContext *v11; // rdi
  int v12; // r14d
  HRESULT StreamOnHGlobal; // edi
  void ***v14; // rcx
  struct CallStackContext *v15; // rax
  void ***v16; // rcx
  struct CallStackContext *v17; // rax
  int v18; // r8d
  unsigned __int64 v19; // r8
  HRESULT v20; // eax
  int v21; // r9d
  int v22; // r10d
  __int64 v23; // r11
  void ***v24; // rcx
  unsigned __int16 v25; // r13
  void ***v26; // rcx
  struct CallStackContext *v27; // rax
  void ***v28; // rcx
  void ***v29; // rcx
  void ***v30; // rcx
  void ***v31; // rcx
  void ***v32; // rcx
  void ***v33; // rcx
  void ***v34; // rcx
  void ***v35; // rcx
  void ***v36; // rcx
  void ***v37; // rcx
  __int64 v38; // rcx
  void ***v39; // rcx
  __int64 v40; // rcx
  struct IStream **v41; // r13
  void ***v42; // rcx
  struct IStream *v43; // rcx
  void ***v44; // rcx
  struct CallStackContext *v45; // rax
  const char *v46; // r9
  __int64 result; // rax
  int v48; // [rsp+20h] [rbp-E8h]
  int v49; // [rsp+20h] [rbp-E8h]
  DWORD pusResult; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v51[4]; // [rsp+44h] [rbp-C4h] BYREF
  HGLOBAL hGlobal; // [rsp+48h] [rbp-C0h] BYREF
  union _LARGE_INTEGER v53; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v54; // [rsp+58h] [rbp-B0h] BYREF
  union _LARGE_INTEGER v55; // [rsp+60h] [rbp-A8h] BYREF
  struct IStream **v56; // [rsp+68h] [rbp-A0h]
  __int64 v57; // [rsp+70h] [rbp-98h]
  _BYTE v58[32]; // [rsp+78h] [rbp-90h] BYREF
  union _LARGE_INTEGER v59; // [rsp+98h] [rbp-70h] BYREF
  char *v60; // [rsp+B8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v57 = -2;
  v56 = a2;
  try
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v51, "CRawImageReader::GetExifMetadata", 690);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char **))(**((_QWORD **)this + 34) + 280LL))(
                                                              *((_QWORD *)this + 34),
                                                              &v60);
      *((_DWORD *)ThreadRelativeContext + 504) = v8;
    }
    v9 = (unsigned int *)((char *)this + 56);
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)v58,
      (struct CTraceBase *)(((unsigned __int64)this + 56) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
      "CRawImageReader::GetExifMetadata",
      v6,
      v48);
    v60 = (char *)this + 64;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    ++*((_DWORD *)this + 259);
    *a2 = 0;
    *a3 = *((_BYTE *)this + 107);
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&pusResult,
      "CRawImageReader::VerifyImageOpened",
      88);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 34) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 34) + 296LL))(*((_QWORD *)this + 34));
      *((_OWORD *)v11 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER *))(**((_QWORD **)this + 34) + 280LL))(
                                            *((_QWORD *)this + 34),
                                            &v59);
      *((_DWORD *)v11 + 504) = v12;
    }
    StreamOnHGlobal = 0;
    CTraceBase::CAutoTrace::CAutoTrace(
      (CTraceBase::CAutoTrace *)&v59,
      (CRawImageReader *)((char *)this + 56),
      "CRawImageReader::VerifyImageOpened",
      v10,
      v49);
    if ( !*((_BYTE *)this + 108) )
    {
      StreamOnHGlobal = -2147418113;
      v14 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v15 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v15, "CRawImageReader::VerifyImageOpened", 89, -2147418113);
      }
      CTraceBase::OutputMsg(
        (CRawImageReader *)((char *)this + 56),
        1u,
        1u,
        "%s failed(0x%X) at line %d in file %s",
        "CRawImageReader::VerifyImageOpened",
        -2147418113,
        89,
        "avcore\\mf\\rawimage\\rawimagereader\\RawImageReader.h");
    }
    CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)&v59);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&pusResult);
    if ( StreamOnHGlobal < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v9,
          StreamOnHGlobal);
      }
      v16 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v16 + 8) )
        goto LABEL_202;
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
      if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
        goto LABEL_202;
      v18 = 697;
      goto LABEL_25;
    }
    if ( *((_QWORD *)this + 31) )
      goto LABEL_181;
    v19 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3);
    if ( !v19
      && *((_QWORD *)this + 23) == *((_QWORD *)this + 22)
      && !(0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)) >> 3)) )
    {
      goto LABEL_181;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)) >> 3),
        v19,
        *v9,
        v19,
        -858993459 * ((__int64)(*((_QWORD *)this + 23) - *((_QWORD *)this + 22)) >> 3),
        -858993459 * ((__int64)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)) >> 3));
    }
    *((_DWORD *)this + 33) += 6;
    LOWORD(pusResult) = 0;
    v20 = UIntPtrToUShort(
            0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 26) - *((_QWORD *)this + 25)) >> 3),
            (USHORT *)&pusResult);
    StreamOnHGlobal = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && ((unsigned __int8)(v22 + 1) & *((_BYTE *)WPP_GLOBAL_Control + 28)) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(v22 + 54),
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *v9,
          v20);
        LOBYTE(v22) = 0;
      }
      v24 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v24 + 8) == (_BYTE)v22 )
        goto LABEL_202;
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
        goto LABEL_202;
      v18 = 710;
      goto LABEL_25;
    }
    v25 = pusResult;
    if ( v23 * ((__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3) )
    {
      v21 += 12;
      *((_DWORD *)this + 33) = v21;
      *((_DWORD *)this + 31) += 6;
      ++v25;
    }
    if ( v23 * ((__int64)(*((_QWORD *)this + 23) - *((_QWORD *)this + 22)) >> 3) )
    {
      v21 += 12;
      *((_DWORD *)this + 33) = v21;
      *((_DWORD *)this + 32) += 6;
      ++v25;
    }
    hGlobal = GlobalAlloc(0, (unsigned int)(v21 + *((_DWORD *)this + 32) + *((_DWORD *)this + 31)));
    if ( !hGlobal )
    {
      StreamOnHGlobal = -2147024882;
      goto LABEL_202;
    }
    Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease((char *)this + 248);
    StreamOnHGlobal = CreateStreamOnHGlobal(hGlobal, 1, (LPSTREAM *)this + 31);
    if ( StreamOnHGlobal < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          StreamOnHGlobal);
      }
      v26 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v27 + 499) != StreamOnHGlobal )
          CallStackContext::TraceFailure(v27, "CRawImageReader::GetExifMetadata", 732, StreamOnHGlobal);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
      GlobalFree(hGlobal);
      goto LABEL_203;
    }
    v53.QuadPart = 0;
    v55.QuadPart = 0;
    v59.QuadPart = 0;
    v54 = 0;
    StreamOnHGlobal = CRawImageReader::WriteTopIFDEntry(this, &v53, &v54, v25, &v55, &v59);
    if ( StreamOnHGlobal < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          StreamOnHGlobal);
      }
      v28 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v28 + 8) )
        goto LABEL_202;
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
      if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
        goto LABEL_202;
      v18 = 740;
      goto LABEL_25;
    }
    LOWORD(pusResult) = 0;
    StreamOnHGlobal = UIntPtrToUShort(
                        0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3),
                        (USHORT *)&pusResult);
    if ( StreamOnHGlobal < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          StreamOnHGlobal);
      }
      v29 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v29 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v29 + 8) )
        goto LABEL_202;
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
        goto LABEL_202;
      v18 = 743;
      goto LABEL_25;
    }
    if ( (_WORD)pusResult )
    {
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER, _QWORD, _QWORD))(**((_QWORD **)this + 31)
                                                                                                + 40LL))(
                          *((_QWORD *)this + 31),
                          v55,
                          0,
                          0);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v30 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v30 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 747;
        goto LABEL_25;
      }
      if ( *((_BYTE *)this + 107) )
      {
        LOBYTE(pusResult) = BYTE3(v53.QuadPart);
        BYTE1(pusResult) = BYTE2(v53.u.LowPart);
        BYTE2(pusResult) = BYTE1(v53.LowPart);
        HIBYTE(pusResult) = v53.LowPart;
      }
      else
      {
        pusResult = v53.LowPart;
      }
      LODWORD(hGlobal) = 0;
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, DWORD *, __int64, HGLOBAL *))(**((_QWORD **)this + 31) + 32LL))(
                          *((_QWORD *)this + 31),
                          &pusResult,
                          4,
                          &hGlobal);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v31 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v31 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 751;
        goto LABEL_25;
      }
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER, _QWORD, _QWORD))(**((_QWORD **)this + 31)
                                                                                                + 40LL))(
                          *((_QWORD *)this + 31),
                          v53,
                          0,
                          0);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v32 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v32 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 753;
        goto LABEL_25;
      }
      StreamOnHGlobal = CRawImageReader::WriteSubIFDEntry(this);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            61,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v33 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v33 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 754;
        goto LABEL_25;
      }
      std::vector<CRawImageReader::IFDDataEntry>::clear((char *)this + 152);
    }
    if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 23) - *((_QWORD *)this + 22)) >> 3) )
    {
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER, _QWORD, _QWORD))(**((_QWORD **)this + 31)
                                                                                                + 40LL))(
                          *((_QWORD *)this + 31),
                          v59,
                          0,
                          0);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v34 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v34 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 761;
        goto LABEL_25;
      }
      if ( *((_BYTE *)this + 107) )
      {
        LOBYTE(pusResult) = BYTE3(v53.QuadPart);
        BYTE1(pusResult) = BYTE2(v53.u.LowPart);
        BYTE2(pusResult) = BYTE1(v53.LowPart);
        HIBYTE(pusResult) = v53.LowPart;
      }
      else
      {
        pusResult = v53.LowPart;
      }
      LODWORD(hGlobal) = 0;
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, DWORD *, __int64, HGLOBAL *))(**((_QWORD **)this + 31) + 32LL))(
                          *((_QWORD *)this + 31),
                          &pusResult,
                          4,
                          &hGlobal);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v35 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v35 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 765;
        goto LABEL_25;
      }
      StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, union _LARGE_INTEGER, _QWORD, _QWORD))(**((_QWORD **)this + 31)
                                                                                                + 40LL))(
                          *((_QWORD *)this + 31),
                          v53,
                          0,
                          0);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v36 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v36 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 767;
        goto LABEL_25;
      }
      StreamOnHGlobal = CRawImageReader::WriteSubIFDEntry(this);
      if ( StreamOnHGlobal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
            *((unsigned int *)this + 14),
            StreamOnHGlobal);
        }
        v37 = (void ***)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = &off_1800E5190;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
        }
        if ( !*((_BYTE *)v37 + 8) )
          goto LABEL_202;
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
          goto LABEL_202;
        v18 = 768;
        goto LABEL_25;
      }
      std::vector<CRawImageReader::IFDDataEntry>::clear((char *)this + 176);
    }
    v38 = *((_QWORD *)this + 31);
    hGlobal = 0;
    StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v38 + 40LL))(v38, 0, 0, 0);
    if ( StreamOnHGlobal >= 0 )
    {
LABEL_181:
      v40 = *((_QWORD *)this + 31);
      if ( !v40 )
        goto LABEL_202;
      v41 = v56;
      StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v40 + 104LL))(v40, v56);
      if ( StreamOnHGlobal >= 0 )
      {
        v43 = *v41;
        v59.QuadPart = 0;
        StreamOnHGlobal = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))v43->lpVtbl->Seek)(
                            v43,
                            0,
                            0,
                            0);
        if ( StreamOnHGlobal < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
              *((unsigned int *)this + 14),
              StreamOnHGlobal);
          }
          v44 = (void ***)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v44 = &off_1800E5190;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
          }
          if ( *((_BYTE *)v44 + 8) )
          {
            v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v45 + 499) != StreamOnHGlobal )
              CallStackContext::TraceFailure(v45, "CRawImageReader::GetExifMetadata", 781, StreamOnHGlobal);
          }
        }
        goto LABEL_202;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          StreamOnHGlobal);
      }
      v42 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v42 + 8)
        || (v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42),
            *((_DWORD *)v17 + 499) == StreamOnHGlobal) )
      {
LABEL_202:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
LABEL_203:
        CTraceBase::CAutoTrace::~CAutoTrace((CTraceBase::CAutoTrace *)v58);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
        return (unsigned int)StreamOnHGlobal;
      }
      v18 = 780;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          &WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids,
          *((unsigned int *)this + 14),
          StreamOnHGlobal);
      }
      v39 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = &off_1800E5190;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&off_1800E5190;
      }
      if ( !*((_BYTE *)v39 + 8) )
        goto LABEL_202;
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v17 + 499) == StreamOnHGlobal )
        goto LABEL_202;
      v18 = 775;
    }
LABEL_25:
    CallStackContext::TraceFailure(v17, "CRawImageReader::GetExifMetadata", v18, StreamOnHGlobal);
    goto LABEL_202;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x319,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           v46);
  }
  return result;
}

```

## disassembly

```asm
0x1800a98c0  push    rbx
0x1800a98c2  push    rsi
0x1800a98c3  push    rdi
0x1800a98c4  push    r12
0x1800a98c6  push    r13
0x1800a98c8  push    r14
0x1800a98ca  push    r15
0x1800a98cc  sub     rsp, 0D0h
0x1800a98d3  mov     [rsp+108h+var_98], 0FFFFFFFFFFFFFFFEh
0x1800a98dc  mov     rax, cs:__security_cookie
0x1800a98e3  xor     rax, rsp
0x1800a98e6  mov     [rsp+108h+var_40], rax
0x1800a98ee  mov     r14, r8
0x1800a98f1  mov     r15, rdx
0x1800a98f4  mov     [rsp+108h+var_A0], rdx
0x1800a98f9  mov     rsi, rcx
0x1800a98fc  mov     r8d, 2B2h; int
0x1800a9902  lea     rdx, aCrawimagereade_16; "CRawImageReader::GetExifMetadata"
0x1800a9909  lea     rcx, [rsp+108h+var_C4]; this
0x1800a990e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9913  nop
0x1800a9914  xor     r12d, r12d
0x1800a9917  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a991e  cmp     [rcx+8], r12b
0x1800a9922  jz      short loc_1800A997C
0x1800a9924  cmp     [rsi+110h], r12
0x1800a992b  jz      short loc_1800A997C
0x1800a992d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9932  mov     rbx, rax
0x1800a9935  mov     rcx, [rsi+110h]
0x1800a993c  mov     rdx, [rcx]
0x1800a993f  mov     rax, [rdx+128h]
0x1800a9946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a994b  mov     edi, eax
0x1800a994d  mov     rcx, [rsi+110h]
0x1800a9954  mov     rdx, [rcx]
0x1800a9957  mov     rax, [rdx+118h]
0x1800a995e  lea     rdx, [rsp+108h+var_50]
0x1800a9966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a996b  movups  xmm0, xmmword ptr [rax]
0x1800a996e  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x1800a9976  mov     [rbx+7E0h], edi
0x1800a997c  lea     r13, [rsi+38h]
0x1800a9980  mov     rax, rsi
0x1800a9983  neg     rax
0x1800a9986  sbb     rdx, rdx
0x1800a9989  and     rdx, r13; struct CTraceBase *
0x1800a998c  lea     r8, aCrawimagereade_16; "CRawImageReader::GetExifMetadata"
0x1800a9993  lea     rcx, [rsp+108h+var_90]; this
0x1800a9998  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a999d  nop
0x1800a999e  lea     rbx, [rsi+40h]
0x1800a99a2  mov     [rsp+108h+var_50], rbx
0x1800a99aa  mov     rcx, rbx; lpCriticalSection
0x1800a99ad  call    cs:__imp_EnterCriticalSection
0x1800a99b4  nop     dword ptr [rax+rax+00h]
0x1800a99b9  nop
0x1800a99ba  mov     eax, 1
0x1800a99bf  add     [rsi+40Ch], eax
0x1800a99c5  mov     [r15], r12
0x1800a99c8  mov     al, [rsi+6Bh]
0x1800a99cb  mov     [r14], al
0x1800a99ce  mov     r8d, 58h ; 'X'; int
0x1800a99d4  lea     r14, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800a99db  mov     rdx, r14; char *
0x1800a99de  lea     rcx, [rsp+108h+pusResult]; this
0x1800a99e3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a99e8  nop
0x1800a99e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a99f0  xor     r15d, r15d
0x1800a99f3  cmp     [rcx+8], r15b
0x1800a99f7  jz      short loc_1800A9A5A
0x1800a99f9  cmp     [rsi+110h], r15
0x1800a9a00  jz      short loc_1800A9A5A
0x1800a9a02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9a07  mov     rdi, rax
0x1800a9a0a  mov     rcx, [rsi+110h]
0x1800a9a11  mov     rdx, [rcx]
0x1800a9a14  mov     rax, [rdx+128h]
0x1800a9a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a20  mov     r14d, eax
0x1800a9a23  mov     rcx, [rsi+110h]
0x1800a9a2a  mov     rdx, [rcx]
0x1800a9a2d  mov     rax, [rdx+118h]
0x1800a9a34  lea     rdx, [rsp+108h+var_70]
0x1800a9a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a41  movups  xmm0, xmmword ptr [rax]
0x1800a9a44  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800a9a4c  mov     [rdi+7E0h], r14d
0x1800a9a53  lea     r14, aCrawimagereade_26; "CRawImageReader::VerifyImageOpened"
0x1800a9a5a  mov     edi, r15d
0x1800a9a5d  mov     r8, r14; char *
0x1800a9a60  mov     rdx, r13; struct CTraceBase *
0x1800a9a63  lea     rcx, [rsp+108h+var_70]; this
0x1800a9a6b  call    ??0CAutoTrace@CTraceBase@@QEAA@PEAV1@PEBDPEAJH@Z; CTraceBase::CAutoTrace::CAutoTrace(CTraceBase *,char const *,long *,int)
0x1800a9a70  nop
0x1800a9a71  lea     r12, off_1800E5190
0x1800a9a78  cmp     [rsi+6Ch], r15b
0x1800a9a7c  jnz     short loc_1800A9AFA
0x1800a9a7e  mov     edi, 8000FFFFh
0x1800a9a83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a8a  test    rcx, rcx
0x1800a9a8d  jnz     short loc_1800A9A99
0x1800a9a8f  mov     rcx, r12; this
0x1800a9a92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a99  cmp     [rcx+8], r15b
0x1800a9a9d  jz      short loc_1800A9AC0
0x1800a9a9f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9aa4  cmp     [rax+7CCh], edi
0x1800a9aaa  jz      short loc_1800A9AC0
0x1800a9aac  mov     r9d, edi; int
0x1800a9aaf  mov     r8d, 59h ; 'Y'; int
0x1800a9ab5  mov     rdx, r14; char *
0x1800a9ab8  mov     rcx, rax; this
0x1800a9abb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9ac0  lea     rax, aAvcoreMfRawima; "avcore\\mf\\rawimage\\rawimagereader\\R"...
0x1800a9ac7  mov     [rsp+108h+var_D0], rax
0x1800a9acc  mov     [rsp+108h+var_D8], 59h ; 'Y'
0x1800a9ad4  mov     dword ptr [rsp+108h+var_E0], edi
0x1800a9ad8  mov     [rsp+108h+var_E8], r14
0x1800a9add  lea     r9, aSFailed0xXAtLi; "%s failed(0x%X) at line %d in file %s"
0x1800a9ae4  mov     r14d, 1
0x1800a9aea  mov     r8d, r14d; unsigned int
0x1800a9aed  mov     edx, r14d; unsigned int
0x1800a9af0  mov     rcx, r13; this
0x1800a9af3  call    ?OutputMsg@CTraceBase@@QEAA_NKKPEBDZZ; CTraceBase::OutputMsg(ulong,ulong,char const *,...)
0x1800a9af8  jmp     short loc_1800A9B00
0x1800a9afa  mov     r14d, 1
0x1800a9b00  lea     rcx, [rsp+108h+var_70]; this
0x1800a9b08  call    ??1CAutoTrace@CTraceBase@@QEAA@XZ; CTraceBase::CAutoTrace::~CAutoTrace(void)
0x1800a9b0d  nop
0x1800a9b0e  lea     rcx, [rsp+108h+pusResult]; this
0x1800a9b13  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a9b18  test    edi, edi
0x1800a9b1a  jns     loc_1800A9BB2
0x1800a9b20  lea     r15, WPP_GLOBAL_Control
0x1800a9b27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9b2e  cmp     rcx, r15
0x1800a9b31  jz      short loc_1800A9B61
0x1800a9b33  test    [rcx+1Ch], r14b
0x1800a9b37  jz      short loc_1800A9B61
0x1800a9b39  mov     r14d, 4
0x1800a9b3f  cmp     [rcx+19h], r14b
0x1800a9b43  jb      short loc_1800A9B61
0x1800a9b45  lea     edx, [r14+30h]
0x1800a9b49  mov     dword ptr [rsp+108h+var_E8], edi
0x1800a9b4d  mov     r9d, [r13+0]
0x1800a9b51  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a9b58  mov     rcx, [rcx+10h]
0x1800a9b5c  call    WPP_SF_Dd
0x1800a9b61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b68  xor     r8d, r8d
0x1800a9b6b  test    rcx, rcx
0x1800a9b6e  jnz     short loc_1800A9B7A
0x1800a9b70  mov     rcx, r12; this
0x1800a9b73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b7a  cmp     [rcx+8], r8b
0x1800a9b7e  jz      loc_1800AA78C
0x1800a9b84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9b89  cmp     [rax+7CCh], edi
0x1800a9b8f  jz      loc_1800AA78C
0x1800a9b95  mov     r8d, 2B9h; int
0x1800a9b9b  mov     r9d, edi; int
0x1800a9b9e  lea     rdx, aCrawimagereade_16; "CRawImageReader::GetExifMetadata"
0x1800a9ba5  mov     rcx, rax; this
0x1800a9ba8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9bad  jmp     loc_1800AA78C
0x1800a9bb2  cmp     [rsi+0F8h], r15
0x1800a9bb9  jnz     loc_1800AA63F
0x1800a9bbf  mov     r8, [rsi+0A0h]
0x1800a9bc6  sub     r8, [rsi+98h]
0x1800a9bcd  sar     r8, 3
0x1800a9bd1  mov     r11, 0CCCCCCCCCCCCCCCDh
0x1800a9bdb  imul    r8, r11
0x1800a9bdf  test    r8, r8
0x1800a9be2  jnz     short loc_1800A9C13
0x1800a9be4  mov     rax, [rsi+0B8h]
0x1800a9beb  cmp     rax, [rsi+0B0h]
0x1800a9bf2  jnz     short loc_1800A9C13
0x1800a9bf4  mov     rax, [rsi+0D0h]
0x1800a9bfb  sub     rax, [rsi+0C8h]
0x1800a9c02  sar     rax, 3
0x1800a9c06  imul    rax, r11
0x1800a9c0a  test    rax, rax
0x1800a9c0d  jz      loc_1800AA63F
0x1800a9c13  lea     r15, WPP_GLOBAL_Control
0x1800a9c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9c21  cmp     rcx, r15
0x1800a9c24  jz      short loc_1800A9C8A
0x1800a9c26  test    [rcx+1Ch], r14b
0x1800a9c2a  jz      short loc_1800A9C8A
0x1800a9c2c  mov     r14d, 4
0x1800a9c32  cmp     [rcx+19h], r14b
0x1800a9c36  jb      short loc_1800A9C90
0x1800a9c38  mov     rdx, [rsi+0D0h]
0x1800a9c3f  sub     rdx, [rsi+0C8h]
0x1800a9c46  sar     rdx, 3
0x1800a9c4a  imul    rdx, r11
0x1800a9c4e  mov     rax, [rsi+0B8h]
0x1800a9c55  sub     rax, [rsi+0B0h]
0x1800a9c5c  sar     rax, 3
0x1800a9c60  imul    rax, r11
0x1800a9c64  mov     [rsp+108h+var_D8], edx
0x1800a9c68  mov     dword ptr [rsp+108h+var_E0], eax
0x1800a9c6c  mov     dword ptr [rsp+108h+var_E8], r8d
0x1800a9c71  mov     r9d, [r13+0]
0x1800a9c75  mov     rcx, [rcx+10h]
0x1800a9c79  call    WPP_SF_DDDD
0x1800a9c7e  mov     r11, 0CCCCCCCCCCCCCCCDh
0x1800a9c88  jmp     short loc_1800A9C90
0x1800a9c8a  mov     r14d, 4
0x1800a9c90  mov     r9d, [rsi+84h]
0x1800a9c97  add     r9d, 6
0x1800a9c9b  mov     [rsi+84h], r9d
0x1800a9ca2  xor     r10d, r10d
0x1800a9ca5  mov     [rsp+108h+pusResult], r10w
0x1800a9cab  mov     rcx, [rsi+0D0h]
0x1800a9cb2  sub     rcx, [rsi+0C8h]
0x1800a9cb9  sar     rcx, 3
0x1800a9cbd  imul    rcx, r11; uOperand
0x1800a9cc1  lea     rdx, [rsp+108h+pusResult]; pusResult
0x1800a9cc6  call    UIntPtrToUShort
0x1800a9ccb  mov     edi, eax
0x1800a9ccd  test    eax, eax
0x1800a9ccf  jns     short loc_1800A9D47
0x1800a9cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9cd8  cmp     rcx, r15
0x1800a9cdb  jz      short loc_1800A9D0B
0x1800a9cdd  lea     edx, [r10+1]
0x1800a9ce1  test    [rcx+1Ch], dl
0x1800a9ce4  jz      short loc_1800A9D0B
0x1800a9ce6  cmp     [rcx+19h], r14b
0x1800a9cea  jb      short loc_1800A9D0B
0x1800a9cec  lea     edx, [r10+36h]
0x1800a9cf0  mov     dword ptr [rsp+108h+var_E8], eax
0x1800a9cf4  mov     r9d, [r13+0]
0x1800a9cf8  lea     r8, WPP_cb367cb5417a36a7f25c9f0919268851_Traceguids
0x1800a9cff  mov     rcx, [rcx+10h]
0x1800a9d03  call    WPP_SF_Dd
0x1800a9d08  xor     r10d, r10d
0x1800a9d0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9d12  test    rcx, rcx
0x1800a9d15  jnz     short loc_1800A9D21
0x1800a9d17  mov     rcx, r12; this
0x1800a9d1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9d21  cmp     [rcx+8], r10b
0x1800a9d25  jz      loc_1800AA78C
0x1800a9d2b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9d30  cmp     [rax+7CCh], edi
0x1800a9d36  jz      loc_1800AA78C
0x1800a9d3c  mov     r8d, 2C6h
0x1800a9d42  jmp     loc_1800A9B9B
0x1800a9d47  mov     rax, [rsi+0A0h]
0x1800a9d4e  sub     rax, [rsi+98h]
0x1800a9d55  sar     rax, 3
0x1800a9d59  imul    rax, r11
0x1800a9d5d  movzx   r13d, [rsp+108h+pusResult]
0x1800a9d63  mov     ecx, 1
0x1800a9d68  test    rax, rax
0x1800a9d6b  jz      short loc_1800A9D80
0x1800a9d6d  add     r9d, 0Ch
0x1800a9d71  mov     [rsi+84h], r9d
0x1800a9d78  add     dword ptr [rsi+7Ch], 6
0x1800a9d7c  add     r13w, cx
0x1800a9d80  mov     rax, [rsi+0B8h]
0x1800a9d87  sub     rax, [rsi+0B0h]
0x1800a9d8e  sar     rax, 3
0x1800a9d92  imul    rax, r11
0x1800a9d96  test    rax, rax
0x1800a9d99  jz      short loc_1800A9DB1
0x1800a9d9b  add     r9d, 0Ch
0x1800a9d9f  mov     [rsi+84h], r9d
0x1800a9da6  add     dword ptr [rsi+80h], 6
0x1800a9dad  add     r13w, cx
0x1800a9db1  mov     edx, [rsi+7Ch]
0x1800a9db4  add     edx, [rsi+80h]
0x1800a9dba  add     edx, r9d; dwBytes
0x1800a9dbd  xor     ecx, ecx; uFlags
0x1800a9dbf  call    cs:__imp_GlobalAlloc
0x1800a9dc6  nop     dword ptr [rax+rax+00h]
0x1800a9dcb  mov     [rsp+108h+hGlobal], rax
0x1800a9dd0  test    rax, rax
0x1800a9dd3  jnz     short loc_1800A9DDF
0x1800a9dd5  mov     edi, 8007000Eh
0x1800a9dda  jmp     loc_1800AA78C
0x1800a9ddf  lea     rdi, [rsi+0F8h]
0x1800a9de6  mov     rcx, rdi
0x1800a9de9  call    ?InternalRelease@?$ComPtr@UIWICMetadataBlockReader@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICMetadataBlockReader>::InternalRelease(void)
0x1800a9dee  mov     r8, rdi; ppstm
0x1800a9df1  mov     edx, 1; fDeleteOnRelease
0x1800a9df6  mov     rcx, [rsp+108h+hGlobal]; hGlobal
0x1800a9dfb  call    cs:__imp_CreateStreamOnHGlobal
0x1800a9e02  nop     dword ptr [rax+rax+00h]
0x1800a9e07  mov     edi, eax
0x1800a9e09  xor     edx, edx
0x1800a9e0b  test    eax, eax
0x1800a9e0d  jns     loc_1800A9EB0
0x1800a9e13  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9e1a  cmp     rcx, r15
0x1800a9e1d  jz      short loc_1800A9E4A
  ... truncated ...
```
