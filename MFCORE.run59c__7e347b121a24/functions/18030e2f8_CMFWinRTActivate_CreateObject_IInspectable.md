# CMFWinRTActivate::_CreateObject(IInspectable * *)

- ea: `0x18030e2f8`
- end: `0x18030ed10`
- name: `?_CreateObject@CMFWinRTActivate@@AEAAJPEAPEAUIInspectable@@@Z`
- size: `2584`
- prototype: `__int64 __fastcall(struct IMFTransform *this, struct IInspectable **)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801cf9c0`
- `0x1801d1500`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180097f10`
- `0x1800ec0e0`
- `0x180127f08`
- `0x180197308`
- `0x1801a5230`
- `0x180258480`
- `0x18029dc10`
- `0x18029e06c`
- `0x1803085f4`
- `0x18030864c`
- `0x18030e2f8`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030ec92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030ec92`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030e569`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030e731`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030e569`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18030e731`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e3a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e58b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e64f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e753`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e817`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e91f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e9d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030eaf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030ebbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e3a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e487`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e58b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e64f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e753`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e817`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e91f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030e9d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030eaf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030ebbe`

## string_xrefs

- `0x18030e707`: `Windows.Media.Effects.BasicVideoEffectMediaExtensionWrapper`
- `0x18030e53f`: `Windows.Media.Effects.BasicAudioEffectMediaExtensionWrapper`
- `0x18030e325`: `CMFWinRTActivate::_CreateObject`

## pseudocode

```c
__int64 __fastcall CMFWinRTActivate::_CreateObject(struct IMFTransform *this, struct IInspectable **a2)
{
  struct IMFTransformVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetInputAvailableType)(IMFTransform *, DWORD, DWORD, IMFMediaType **); // rax
  __int64 v6; // rdx
  int ActivationFactory; // esi
  __int64 v8; // r8
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  HSTRING v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  struct IInspectable *v19; // rbx
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rdi
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *); // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  struct IInspectable *v34; // rbx
  HRESULT (__stdcall *v35)(IInspectable *, const IID *const, void **); // rdi
  __int64 v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, __int64, __int64 *); // rbx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rcx
  struct IInspectable *v50; // rbx
  HRESULT (__stdcall *v51)(IInspectable *, const IID *const, void **); // rdi
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  struct IInspectable *v62; // rbx
  HRESULT (__stdcall *v63)(IInspectable *, const IID *const, void **); // rdi
  __int64 v64; // rdx
  struct IMFAttributes *v65; // r8
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  char v75; // al
  _BYTE v77[8]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v78; // [rsp+38h] [rbp-61h] BYREF
  struct IInspectable *v79; // [rsp+40h] [rbp-59h] BYREF
  struct IMFTransform *v80; // [rsp+48h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-49h] BYREF
  __int64 v82; // [rsp+58h] [rbp-41h] BYREF
  __int64 v83; // [rsp+60h] [rbp-39h] BYREF
  __int64 v84; // [rsp+68h] [rbp-31h] BYREF
  __int64 v85; // [rsp+70h] [rbp-29h] BYREF
  void *v86; // [rsp+78h] [rbp-21h] BYREF
  int v87; // [rsp+80h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+88h] [rbp-11h] BYREF
  HSTRING string[4]; // [rsp+98h] [rbp-1h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v77, "CMFWinRTActivate::_CreateObject", 462);
  *a2 = 0;
  lpVtbl = this->lpVtbl;
  pv = 0;
  v87 = 0;
  v79 = 0;
  GetInputAvailableType = lpVtbl->GetInputAvailableType;
  v86 = 0;
  Buf1 = 0;
  v78 = 0;
  v85 = 0;
  v84 = 0;
  v83 = 0;
  v82 = 0;
  ActivationFactory = ((__int64 (__fastcall *)(struct IMFTransform *, void *, LPVOID *, int *))GetInputAvailableType)(
                        this,
                        &MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID,
                        &pv,
                        &v87);
  if ( ActivationFactory < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != ActivationFactory )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFWinRTActivate::_CreateObject", 479, ActivationFactory);
    }
    if ( g_wppLevels )
    {
      v12 = 57;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
        this,
        ActivationFactory);
      goto LABEL_126;
    }
    goto LABEL_126;
  }
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)string,
    (const unsigned __int16 *)pv);
  v13 = string[0];
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v79);
  ActivationFactory = Windows::Foundation::ActivateInstance<IInspectable>(v13, &v79);
  if ( ActivationFactory >= 0 )
  {
    v19 = v79;
    QueryInterface = v79->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v85);
    if ( ((int (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
           v19,
           &GUID_8c062c53_6bc0_48b8_a99a_4b41550f1359,
           &v85) < 0 )
    {
      v34 = v79;
      v35 = v79->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v84);
      if ( ((int (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v35)(
             v34,
             &GUID_8262c7ef_b360_40be_949b_2ff42ff35693,
             &v84) < 0 )
        goto LABEL_71;
      v36 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                         string,
                         L"Windows.Media.Effects.BasicVideoEffectMediaExtensionWrapper");
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v82);
      ActivationFactory = RoGetActivationFactory(v36, &GUID_fb8471b9_91dc_465c_b1e7_89ab34ddd8e3, &v82);
      if ( ActivationFactory < 0 )
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
          if ( *((_DWORD *)v41 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v41, "CMFWinRTActivate::_CreateObject", 505, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v12 = 61;
          goto LABEL_12;
        }
        goto LABEL_126;
      }
      v42 = v82;
      v43 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v82 + 48LL);
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v78);
      ActivationFactory = v43(v42, v84, &v78);
      if ( ActivationFactory < 0 )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
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
          if ( *((_DWORD *)v48 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v48, "CMFWinRTActivate::_CreateObject", 506, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v12 = 62;
          goto LABEL_12;
        }
        goto LABEL_126;
      }
    }
    else
    {
      v21 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                         string,
                         L"Windows.Media.Effects.BasicAudioEffectMediaExtensionWrapper");
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v83);
      ActivationFactory = RoGetActivationFactory(v21, &GUID_f72124a3_03fb_49ef_9009_6d214a5c3740, &v83);
      if ( ActivationFactory < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v26, "CMFWinRTActivate::_CreateObject", 496, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v12 = 59;
          goto LABEL_12;
        }
        goto LABEL_126;
      }
      v27 = v83;
      v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v83 + 48LL);
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v78);
      ActivationFactory = v28(v27, v85, &v78);
      if ( ActivationFactory < 0 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v33, "CMFWinRTActivate::_CreateObject", 497, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v12 = 60;
          goto LABEL_12;
        }
        goto LABEL_126;
      }
    }
    Microsoft::WRL::ComPtr<IInspectable>::operator=<Windows::Media::IMediaExtension>(&v79, &v78);
LABEL_71:
    Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v86);
    if ( (int)CGITPtr::Get((CGITPtr *)&this[19], &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v86) >= 0 )
    {
      v49 = v78;
      if ( !v78 )
      {
        v50 = v79;
        v51 = v79->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v78);
        ActivationFactory = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))v51)(
                              v50,
                              &GUID_07915118_45df_442b_8a3f_f7826a6370ab,
                              &v78);
        if ( ActivationFactory < 0 )
        {
          v54 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
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
            if ( *((_DWORD *)v56 + 499) != ActivationFactory )
              CallStackContext::TraceFailure(v56, "CMFWinRTActivate::_CreateObject", 516, ActivationFactory);
          }
          if ( g_wppLevels )
          {
            v12 = 63;
            goto LABEL_12;
          }
          goto LABEL_126;
        }
        v49 = v78;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v49 + 48LL))(v49, v86);
      if ( ActivationFactory < 0 )
      {
        v59 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v57, v58);
          CallStackTracing::s_wpInstance = v60;
          if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
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
          if ( *((_DWORD *)v61 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v61, "CMFWinRTActivate::_CreateObject", 518, ActivationFactory);
        }
        if ( g_wppLevels )
        {
          v12 = 64;
          goto LABEL_12;
        }
        goto LABEL_126;
      }
    }
    if ( !((unsigned int (__fastcall *)(struct IMFTransform *, const GUID *, __int128 *))this->lpVtbl->GetOutputStreamAttributes)(
            this,
            &MF_TRANSFORM_CATEGORY_Attribute,
            &Buf1)
      && (!memcmp_0(&Buf1, &MFT_CATEGORY_AUDIO_ENCODER, 0x10u) || !memcmp_0(&Buf1, &MFT_CATEGORY_VIDEO_ENCODER, 0x10u)) )
    {
      v62 = v79;
      v80 = 0;
      v63 = v79->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v80);
      ActivationFactory = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, struct IMFTransform **))v63)(
                            v62,
                            &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
                            &v80);
      if ( ActivationFactory < 0 )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65);
          CallStackTracing::s_wpInstance = v67;
          if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
          {
            v66 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v66 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
          if ( *((_DWORD *)v68 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v68, "CMFWinRTActivate::_CreateObject", 527, ActivationFactory);
        }
        if ( !g_wppLevels )
          goto LABEL_111;
        v69 = 65;
LABEL_110:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v69,
          &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
          this,
          ActivationFactory);
LABEL_111:
        Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v80);
        goto LABEL_126;
      }
      ActivationFactory = MFTActivateHelper::ConfigureEncoderFromActivateAttributes(v80, this, v65);
      if ( ActivationFactory < 0 )
      {
        v72 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71);
          CallStackTracing::s_wpInstance = v73;
          if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
          {
            v72 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v72 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v72 + 8) )
        {
          v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
          if ( *((_DWORD *)v74 + 499) != ActivationFactory )
            CallStackContext::TraceFailure(v74, "CMFWinRTActivate::_CreateObject", 529, ActivationFactory);
        }
        if ( !g_wppLevels )
          goto LABEL_111;
        v69 = 66;
        goto LABEL_110;
      }
      Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v80);
    }
    v75 = (char)v79;
    *a2 = v79;
    v79 = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qSq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        67,
        (unsigned int)&WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
        (_DWORD)this,
        (__int64)pv,
        v75);
    goto LABEL_126;
  }
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
    if ( *((_DWORD *)v18 + 499) != ActivationFactory )
      CallStackContext::TraceFailure(v18, "CMFWinRTActivate::_CreateObject", 482, ActivationFactory);
  }
  if ( g_wppLevels )
  {
    v12 = 58;
    goto LABEL_12;
  }
LABEL_126:
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v79);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v77);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18030e2f8  mov     [rsp-8+arg_10], rbx
0x18030e2fd  push    rbp
0x18030e2fe  push    rsi
0x18030e2ff  push    rdi
0x18030e300  push    r12
0x18030e302  push    r13
0x18030e304  push    r14
0x18030e306  push    r15
0x18030e308  lea     rbp, [rsp-27h]
0x18030e30d  sub     rsp, 0C0h
0x18030e314  mov     rax, cs:__security_cookie
0x18030e31b  xor     rax, rsp
0x18030e31e  mov     [rbp+57h+var_38], rax
0x18030e322  mov     r15, rdx
0x18030e325  lea     r13, aCmfwinrtactiva_3; "CMFWinRTActivate::_CreateObject"
0x18030e32c  mov     r14, rcx
0x18030e32f  mov     rdx, r13; char *
0x18030e332  mov     r8d, 1CEh; int
0x18030e338  lea     rcx, [rbp+57h+var_C0]; this
0x18030e33c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18030e341  xor     r12d, r12d
0x18030e344  lea     r9, [rbp+57h+var_70]
0x18030e348  mov     [r15], r12
0x18030e34b  lea     r8, [rbp+57h+pv]
0x18030e34f  mov     rax, [r14]
0x18030e352  lea     rdx, MF_MEDIA_EXTENSION_ACTIVATABLE_CLASS_ID
0x18030e359  xorps   xmm0, xmm0
0x18030e35c  mov     [rbp+57h+pv], r12
0x18030e360  mov     rcx, r14
0x18030e363  mov     [rbp+57h+var_70], r12d
0x18030e367  mov     [rbp+57h+var_B0], r12
0x18030e36b  mov     rax, [rax+68h]
0x18030e36f  mov     [rbp+57h+var_78], r12
0x18030e373  movups  [rbp+57h+Buf1], xmm0
0x18030e377  mov     [rbp+57h+var_B8], r12
0x18030e37b  mov     [rbp+57h+var_80], r12
0x18030e37f  mov     [rbp+57h+var_88], r12
0x18030e383  mov     [rbp+57h+var_90], r12
0x18030e387  mov     [rbp+57h+var_98], r12
0x18030e38b  call    cs:__guard_dispatch_icall_fptr
0x18030e391  mov     esi, eax
0x18030e393  test    eax, eax
0x18030e395  jns     loc_18030E44B
0x18030e39b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e3a2  test    rcx, rcx
0x18030e3a5  jnz     short loc_18030E3EF
0x18030e3a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18030e3ae  nop     dword ptr [rax+rax+00h]
0x18030e3b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e3ba  mov     rcx, rax
0x18030e3bd  test    rax, rax
0x18030e3c0  jz      short loc_18030E3E1
0x18030e3c2  mov     rax, [rax]
0x18030e3c5  mov     edx, 7F0h
0x18030e3ca  mov     rax, [rax+8]
0x18030e3ce  call    cs:__guard_dispatch_icall_fptr
0x18030e3d4  test    eax, eax
0x18030e3d6  jz      short loc_18030E3E1
0x18030e3d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e3df  jmp     short loc_18030E3EF
0x18030e3e1  lea     rcx, qword_1803CE250; this
0x18030e3e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e3ef  cmp     [rcx+8], r12b
0x18030e3f3  jz      short loc_18030E416
0x18030e3f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18030e3fa  cmp     [rax+7CCh], esi
0x18030e400  jz      short loc_18030E416
0x18030e402  mov     r9d, esi; int
0x18030e405  mov     r8d, 1DFh; int
0x18030e40b  mov     rdx, r13; char *
0x18030e40e  mov     rcx, rax; this
0x18030e411  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18030e416  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18030e41d  jb      loc_18030EC8E
0x18030e423  mov     edx, 39h ; '9'
0x18030e428  mov     rcx, cs:WPP_GLOBAL_Control
0x18030e42f  lea     r8, WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids
0x18030e436  mov     r9, r14
0x18030e439  mov     dword ptr [rsp+0F0h+var_D0], esi
0x18030e43d  mov     rcx, [rcx+10h]
0x18030e441  call    WPP_SF_qD
0x18030e446  jmp     loc_18030EC8E
0x18030e44b  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18030e44f  lea     rcx, [rbp+57h+string]; this
0x18030e453  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18030e458  mov     rbx, [rbp+57h+string]
0x18030e45c  lea     rcx, [rbp+57h+var_B0]
0x18030e460  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e465  lea     rdx, [rbp+57h+var_B0]
0x18030e469  mov     rcx, rbx
0x18030e46c  call    ??$ActivateInstance@UIInspectable@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; Windows::Foundation::ActivateInstance<IInspectable>(HSTRING__ *,IInspectable * *)
0x18030e471  mov     esi, eax
0x18030e473  test    eax, eax
0x18030e475  jns     loc_18030E50D
0x18030e47b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e482  test    rcx, rcx
0x18030e485  jnz     short loc_18030E4CF
0x18030e487  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18030e48e  nop     dword ptr [rax+rax+00h]
0x18030e493  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e49a  mov     rcx, rax
0x18030e49d  test    rax, rax
0x18030e4a0  jz      short loc_18030E4C1
0x18030e4a2  mov     rax, [rax]
0x18030e4a5  mov     edx, 7F0h
0x18030e4aa  mov     rax, [rax+8]
0x18030e4ae  call    cs:__guard_dispatch_icall_fptr
0x18030e4b4  test    eax, eax
0x18030e4b6  jz      short loc_18030E4C1
0x18030e4b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e4bf  jmp     short loc_18030E4CF
0x18030e4c1  lea     rcx, qword_1803CE250; this
0x18030e4c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e4cf  cmp     [rcx+8], r12b
0x18030e4d3  jz      short loc_18030E4F6
0x18030e4d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18030e4da  cmp     [rax+7CCh], esi
0x18030e4e0  jz      short loc_18030E4F6
0x18030e4e2  mov     r9d, esi; int
0x18030e4e5  mov     r8d, 1E2h; int
0x18030e4eb  mov     rdx, r13; char *
0x18030e4ee  mov     rcx, rax; this
0x18030e4f1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18030e4f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18030e4fd  jb      loc_18030EC8E
0x18030e503  mov     edx, 3Ah ; ':'
0x18030e508  jmp     loc_18030E428
0x18030e50d  mov     rbx, [rbp+57h+var_B0]
0x18030e511  lea     rcx, [rbp+57h+var_80]
0x18030e515  mov     rax, [rbx]
0x18030e518  mov     rdi, [rax]
0x18030e51b  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e520  lea     r8, [rbp+57h+var_80]
0x18030e524  mov     rcx, rbx
0x18030e527  lea     rdx, _GUID_8c062c53_6bc0_48b8_a99a_4b41550f1359
0x18030e52e  mov     rax, rdi
0x18030e531  call    cs:__guard_dispatch_icall_fptr
0x18030e537  test    eax, eax
0x18030e539  js      loc_18030E6D5
0x18030e53f  lea     rdx, ?RuntimeClass_Windows_Media_Effects_BasicAudioEffectMediaExtensionWrapper@@3QBGB; "Windows.Media.Effects.BasicAudioEffectM"...
0x18030e546  lea     rcx, [rbp+57h+string]; string
0x18030e54a  call    ??$?0$0DM@@StringReference@Internal@Windows@@QEAA@AEAY0DM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[60])
0x18030e54f  lea     rcx, [rbp+57h+var_90]
0x18030e553  mov     rbx, [rax]
0x18030e556  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e55b  lea     r8, [rbp+57h+var_90]
0x18030e55f  mov     rcx, rbx
0x18030e562  lea     rdx, _GUID_f72124a3_03fb_49ef_9009_6d214a5c3740
0x18030e569  call    cs:__imp_RoGetActivationFactory
0x18030e570  nop     dword ptr [rax+rax+00h]
0x18030e575  mov     esi, eax
0x18030e577  test    eax, eax
0x18030e579  jns     loc_18030E611
0x18030e57f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e586  test    rcx, rcx
0x18030e589  jnz     short loc_18030E5D3
0x18030e58b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18030e592  nop     dword ptr [rax+rax+00h]
0x18030e597  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e59e  mov     rcx, rax
0x18030e5a1  test    rax, rax
0x18030e5a4  jz      short loc_18030E5C5
0x18030e5a6  mov     rax, [rax]
0x18030e5a9  mov     edx, 7F0h
0x18030e5ae  mov     rax, [rax+8]
0x18030e5b2  call    cs:__guard_dispatch_icall_fptr
0x18030e5b8  test    eax, eax
0x18030e5ba  jz      short loc_18030E5C5
0x18030e5bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e5c3  jmp     short loc_18030E5D3
0x18030e5c5  lea     rcx, qword_1803CE250; this
0x18030e5cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e5d3  cmp     [rcx+8], r12b
0x18030e5d7  jz      short loc_18030E5FA
0x18030e5d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18030e5de  cmp     [rax+7CCh], esi
0x18030e5e4  jz      short loc_18030E5FA
0x18030e5e6  mov     r9d, esi; int
0x18030e5e9  mov     r8d, 1F0h; int
0x18030e5ef  mov     rdx, r13; char *
0x18030e5f2  mov     rcx, rax; this
0x18030e5f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18030e5fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18030e601  jb      loc_18030EC8E
0x18030e607  mov     edx, 3Bh ; ';'
0x18030e60c  jmp     loc_18030E428
0x18030e611  mov     rdi, [rbp+57h+var_90]
0x18030e615  lea     rcx, [rbp+57h+var_B8]
0x18030e619  mov     rax, [rdi]
0x18030e61c  mov     rbx, [rax+30h]
0x18030e620  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e625  mov     rdx, [rbp+57h+var_80]
0x18030e629  lea     r8, [rbp+57h+var_B8]
0x18030e62d  mov     rcx, rdi
0x18030e630  mov     rax, rbx
0x18030e633  call    cs:__guard_dispatch_icall_fptr
0x18030e639  mov     esi, eax
0x18030e63b  test    eax, eax
0x18030e63d  jns     loc_18030E89D
0x18030e643  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e64a  test    rcx, rcx
0x18030e64d  jnz     short loc_18030E697
0x18030e64f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18030e656  nop     dword ptr [rax+rax+00h]
0x18030e65b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e662  mov     rcx, rax
0x18030e665  test    rax, rax
0x18030e668  jz      short loc_18030E689
0x18030e66a  mov     rax, [rax]
0x18030e66d  mov     edx, 7F0h
0x18030e672  mov     rax, [rax+8]
0x18030e676  call    cs:__guard_dispatch_icall_fptr
0x18030e67c  test    eax, eax
0x18030e67e  jz      short loc_18030E689
0x18030e680  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e687  jmp     short loc_18030E697
0x18030e689  lea     rcx, qword_1803CE250; this
0x18030e690  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e697  cmp     [rcx+8], r12b
0x18030e69b  jz      short loc_18030E6BE
0x18030e69d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18030e6a2  cmp     [rax+7CCh], esi
0x18030e6a8  jz      short loc_18030E6BE
0x18030e6aa  mov     r9d, esi; int
0x18030e6ad  mov     r8d, 1F1h; int
0x18030e6b3  mov     rdx, r13; char *
0x18030e6b6  mov     rcx, rax; this
0x18030e6b9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18030e6be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18030e6c5  jb      loc_18030EC8E
0x18030e6cb  mov     edx, 3Ch ; '<'
0x18030e6d0  jmp     loc_18030E428
0x18030e6d5  mov     rbx, [rbp+57h+var_B0]
0x18030e6d9  lea     rcx, [rbp+57h+var_88]
0x18030e6dd  mov     rax, [rbx]
0x18030e6e0  mov     rdi, [rax]
0x18030e6e3  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e6e8  lea     r8, [rbp+57h+var_88]
0x18030e6ec  mov     rcx, rbx
0x18030e6ef  lea     rdx, _GUID_8262c7ef_b360_40be_949b_2ff42ff35693
0x18030e6f6  mov     rax, rdi
0x18030e6f9  call    cs:__guard_dispatch_icall_fptr
0x18030e6ff  test    eax, eax
0x18030e701  js      loc_18030E8AA
0x18030e707  lea     rdx, ?RuntimeClass_Windows_Media_Effects_BasicVideoEffectMediaExtensionWrapper@@3QBGB; "Windows.Media.Effects.BasicVideoEffectM"...
0x18030e70e  lea     rcx, [rbp+57h+string]; string
0x18030e712  call    ??$?0$0DM@@StringReference@Internal@Windows@@QEAA@AEAY0DM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[60])
0x18030e717  lea     rcx, [rbp+57h+var_98]
0x18030e71b  mov     rbx, [rax]
0x18030e71e  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e723  lea     r8, [rbp+57h+var_98]
0x18030e727  mov     rcx, rbx
0x18030e72a  lea     rdx, _GUID_fb8471b9_91dc_465c_b1e7_89ab34ddd8e3
0x18030e731  call    cs:__imp_RoGetActivationFactory
0x18030e738  nop     dword ptr [rax+rax+00h]
0x18030e73d  mov     esi, eax
0x18030e73f  test    eax, eax
0x18030e741  jns     loc_18030E7D9
0x18030e747  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e74e  test    rcx, rcx
0x18030e751  jnz     short loc_18030E79B
0x18030e753  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18030e75a  nop     dword ptr [rax+rax+00h]
0x18030e75f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e766  mov     rcx, rax
0x18030e769  test    rax, rax
0x18030e76c  jz      short loc_18030E78D
0x18030e76e  mov     rax, [rax]
0x18030e771  mov     edx, 7F0h
0x18030e776  mov     rax, [rax+8]
0x18030e77a  call    cs:__guard_dispatch_icall_fptr
0x18030e780  test    eax, eax
0x18030e782  jz      short loc_18030E78D
0x18030e784  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e78b  jmp     short loc_18030E79B
0x18030e78d  lea     rcx, qword_1803CE250; this
0x18030e794  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18030e79b  cmp     [rcx+8], r12b
0x18030e79f  jz      short loc_18030E7C2
0x18030e7a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18030e7a6  cmp     [rax+7CCh], esi
0x18030e7ac  jz      short loc_18030E7C2
0x18030e7ae  mov     r9d, esi; int
0x18030e7b1  mov     r8d, 1F9h; int
0x18030e7b7  mov     rdx, r13; char *
0x18030e7ba  mov     rcx, rax; this
0x18030e7bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18030e7c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18030e7c9  jb      loc_18030EC8E
0x18030e7cf  mov     edx, 3Dh ; '='
0x18030e7d4  jmp     loc_18030E428
0x18030e7d9  mov     rdi, [rbp+57h+var_98]
0x18030e7dd  lea     rcx, [rbp+57h+var_B8]
0x18030e7e1  mov     rax, [rdi]
0x18030e7e4  mov     rbx, [rax+30h]
0x18030e7e8  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030e7ed  mov     rdx, [rbp+57h+var_88]
0x18030e7f1  lea     r8, [rbp+57h+var_B8]
0x18030e7f5  mov     rcx, rdi
0x18030e7f8  mov     rax, rbx
  ... truncated ...
```
