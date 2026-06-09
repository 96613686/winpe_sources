# LowLightFusionOperation::Invoke(Windows::Foundation::IAsyncAction *)

- ea: `0x1800a9b90`
- end: `0x1800aab6b`
- name: `?Invoke@LowLightFusionOperation@@EEAAJPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `4059`
- prototype: `__int64 __fastcall(LowLightFusionOperation *__hidden this, struct Windows::Foundation::IAsyncAction *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001784`
- `0x180001a4c`
- `0x180002420`
- `0x180005660`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x18002bb98`
- `0x18002cadc`
- `0x18002cb2c`
- `0x18002fbc8`
- `0x18002fbfc`
- `0x1800a75a0`
- `0x1800a8c18`
- `0x1800a8c58`
- `0x1800a96f0`
- `0x1800a9b90`
- `0x1800ab500`
- `0x1800abb80`
- `0x18012f808`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a9c40`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a9c40`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa0a6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa10f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa0a6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa10f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800aa09c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800aa09c`
- `MFPlat!MFStartup` at `0x1800a9f07`
- `MFPlat!MFStartup` at `0x1800a9f07`
- `MFPlat!MFShutdown` at `0x1800aa17f`
- `MFPlat!MFShutdown` at `0x1800aa17f`

## pseudocode

```c
__int64 __fastcall LowLightFusionOperation::Invoke(
        LowLightFusionOperation *this,
        struct Windows::Foundation::IAsyncAction *a2)
{
  int v3; // r12d
  __int64 v4; // rdi
  int v5; // r13d
  char v6; // r15
  HRESULT v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  char *v10; // r9
  __int64 v11; // rdx
  char *v12; // rsi
  struct Windows::Graphics::Imaging::ISoftwareBitmap *v13; // rdx
  struct Windows::Graphics::Imaging::ISoftwareBitmap *v14; // rdx
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  int v26; // edx
  int v27; // r8d
  signed int v28; // ecx
  double v29; // xmm0_8
  unsigned __int64 v30; // rax
  double v31; // xmm0_8
  double LowPart; // xmm1_8
  float v33; // xmm0_4
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  int v40; // edx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  int v45; // edx
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  CallStackTracing *v48; // rcx
  struct CallStackContext *v49; // rax
  _QWORD *v50; // rcx
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, GUID *, __int64 *); // rbx
  int v57; // edx
  CallStackTracing *v58; // rcx
  struct CallStackContext *v59; // rax
  __int64 v60; // rdx
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  char *v64; // rcx
  HRESULT v65; // eax
  CallStackTracing *v66; // rcx
  struct CallStackContext *v67; // rax
  CallStackTracing *v68; // rcx
  struct CallStackContext *v69; // rax
  __int64 v70; // rcx
  CallStackTracing *v71; // rcx
  struct CallStackContext *v72; // rax
  __int64 v73; // rcx
  CallStackTracing *v74; // rcx
  struct CallStackContext *v75; // rax
  LPVOID v76; // rdi
  __int64 (__fastcall *v77)(LPVOID, __int64, const GUID *, _QWORD, int, _DWORD, __int128 *, GUID *, LARGE_INTEGER *); // rbx
  CallStackTracing *v78; // rcx
  struct CallStackContext *v79; // rax
  CallStackTracing *v80; // rcx
  struct CallStackContext *v81; // rax
  int v83; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v84; // [rsp+74h] [rbp-8Ch] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v86[4]; // [rsp+80h] [rbp-80h] BYREF
  int v87; // [rsp+84h] [rbp-7Ch] BYREF
  int v88; // [rsp+88h] [rbp-78h] BYREF
  int v89; // [rsp+8Ch] [rbp-74h] BYREF
  int v90; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v91; // [rsp+94h] [rbp-6Ch] BYREF
  int v92; // [rsp+98h] [rbp-68h] BYREF
  int v93; // [rsp+9Ch] [rbp-64h] BYREF
  int v94; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v95; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int8 *v96; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v97; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v98; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v100; // [rsp+C8h] [rbp-38h] BYREF
  int v101; // [rsp+D0h] [rbp-30h] BYREF
  int v102; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v103; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v104; // [rsp+E0h] [rbp-20h] BYREF
  LARGE_INTEGER Frequency[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v106; // [rsp+100h] [rbp+0h] BYREF
  __int128 v107; // [rsp+110h] [rbp+10h] BYREF
  __int128 v108; // [rsp+120h] [rbp+20h] BYREF
  __int128 v109; // [rsp+130h] [rbp+30h] BYREF

  v88 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v86, "LowLightFusionOperation::Invoke", 140);
  v3 = 0;
  v89 = 0;
  v4 = 0;
  v90 = 0;
  v108 = 0;
  v5 = 0;
  v93 = 0;
  v104 = 0;
  v92 = 0;
  v6 = 0;
  v100.QuadPart = 0;
  ppv = 0;
  v98 = 0;
  v87 = 0;
  v103 = 0;
  v97 = 0;
  v83 = 0;
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppv);
  v7 = CoCreateInstance(&CLSID_SoftwareBitmapNativeFactory, 0, 1u, &GUID_c3c181ec_2914_4791_af02_02d224a10b43, &ppv);
  if ( v7 >= 0 )
  {
    v109 = 0;
    v12 = (char *)this - 16;
    if ( (unsigned __int8)byte_180160807 >= 8u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        30,
        &WPP_0acac61da4473a1de7b74d610951a400_Traceguids,
        (char *)this - 16);
    if ( *((_DWORD *)this + 60) )
    {
      while ( 1 )
      {
        v13 = (struct Windows::Graphics::Imaging::ISoftwareBitmap *)*((_QWORD *)this + v4 + 26);
        PerformanceCount.QuadPart = 0;
        v91 = 0;
        *(_OWORD *)&Frequency[0].LowPart = 0;
        v7 = LowLightFusionOperation::_ExtractBufferInfo(
               (LowLightFusionOperation *)((char *)this - 16),
               v13,
               (struct Windows::Graphics::Imaging::BitmapPlaneDescription *)&v104,
               (struct Windows::Graphics::Imaging::BitmapPlaneDescription *)Frequency,
               (unsigned __int8 **)&PerformanceCount,
               &v91);
        if ( v7 < 0 )
          break;
        v14 = (struct Windows::Graphics::Imaging::ISoftwareBitmap *)*((_QWORD *)this + v4 + 28);
        if ( v14 )
        {
          v96 = 0;
          v84 = 0;
          v6 = 1;
          v107 = 0;
          v106 = 0;
          v7 = LowLightFusionOperation::_ExtractBufferInfo(
                 (LowLightFusionOperation *)((char *)this - 16),
                 v14,
                 (struct Windows::Graphics::Imaging::BitmapPlaneDescription *)&v107,
                 (struct Windows::Graphics::Imaging::BitmapPlaneDescription *)&v106,
                 &v96,
                 &v84);
          if ( v7 < 0 )
          {
            v20 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v20 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v20);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "LowLightFusionOperation::Invoke", 185, v7);
            }
            if ( g_wppLevels )
            {
              v17 = 32;
              goto LABEL_58;
            }
            goto LABEL_59;
          }
          v7 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, LONGLONG, _QWORD, _DWORD, _DWORD, unsigned __int8 *, unsigned __int8 *))(**((_QWORD **)v12 + 27) + 32LL))(
                 *((_QWORD *)v12 + 27),
                 PerformanceCount.QuadPart + (int)v104,
                 PerformanceCount.QuadPart + (int)Frequency[0].LowPart,
                 DWORD1(v104),
                 DWORD2(v104),
                 HIDWORD(v104),
                 &v96[(int)v107],
                 &v96[(int)v106]);
          if ( v7 < 0 )
          {
            v15 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v15 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v15 + 8) )
            {
              v16 = CallStackTracing::GetThreadRelativeContext(v15);
              if ( *((_DWORD *)v16 + 499) != v7 )
                CallStackContext::TraceFailure(v16, "LowLightFusionOperation::Invoke", 194, v7);
            }
            if ( g_wppLevels )
            {
              v17 = 33;
              goto LABEL_58;
            }
            goto LABEL_59;
          }
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, LONGLONG, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD))(**((_QWORD **)this + 25) + 32LL))(
                 *((_QWORD *)this + 25),
                 PerformanceCount.QuadPart + (int)v104,
                 PerformanceCount.QuadPart + (int)Frequency[0].LowPart,
                 DWORD1(v104),
                 DWORD2(v104),
                 HIDWORD(v104),
                 0,
                 0);
          if ( v7 < 0 )
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
              if ( *((_DWORD *)v23 + 499) != v7 )
                CallStackContext::TraceFailure(v23, "LowLightFusionOperation::Invoke", 205, v7);
            }
            if ( g_wppLevels )
            {
              v17 = 34;
              goto LABEL_58;
            }
            goto LABEL_59;
          }
        }
        if ( ++v4 >= (unsigned __int64)*((unsigned int *)this + 60) )
          goto LABEL_26;
      }
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v24);
        if ( *((_DWORD *)v25 + 499) != v7 )
          CallStackContext::TraceFailure(v25, "LowLightFusionOperation::Invoke", 171, v7);
      }
      if ( g_wppLevels )
      {
        v17 = 31;
        goto LABEL_58;
      }
      goto LABEL_59;
    }
LABEL_26:
    if ( (unsigned __int8)byte_180160807 >= 8u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        35,
        &WPP_0acac61da4473a1de7b74d610951a400_Traceguids,
        (char *)this - 16);
    if ( v6 )
    {
      v7 = MFStartup(0x20070u, 1u);
      if ( v7 < 0 )
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
          if ( *((_DWORD *)v19 + 499) != v7 )
            CallStackContext::TraceFailure(v19, "LowLightFusionOperation::Invoke", 215, v7);
        }
        if ( g_wppLevels )
        {
          v17 = 36;
LABEL_58:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            &WPP_0acac61da4473a1de7b74d610951a400_Traceguids,
            (char *)this - 16,
            v7);
        }
LABEL_59:
        LODWORD(v4) = 0;
        goto LABEL_158;
      }
    }
    QueryPerformanceFrequency(Frequency);
    QueryPerformanceCounter(&Frequency[1]);
    v7 = (*(__int64 (__fastcall **)(_QWORD, int *, int *, int *, int *, int *, int *, __int128 *, _DWORD))(**((_QWORD **)v12 + 27) + 24LL))(
           *((_QWORD *)v12 + 27),
           &v88,
           &v87,
           &v89,
           &v90,
           &v93,
           &v92,
           &v109,
           *((_DWORD *)this + 61));
    if ( v6 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v28 = PerformanceCount.LowPart - Frequency[1].LowPart;
      if ( PerformanceCount.QuadPart - Frequency[1].QuadPart < 0 )
      {
        v30 = v28 & 1 | ((unsigned __int64)(PerformanceCount.QuadPart - Frequency[1].QuadPart) >> 1);
        v29 = (double)(int)v30 + (double)(int)v30;
      }
      else
      {
        v29 = (double)v28;
      }
      v31 = v29 * 1000.0;
      if ( Frequency[0].QuadPart < 0 )
        LowPart = (double)(int)(Frequency[0].LowPart & 1 | ((unsigned __int64)Frequency[0].QuadPart >> 1))
                + (double)(int)(Frequency[0].LowPart & 1 | ((unsigned __int64)Frequency[0].QuadPart >> 1));
      else
        LowPart = (double)(int)Frequency[0].LowPart;
      v33 = v31 / LowPart;
      LODWORD(v4) = (int)v33;
      v83 = (int)v33;
      v7 = MFShutdown();
      if ( v7 < 0 )
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
          if ( *((_DWORD *)v35 + 499) != v7 )
            CallStackContext::TraceFailure(v35, "LowLightFusionOperation::Invoke", 232, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 37;
        goto LABEL_75;
      }
    }
    else
    {
      LODWORD(v4) = 0;
    }
    v3 = (int)*((float *)&v109 + 2);
    v5 = (int)*((float *)&v109 + 3);
    if ( (unsigned __int8)byte_180160807 >= 8u )
      WPP_SF_qDddddddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        v26,
        v27,
        (_DWORD)this - 16,
        v7,
        v88,
        *((_DWORD *)this + 61),
        v87,
        v89,
        v90,
        v93,
        v92,
        (int)*((float *)&v109 + 2),
        (int)*((float *)&v109 + 3));
    if ( v7 < 0 )
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
        if ( *((_DWORD *)v37 + 499) != v7 )
          CallStackContext::TraceFailure(v37, "LowLightFusionOperation::Invoke", 242, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_158;
      v11 = 39;
      goto LABEL_75;
    }
    if ( v88 )
    {
      if ( v88 == 2 || v88 == 3 || v88 == 4 )
      {
        PerformanceCount.QuadPart = 0;
        v84 = 3;
        v7 = Microsoft::WRL::Details::MakeAndInitialize<LowLightFusionResultImpl,Windows::Media::Core::ILowLightFusionResult,enum Windows::Media::Core::LowLightFusionStatus,std::nullptr_t>(
               (char *)this + 192,
               &v84,
               &PerformanceCount);
        if ( v7 < 0 )
        {
          v41 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v41 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v41 + 8) )
          {
            v42 = CallStackTracing::GetThreadRelativeContext(v41);
            if ( *((_DWORD *)v42 + 499) != v7 )
              CallStackContext::TraceFailure(v42, "LowLightFusionOperation::Invoke", 250, v7);
          }
          if ( !g_wppLevels )
            goto LABEL_158;
          v11 = 40;
          goto LABEL_75;
        }
        v7 = Windows::Media::Report((Windows::Media *)0x80004005LL, v40);
        if ( v7 < 0 )
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
            if ( *((_DWORD *)v44 + 499) != v7 )
              CallStackContext::TraceFailure(v44, "LowLightFusionOperation::Invoke", 251, v7);
          }
          if ( !g_wppLevels )
            goto LABEL_158;
          v11 = 41;
          goto LABEL_75;
        }
      }
      else if ( v88 != 5 )
      {
LABEL_92:
        v38 = CallStackTracing::s_wpInstance;
        v7 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v38 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext(v38);
          if ( *((_DWORD *)v39 + 499) != -2147418113 )
            CallStackContext::TraceFailure(v39, "LowLightFusionOperation::Invoke", 256, -2147418113);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 44;
        goto LABEL_75;
      }
      PerformanceCount.QuadPart = 0;
      v84 = 4;
      v7 = Microsoft::WRL::Details::MakeAndInitialize<LowLightFusionResultImpl,Windows::Media::Core::ILowLightFusionResult,enum Windows::Media::Core::LowLightFusionStatus,std::nullptr_t>(
             (char *)this + 192,
             &v84,
             &PerformanceCount);
      if ( v7 >= 0 )
      {
        v7 = Windows::Media::Report((Windows::Media *)0x8007000ELL, v45);
        if ( v7 >= 0 )
          goto LABEL_92;
        v48 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v48 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v48 + 8) )
        {
          v49 = CallStackTracing::GetThreadRelativeContext(v48);
          if ( *((_DWORD *)v49 + 499) != v7 )
            CallStackContext::TraceFailure(v49, "LowLightFusionOperation::Invoke", 254, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 43;
      }
      else
      {
        v46 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v46 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v46);
          if ( *((_DWORD *)v47 + 499) != v7 )
            CallStackContext::TraceFailure(v47, "LowLightFusionOperation::Invoke", 253, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 42;
      }
LABEL_75:
      v10 = (char *)this - 16;
      goto LABEL_9;
    }
    v50 = (_QWORD *)((char *)this + 8 * v87 + 224);
    if ( *v50 )
    {
      v7 = Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::As<ISoftwareBitmapNative>(v50, &v98);
      if ( v7 < 0 )
      {
        v51 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v51 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v51 + 8) )
        {
          v52 = CallStackTracing::GetThreadRelativeContext(v51);
          if ( *((_DWORD *)v52 + 499) != v7 )
            CallStackContext::TraceFailure(v52, "LowLightFusionOperation::Invoke", 262, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 45;
        goto LABEL_75;
      }
    }
    else
    {
      v7 = Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>::As<ISoftwareBitmapNative>(
             (char *)this + 8 * v87 + 208,
             &v98);
      if ( v7 < 0 )
      {
        v53 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v53 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v54 = CallStackTracing::GetThreadRelativeContext(v53);
          if ( *((_DWORD *)v54 + 499) != v7 )
            CallStackContext::TraceFailure(v54, "LowLightFusionOperation::Invoke", 267, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v11 = 46;
        goto LABEL_75;
      }
    }
    v55 = v98;
    v56 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v98 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
    v7 = v56(v55, &GUID_045fa593_8799_42b8_bc8d_8968c6453507, &v97);
    if ( v7 >= 0 )
    {
      if ( v97 )
      {
        v7 = Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(&v97, &v103);
        if ( v7 >= 0 )
        {
          WORD1(v108) = v89;
          WORD3(v108) = v90;
          *((_QWORD *)&v108 + 1) = __PAIR64__(v5, v3);
          v95 = 0;
          v94 = 0;
          v70 = *((_QWORD *)this + v87 + 26);
          v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v70 + 64LL))(v70, &v95);
          if ( v7 >= 0 )
          {
            v73 = *((_QWORD *)this + v87 + 26);
            v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v73 + 72LL))(v73, &v94);
            if ( v7 >= 0 )
            {
              v76 = ppv;
              v77 = *(__int64 (__fastcall **)(LPVOID, __int64, const GUID *, _QWORD, int, _DWORD, __int128 *, GUID *, LARGE_INTEGER *))(*(_QWORD *)ppv + 56LL);
              Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v100);
              v7 = v77(
                     v76,
                     v103,
                     &MFVideoFormat_NV12,
                     v95,
                     v94,
                     0,
                     &v108,
                     &GUID_689e0708_7eef_483f_963f_da938818e073,
                     &v100);
              if ( v7 >= 0 )
              {
                PerformanceCount = v100;
                v84 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 192);
                v7 = Microsoft::WRL::Details::MakeAndInitialize<LowLightFusionResultImpl,Windows::Media::Core::ILowLightFusionResult,enum Windows::Media::Core::LowLightFusionStatus,Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Foundation::Rect &>(
                       (char *)this + 192,
                       &v84,
                       &PerformanceCount,
                       &v109);
                if ( v7 >= 0 )
                  goto LABEL_157;
                v80 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v80 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v80 + 8) )
                {
                  v81 = CallStackTracing::GetThreadRelativeContext(v80);
                  if ( *((_DWORD *)v81 + 499) != v7 )
                    CallStackContext::TraceFailure(v81, "LowLightFusionOperation::Invoke", 293, v7);
                }
                if ( !g_wppLevels )
                  goto LABEL_157;
                v60 = 53;
              }
              else
              {
                v78 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::InitInstance();
                  v78 = CallStackTracing::s_wpInstance;
                }
                if ( *((_BYTE *)v78 + 8) )
                {
                  v79 = CallStackTracing::GetThreadRelativeContext(v78);
                  if ( *((_DWORD *)v79 + 499) != v7 )
                    CallStackContext::TraceFailure(v79, "LowLightFusionOperation::Invoke", 291, v7);
                }
                if ( !g_wppLevels )
                  goto LABEL_157;
                v60 = 52;
              }
            }
            else
            {
              v74 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::InitInstance();
                v74 = CallStackTracing::s_wpInstance;
              }
              if ( *((_BYTE *)v74 + 8) )
              {
                v75 = CallStackTracing::GetThreadRelativeContext(v74);
                if ( *((_DWORD *)v75 + 499) != v7 )
                  CallStackContext::TraceFailure(v75, "LowLightFusionOperation::Invoke", 281, v7);
              }
              if ( !g_wppLevels )
                goto LABEL_157;
              v60 = 51;
            }
          }
          else
          {
            v71 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v71 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v71 + 8) )
            {
              v72 = CallStackTracing::GetThreadRelativeContext(v71);
              if ( *((_DWORD *)v72 + 499) != v7 )
                CallStackContext::TraceFailure(v72, "LowLightFusionOperation::Invoke", 280, v7);
            }
            if ( !g_wppLevels )
              goto LABEL_157;
            v60 = 50;
          }
        }
        else
        {
          v68 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v68 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v68 + 8) )
          {
            v69 = CallStackTracing::GetThreadRelativeContext(v68);
            if ( *((_DWORD *)v69 + 499) != v7 )
              CallStackContext::TraceFailure(v69, "LowLightFusionOperation::Invoke", 271, v7);
          }
          if ( !g_wppLevels )
            goto LABEL_157;
          v60 = 49;
        }
      }
      else
      {
        v65 = Windows::Media::Report((Windows::Media *)0x80004003LL, v57);
        v66 = CallStackTracing::s_wpInstance;
        v7 = v65;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v66 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v66 + 8) )
        {
          v67 = CallStackTracing::GetThreadRelativeContext(v66);
          if ( v7 < 0 && *((_DWORD *)v67 + 499) != v7 )
            CallStackContext::TraceFailure(v67, "LowLightFusionOperation::Invoke", 270, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_157;
        v60 = 48;
      }
    }
    else
    {
      v58 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v58 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v58 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext(v58);
        if ( *((_DWORD *)v59 + 499) != v7 )
          CallStackContext::TraceFailure(v59, "LowLightFusionOperation::Invoke", 269, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_157;
      v60 = 47;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v60,
      &WPP_0acac61da4473a1de7b74d610951a400_Traceguids,
      (char *)this - 16,
      v7);
LABEL_157:
    LODWORD(v4) = v83;
    goto LABEL_158;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v8 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v9 = CallStackTracing::GetThreadRelativeContext(v8);
    if ( *((_DWORD *)v9 + 499) != v7 )
      CallStackContext::TraceFailure(v9, "LowLightFusionOperation::Invoke", 160, v7);
  }
  if ( g_wppLevels )
  {
    v10 = (char *)this - 16;
    v11 = 29;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_0acac61da4473a1de7b74d610951a400_Traceguids, v10, v7);
  }
LABEL_158:
  if ( (unsigned __int8)byte_180160807 >= 8u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      54,
      &WPP_0acac61da4473a1de7b74d610951a400_Traceguids,
      (char *)this - 16,
      v7);
  if ( v6 && (unsigned int)dword_18015F098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015F098, 0x400000000000LL) )
  {
    v102 = DWORD2(v104);
    LODWORD(v96) = DWORD1(v104);
    PerformanceCount.LowPart = *((_DWORD *)this + 60);
    v84 = v7;
    v91 = v4;
    v83 = v5;
    v101 = v3;
    Frequency[0].QuadPart = 50333696;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v61,
      (unsigned int)byte_180152A83,
      v62,
      v63,
      (__int64)Frequency,
      (__int64)&PerformanceCount,
      (__int64)&v96,
      (__int64)&v102,
      (__int64)&v101,
      (__int64)&v83,
      (__int64)&v91,
      (__int64)&v84);
  }
  v64 = (char *)this + 8;
  if ( v7 >= 0 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(
      v64,
      1);
  else
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      v64,
      (unsigned int)v7);
  Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion((char *)this + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v103);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v98);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v100);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v86);
  return 0;
}

```

## disassembly

```asm
0x1800a9b90  push    rbp
0x1800a9b92  push    rbx
0x1800a9b93  push    rsi
0x1800a9b94  push    rdi
0x1800a9b95  push    r12
0x1800a9b97  push    r13
0x1800a9b99  push    r14
0x1800a9b9b  push    r15
0x1800a9b9d  lea     rbp, [rsp-58h]
0x1800a9ba2  sub     rsp, 158h
0x1800a9ba9  mov     rax, cs:__security_cookie
0x1800a9bb0  xor     rax, rsp
0x1800a9bb3  mov     [rbp+90h+var_50], rax
0x1800a9bb7  mov     r14, rcx
0x1800a9bba  mov     [rbp+90h+var_108], 0
0x1800a9bc1  lea     rcx, [rbp+90h+var_110]; this
0x1800a9bc5  mov     r8d, 8Ch; int
0x1800a9bcb  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800a9bd2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9bd7  xor     r12d, r12d
0x1800a9bda  lea     rcx, [rbp+90h+var_D0]
0x1800a9bde  xorps   xmm0, xmm0
0x1800a9be1  mov     [rbp+90h+var_104], r12d
0x1800a9be5  xor     edi, edi
0x1800a9be7  mov     [rbp+90h+var_100], r12d
0x1800a9beb  movups  [rbp+90h+var_70], xmm0
0x1800a9bef  xor     r13d, r13d
0x1800a9bf2  mov     [rbp+90h+var_F4], r12d
0x1800a9bf6  movups  [rbp+90h+var_B0], xmm0
0x1800a9bfa  mov     [rbp+90h+var_F8], r12d
0x1800a9bfe  xor     r15b, r15b
0x1800a9c01  mov     [rbp+90h+var_C8], r12
0x1800a9c05  mov     [rbp+90h+var_D0], r12
0x1800a9c09  mov     [rbp+90h+var_D8], r12
0x1800a9c0d  mov     [rbp+90h+var_10C], r12d
0x1800a9c11  mov     [rbp+90h+var_B8], r12
0x1800a9c15  mov     [rbp+90h+var_E0], r12
0x1800a9c19  mov     [rsp+190h+var_120], edi
0x1800a9c1d  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800a9c22  lea     rax, [rbp+90h+var_D0]
0x1800a9c26  xor     edx, edx; pUnkOuter
0x1800a9c28  lea     r9, _GUID_c3c181ec_2914_4791_af02_02d224a10b43; riid
0x1800a9c2f  mov     [rsp+190h+ppv], rax; ppv
0x1800a9c34  lea     r8d, [r12+1]; dwClsContext
0x1800a9c39  lea     rcx, CLSID_SoftwareBitmapNativeFactory; rclsid
0x1800a9c40  call    cs:__imp_CoCreateInstance
0x1800a9c46  mov     ebx, eax
0x1800a9c48  test    eax, eax
0x1800a9c4a  jns     short loc_1800A9CC5
0x1800a9c4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9c53  test    rcx, rcx
0x1800a9c56  jnz     short loc_1800A9C64
0x1800a9c58  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9c5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9c64  cmp     [rcx+8], dil
0x1800a9c68  jz      short loc_1800A9C8F
0x1800a9c6a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9c6f  cmp     [rax+7CCh], ebx
0x1800a9c75  jz      short loc_1800A9C8F
0x1800a9c77  mov     r9d, ebx; int
0x1800a9c7a  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800a9c81  mov     r8d, 0A0h; int
0x1800a9c87  mov     rcx, rax; this
0x1800a9c8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9c8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9c96  jb      loc_1800AA6B4
0x1800a9c9c  lea     r9, [r14-10h]
0x1800a9ca0  mov     edx, 1Dh
0x1800a9ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9cac  lea     r8, WPP_0acac61da4473a1de7b74d610951a400_Traceguids
0x1800a9cb3  mov     dword ptr [rsp+190h+ppv], ebx
0x1800a9cb7  mov     rcx, [rcx+10h]
0x1800a9cbb  call    WPP_SF_qD
0x1800a9cc0  jmp     loc_1800AA6B4
0x1800a9cc5  xorps   xmm0, xmm0
0x1800a9cc8  movups  [rbp+90h+var_60], xmm0
0x1800a9ccc  cmp     cs:byte_180160807, 8
0x1800a9cd3  lea     rsi, [r14-10h]
0x1800a9cd7  jb      short loc_1800A9CFB
0x1800a9cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9ce0  lea     r8, WPP_0acac61da4473a1de7b74d610951a400_Traceguids
0x1800a9ce7  mov     edx, 1Eh
0x1800a9cec  mov     r9, rsi
0x1800a9cef  mov     rcx, [rcx+128h]
0x1800a9cf6  call    WPP_SF_q
0x1800a9cfb  cmp     [r14+0F0h], edi
0x1800a9d02  jbe     loc_1800A9EC9
0x1800a9d08  mov     rdx, [r14+rdi*8+0D0h]; struct Windows::Graphics::Imaging::ISoftwareBitmap *
0x1800a9d10  lea     rax, [rbp+90h+var_FC]
0x1800a9d14  mov     [rsp+190h+var_168], rax; unsigned int *
0x1800a9d19  lea     r9, [rbp+90h+Frequency]; struct Windows::Graphics::Imaging::BitmapPlaneDescription *
0x1800a9d1d  lea     rax, [rsp+190h+PerformanceCount]
0x1800a9d22  mov     qword ptr [rsp+190h+PerformanceCount], r12
0x1800a9d27  xorps   xmm0, xmm0
0x1800a9d2a  mov     [rsp+190h+ppv], rax; unsigned __int8 **
0x1800a9d2f  lea     r8, [rbp+90h+var_B0]; struct Windows::Graphics::Imaging::BitmapPlaneDescription *
0x1800a9d33  mov     [rbp+90h+var_FC], r12d
0x1800a9d37  mov     rcx, rsi; this
0x1800a9d3a  movups  xmmword ptr [rbp+90h+Frequency], xmm0
0x1800a9d3e  call    ?_ExtractBufferInfo@LowLightFusionOperation@@AEAAJPEAUISoftwareBitmap@Imaging@Graphics@Windows@@PEAUBitmapPlaneDescription@345@1PEAPEAEPEAI@Z; LowLightFusionOperation::_ExtractBufferInfo(Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Graphics::Imaging::BitmapPlaneDescription *,Windows::Graphics::Imaging::BitmapPlaneDescription *,uchar * *,uint *)
0x1800a9d43  xor     r8d, r8d
0x1800a9d46  mov     ebx, eax
0x1800a9d48  test    eax, eax
0x1800a9d4a  js      loc_1800AA01E
0x1800a9d50  mov     rdx, [r14+rdi*8+0E0h]; struct Windows::Graphics::Imaging::ISoftwareBitmap *
0x1800a9d58  test    rdx, rdx
0x1800a9d5b  jz      loc_1800A9E64
0x1800a9d61  lea     rax, [rsp+190h+var_11C]
0x1800a9d66  mov     [rbp+90h+var_E8], r8
0x1800a9d6a  mov     [rsp+190h+var_168], rax; unsigned int *
0x1800a9d6f  lea     r9, [rbp+90h+var_90]; struct Windows::Graphics::Imaging::BitmapPlaneDescription *
0x1800a9d73  lea     rax, [rbp+90h+var_E8]
0x1800a9d77  mov     [rsp+190h+var_11C], r8d
0x1800a9d7c  xorps   xmm0, xmm0
0x1800a9d7f  mov     [rsp+190h+ppv], rax; unsigned __int8 **
0x1800a9d84  xorps   xmm1, xmm1
0x1800a9d87  lea     r8, [rbp+90h+var_80]; struct Windows::Graphics::Imaging::BitmapPlaneDescription *
0x1800a9d8b  mov     rcx, rsi; this
0x1800a9d8e  mov     r15b, 1
0x1800a9d91  movups  [rbp+90h+var_80], xmm0
0x1800a9d95  movups  [rbp+90h+var_90], xmm1
0x1800a9d99  call    ?_ExtractBufferInfo@LowLightFusionOperation@@AEAAJPEAUISoftwareBitmap@Imaging@Graphics@Windows@@PEAUBitmapPlaneDescription@345@1PEAPEAEPEAI@Z; LowLightFusionOperation::_ExtractBufferInfo(Windows::Graphics::Imaging::ISoftwareBitmap *,Windows::Graphics::Imaging::BitmapPlaneDescription *,Windows::Graphics::Imaging::BitmapPlaneDescription *,uchar * *,uint *)
0x1800a9d9e  mov     ebx, eax
0x1800a9da0  test    eax, eax
0x1800a9da2  js      loc_1800A9F71
0x1800a9da8  mov     rcx, [rsi+0D8h]
0x1800a9daf  movsxd  r9, dword ptr [rbp+90h+var_90]
0x1800a9db3  add     r9, [rbp+90h+var_E8]
0x1800a9db7  movsxd  r8, dword ptr [rbp+90h+var_80]
0x1800a9dbb  add     r8, [rbp+90h+var_E8]
0x1800a9dbf  mov     rax, [rcx]
0x1800a9dc2  movsxd  r10, dword ptr [rbp+90h+Frequency]
0x1800a9dc6  add     r10, qword ptr [rsp+190h+PerformanceCount]
0x1800a9dcb  movsxd  rdx, dword ptr [rbp+90h+var_B0]
0x1800a9dcf  mov     rax, [rax+20h]
0x1800a9dd3  add     rdx, qword ptr [rsp+190h+PerformanceCount]
0x1800a9dd8  mov     [rsp+190h+var_158], r9
0x1800a9ddd  mov     r9d, dword ptr [rbp+90h+var_B0+4]
0x1800a9de1  mov     [rsp+190h+var_160], r8
0x1800a9de6  mov     r8d, dword ptr [rbp+90h+var_B0+0Ch]
0x1800a9dea  mov     dword ptr [rsp+190h+var_168], r8d
0x1800a9def  mov     r8d, dword ptr [rbp+90h+var_B0+8]
0x1800a9df3  mov     dword ptr [rsp+190h+ppv], r8d
0x1800a9df8  mov     r8, r10
0x1800a9dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9e00  mov     ebx, eax
0x1800a9e02  test    eax, eax
0x1800a9e04  jns     loc_1800A9EB6
0x1800a9e0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9e11  test    rcx, rcx
0x1800a9e14  jnz     short loc_1800A9E22
0x1800a9e16  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9e1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9e22  cmp     [rcx+8], r12b
0x1800a9e26  jz      short loc_1800A9E4D
0x1800a9e28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9e2d  cmp     [rax+7CCh], ebx
0x1800a9e33  jz      short loc_1800A9E4D
0x1800a9e35  mov     r9d, ebx; int
0x1800a9e38  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800a9e3f  mov     r8d, 0C2h; int
0x1800a9e45  mov     rcx, rax; this
0x1800a9e48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9e4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800a9e54  jb      loc_1800AA090
0x1800a9e5a  mov     edx, 21h ; '!'
0x1800a9e5f  jmp     loc_1800AA072
0x1800a9e64  mov     rcx, [r14+0C8h]
0x1800a9e6b  movsxd  r10, dword ptr [rbp+90h+Frequency]
0x1800a9e6f  add     r10, qword ptr [rsp+190h+PerformanceCount]
0x1800a9e74  movsxd  rdx, dword ptr [rbp+90h+var_B0]
0x1800a9e78  mov     rax, [rcx]
0x1800a9e7b  add     rdx, qword ptr [rsp+190h+PerformanceCount]
0x1800a9e80  mov     r9d, dword ptr [rbp+90h+var_B0+4]
0x1800a9e84  mov     [rsp+190h+var_158], r8
0x1800a9e89  mov     rax, [rax+20h]
0x1800a9e8d  mov     [rsp+190h+var_160], r8
0x1800a9e92  mov     r8d, dword ptr [rbp+90h+var_B0+0Ch]
0x1800a9e96  mov     dword ptr [rsp+190h+var_168], r8d
0x1800a9e9b  mov     r8d, dword ptr [rbp+90h+var_B0+8]
0x1800a9e9f  mov     dword ptr [rsp+190h+ppv], r8d
0x1800a9ea4  mov     r8, r10
0x1800a9ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9eac  mov     ebx, eax
0x1800a9eae  test    eax, eax
0x1800a9eb0  js      loc_1800A9FCB
0x1800a9eb6  mov     eax, [r14+0F0h]
0x1800a9ebd  inc     rdi
0x1800a9ec0  cmp     rdi, rax
0x1800a9ec3  jb      loc_1800A9D08
0x1800a9ec9  cmp     cs:byte_180160807, 8
0x1800a9ed0  jb      short loc_1800A9EF4
0x1800a9ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9ed9  lea     r8, WPP_0acac61da4473a1de7b74d610951a400_Traceguids
0x1800a9ee0  mov     edx, 23h ; '#'
0x1800a9ee5  mov     r9, rsi
0x1800a9ee8  mov     rcx, [rcx+128h]
0x1800a9eef  call    WPP_SF_q
0x1800a9ef4  test    r15b, r15b
0x1800a9ef7  jz      loc_1800AA098
0x1800a9efd  mov     edx, 1; dwFlags
0x1800a9f02  mov     ecx, 20070h; Version
0x1800a9f07  call    cs:__imp_MFStartup
0x1800a9f0d  mov     ebx, eax
0x1800a9f0f  test    eax, eax
0x1800a9f11  jns     loc_1800AA098
0x1800a9f17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9f1e  test    rcx, rcx
0x1800a9f21  jnz     short loc_1800A9F2F
0x1800a9f23  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9f28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9f2f  cmp     [rcx+8], r12b
0x1800a9f33  jz      short loc_1800A9F5A
0x1800a9f35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9f3a  cmp     [rax+7CCh], ebx
0x1800a9f40  jz      short loc_1800A9F5A
0x1800a9f42  mov     r9d, ebx; int
0x1800a9f45  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800a9f4c  mov     r8d, 0D7h; int
0x1800a9f52  mov     rcx, rax; this
0x1800a9f55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9f5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9f61  jb      loc_1800AA090
0x1800a9f67  mov     edx, 24h ; '$'
0x1800a9f6c  jmp     loc_1800AA072
0x1800a9f71  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9f78  test    rcx, rcx
0x1800a9f7b  jnz     short loc_1800A9F89
0x1800a9f7d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9f82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9f89  cmp     [rcx+8], r12b
0x1800a9f8d  jz      short loc_1800A9FB4
0x1800a9f8f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9f94  cmp     [rax+7CCh], ebx
0x1800a9f9a  jz      short loc_1800A9FB4
0x1800a9f9c  mov     r9d, ebx; int
0x1800a9f9f  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800a9fa6  mov     r8d, 0B9h; int
0x1800a9fac  mov     rcx, rax; this
0x1800a9faf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9fb4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800a9fbb  jb      loc_1800AA090
0x1800a9fc1  mov     edx, 20h ; ' '
0x1800a9fc6  jmp     loc_1800AA072
0x1800a9fcb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9fd2  test    rcx, rcx
0x1800a9fd5  jnz     short loc_1800A9FE3
0x1800a9fd7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800a9fdc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800a9fe3  cmp     [rcx+8], r12b
0x1800a9fe7  jz      short loc_1800AA00E
0x1800a9fe9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9fee  cmp     [rax+7CCh], ebx
0x1800a9ff4  jz      short loc_1800AA00E
0x1800a9ff6  mov     r9d, ebx; int
0x1800a9ff9  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800aa000  mov     r8d, 0CDh; int
0x1800aa006  mov     rcx, rax; this
0x1800aa009  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aa00e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aa015  jb      short loc_1800AA090
0x1800aa017  mov     edx, 22h ; '"'
0x1800aa01c  jmp     short loc_1800AA072
0x1800aa01e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aa025  test    rcx, rcx
0x1800aa028  jnz     short loc_1800AA039
0x1800aa02a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800aa02f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aa036  xor     r8d, r8d
0x1800aa039  cmp     [rcx+8], r8b
0x1800aa03d  jz      short loc_1800AA064
0x1800aa03f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aa044  cmp     [rax+7CCh], ebx
0x1800aa04a  jz      short loc_1800AA064
0x1800aa04c  mov     r9d, ebx; int
0x1800aa04f  lea     rdx, aLowlightfusion_1; "LowLightFusionOperation::Invoke"
0x1800aa056  mov     r8d, 0ABh; int
0x1800aa05c  mov     rcx, rax; this
0x1800aa05f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aa064  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aa06b  jb      short loc_1800AA090
0x1800aa06d  mov     edx, 1Fh
0x1800aa072  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aa079  lea     r8, WPP_0acac61da4473a1de7b74d610951a400_Traceguids
0x1800aa080  mov     r9, rsi
0x1800aa083  mov     dword ptr [rsp+190h+ppv], ebx
0x1800aa087  mov     rcx, [rcx+10h]
0x1800aa08b  call    WPP_SF_qD
0x1800aa090  mov     edi, r12d
0x1800aa093  jmp     loc_1800AA6B4
0x1800aa098  lea     rcx, [rbp+90h+Frequency]; lpFrequency
0x1800aa09c  call    cs:__imp_QueryPerformanceFrequency
0x1800aa0a2  lea     rcx, [rbp+90h+Frequency+8]; lpPerformanceCount
0x1800aa0a6  call    cs:__imp_QueryPerformanceCounter
0x1800aa0ac  mov     edx, [r14+0F4h]
0x1800aa0b3  lea     r9, [rbp+90h+var_104]
0x1800aa0b7  mov     rcx, [rsi+0D8h]
0x1800aa0be  lea     r8, [rbp+90h+var_10C]
0x1800aa0c2  mov     dword ptr [rsp+190h+var_150], edx
0x1800aa0c6  lea     rdx, [rbp+90h+var_60]
  ... truncated ...
```
