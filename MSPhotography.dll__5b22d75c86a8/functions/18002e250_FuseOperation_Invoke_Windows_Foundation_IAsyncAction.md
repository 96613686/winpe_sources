# FuseOperation::Invoke(Windows::Foundation::IAsyncAction *)

- ea: `0x18002e250`
- end: `0x18002f064`
- name: `?Invoke@FuseOperation@@EEAAJPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `3604`
- prototype: `__int64 __fastcall(FuseOperation *__hidden this, struct Windows::Foundation::IAsyncAction *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002420`
- `0x180005660`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18001de40`
- `0x1800280e4`
- `0x18002a9bc`
- `0x18002aa84`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb00`
- `0x18002bb98`
- `0x18002cadc`
- `0x18002cb2c`
- `0x18002cd78`
- `0x18002cdb8`
- `0x18002dad0`
- `0x18002e250`
- `0x18002fbc8`
- `0x18002fbfc`
- `0x18002fedc`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e302`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e302`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e31e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e5d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e6a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e80d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e900`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e9c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ec26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ecf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002edaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ee64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ef1e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e31e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e502`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e5d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e6a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e80d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e900`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e9c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ea6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002eb16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ec26`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ecf0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002edaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ee64`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002ef1e`

## pseudocode

```c
__int64 __fastcall FuseOperation::Invoke(FuseOperation *this, struct Windows::Foundation::IAsyncAction *a2)
{
  unsigned int v3; // esi
  HRESULT v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  char *v8; // r9
  __int64 v9; // rdx
  double v10; // xmm1_8
  __int64 v11; // rax
  double v12; // xmm0_8
  unsigned int v13; // ebx
  unsigned int v14; // edi
  char *v15; // r14
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rcx
  HRESULT v29; // eax
  int v30; // esi
  int v31; // r12d
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, GUID *, __int64 *); // rbx
  int v42; // edx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  HRESULT v46; // eax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  LPVOID v53; // rdi
  __int64 (__fastcall *v54)(LPVOID, __int64, const GUID *, _QWORD, _DWORD, _DWORD, __int128 *, GUID *, __int64 *); // rbx
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char *v70; // rcx
  _BYTE v72[12]; // [rsp+70h] [rbp-90h]
  _BYTE v73[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h] BYREF
  int v75; // [rsp+90h] [rbp-70h] BYREF
  int v76; // [rsp+94h] [rbp-6Ch] BYREF
  int v77; // [rsp+98h] [rbp-68h] BYREF
  int v78; // [rsp+9Ch] [rbp-64h] BYREF
  int v79; // [rsp+A0h] [rbp-60h] BYREF
  int v80; // [rsp+A4h] [rbp-5Ch] BYREF
  __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v84; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v85; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v86; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v87; // [rsp+E0h] [rbp-20h] BYREF

  v75 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v73, "FuseOperation::Invoke", 95);
  v77 = 0;
  v3 = 2;
  v78 = 0;
  v80 = 0;
  v86 = 0;
  v79 = 0;
  v83 = 0;
  ppv = 0;
  v85 = 0;
  *(_QWORD *)v72 = 0x100000000LL;
  *(_DWORD *)&v72[8] = 2;
  v76 = 0;
  v84 = 0;
  v81 = 0;
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppv);
  v4 = CoCreateInstance(&CLSID_SoftwareBitmapNativeFactory, 0, 1u, &GUID_c3c181ec_2914_4791_af02_02d224a10b43, &ppv);
  if ( v4 >= 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel() >= 8u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        20,
        &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids,
        (char *)this - 16);
    v10 = *(double *)(*((_QWORD *)this + 27) + 88LL);
    v11 = *((_QWORD *)this + 26);
    v12 = *(double *)(*((_QWORD *)this + 28) + 88LL);
    if ( v10 < *(double *)(v11 + 88) )
    {
      if ( v12 >= *(double *)(v11 + 88) )
      {
        v13 = 1;
        v14 = 0;
        *(_QWORD *)v72 = 1;
LABEL_22:
        *(_DWORD *)&v72[8] = v3;
        goto LABEL_28;
      }
      if ( v12 < v10 )
      {
        v14 = 1;
        v13 = 2;
        *(_QWORD *)&v72[4] = 1;
      }
      else
      {
        v13 = 1;
        *(_QWORD *)&v72[4] = 2;
        v14 = 2;
      }
      v3 = 0;
    }
    else
    {
      if ( v12 >= *(double *)(v11 + 88) )
      {
        v13 = 0;
        *(_DWORD *)v72 = 0;
        if ( v12 < v10 )
        {
          v14 = 2;
          *(_DWORD *)&v72[4] = 2;
          v3 = 1;
        }
        else
        {
          v14 = 1;
          *(_DWORD *)&v72[4] = 1;
        }
        goto LABEL_22;
      }
      v13 = 2;
      *(_DWORD *)&v72[4] = 0;
      v3 = 1;
      v14 = 0;
      *(_DWORD *)&v72[8] = 1;
    }
    *(_DWORD *)v72 = v13;
LABEL_28:
    if ( _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel() >= 8u )
      WPP_SF_qddd(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        21,
        &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids,
        (char *)this - 16,
        v13,
        v14,
        v3);
    v15 = (char *)this - 16;
    v16 = *((_QWORD *)this + v13 + 26);
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**((_QWORD **)this + 25) + 32LL))(
           *((_QWORD *)this + 25),
           *(_QWORD *)(v16 + 56),
           *(_QWORD *)(v16 + 64),
           *(unsigned int *)(v16 + 76),
           *(_DWORD *)(v16 + 80),
           *(_DWORD *)(v16 + 84));
    if ( v4 >= 0 )
    {
      v20 = *((_QWORD *)this + v14 + 26);
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**((_QWORD **)v15 + 27) + 32LL))(
             *((_QWORD *)v15 + 27),
             *(_QWORD *)(v20 + 56),
             *(_QWORD *)(v20 + 64),
             *(unsigned int *)(v20 + 76),
             *(_DWORD *)(v20 + 80),
             *(_DWORD *)(v20 + 84));
      if ( v4 >= 0 )
      {
        v24 = *((_QWORD *)this + v3 + 26);
        v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(**((_QWORD **)v15 + 27) + 32LL))(
               *((_QWORD *)v15 + 27),
               *(_QWORD *)(v24 + 56),
               *(_QWORD *)(v24 + 64),
               *(unsigned int *)(v24 + 76),
               *(_DWORD *)(v24 + 80),
               *(_DWORD *)(v24 + 84));
        if ( v4 >= 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel() >= 8u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              25,
              &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids,
              (char *)this - 16);
          v28 = *((_QWORD *)this + 25);
          v87 = 0;
          v29 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *, int *, int *, __int128 *))(*(_QWORD *)v28 + 24LL))(
                  v28,
                  &v75,
                  &v76,
                  &v77,
                  &v78,
                  &v80,
                  &v79,
                  &v87);
          v30 = (int)*((float *)&v87 + 2);
          v4 = v29;
          v31 = (int)*((float *)&v87 + 3);
          if ( _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel() >= 8u )
            WPP_SF_qDdddddddd(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              v32,
              v33,
              (char *)this - 16,
              v4,
              v75,
              v76,
              v77,
              v78,
              v80,
              v79,
              v30,
              v31);
          if ( v4 >= 0 )
          {
            switch ( v75 )
            {
              case 1:
                *(_QWORD *)v72 = 0;
                LODWORD(v74) = 1;
                v4 = Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeResultImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,enum Windows::Graphics::Imaging::Internal::HighDynamicRangeStatus,std::nullptr_t>((void **)this + 24);
                if ( v4 >= 0 )
                  goto LABEL_184;
                v67 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v68;
                  if ( v68
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                  {
                    v67 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v67 = &qword_18015FF10;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                  }
                }
                if ( *((_BYTE *)v67 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
                    CallStackContext::TraceFailure(ThreadRelativeContext, "FuseOperation::Invoke", 195, v4);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_184;
                v9 = 28;
                break;
              case 2:
                *(_QWORD *)v72 = 0;
                LODWORD(v74) = 2;
                v4 = Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeResultImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,enum Windows::Graphics::Imaging::Internal::HighDynamicRangeStatus,std::nullptr_t>((void **)this + 24);
                if ( v4 >= 0 )
                  goto LABEL_184;
                v64 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v65;
                  if ( v65
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
                  {
                    v64 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v64 = &qword_18015FF10;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                  }
                }
                if ( *((_BYTE *)v64 + 8) )
                {
                  v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                  if ( *((_DWORD *)v66 + 499) != v4 )
                    CallStackContext::TraceFailure(v66, "FuseOperation::Invoke", 198, v4);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_184;
                v9 = 29;
                break;
              case 3:
                *(_QWORD *)v72 = 0;
                LODWORD(v74) = 3;
                v4 = Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeResultImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,enum Windows::Graphics::Imaging::Internal::HighDynamicRangeStatus,std::nullptr_t>((void **)this + 24);
                if ( v4 >= 0 )
                  goto LABEL_184;
                v61 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v62;
                  if ( v62
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
                  {
                    v61 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v61 = &qword_18015FF10;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                  }
                }
                if ( *((_BYTE *)v61 + 8) )
                {
                  v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                  if ( *((_DWORD *)v63 + 499) != v4 )
                    CallStackContext::TraceFailure(v63, "FuseOperation::Invoke", 201, v4);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_184;
                v9 = 30;
                break;
              default:
                v74 = *(_QWORD *)(*((_QWORD *)this + *(unsigned int *)&v72[4 * v76] + 26) + 32LL);
                Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v74);
                v4 = Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::As<ISoftwareBitmapNative>(
                       &v74,
                       &v85);
                Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v74);
                if ( v4 >= 0 )
                {
                  v40 = v85;
                  v41 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v85 + 48LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
                  v4 = v41(v40, &GUID_045fa593_8799_42b8_bc8d_8968c6453507, &v81);
                  if ( v4 >= 0 )
                  {
                    if ( v81 )
                    {
                      v4 = Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(&v81, &v84);
                      if ( v4 >= 0 )
                      {
                        v53 = ppv;
                        WORD1(v86) = v77;
                        WORD3(v86) = v78;
                        *((_QWORD *)&v86 + 1) = __PAIR64__(v31, v30);
                        v54 = *(__int64 (__fastcall **)(LPVOID, __int64, const GUID *, _QWORD, _DWORD, _DWORD, __int128 *, GUID *, __int64 *))(*(_QWORD *)ppv + 56LL);
                        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v83);
                        v4 = v54(
                               v53,
                               v84,
                               &MFVideoFormat_NV12,
                               *(unsigned int *)(*((_QWORD *)this + 26) + 76LL),
                               *(_DWORD *)(*((_QWORD *)this + 26) + 80LL),
                               0,
                               &v86,
                               &GUID_689e0708_7eef_483f_963f_da938818e073,
                               &v83);
                        if ( v4 >= 0 )
                        {
                          *(_QWORD *)v72 = v83;
                          LODWORD(v74) = 0;
                          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease((char *)this + 192);
                          v4 = Microsoft::WRL::Details::MakeAndInitialize<HighDynamicRangeResultImpl,Windows::Graphics::Imaging::Internal::IHighDynamicRangeResult,enum Windows::Graphics::Imaging::Internal::HighDynamicRangeStatus,Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Foundation::Rect &>((void **)this + 24);
                          if ( v4 >= 0 )
                            goto LABEL_184;
                          v58 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                            CallStackTracing::s_wpInstance = v59;
                            if ( v59
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(
                                   v59,
                                   2032) )
                            {
                              v58 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v58 = &qword_18015FF10;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                            }
                          }
                          if ( *((_BYTE *)v58 + 8) )
                          {
                            v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
                            if ( *((_DWORD *)v60 + 499) != v4 )
                              CallStackContext::TraceFailure(v60, "FuseOperation::Invoke", 234, v4);
                          }
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_184;
                          v9 = 36;
                        }
                        else
                        {
                          v55 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                            CallStackTracing::s_wpInstance = v56;
                            if ( v56
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(
                                   v56,
                                   2032) )
                            {
                              v55 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v55 = &qword_18015FF10;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                            }
                          }
                          if ( *((_BYTE *)v55 + 8) )
                          {
                            v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                            if ( *((_DWORD *)v57 + 499) != v4 )
                              CallStackContext::TraceFailure(v57, "FuseOperation::Invoke", 232, v4);
                          }
                          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                            goto LABEL_184;
                          v9 = 35;
                        }
                      }
                      else
                      {
                        v50 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                          CallStackTracing::s_wpInstance = v51;
                          if ( v51
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(
                                 v51,
                                 2032) )
                          {
                            v50 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v50 = &qword_18015FF10;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                          }
                        }
                        if ( *((_BYTE *)v50 + 8) )
                        {
                          v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
                          if ( *((_DWORD *)v52 + 499) != v4 )
                            CallStackContext::TraceFailure(v52, "FuseOperation::Invoke", 214, v4);
                        }
                        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                          goto LABEL_184;
                        v9 = 34;
                      }
                    }
                    else
                    {
                      v46 = MF::OriginateError((MF *)0x80004003LL, v42);
                      v47 = (__int64 *)CallStackTracing::s_wpInstance;
                      v4 = v46;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v48;
                        if ( v48
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(
                               v48,
                               2032) )
                        {
                          v47 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v47 = &qword_18015FF10;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                        }
                      }
                      if ( *((_BYTE *)v47 + 8) )
                      {
                        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                        if ( v4 < 0 && *((_DWORD *)v49 + 499) != v4 )
                          CallStackContext::TraceFailure(v49, "FuseOperation::Invoke", 213, v4);
                      }
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_184;
                      v9 = 33;
                    }
                  }
                  else
                  {
                    v43 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v44;
                      if ( v44
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(
                             v44,
                             2032) )
                      {
                        v43 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v43 = &qword_18015FF10;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                      }
                    }
                    if ( *((_BYTE *)v43 + 8) )
                    {
                      v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                      if ( *((_DWORD *)v45 + 499) != v4 )
                        CallStackContext::TraceFailure(v45, "FuseOperation::Invoke", 212, v4);
                    }
                    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      goto LABEL_184;
                    v9 = 32;
                  }
                }
                else
                {
                  v37 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v38;
                    if ( v38
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                    {
                      v37 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v37 = &qword_18015FF10;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
                    }
                  }
                  if ( *((_BYTE *)v37 + 8) )
                  {
                    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                    if ( *((_DWORD *)v39 + 499) != v4 )
                      CallStackContext::TraceFailure(v39, "FuseOperation::Invoke", 211, v4);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_184;
                  v9 = 31;
                }
                break;
            }
          }
          else
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_18015FF10;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v36 + 499) != v4 )
                CallStackContext::TraceFailure(v36, "FuseOperation::Invoke", 188, v4);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_184;
            v9 = 27;
          }
        }
        else
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_18015FF10;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != v4 )
              CallStackContext::TraceFailure(v27, "FuseOperation::Invoke", 166, v4);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_184;
          v9 = 24;
        }
      }
      else
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_18015FF10;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v4 )
            CallStackContext::TraceFailure(v23, "FuseOperation::Invoke", 164, v4);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_184;
        v9 = 23;
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_18015FF10;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v4 )
          CallStackContext::TraceFailure(v19, "FuseOperation::Invoke", 162, v4);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_184;
      v9 = 22;
    }
    v8 = (char *)this - 16;
    goto LABEL_183;
  }
  v5 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v6;
    if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
    {
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &qword_18015FF10;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
    }
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    if ( *((_DWORD *)v7 + 499) != v4 )
      CallStackContext::TraceFailure(v7, "FuseOperation::Invoke", 111, v4);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = (char *)this - 16;
    v9 = 19;
LABEL_183:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids, v8, v4);
  }
LABEL_184:
  if ( _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel() >= 8u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      37,
      &WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids,
      (char *)this - 16,
      v4);
  v70 = (char *)this + 8;
  if ( v4 >= 0 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(
      v70,
      1);
  else
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      v70,
      (unsigned int)v4);
  Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion((char *)this + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v83);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  return 0;
}

```

## disassembly

```asm
0x18002e250  push    rbp
0x18002e252  push    rbx
0x18002e253  push    rsi
0x18002e254  push    rdi
0x18002e255  push    r12
0x18002e257  push    r13
0x18002e259  push    r14
0x18002e25b  push    r15
0x18002e25d  lea     rbp, [rsp-8]
0x18002e262  sub     rsp, 108h
0x18002e269  mov     rax, cs:__security_cookie
0x18002e270  xor     rax, rsp
0x18002e273  mov     [rbp+40h+var_50], rax
0x18002e277  xor     r13d, r13d
0x18002e27a  lea     r12, aFuseoperationI; "FuseOperation::Invoke"
0x18002e281  mov     r15, rcx
0x18002e284  mov     [rbp+40h+var_B0], r13d
0x18002e288  mov     rdx, r12; char *
0x18002e28b  lea     rcx, [rbp+40h+var_C0]; this
0x18002e28f  lea     r8d, [r13+5Fh]; int
0x18002e293  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002e298  xorps   xmm0, xmm0
0x18002e29b  mov     [rbp+40h+var_A8], r13d
0x18002e29f  lea     esi, [r13+2]
0x18002e2a3  mov     [rbp+40h+var_A4], r13d
0x18002e2a7  lea     rcx, [rbp+40h+var_90]
0x18002e2ab  mov     [rbp+40h+var_9C], r13d
0x18002e2af  movups  [rbp+40h+var_70], xmm0
0x18002e2b3  mov     [rbp+40h+var_A0], r13d
0x18002e2b7  mov     [rbp+40h+var_88], r13
0x18002e2bb  mov     [rbp+40h+var_90], r13
0x18002e2bf  mov     [rbp+40h+var_78], r13
0x18002e2c3  mov     dword ptr [rsp+140h+var_D0], r13d
0x18002e2c8  mov     dword ptr [rsp+140h+var_D0+4], 1
0x18002e2d0  mov     [rsp+140h+var_C8], esi
0x18002e2d4  mov     [rbp+40h+var_AC], r13d
0x18002e2d8  mov     [rbp+40h+var_80], r13
0x18002e2dc  mov     [rbp+40h+var_98], r13
0x18002e2e0  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002e2e5  lea     rax, [rbp+40h+var_90]
0x18002e2e9  xor     edx, edx; pUnkOuter
0x18002e2eb  lea     r9, _GUID_c3c181ec_2914_4791_af02_02d224a10b43; riid
0x18002e2f2  mov     [rsp+140h+ppv], rax; ppv
0x18002e2f7  lea     r8d, [r13+1]; dwClsContext
0x18002e2fb  lea     rcx, CLSID_SoftwareBitmapNativeFactory; rclsid
0x18002e302  call    cs:__imp_CoCreateInstance
0x18002e308  mov     ebx, eax
0x18002e30a  test    eax, eax
0x18002e30c  jns     loc_18002E3A1
0x18002e312  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e319  test    rcx, rcx
0x18002e31c  jnz     short loc_18002E35F
0x18002e31e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e324  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e32b  mov     rcx, rax
0x18002e32e  test    rax, rax
0x18002e331  jz      short loc_18002E351
0x18002e333  mov     rax, [rax]
0x18002e336  mov     edx, 7F0h
0x18002e33b  mov     rax, [rax+8]
0x18002e33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e344  test    eax, eax
0x18002e346  jz      short loc_18002E351
0x18002e348  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e34f  jmp     short loc_18002E35F
0x18002e351  lea     rcx, qword_18015FF10; this
0x18002e358  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e35f  cmp     [rcx+8], r13b
0x18002e363  jz      short loc_18002E386
0x18002e365  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e36a  cmp     [rax+7CCh], ebx
0x18002e370  jz      short loc_18002E386
0x18002e372  mov     r9d, ebx; int
0x18002e375  mov     r8d, 6Fh ; 'o'; int
0x18002e37b  mov     rdx, r12; char *
0x18002e37e  mov     rcx, rax; this
0x18002e381  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e386  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e38b  cmp     al, 1
0x18002e38d  jb      loc_18002EFB6
0x18002e393  lea     r9, [r15-10h]
0x18002e397  mov     edx, 13h
0x18002e39c  jmp     loc_18002EF9B
0x18002e3a1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel(void)
0x18002e3a6  cmp     al, 8
0x18002e3a8  jb      short loc_18002E3CD
0x18002e3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3b1  lea     r9, [r15-10h]
0x18002e3b5  mov     edx, 14h
0x18002e3ba  lea     r8, WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids
0x18002e3c1  mov     rcx, [rcx+128h]
0x18002e3c8  call    WPP_SF_q
0x18002e3cd  mov     rax, [r15+0D8h]
0x18002e3d4  mov     rcx, [r15+0E0h]
0x18002e3db  movsd   xmm1, qword ptr [rax+58h]
0x18002e3e0  mov     rax, [r15+0D0h]
0x18002e3e7  movsd   xmm0, qword ptr [rcx+58h]
0x18002e3ec  comisd  xmm1, qword ptr [rax+58h]
0x18002e3f1  jb      short loc_18002E434
0x18002e3f3  comisd  xmm0, qword ptr [rax+58h]
0x18002e3f8  jb      short loc_18002E41F
0x18002e3fa  comisd  xmm0, xmm1
0x18002e3fe  mov     ebx, r13d
0x18002e401  mov     dword ptr [rsp+140h+var_D0], ebx
0x18002e405  jb      short loc_18002E412
0x18002e407  mov     edi, 1
0x18002e40c  mov     dword ptr [rsp+140h+var_D0+4], edi
0x18002e410  jmp     short loc_18002E448
0x18002e412  mov     edi, esi
0x18002e414  mov     dword ptr [rsp+140h+var_D0+4], esi
0x18002e418  mov     esi, 1
0x18002e41d  jmp     short loc_18002E448
0x18002e41f  mov     ebx, esi
0x18002e421  mov     dword ptr [rsp+140h+var_D0+4], r13d
0x18002e426  mov     esi, 1
0x18002e42b  mov     edi, r13d
0x18002e42e  mov     [rsp+140h+var_C8], esi
0x18002e432  jmp     short loc_18002E471
0x18002e434  comisd  xmm0, qword ptr [rax+58h]
0x18002e439  jb      short loc_18002E44E
0x18002e43b  mov     ebx, 1
0x18002e440  mov     edi, r13d
0x18002e443  mov     [rsp+140h+var_D0], rbx
0x18002e448  mov     [rsp+140h+var_C8], esi
0x18002e44c  jmp     short loc_18002E475
0x18002e44e  comisd  xmm0, xmm1
0x18002e452  jb      short loc_18002E462
0x18002e454  mov     ebx, 1
0x18002e459  mov     [rsp+140h+var_D0+4], rsi
0x18002e45e  mov     edi, esi
0x18002e460  jmp     short loc_18002E46E
0x18002e462  mov     edi, 1
0x18002e467  mov     ebx, esi
0x18002e469  mov     [rsp+140h+var_D0+4], rdi
0x18002e46e  mov     esi, r13d
0x18002e471  mov     dword ptr [rsp+140h+var_D0], ebx
0x18002e475  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel(void)
0x18002e47a  cmp     al, 8
0x18002e47c  jb      short loc_18002E4AD
0x18002e47e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e485  lea     r9, [r15-10h]
0x18002e489  mov     dword ptr [rsp+140h+var_110], esi
0x18002e48d  lea     r8, WPP_2a0cc8ddad0832ea6177204d38491785_Traceguids
0x18002e494  mov     edx, 15h
0x18002e499  mov     dword ptr [rsp+140h+var_118], edi
0x18002e49d  mov     dword ptr [rsp+140h+ppv], ebx
0x18002e4a1  mov     rcx, [rcx+128h]
0x18002e4a8  call    WPP_SF_qddd
0x18002e4ad  mov     eax, ebx
0x18002e4af  lea     r14, [r15-10h]
0x18002e4b3  mov     rcx, [r14+0D8h]
0x18002e4ba  mov     rdx, [r15+rax*8+0D0h]
0x18002e4c2  mov     rax, [rcx]
0x18002e4c5  mov     r8d, [rdx+54h]
0x18002e4c9  mov     r9d, [rdx+4Ch]
0x18002e4cd  mov     rax, [rax+20h]
0x18002e4d1  mov     dword ptr [rsp+140h+var_118], r8d
0x18002e4d6  mov     r8d, [rdx+50h]
0x18002e4da  mov     dword ptr [rsp+140h+ppv], r8d
0x18002e4df  mov     r8, [rdx+40h]
0x18002e4e3  mov     rdx, [rdx+38h]
0x18002e4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4ec  mov     ebx, eax
0x18002e4ee  test    eax, eax
0x18002e4f0  jns     loc_18002E581
0x18002e4f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e4fd  test    rcx, rcx
0x18002e500  jnz     short loc_18002E543
0x18002e502  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e508  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e50f  mov     rcx, rax
0x18002e512  test    rax, rax
0x18002e515  jz      short loc_18002E535
0x18002e517  mov     rax, [rax]
0x18002e51a  mov     edx, 7F0h
0x18002e51f  mov     rax, [rax+8]
0x18002e523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e528  test    eax, eax
0x18002e52a  jz      short loc_18002E535
0x18002e52c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e533  jmp     short loc_18002E543
0x18002e535  lea     rcx, qword_18015FF10; this
0x18002e53c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e543  cmp     [rcx+8], r13b
0x18002e547  jz      short loc_18002E56A
0x18002e549  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e54e  cmp     [rax+7CCh], ebx
0x18002e554  jz      short loc_18002E56A
0x18002e556  mov     r9d, ebx; int
0x18002e559  mov     r8d, 0A2h; int
0x18002e55f  mov     rdx, r12; char *
0x18002e562  mov     rcx, rax; this
0x18002e565  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e56a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e56f  cmp     al, 1
0x18002e571  jb      loc_18002EFB6
0x18002e577  mov     edx, 16h
0x18002e57c  jmp     loc_18002EF98
0x18002e581  mov     rcx, [r14+0D8h]
0x18002e588  mov     eax, edi
0x18002e58a  mov     rdx, [r15+rax*8+0D0h]
0x18002e592  mov     rax, [rcx]
0x18002e595  mov     r8d, [rdx+54h]
0x18002e599  mov     r9d, [rdx+4Ch]
0x18002e59d  mov     rax, [rax+20h]
0x18002e5a1  mov     dword ptr [rsp+140h+var_118], r8d
0x18002e5a6  mov     r8d, [rdx+50h]
0x18002e5aa  mov     dword ptr [rsp+140h+ppv], r8d
0x18002e5af  mov     r8, [rdx+40h]
0x18002e5b3  mov     rdx, [rdx+38h]
0x18002e5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5bc  mov     ebx, eax
0x18002e5be  test    eax, eax
0x18002e5c0  jns     loc_18002E651
0x18002e5c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5cd  test    rcx, rcx
0x18002e5d0  jnz     short loc_18002E613
0x18002e5d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e5d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e5df  mov     rcx, rax
0x18002e5e2  test    rax, rax
0x18002e5e5  jz      short loc_18002E605
0x18002e5e7  mov     rax, [rax]
0x18002e5ea  mov     edx, 7F0h
0x18002e5ef  mov     rax, [rax+8]
0x18002e5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f8  test    eax, eax
0x18002e5fa  jz      short loc_18002E605
0x18002e5fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e603  jmp     short loc_18002E613
0x18002e605  lea     rcx, qword_18015FF10; this
0x18002e60c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e613  cmp     [rcx+8], r13b
0x18002e617  jz      short loc_18002E63A
0x18002e619  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e61e  cmp     [rax+7CCh], ebx
0x18002e624  jz      short loc_18002E63A
0x18002e626  mov     r9d, ebx; int
0x18002e629  mov     r8d, 0A4h; int
0x18002e62f  mov     rdx, r12; char *
0x18002e632  mov     rcx, rax; this
0x18002e635  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e63a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e63f  cmp     al, 1
0x18002e641  jb      loc_18002EFB6
0x18002e647  mov     edx, 17h
0x18002e64c  jmp     loc_18002EF98
0x18002e651  mov     rcx, [r14+0D8h]
0x18002e658  mov     eax, esi
0x18002e65a  mov     rdx, [r15+rax*8+0D0h]
0x18002e662  mov     rax, [rcx]
0x18002e665  mov     r8d, [rdx+54h]
0x18002e669  mov     r9d, [rdx+4Ch]
0x18002e66d  mov     rax, [rax+20h]
0x18002e671  mov     dword ptr [rsp+140h+var_118], r8d
0x18002e676  mov     r8d, [rdx+50h]
0x18002e67a  mov     dword ptr [rsp+140h+ppv], r8d
0x18002e67f  mov     r8, [rdx+40h]
0x18002e683  mov     rdx, [rdx+38h]
0x18002e687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e68c  mov     ebx, eax
0x18002e68e  test    eax, eax
0x18002e690  jns     loc_18002E721
0x18002e696  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e69d  test    rcx, rcx
0x18002e6a0  jnz     short loc_18002E6E3
0x18002e6a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002e6a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6af  mov     rcx, rax
0x18002e6b2  test    rax, rax
0x18002e6b5  jz      short loc_18002E6D5
0x18002e6b7  mov     rax, [rax]
0x18002e6ba  mov     edx, 7F0h
0x18002e6bf  mov     rax, [rax+8]
0x18002e6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6c8  test    eax, eax
0x18002e6ca  jz      short loc_18002E6D5
0x18002e6cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6d3  jmp     short loc_18002E6E3
0x18002e6d5  lea     rcx, qword_18015FF10; this
0x18002e6dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002e6e3  cmp     [rcx+8], r13b
0x18002e6e7  jz      short loc_18002E70A
0x18002e6e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002e6ee  cmp     [rax+7CCh], ebx
0x18002e6f4  jz      short loc_18002E70A
0x18002e6f6  mov     r9d, ebx; int
0x18002e6f9  mov     r8d, 0A6h; int
0x18002e6ff  mov     rdx, r12; char *
0x18002e702  mov     rcx, rax; this
0x18002e705  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002e70a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002e70f  cmp     al, 1
0x18002e711  jb      loc_18002EFB6
0x18002e717  mov     edx, 18h
0x18002e71c  jmp     loc_18002EF98
0x18002e721  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CAPTURE_ENGINE::GetLevel(void)
0x18002e726  cmp     al, 8
0x18002e728  jb      short loc_18002E74C
0x18002e72a  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
