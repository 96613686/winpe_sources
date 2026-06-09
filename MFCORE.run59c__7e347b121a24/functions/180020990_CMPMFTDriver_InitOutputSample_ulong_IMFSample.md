# CMPMFTDriver::InitOutputSample(ulong,IMFSample * *)

- ea: `0x180020990`
- end: `0x180021710`
- name: `?InitOutputSample@CMPMFTDriver@@AEAAJKPEAPEAUIMFSample@@@Z`
- size: `3456`
- prototype: `__int64 __fastcall(CMPMFTDriver *__hidden this, unsigned int, struct IMFSample **)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001fe20`

## callees

- `0x18001616c`
- `0x180020990`
- `0x180021720`
- `0x180022970`
- `0x1800402c0`
- `0x18004c67c`
- `0x18004d118`
- `0x180050d6c`
- `0x18008b3a0`
- `0x1800ec0e0`
- `0x18015ff94`
- `0x180181280`
- `0x1802583a8`
- `0x180258480`
- `0x18028be64`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002105f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002105f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020a1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020a1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020b0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020a01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020af5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020a01`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180020af5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020eea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020eea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020de9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020f7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800211f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002128c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800214a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020de9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180020f7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800211f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002128c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800214a2`
- `MFPlat!MFCreateSample` at `0x180020cb1`
- `MFPlat!MFCreateSample` at `0x180020cb1`

## pseudocode

```c
__int64 __fastcall CMPMFTDriver::InitOutputSample(CMPMFTDriver *this, unsigned int a2, struct IMFSample **a3)
{
  CallStackTracing *v3; // rdi
  __int64 v6; // r15
  char *v7; // rbx
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  struct IMFMediaBuffer *v13; // rbx
  int v14; // eax
  HRESULT v15; // r14d
  CallStackTracing *v16; // rdi
  GUID *v17; // rbx
  DWORD v18; // esi
  GUID *v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  unsigned int v28; // eax
  char *i; // rdx
  unsigned int v30; // ecx
  unsigned __int64 v31; // r8
  struct IMFMediaType *v32; // rcx
  int v33; // edx
  struct IMFMediaType *v34; // rdi
  BOOL v35; // r15d
  unsigned int v36; // r15d
  unsigned int j; // edi
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r8
  CallStackTracing *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  CallStackTracing *v46; // rax
  CallStackTracing *v47; // rcx
  __int64 v48; // rax
  CallStackTracing *v49; // rcx
  __int64 v50; // rax
  CallStackTracing *v51; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  CMFMediaBufferAllocator *v61; // rax
  _BOOL8 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  CallStackTracing *v65; // rax
  CMFMediaBufferAllocator *v66; // rax
  struct CallStackContext *v67; // rax
  struct CallStackContext *v68; // rax
  struct CallStackContext *v69; // rax
  struct CallStackContext *v70; // rax
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  unsigned int *v79; // [rsp+28h] [rbp-59h]
  struct IMFMediaType *v80; // [rsp+48h] [rbp-39h] BYREF
  IMFSample *ppIMFSample; // [rsp+50h] [rbp-31h] BYREF
  int v82; // [rsp+58h] [rbp-29h] BYREF
  struct IMFMediaBuffer *v83; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v84[2]; // [rsp+68h] [rbp-19h] BYREF
  unsigned int v85; // [rsp+70h] [rbp-11h] BYREF
  GUID v86; // [rsp+78h] [rbp-9h] BYREF
  GUID Buf1; // [rsp+88h] [rbp+7h] BYREF

  v3 = CallStackTracing::s_wpInstance;
  v6 = a2;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v47 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v47 = CallStackTracing::s_wpInstance;
      }
      v48 = (**(__int64 (__fastcall ***)(CallStackTracing *))v47)(v47);
      if ( v48 )
        v7 = (char *)v48;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CMPMFTDriver::InitOutputSample";
      *(_DWORD *)&v7[8 * v11 + 8] = 1437;
    }
    ++*((_DWORD *)v7 + 497);
  }
  v12 = *((_QWORD *)this + 41);
  ppIMFSample = 0;
  v13 = 0;
  v83 = 0;
  v80 = 0;
  if ( v12 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, IMFSample **))(*(_QWORD *)v12 + 48LL))(v12, &ppIMFSample);
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( (_BYTE)byte_1803CECE9 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 104, &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids, this, v14);
      goto LABEL_13;
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        105,
        &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
        this,
        ppIMFSample);
LABEL_60:
    *a3 = ppIMFSample;
    goto LABEL_61;
  }
  v23 = *(_QWORD *)this;
  v24 = *((_QWORD *)this + 7);
  *(_QWORD *)v84 = 0;
  v85 = 0;
  v86 = GUID_00000000_0000_0000_0000_000000000000;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v23 + 56LL))(
          v23,
          *(unsigned int *)(v24 + 4 * v6),
          v84);
  if ( v15 < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v26, v25, v27);
      CallStackTracing::s_wpInstance = v51;
      if ( !v51 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v15 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMPMFTDriver::InitOutputSample", 1482, v15);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v42 = 106;
  }
  else
  {
    v28 = v85;
    if ( !v85 )
      v28 = 1;
    v85 = v28;
    if ( ((v28 - 1) & v28) != 0 )
    {
      v71 = (v28 - 1) | ((v28 - 1) >> 1) | (((v28 - 1) | ((v28 - 1) >> 1)) >> 2);
      v72 = v71 | (v71 >> 4) | ((v71 | (v71 >> 4)) >> 8);
      v85 = (v72 | HIWORD(v72)) + 1;
    }
    if ( (unsigned int)v6 >= *((_DWORD *)this + 78) )
    {
LABEL_176:
      v33 = 0;
      v32 = 0;
    }
    else
    {
      for ( i = (char *)this + 112; i; i = (char *)*((_QWORD *)i + 24) )
      {
        v30 = *((_DWORD *)i + 2);
        if ( (unsigned int)v6 >= v30 && (unsigned int)v6 < v30 + 20 )
        {
          v31 = (unsigned int)v6 - v30;
          if ( (CTSparseBlock<unsigned long,_KSEVENT_EX *,20,1>::s_bSingleBitMasks[v31 & 7]
              & (unsigned __int8)i[(v31 >> 3) + 24]) != 0 )
          {
            v32 = *(struct IMFMediaType **)&i[8 * v31 + 32];
            goto LABEL_40;
          }
          break;
        }
      }
      if ( (*((_BYTE *)this + 124) & 1) == 0 )
        goto LABEL_176;
      v32 = (struct IMFMediaType *)*((_QWORD *)this + 16);
LABEL_40:
      v33 = 1;
    }
    if ( !v33 )
      v32 = 0;
    v80 = v32;
    if ( !v32 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType **))(**(_QWORD **)this + 144LL))(
              *(_QWORD *)this,
              (unsigned int)v6,
              &v80);
      if ( v15 < 0 )
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v74, v73, v75);
          CallStackTracing::s_wpInstance = v53;
          if ( !v53 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v54 + 499) != v15 )
            CallStackContext::TraceFailure(v54, "CMPMFTDriver::InitOutputSample", 1510, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_13;
        v42 = 107;
        goto LABEL_110;
      }
      if ( !(unsigned int)CTPtrArray<IMFMediaType,20>::SetAtGrow((char *)this + 112, (unsigned int)v6, v80) )
      {
        v15 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v77, v76, v78);
          CallStackTracing::s_wpInstance = v55;
          if ( !v55 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v56 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v56, "CMPMFTDriver::InitOutputSample", 1513, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_13;
        v42 = 108;
        goto LABEL_110;
      }
      v32 = v80;
    }
    ((void (__fastcall *)(struct IMFMediaType *))v32->lpVtbl->AddRef)(v32);
    v15 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))v80->lpVtbl->GetGUID)(
            v80,
            &MF_MT_SUBTYPE,
            &Buf1);
    if ( v15 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v57 + 499) != v15 )
          CallStackContext::TraceFailure(v57, "CMPMFTDriver::InitOutputSample", 1519, v15);
      }
      if ( !g_wppLevels )
        goto LABEL_13;
      v42 = 109;
    }
    else
    {
      if ( *((__int64 *)this + 76) > 0
        && ((int (__fastcall *)(struct IMFMediaType *, GUID *))v80->lpVtbl->GetMajorType)(v80, &v86) >= 0
        && !memcmp_0(&v86, &MFMediaType_Audio, 0x10u) )
      {
        v15 = ComputeAudioLengthAndAlignmentFromMediaType(v80, *((_QWORD *)this + 76), v84[1], v85, &v84[1], &v85);
        if ( v15 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v44, v43, v45);
            CallStackTracing::s_wpInstance = v46;
            if ( !v46
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v58 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v58 + 499) != v15 )
              CallStackContext::TraceFailure(v58, "CMPMFTDriver::InitOutputSample", 1528, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_13;
          v42 = 110;
          goto LABEL_110;
        }
      }
      if ( !memcmp_0(&Buf1, &MFAudioFormat_Float_SpatialObjects, 0x10u) )
      {
        v15 = CMPMFTDriver::AllocateSpatialAudioSample(this, v80, v84[1], v85, (__int64)v79, &ppIMFSample);
        if ( v15 >= 0 )
          goto LABEL_60;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v39, v38, v40);
          CallStackTracing::s_wpInstance = v41;
          if ( !v41 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v59 + 499) != v15 )
            CallStackContext::TraceFailure(v59, "CMPMFTDriver::InitOutputSample", 1533, v15);
        }
        if ( !g_wppLevels )
          goto LABEL_13;
        v42 = 111;
      }
      else
      {
        v15 = MFCreateSample(&ppIMFSample);
        if ( v15 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
            CallStackTracing::InitInstance();
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v60 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v60 + 499) != v15 )
              CallStackContext::TraceFailure(v60, "CMPMFTDriver::InitOutputSample", 1540, v15);
          }
          if ( !g_wppLevels )
            goto LABEL_13;
          v42 = 112;
        }
        else
        {
          if ( *((_QWORD *)this + 43) )
            goto LABEL_49;
          v61 = (CMFMediaBufferAllocator *)operator new(0x3F0u);
          if ( v61 )
          {
            v66 = CMFMediaBufferAllocator::CMFMediaBufferAllocator(v61, v62);
            *((_QWORD *)this + 43) = v66;
            v62 = (_BOOL8)v66;
            if ( v66 )
            {
              (*(void (__fastcall **)(CMFMediaBufferAllocator *))(*(_QWORD *)v66 + 8LL))(v66);
              v15 = 0;
LABEL_49:
              v34 = v80;
              v82 = 0;
              v35 = 0;
              if ( ((int (__fastcall *)(struct IMFMediaType *, __int128 *, int *))v80->lpVtbl->GetUINT32)(
                     v80,
                     &MF_MT_VIDEO_3D,
                     &v82) < 0 )
              {
                v82 = 0;
              }
              else if ( v82 )
              {
                v35 = MFGetAttributeUINT32(v34, &MF_MT_VIDEO_3D_FORMAT, 0) == 1;
              }
              v36 = v35 + 1;
              for ( j = 0; ; ++j )
              {
                if ( j >= v36 )
                {
                  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
                    WPP_SF_qqDd(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      117,
                      &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
                      this,
                      ppIMFSample,
                      v84[1],
                      v36);
                  goto LABEL_60;
                }
                v15 = CMFMediaBufferAllocator::AllocateBuffer(
                        *((CMFMediaBufferAllocator **)this + 43),
                        v84[1],
                        v85,
                        &v83);
                if ( v15 < 0 )
                {
                  if ( !CallStackTracing::s_wpInstance )
                    CallStackTracing::InitInstance();
                  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
                  {
                    v70 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                    if ( *((_DWORD *)v70 + 499) != v15 )
                      CallStackContext::TraceFailure(v70, "CMPMFTDriver::InitOutputSample", 1555, v15);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      114,
                      &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids,
                      this,
                      v15);
                  v13 = v83;
                  goto LABEL_13;
                }
                v13 = v83;
                v15 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _QWORD))v83->lpVtbl->SetCurrentLength)(v83, 0);
                if ( v15 < 0 )
                  break;
                v15 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                        ppIMFSample,
                        v13);
                if ( v15 < 0 )
                {
                  if ( !CallStackTracing::s_wpInstance )
                    CallStackTracing::InitInstance();
                  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
                  {
                    v68 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                    if ( *((_DWORD *)v68 + 499) != v15 )
                      CallStackContext::TraceFailure(v68, "CMPMFTDriver::InitOutputSample", 1559, v15);
                  }
                  if ( g_wppLevels )
                  {
                    v42 = 116;
                    goto LABEL_110;
                  }
                  goto LABEL_13;
                }
                ((void (__fastcall *)(struct IMFMediaBuffer *))v13->lpVtbl->Release)(v13);
                v13 = 0;
                v83 = 0;
              }
              if ( !CallStackTracing::s_wpInstance )
                CallStackTracing::InitInstance();
              if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
              {
                v69 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                if ( *((_DWORD *)v69 + 499) != v15 )
                  CallStackContext::TraceFailure(v69, "CMPMFTDriver::InitOutputSample", 1557, v15);
              }
              if ( g_wppLevels )
              {
                v42 = 115;
                goto LABEL_110;
              }
              goto LABEL_13;
            }
          }
          else
          {
            *((_QWORD *)this + 43) = 0;
          }
          v15 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v63, v62, v64);
            CallStackTracing::s_wpInstance = v65;
            if ( !v65
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v67 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v67 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v67, "CMPMFTDriver::InitOutputSample", 1544, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_13;
          v42 = 113;
        }
      }
    }
  }
LABEL_110:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, &WPP_74268b52eb7b368509d4a1f76a866452_Traceguids, this, v15);
LABEL_13:
  if ( !ppIMFSample )
    goto LABEL_14;
  ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
LABEL_61:
  ppIMFSample = 0;
LABEL_14:
  if ( v13 )
    ((void (__fastcall *)(struct IMFMediaBuffer *))v13->lpVtbl->Release)(v13);
  if ( v80 )
  {
    ((void (__fastcall *)(struct IMFMediaType *))v80->lpVtbl->Release)(v80);
    v80 = 0;
  }
  v16 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v17 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v18 = GetLastError();
    v19 = (GUID *)TlsGetValue(*((_DWORD *)v16 + 3));
    if ( v19 )
    {
      v17 = v19;
    }
    else if ( !GetLastError() )
    {
      v49 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v49 = CallStackTracing::s_wpInstance;
      }
      v50 = (**(__int64 (__fastcall ***)(CallStackTracing *))v49)(v49);
      if ( v50 )
        v17 = (GUID *)v50;
    }
    SetLastError(v18);
    v20 = *(_DWORD *)&v17[124].Data2;
    if ( v20 )
    {
      v21 = v20 - 1;
      *(_DWORD *)&v17[124].Data2 = v21;
      if ( !v21 )
      {
        *(_DWORD *)&v17[124].Data2 = 0;
        *(_QWORD *)&v17[126].Data1 = 0;
        *(_DWORD *)&v17[124].Data4[4] = 0;
        v17[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v17[126].Data4 = 0;
        v17[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180020990  mov     r11, rsp
0x180020993  push    rbp
0x180020994  push    rbx
0x180020995  push    rsi
0x180020996  push    rdi
0x180020997  push    r13
0x180020999  lea     rbp, [r11-5Fh]
0x18002099d  sub     rsp, 0B0h
0x1800209a4  mov     rax, cs:__security_cookie
0x1800209ab  xor     rax, rsp
0x1800209ae  mov     [rbp+57h+var_40], rax
0x1800209b2  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800209b9  mov     rsi, rcx
0x1800209bc  mov     [r11+20h], r12
0x1800209c0  mov     r12, r8
0x1800209c3  mov     [r11-38h], r15
0x1800209c7  mov     r15d, edx
0x1800209ca  test    rdi, rdi
0x1800209cd  jz      loc_18002101D
0x1800209d3  cmp     byte ptr [rdi+8], 0
0x1800209d7  lea     rcx, aCmpmftdriverIn; "CMPMFTDriver::InitOutputSample"
0x1800209de  mov     qword ptr [rsp+0D0h+var_28], r14
0x1800209e6  jz      short loc_180020A52
0x1800209e8  lea     rbx, [rdi+0D0h]
0x1800209ef  call    cs:__imp_GetLastError
0x1800209f6  nop     dword ptr [rax+rax+00h]
0x1800209fb  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800209fe  mov     r14d, eax
0x180020a01  call    cs:__imp_TlsGetValue
0x180020a08  nop     dword ptr [rax+rax+00h]
0x180020a0d  test    rax, rax
0x180020a10  jz      loc_18002105F
0x180020a16  mov     rbx, rax
0x180020a19  mov     ecx, r14d; dwErrCode
0x180020a1c  call    cs:__imp_SetLastError
0x180020a23  nop     dword ptr [rax+rax+00h]
0x180020a28  mov     eax, [rbx+7C4h]
0x180020a2e  lea     rcx, aCmpmftdriverIn; "CMPMFTDriver::InitOutputSample"
0x180020a35  cmp     eax, [rbx+7C8h]
0x180020a3b  jnb     short loc_180020A4C
0x180020a3d  add     rax, rax
0x180020a40  mov     [rbx+rax*8], rcx
0x180020a44  mov     dword ptr [rbx+rax*8+8], 59Dh
0x180020a4c  inc     dword ptr [rbx+7C4h]
0x180020a52  mov     rcx, [rsi+148h]
0x180020a59  xor     r13d, r13d
0x180020a5c  mov     [rbp+57h+ppIMFSample], r13
0x180020a60  mov     ebx, r13d
0x180020a63  mov     [rbp+57h+var_78], rbx
0x180020a67  mov     [rbp+57h+var_90], r13
0x180020a6b  test    rcx, rcx
0x180020a6e  jz      loc_180020B5A
0x180020a74  mov     rax, [rcx]
0x180020a77  lea     rdx, [rbp+57h+ppIMFSample]
0x180020a7b  mov     rax, [rax+30h]
0x180020a7f  call    cs:__guard_dispatch_icall_fptr
0x180020a85  mov     r14d, eax
0x180020a88  test    eax, eax
0x180020a8a  jns     loc_180020FE3
0x180020a90  cmp     cs:byte_1803CECE9, 1
0x180020a97  jnb     loc_1800215F8
0x180020a9d  mov     rcx, [rbp+57h+ppIMFSample]
0x180020aa1  test    rcx, rcx
0x180020aa4  jnz     loc_1800216E9
0x180020aaa  mov     r15, [rsp+0D0h+var_30]
0x180020ab2  mov     r12, [rsp+0D0h+arg_18]
0x180020aba  test    rbx, rbx
0x180020abd  jnz     loc_1800216FB
0x180020ac3  mov     rcx, [rbp+57h+var_90]
0x180020ac7  test    rcx, rcx
0x180020aca  jnz     loc_180020C08
0x180020ad0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020ad7  cmp     [rdi+8], r13b
0x180020adb  jz      short loc_180020B34
0x180020add  lea     rbx, [rdi+0D0h]
0x180020ae4  call    cs:__imp_GetLastError
0x180020aeb  nop     dword ptr [rax+rax+00h]
0x180020af0  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180020af3  mov     esi, eax
0x180020af5  call    cs:__imp_TlsGetValue
0x180020afc  nop     dword ptr [rax+rax+00h]
0x180020b01  test    rax, rax
0x180020b04  jz      loc_1800210EF
0x180020b0a  mov     rbx, rax
0x180020b0d  mov     ecx, esi; dwErrCode
0x180020b0f  call    cs:__imp_SetLastError
0x180020b16  nop     dword ptr [rax+rax+00h]
0x180020b1b  mov     eax, [rbx+7C4h]
0x180020b21  test    eax, eax
0x180020b23  jz      short loc_180020B34
0x180020b25  sub     eax, 1
0x180020b28  mov     [rbx+7C4h], eax
0x180020b2e  jz      loc_180020EC0
0x180020b34  mov     eax, r14d
0x180020b37  mov     r14, qword ptr [rsp+0D0h+var_28]
0x180020b3f  mov     rcx, [rbp+57h+var_40]
0x180020b43  xor     rcx, rsp; StackCookie
0x180020b46  call    __security_check_cookie
0x180020b4b  add     rsp, 0B0h
0x180020b52  pop     r13
0x180020b54  pop     rdi
0x180020b55  pop     rsi
0x180020b56  pop     rbx
0x180020b57  pop     rbp
0x180020b58  retn
0x180020b5a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180020b61  mov     rcx, [rsi]
0x180020b64  lea     r8, [rbp+57h+var_70]
0x180020b68  mov     rdx, [rsi+38h]
0x180020b6c  xor     eax, eax
0x180020b6e  mov     qword ptr [rbp+57h+var_70], rax
0x180020b72  mov     [rbp+57h+var_68], eax
0x180020b75  movups  [rbp+57h+var_60], xmm0
0x180020b79  movups  [rbp+57h+Buf1], xmm0
0x180020b7d  mov     rax, [rcx]
0x180020b80  mov     edx, [rdx+r15*4]
0x180020b84  mov     rax, [rax+38h]
0x180020b88  call    cs:__guard_dispatch_icall_fptr
0x180020b8e  mov     r14d, eax
0x180020b91  test    eax, eax
0x180020b93  js      loc_1800211ED
0x180020b99  mov     eax, [rbp+57h+var_68]
0x180020b9c  mov     r10d, 1
0x180020ba2  cmp     eax, r10d
0x180020ba5  cmovb   eax, r10d
0x180020ba9  mov     [rbp+57h+var_68], eax
0x180020bac  lea     ecx, [rax-1]
0x180020baf  test    eax, ecx
0x180020bb1  jnz     loc_180021620
0x180020bb7  cmp     r15d, [rsi+138h]
0x180020bbe  jnb     loc_18002164C
0x180020bc4  lea     rdx, [rsi+70h]
0x180020bc8  test    rdx, rdx
0x180020bcb  jz      short loc_180020C27
0x180020bcd  mov     ecx, [rdx+8]
0x180020bd0  cmp     r15d, ecx
0x180020bd3  jb      short loc_180020C1E
0x180020bd5  lea     eax, [rcx+14h]
0x180020bd8  cmp     r15d, eax
0x180020bdb  jnb     short loc_180020C1E
0x180020bdd  mov     eax, r15d
0x180020be0  lea     r9, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_KSEVENT_EX@@$0BE@$00@@0QBEB; uchar const near * const CTSparseBlock<ulong,_KSEVENT_EX *,20,1>::s_bSingleBitMasks
0x180020be7  sub     eax, ecx
0x180020be9  mov     r8d, eax
0x180020bec  and     eax, 7
0x180020bef  mov     ecx, r8d
0x180020bf2  shr     rcx, 3
0x180020bf6  movzx   eax, byte ptr [rax+r9]
0x180020bfb  test    [rcx+rdx+18h], al
0x180020bff  jz      short loc_180020C27
0x180020c01  mov     rcx, [rdx+r8*8+20h]
0x180020c06  jmp     short loc_180020C38
0x180020c08  mov     rax, [rcx]
0x180020c0b  mov     rax, [rax+10h]
0x180020c0f  call    cs:__guard_dispatch_icall_fptr
0x180020c15  mov     [rbp+57h+var_90], r13
0x180020c19  jmp     loc_180020AD0
0x180020c1e  mov     rdx, [rdx+0C0h]
0x180020c25  jmp     short loc_180020BC8
0x180020c27  test    [rsi+7Ch], r10b
0x180020c2b  jz      loc_18002164C
0x180020c31  mov     rcx, [rsi+80h]
0x180020c38  mov     edx, r10d
0x180020c3b  test    edx, edx
0x180020c3d  cmovz   rcx, r13
0x180020c41  mov     [rbp+57h+var_90], rcx
0x180020c45  test    rcx, rcx
0x180020c48  jz      loc_180021657
0x180020c4e  mov     rax, [rcx]
0x180020c51  mov     rax, [rax+8]
0x180020c55  call    cs:__guard_dispatch_icall_fptr
0x180020c5b  mov     rcx, [rbp+57h+var_90]
0x180020c5f  lea     r8, [rbp+57h+Buf1]
0x180020c63  lea     rdx, MF_MT_SUBTYPE
0x180020c6a  mov     rax, [rcx]
0x180020c6d  mov     rax, [rax+50h]
0x180020c71  call    cs:__guard_dispatch_icall_fptr
0x180020c77  mov     r14d, eax
0x180020c7a  test    eax, eax
0x180020c7c  js      loc_18002102E
0x180020c82  cmp     [rsi+260h], rbx
0x180020c89  jg      loc_180020F01
0x180020c8f  mov     r8d, 10h; Size
0x180020c95  lea     rdx, MFAudioFormat_Float_SpatialObjects; Buf2
0x180020c9c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180020ca0  call    memcmp_0
0x180020ca5  test    eax, eax
0x180020ca7  jz      loc_180020DBC
0x180020cad  lea     rcx, [rbp+57h+ppIMFSample]; ppIMFSample
0x180020cb1  call    cs:__imp_MFCreateSample
0x180020cb8  nop     dword ptr [rax+rax+00h]
0x180020cbd  mov     r14d, eax
0x180020cc0  test    eax, eax
0x180020cc2  js      loc_180020E58
0x180020cc8  cmp     [rsi+158h], rbx
0x180020ccf  jz      loc_18002147D
0x180020cd5  mov     rdi, [rbp+57h+var_90]
0x180020cd9  lea     r8, [rbp+57h+var_80]
0x180020cdd  lea     rdx, MF_MT_VIDEO_3D
0x180020ce4  mov     [rbp+57h+var_80], r13d
0x180020ce8  mov     rcx, rdi
0x180020ceb  mov     r15d, r13d
0x180020cee  mov     rax, [rdi]
0x180020cf1  mov     rax, [rax+38h]
0x180020cf5  call    cs:__guard_dispatch_icall_fptr
0x180020cfb  test    eax, eax
0x180020cfd  js      loc_180020E4F
0x180020d03  cmp     [rbp+57h+var_80], ebx
0x180020d06  jnz     loc_18002169D
0x180020d0c  inc     r15d
0x180020d0f  mov     edi, r13d
0x180020d12  cmp     edi, r15d
0x180020d15  jnb     loc_180020D9E
0x180020d1b  mov     r8d, [rbp+57h+var_68]; unsigned int
0x180020d1f  lea     r9, [rbp+57h+var_78]; struct IMFMediaBuffer **
0x180020d23  mov     edx, [rbp+57h+var_70+4]; unsigned int
0x180020d26  mov     rcx, [rsi+158h]; this
0x180020d2d  call    ?AllocateBuffer@CMFMediaBufferAllocator@@QEAAJKKPEAPEAUIMFMediaBuffer@@@Z; CMFMediaBufferAllocator::AllocateBuffer(ulong,ulong,IMFMediaBuffer * *)
0x180020d32  mov     r14d, eax
0x180020d35  test    eax, eax
0x180020d37  js      loc_180020E8C
0x180020d3d  mov     rbx, [rbp+57h+var_78]
0x180020d41  xor     edx, edx
0x180020d43  mov     rcx, rbx
0x180020d46  mov     rax, [rbx]
0x180020d49  mov     rax, [rax+30h]
0x180020d4d  call    cs:__guard_dispatch_icall_fptr
0x180020d53  mov     r14d, eax
0x180020d56  test    eax, eax
0x180020d58  js      loc_18002112B
0x180020d5e  mov     rcx, [rbp+57h+ppIMFSample]
0x180020d62  mov     rdx, rbx
0x180020d65  mov     rax, [rcx]
0x180020d68  mov     rax, [rax+150h]
0x180020d6f  call    cs:__guard_dispatch_icall_fptr
0x180020d75  mov     r14d, eax
0x180020d78  test    eax, eax
0x180020d7a  js      loc_18002109B
0x180020d80  mov     rax, [rbx]
0x180020d83  mov     rcx, rbx
0x180020d86  mov     rax, [rax+10h]
0x180020d8a  call    cs:__guard_dispatch_icall_fptr
0x180020d90  mov     rbx, r13
0x180020d93  inc     edi
0x180020d95  mov     [rbp+57h+var_78], rbx
0x180020d99  jmp     loc_180020D12
0x180020d9e  cmp     cs:byte_1803CECE9, 8
0x180020da5  jnb     loc_180021174
0x180020dab  mov     rax, [rbp+57h+ppIMFSample]
0x180020daf  mov     [r12], rax
0x180020db3  mov     [rbp+57h+ppIMFSample], r13
0x180020db7  jmp     loc_180020AAA
0x180020dbc  mov     r9d, [rbp+57h+var_68]; unsigned int
0x180020dc0  lea     rax, [rbp+57h+ppIMFSample]
0x180020dc4  mov     r8d, [rbp+57h+var_70+4]; unsigned int
0x180020dc8  mov     rcx, rsi; this
0x180020dcb  mov     rdx, [rbp+57h+var_90]; struct IMFMediaType *
0x180020dcf  mov     [rsp+0D0h+var_A8], rax; struct IMFSample **
0x180020dd4  call    ?AllocateSpatialAudioSample@CMPMFTDriver@@AEAAJPEAUIMFMediaType@@KK_JPEAPEAUIMFSample@@@Z; CMPMFTDriver::AllocateSpatialAudioSample(IMFMediaType *,ulong,ulong,__int64,IMFSample * *)
0x180020dd9  mov     r14d, eax
0x180020ddc  test    eax, eax
0x180020dde  jns     short loc_180020DAB
0x180020de0  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020de7  jnz     short loc_180020E28
0x180020de9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180020df0  nop     dword ptr [rax+rax+00h]
0x180020df5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180020dfc  mov     rcx, rax
0x180020dff  test    rax, rax
0x180020e02  jz      short loc_180020E1A
0x180020e04  mov     rax, [rax]
0x180020e07  mov     edx, 7F0h
0x180020e0c  mov     rax, [rax+8]
0x180020e10  call    cs:__guard_dispatch_icall_fptr
0x180020e16  test    eax, eax
0x180020e18  jnz     short loc_180020E28
0x180020e1a  lea     rax, qword_1803CE250
0x180020e21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e28  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e2f  cmp     [rdi+8], bl
0x180020e32  jnz     loc_180021419
0x180020e38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020e3f  jb      loc_180020A9D
0x180020e45  mov     edx, 6Fh ; 'o'
0x180020e4a  jmp     loc_1800210CB
0x180020e4f  mov     [rbp+57h+var_80], r13d
0x180020e53  jmp     loc_180020D0C
0x180020e58  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e5f  jz      loc_180021160
0x180020e65  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e6c  cmp     [rdi+8], bl
0x180020e6f  jnz     loc_18002144B
0x180020e75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020e7c  jb      loc_180020A9D
0x180020e82  mov     edx, 70h ; 'p'
0x180020e87  jmp     loc_1800210CB
0x180020e8c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180020e93  jz      loc_18002116A
0x180020e99  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020ea0  cmp     [rdi+8], r13b
  ... truncated ...
```
