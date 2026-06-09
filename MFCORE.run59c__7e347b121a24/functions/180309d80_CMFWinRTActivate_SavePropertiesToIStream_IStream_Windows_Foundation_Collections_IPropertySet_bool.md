# CMFWinRTActivate::SavePropertiesToIStream(IStream *,Windows::Foundation::Collections::IPropertySet *,bool)

- ea: `0x180309d80`
- end: `0x18030ac57`
- name: `?SavePropertiesToIStream@CMFWinRTActivate@@SAJPEAUIStream@@PEAUIPropertySet@Collections@Foundation@Windows@@_N@Z`
- size: `3799`
- prototype: `__int64 __fastcall(LPSTREAM pStm, struct Windows::Foundation::Collections::IPropertySet *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180309930`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180097f10`
- `0x1800ec0e0`
- `0x180308918`
- `0x180308a70`
- `0x180308aa8`
- `0x180309d80`
- `0x18030ae7c`
- `0x18030ed18`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18030a2b5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18030a310`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18030a2b5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18030a310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18030a1cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18030a1cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18030a21d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18030a21d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309de8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309ea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309f67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a38b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a41d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a4f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a58a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a63f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a6d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a8a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a9cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030aa5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030aaf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030ab83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309de8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309ea5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180309f67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a38b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a41d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a4f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a58a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a63f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a6d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a781`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a813`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a8a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030a9cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030aa5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030aaf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18030ab83`

## pseudocode

```c
__int64 __fastcall CMFWinRTActivate::SavePropertiesToIStream(
        LPSTREAM pStm,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *),
        char a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rcx
  int Type; // edi
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 (__fastcall *v16)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int v22; // r14d
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 **); // rbx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  int v38; // eax
  LPUNKNOWN *v39; // rbx
  LPUNKNOWN v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  UINT32 StringLen; // eax
  __int64 v47; // rdx
  __int64 v48; // r8
  UINT32 v49; // ebx
  __int64 (__fastcall *v50)(LPSTREAM, PCWSTR, _QWORD, int *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  LPUNKNOWN v54; // rbx
  __int64 v55; // rdx
  __int64 v56; // r8
  IUnknown v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  __int64 v69; // rdx
  __int64 *v70; // rcx
  CallStackTracing *v71; // rax
  struct CallStackContext *v72; // rax
  __int64 *v73; // rcx
  CallStackTracing *v74; // rax
  struct CallStackContext *v75; // rax
  __int64 *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  __int64 *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  __int64 *v83; // rcx
  CallStackTracing *v84; // rax
  struct CallStackContext *v85; // rax
  __int64 v86; // rdx
  __int64 *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  __int64 *v90; // rcx
  CallStackTracing *v91; // rax
  struct CallStackContext *v92; // rax
  __int64 *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  __int64 *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  __int64 *v99; // rcx
  CallStackTracing *v100; // rax
  struct CallStackContext *v101; // rax
  __int64 *v102; // rcx
  CallStackTracing *v103; // rax
  struct CallStackContext *v104; // rax
  __int64 *v105; // rcx
  CallStackTracing *v106; // rax
  struct CallStackContext *v107; // rax
  __int64 *v108; // rcx
  CallStackTracing *v109; // rax
  struct CallStackContext *v110; // rax
  __int64 v112; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v113; // [rsp+38h] [rbp-61h] BYREF
  HSTRING string; // [rsp+40h] [rbp-59h] BYREF
  LPUNKNOWN pUnk; // [rsp+48h] [rbp-51h] BYREF
  int v116; // [rsp+50h] [rbp-49h]
  UINT32 length; // [rsp+58h] [rbp-41h] BYREF
  int v118; // [rsp+5Ch] [rbp-3Dh] BYREF
  LPUNKNOWN v119; // [rsp+60h] [rbp-39h] BYREF
  int v120; // [rsp+68h] [rbp-31h] BYREF
  __int64 v121; // [rsp+70h] [rbp-29h] BYREF
  int v122; // [rsp+78h] [rbp-21h] BYREF
  LPUNKNOWN v123; // [rsp+80h] [rbp-19h] BYREF
  int v124; // [rsp+88h] [rbp-11h]
  IUnknown *v125; // [rsp+90h] [rbp-9h] BYREF
  int v126; // [rsp+98h] [rbp-1h]
  LPUNKNOWN *p_pUnk; // [rsp+A0h] [rbp+7h]
  struct IInspectable *v128; // [rsp+A8h] [rbp+Fh] BYREF
  LPUNKNOWN v129; // [rsp+B0h] [rbp+17h] BYREF
  int v130; // [rsp+B8h] [rbp+1Fh]
  char v131; // [rsp+100h] [rbp+67h] BYREF
  int v132; // [rsp+118h] [rbp+7Fh] BYREF

  v132 = 0;
  v121 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v131,
    "CMFWinRTActivate::SavePropertiesToIStream",
    788);
  if ( !pStm )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    Type = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFWinRTActivate::SavePropertiesToIStream",
          788,
          -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_219;
    v12 = 122;
    goto LABEL_12;
  }
  if ( !a2 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    Type = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v15, "CMFWinRTActivate::SavePropertiesToIStream", 789, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_219;
    v12 = 123;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
      0,
      -2147024809);
    goto LABEL_219;
  }
  v16 = **a2;
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v121);
  Type = v16(
           (struct Windows::Foundation::Collections::IPropertySet *)a2,
           &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204,
           &v121);
  if ( Type < 0 )
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != Type )
        CallStackContext::TraceFailure(v21, "CMFWinRTActivate::SavePropertiesToIStream", 791, Type);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
    goto LABEL_219;
  }
  v122 = 0;
  v22 = 0;
LABEL_37:
  if ( v22 < 2 )
  {
    v112 = 0;
    if ( v22 == 1 )
    {
      Type = (*(__int64 (__fastcall **)(LPSTREAM, int *, __int64, int *))(*(_QWORD *)pStm + 32LL))(
               pStm,
               &v132,
               4,
               &v122);
      if ( Type < 0 )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
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
          if ( *((_DWORD *)v68 + 499) != Type )
            CallStackContext::TraceFailure(v68, "CMFWinRTActivate::SavePropertiesToIStream", 805, Type);
        }
        if ( !g_wppLevels )
          goto LABEL_218;
        v69 = 125;
        goto LABEL_217;
      }
      if ( !v132 )
        goto LABEL_218;
    }
    v25 = v121;
    v131 = 0;
    v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v121 + 48LL);
    Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v112);
    Type = v26(v25, &v112);
    if ( Type < 0 )
    {
      v108 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v109 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
        CallStackTracing::s_wpInstance = v109;
        if ( v109 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v109 + 8LL))(v109, 2032) )
        {
          v108 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v108 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v108 + 8) )
      {
        v110 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v108);
        if ( *((_DWORD *)v110 + 499) != Type )
          CallStackContext::TraceFailure(v110, "CMFWinRTActivate::SavePropertiesToIStream", 813, Type);
      }
      if ( !g_wppLevels )
        goto LABEL_218;
      v69 = 126;
    }
    else
    {
      Type = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v112 + 56LL))(v112, &v131);
      if ( Type >= 0 )
      {
        while ( 1 )
        {
          if ( !v131 )
          {
            Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v112);
            ++v22;
            goto LABEL_37;
          }
          v31 = v112;
          v113 = 0;
          string = 0;
          pUnk = 0;
          v116 = 0;
          v118 = 0;
          v32 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v112 + 48LL);
          Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v113);
          Type = v32(v31, &v113);
          if ( Type < 0 )
            break;
          Type = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v113 + 48))(v113, &string);
          if ( Type < 0 )
          {
            v99 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v100 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36);
              CallStackTracing::s_wpInstance = v100;
              if ( v100
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v100 + 8LL))(v100, 2032) )
              {
                v99 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v99 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v99 + 8) )
            {
              v101 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v99);
              if ( *((_DWORD *)v101 + 499) != Type )
                CallStackContext::TraceFailure(v101, "CMFWinRTActivate::SavePropertiesToIStream", 824, Type);
            }
            if ( !g_wppLevels )
              goto LABEL_91;
            v86 = 129;
            goto LABEL_135;
          }
          v37 = *v113;
          p_pUnk = &pUnk;
          v128 = 0;
          v38 = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable **))(v37 + 56))(v113, &v128);
          v39 = p_pUnk;
          Type = v38;
          RoVariant::RoVariant((RoVariant *)&v125, v128, 1);
          v40 = *v39;
          *v39 = v125;
          v41 = v126;
          v125 = v40;
          v126 = *((_DWORD *)v39 + 2);
          *((_DWORD *)v39 + 2) = v41;
          RoVariant::~RoVariant((RoVariant *)&v125);
          if ( Type < 0 )
          {
            v96 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43);
              CallStackTracing::s_wpInstance = v97;
              if ( v97
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
              {
                v96 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v96 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v96 + 8) )
            {
              v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
              if ( *((_DWORD *)v98 + 499) != Type )
                CallStackContext::TraceFailure(v98, "CMFWinRTActivate::SavePropertiesToIStream", 825, Type);
            }
            if ( !g_wppLevels )
              goto LABEL_91;
            v86 = 130;
            goto LABEL_135;
          }
          v129 = pUnk;
          v130 = v116;
          Type = RoVariant::Accessor::get_Type(
                   (RoVariant::Accessor *)&v129,
                   (enum Windows::Foundation::PropertyType *)&v118);
          if ( Type < 0 )
          {
            v93 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45);
              CallStackTracing::s_wpInstance = v94;
              if ( v94
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
              {
                v93 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v93 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v93 + 8) )
            {
              v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
              if ( *((_DWORD *)v95 + 499) != Type )
                CallStackContext::TraceFailure(v95, "CMFWinRTActivate::SavePropertiesToIStream", 826, Type);
            }
            if ( !g_wppLevels )
              goto LABEL_91;
            v86 = 131;
            goto LABEL_135;
          }
          if ( v118 != 1037 && v118 != 20 && v118 != 1044 && v118 && (v118 != 13 || a3) )
          {
            if ( v22 )
            {
              StringLen = WindowsGetStringLen(string);
              v120 = 0;
              length = StringLen;
              Type = (*(__int64 (__fastcall **)(LPSTREAM, UINT32 *, __int64, int *))(*(_QWORD *)pStm + 32LL))(
                       pStm,
                       &length,
                       4,
                       &v120);
              if ( Type < 0 )
              {
                v87 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48);
                  CallStackTracing::s_wpInstance = v88;
                  if ( v88
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
                  {
                    v87 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v87 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v87 + 8) )
                {
                  v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
                  if ( *((_DWORD *)v89 + 499) != Type )
                    CallStackContext::TraceFailure(v89, "CMFWinRTActivate::SavePropertiesToIStream", 840, Type);
                }
                if ( g_wppLevels )
                {
                  v86 = 132;
                  goto LABEL_135;
                }
                goto LABEL_91;
              }
              v49 = 2 * length;
              v50 = *(__int64 (__fastcall **)(LPSTREAM, PCWSTR, _QWORD, int *))(*(_QWORD *)pStm + 32LL);
              StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
              Type = v50(pStm, StringRawBuffer, v49, &v120);
              if ( Type < 0 )
              {
                v83 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v84 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53);
                  CallStackTracing::s_wpInstance = v84;
                  if ( v84
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v84 + 8LL))(v84, 2032) )
                  {
                    v83 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v83 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v83 + 8) )
                {
                  v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v83);
                  if ( *((_DWORD *)v85 + 499) != Type )
                    CallStackContext::TraceFailure(v85, "CMFWinRTActivate::SavePropertiesToIStream", 841, Type);
                }
                if ( g_wppLevels )
                {
                  v86 = 133;
                  goto LABEL_135;
                }
                goto LABEL_91;
              }
              if ( v118 == 13 )
              {
                v54 = pUnk;
                Type = v116;
                v119 = 0;
                Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v119);
                v119 = 0;
                if ( Type < 0 )
                  goto LABEL_93;
                if ( !Type || ((Type - 1) & 0xFFFFFFFD) != 0 )
                {
                  Type = -2147316576;
LABEL_93:
                  v73 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
                    CallStackTracing::s_wpInstance = v74;
                    if ( v74
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
                    {
                      v73 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v73 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v73 + 8) )
                  {
                    v75 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                    if ( *((_DWORD *)v75 + 499) != Type )
                      CallStackContext::TraceFailure(v75, "CMFWinRTActivate::SavePropertiesToIStream", 847, Type);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      134,
                      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
                      0,
                      Type);
LABEL_90:
                  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v119);
                  goto LABEL_91;
                }
                v57.lpVtbl = v54->lpVtbl;
                v119 = v54;
                ((void (__fastcall *)(LPUNKNOWN))v57.lpVtbl->AddRef)(v54);
                Type = CoMarshalInterface(pStm, &IID_IInspectable, v54, 0, 0, 0);
                if ( Type < 0 )
                {
                  v70 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v71 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59);
                    CallStackTracing::s_wpInstance = v71;
                    if ( v71
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v71 + 8LL))(v71, 2032) )
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
                    v72 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v70);
                    if ( *((_DWORD *)v72 + 499) != Type )
                      CallStackContext::TraceFailure(v72, "CMFWinRTActivate::SavePropertiesToIStream", 848, Type);
                  }
                  if ( g_wppLevels )
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      135,
                      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
                      0,
                      Type);
                  goto LABEL_90;
                }
                Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v119);
              }
              else
              {
                v123 = 0;
                v124 = 0;
                Type = ClonePropertyValue(&pUnk, &v123);
                if ( Type < 0 )
                {
                  v80 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61);
                    CallStackTracing::s_wpInstance = v81;
                    if ( v81
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(v81, 2032) )
                    {
                      v80 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v80 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v80 + 8) )
                  {
                    v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
                    if ( *((_DWORD *)v82 + 499) != Type )
                      CallStackContext::TraceFailure(v82, "CMFWinRTActivate::SavePropertiesToIStream", 856, Type);
                  }
                  if ( g_wppLevels )
                  {
                    v79 = 136;
LABEL_113:
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v79,
                      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
                      0,
                      Type);
                  }
LABEL_114:
                  RoVariant::~RoVariant((RoVariant *)&v123);
                  goto LABEL_91;
                }
                Type = CoMarshalInterface(pStm, &IID_IInspectable, v123, 0, 0, 0);
                if ( Type < 0 )
                {
                  v76 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63);
                    CallStackTracing::s_wpInstance = v77;
                    if ( v77
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(v77, 2032) )
                    {
                      v76 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v76 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  if ( *((_BYTE *)v76 + 8) )
                  {
                    v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
                    if ( *((_DWORD *)v78 + 499) != Type )
                      CallStackContext::TraceFailure(v78, "CMFWinRTActivate::SavePropertiesToIStream", 857, Type);
                  }
                  if ( g_wppLevels )
                  {
                    v79 = 137;
                    goto LABEL_113;
                  }
                  goto LABEL_114;
                }
                RoVariant::~RoVariant((RoVariant *)&v123);
              }
            }
            else
            {
              ++v132;
            }
          }
          Type = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v112 + 64LL))(v112, &v131);
          if ( Type < 0 )
          {
            v90 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v91 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65);
              CallStackTracing::s_wpInstance = v91;
              if ( v91
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v91 + 8LL))(v91, 2032) )
              {
                v90 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v90 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v90 + 8) )
            {
              v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v90);
              if ( *((_DWORD *)v92 + 499) != Type )
                CallStackContext::TraceFailure(v92, "CMFWinRTActivate::SavePropertiesToIStream", 862, Type);
            }
            if ( g_wppLevels )
            {
              v86 = 138;
              goto LABEL_135;
            }
LABEL_91:
            RoVariant::~RoVariant((RoVariant *)&pUnk);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v113);
LABEL_218:
            Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v112);
            goto LABEL_219;
          }
          RoVariant::~RoVariant((RoVariant *)&pUnk);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v113);
        }
        v102 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v103 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
          CallStackTracing::s_wpInstance = v103;
          if ( v103 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v103 + 8LL))(v103, 2032) )
          {
            v102 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v102 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v102 + 8) )
        {
          v104 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v102);
          if ( *((_DWORD *)v104 + 499) != Type )
            CallStackContext::TraceFailure(v104, "CMFWinRTActivate::SavePropertiesToIStream", 823, Type);
        }
        if ( !g_wppLevels )
          goto LABEL_91;
        v86 = 128;
LABEL_135:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v86, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
        goto LABEL_91;
      }
      v105 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v106 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
        CallStackTracing::s_wpInstance = v106;
        if ( v106 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v106 + 8LL))(v106, 2032) )
        {
          v105 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v105 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v105 + 8) )
      {
        v107 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v105);
        if ( *((_DWORD *)v107 + 499) != Type )
          CallStackContext::TraceFailure(v107, "CMFWinRTActivate::SavePropertiesToIStream", 814, Type);
      }
      if ( !g_wppLevels )
        goto LABEL_218;
      v69 = 127;
    }
LABEL_217:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v69, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
    goto LABEL_218;
  }
LABEL_219:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v131);
  Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(&v121);
  return (unsigned int)Type;
}

```

## disassembly

```asm
0x180309d80  mov     [rsp-8+arg_8], rbx
0x180309d85  push    rbp
0x180309d86  push    rsi
0x180309d87  push    rdi
0x180309d88  push    r12
0x180309d8a  push    r13
0x180309d8c  push    r14
0x180309d8e  push    r15
0x180309d90  lea     rbp, [rsp-27h]
0x180309d95  sub     rsp, 0C0h
0x180309d9c  mov     r15b, r8b
0x180309d9f  lea     r13, aCmfwinrtactiva_9; "CMFWinRTActivate::SavePropertiesToIStre"...
0x180309da6  mov     rdi, rdx
0x180309da9  mov     rsi, rcx
0x180309dac  xor     r12d, r12d
0x180309daf  lea     rcx, [rbp+57h+arg_0]; this
0x180309db3  mov     r14d, 314h
0x180309db9  mov     [rbp+57h+arg_18], r12d
0x180309dbd  mov     r8d, r14d; int
0x180309dc0  mov     [rbp+57h+var_80], r12
0x180309dc4  mov     rdx, r13; char *
0x180309dc7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180309dcc  test    rsi, rsi
0x180309dcf  jnz     loc_180309E89
0x180309dd5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309ddc  mov     ebx, 80070057h
0x180309de1  mov     edi, ebx
0x180309de3  test    rcx, rcx
0x180309de6  jnz     short loc_180309E30
0x180309de8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180309def  nop     dword ptr [rax+rax+00h]
0x180309df4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180309dfb  mov     rcx, rax
0x180309dfe  test    rax, rax
0x180309e01  jz      short loc_180309E22
0x180309e03  mov     rax, [rax]
0x180309e06  mov     edx, 7F0h
0x180309e0b  mov     rax, [rax+8]
0x180309e0f  call    cs:__guard_dispatch_icall_fptr
0x180309e15  test    eax, eax
0x180309e17  jz      short loc_180309E22
0x180309e19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309e20  jmp     short loc_180309E30
0x180309e22  lea     rcx, qword_1803CE250; this
0x180309e29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180309e30  cmp     [rcx+8], r12b
0x180309e34  jz      short loc_180309E54
0x180309e36  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180309e3b  cmp     [rax+7CCh], ebx
0x180309e41  jz      short loc_180309E54
0x180309e43  mov     r9d, ebx; int
0x180309e46  mov     r8d, r14d; int
0x180309e49  mov     rdx, r13; char *
0x180309e4c  mov     rcx, rax; this
0x180309e4f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180309e54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180309e5b  jb      loc_18030AC27
0x180309e61  mov     edx, 7Ah ; 'z'
0x180309e66  mov     dword ptr [rsp+0F0h+pvDestContext], ebx
0x180309e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180309e71  lea     r8, WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids
0x180309e78  xor     r9d, r9d
0x180309e7b  mov     rcx, [rcx+10h]
0x180309e7f  call    WPP_SF_qD
0x180309e84  jmp     loc_18030AC27
0x180309e89  test    rdi, rdi
0x180309e8c  jnz     loc_180309F2B
0x180309e92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309e99  mov     ebx, 80070057h
0x180309e9e  mov     edi, ebx
0x180309ea0  test    rcx, rcx
0x180309ea3  jnz     short loc_180309EED
0x180309ea5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180309eac  nop     dword ptr [rax+rax+00h]
0x180309eb1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180309eb8  mov     rcx, rax
0x180309ebb  test    rax, rax
0x180309ebe  jz      short loc_180309EDF
0x180309ec0  mov     rax, [rax]
0x180309ec3  mov     edx, 7F0h
0x180309ec8  mov     rax, [rax+8]
0x180309ecc  call    cs:__guard_dispatch_icall_fptr
0x180309ed2  test    eax, eax
0x180309ed4  jz      short loc_180309EDF
0x180309ed6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309edd  jmp     short loc_180309EED
0x180309edf  lea     rcx, qword_1803CE250; this
0x180309ee6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180309eed  cmp     [rcx+8], r12b
0x180309ef1  jz      short loc_180309F14
0x180309ef3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180309ef8  cmp     [rax+7CCh], ebx
0x180309efe  jz      short loc_180309F14
0x180309f00  mov     r9d, ebx; int
0x180309f03  mov     r8d, 315h; int
0x180309f09  mov     rdx, r13; char *
0x180309f0c  mov     rcx, rax; this
0x180309f0f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180309f14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180309f1b  jb      loc_18030AC27
0x180309f21  mov     edx, 7Bh ; '{'
0x180309f26  jmp     loc_180309E66
0x180309f2b  mov     rax, [rdi]
0x180309f2e  lea     rcx, [rbp+57h+var_80]
0x180309f32  mov     rbx, [rax]
0x180309f35  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x180309f3a  lea     r8, [rbp+57h+var_80]
0x180309f3e  mov     rcx, rdi
0x180309f41  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x180309f48  mov     rax, rbx
0x180309f4b  call    cs:__guard_dispatch_icall_fptr
0x180309f51  mov     edi, eax
0x180309f53  test    eax, eax
0x180309f55  jns     loc_180309FF1
0x180309f5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309f62  test    rcx, rcx
0x180309f65  jnz     short loc_180309FAF
0x180309f67  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180309f6e  nop     dword ptr [rax+rax+00h]
0x180309f73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180309f7a  mov     rcx, rax
0x180309f7d  test    rax, rax
0x180309f80  jz      short loc_180309FA1
0x180309f82  mov     rax, [rax]
0x180309f85  mov     edx, 7F0h
0x180309f8a  mov     rax, [rax+8]
0x180309f8e  call    cs:__guard_dispatch_icall_fptr
0x180309f94  test    eax, eax
0x180309f96  jz      short loc_180309FA1
0x180309f98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180309f9f  jmp     short loc_180309FAF
0x180309fa1  lea     rcx, qword_1803CE250; this
0x180309fa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180309faf  cmp     [rcx+8], r12b
0x180309fb3  jz      short loc_180309FD6
0x180309fb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180309fba  cmp     [rax+7CCh], edi
0x180309fc0  jz      short loc_180309FD6
0x180309fc2  mov     r9d, edi; int
0x180309fc5  mov     r8d, 317h; int
0x180309fcb  mov     rdx, r13; char *
0x180309fce  mov     rcx, rax; this
0x180309fd1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180309fd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180309fdd  jb      loc_18030AC27
0x180309fe3  mov     edx, 7Ch ; '|'
0x180309fe8  mov     dword ptr [rsp+0F0h+pvDestContext], edi
0x180309fec  jmp     loc_180309E6A
0x180309ff1  mov     [rbp+57h+var_78], r12d
0x180309ff5  mov     r14d, r12d
0x180309ff8  cmp     r14d, 2
0x180309ffc  jnb     loc_18030AC27
0x18030a002  mov     [rbp+57h+var_C0], r12
0x18030a006  cmp     r14d, 1
0x18030a00a  jnz     short loc_18030A03C
0x18030a00c  mov     rax, [rsi]
0x18030a00f  lea     r9, [rbp+57h+var_78]
0x18030a013  lea     r8d, [r14+3]
0x18030a017  mov     rcx, rsi
0x18030a01a  lea     rdx, [rbp+57h+arg_18]
0x18030a01e  mov     rax, [rax+20h]
0x18030a022  call    cs:__guard_dispatch_icall_fptr
0x18030a028  mov     edi, eax
0x18030a02a  test    eax, eax
0x18030a02c  js      loc_18030A37F
0x18030a032  cmp     [rbp+57h+arg_18], r12d
0x18030a036  jz      loc_18030AC1E
0x18030a03c  mov     rdi, [rbp+57h+var_80]
0x18030a040  lea     rcx, [rbp+57h+var_C0]
0x18030a044  mov     [rbp+57h+arg_0], r12b
0x18030a048  mov     rax, [rdi]
0x18030a04b  mov     rbx, [rax+30h]
0x18030a04f  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030a054  lea     rdx, [rbp+57h+var_C0]
0x18030a058  mov     rcx, rdi
0x18030a05b  mov     rax, rbx
0x18030a05e  call    cs:__guard_dispatch_icall_fptr
0x18030a064  mov     edi, eax
0x18030a066  test    eax, eax
0x18030a068  js      loc_18030AB77
0x18030a06e  mov     rcx, [rbp+57h+var_C0]
0x18030a072  lea     rdx, [rbp+57h+arg_0]
0x18030a076  mov     rax, [rcx]
0x18030a079  mov     rax, [rax+38h]
0x18030a07d  call    cs:__guard_dispatch_icall_fptr
0x18030a083  mov     edi, eax
0x18030a085  test    eax, eax
0x18030a087  js      loc_18030AAE5
0x18030a08d  cmp     [rbp+57h+arg_0], r12b
0x18030a091  jz      loc_18030A36E
0x18030a097  mov     rdi, [rbp+57h+var_C0]
0x18030a09b  lea     rcx, [rbp+57h+var_B8]
0x18030a09f  mov     [rbp+57h+var_B8], r12
0x18030a0a3  mov     [rbp+57h+string], r12
0x18030a0a7  mov     [rbp+57h+pUnk], r12
0x18030a0ab  mov     [rbp+57h+var_A0], r12d
0x18030a0af  mov     [rbp+57h+var_94], r12d
0x18030a0b3  mov     rax, [rdi]
0x18030a0b6  mov     rbx, [rax+30h]
0x18030a0ba  call    ?InternalRelease@?$ComPtr@UIMFMediaType@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFMediaType>::InternalRelease(void)
0x18030a0bf  lea     rdx, [rbp+57h+var_B8]
0x18030a0c3  mov     rcx, rdi
0x18030a0c6  mov     rax, rbx
0x18030a0c9  call    cs:__guard_dispatch_icall_fptr
0x18030a0cf  mov     edi, eax
0x18030a0d1  test    eax, eax
0x18030a0d3  js      loc_18030AA53
0x18030a0d9  mov     rcx, [rbp+57h+var_B8]
0x18030a0dd  lea     rdx, [rbp+57h+string]
0x18030a0e1  mov     rax, [rcx]
0x18030a0e4  mov     rax, [rax+30h]
0x18030a0e8  call    cs:__guard_dispatch_icall_fptr
0x18030a0ee  mov     edi, eax
0x18030a0f0  test    eax, eax
0x18030a0f2  js      loc_18030A9C1
0x18030a0f8  mov     rcx, [rbp+57h+var_B8]
0x18030a0fc  lea     rdx, [rbp+57h+pUnk]
0x18030a100  mov     rax, [rcx]
0x18030a103  mov     [rbp+57h+var_50], rdx
0x18030a107  lea     rdx, [rbp+57h+var_48]
0x18030a10b  mov     [rbp+57h+var_48], r12
0x18030a10f  mov     rax, [rax+38h]
0x18030a113  call    cs:__guard_dispatch_icall_fptr
0x18030a119  mov     rdx, [rbp+57h+var_48]; struct IInspectable *
0x18030a11d  lea     rcx, [rbp+57h+var_60]; this
0x18030a121  mov     rbx, [rbp+57h+var_50]
0x18030a125  mov     r8b, 1; bool
0x18030a128  mov     edi, eax
0x18030a12a  call    ??0RoVariant@@QEAA@PEAUIInspectable@@_N@Z; RoVariant::RoVariant(IInspectable *,bool)
0x18030a12f  mov     rcx, [rbx]
0x18030a132  mov     rax, [rbp+57h+var_60]
0x18030a136  mov     [rbx], rax
0x18030a139  mov     eax, [rbp+57h+var_58]
0x18030a13c  mov     [rbp+57h+var_60], rcx
0x18030a140  mov     ecx, [rbx+8]
0x18030a143  mov     [rbp+57h+var_58], ecx
0x18030a146  lea     rcx, [rbp+57h+var_60]; this
0x18030a14a  mov     [rbx+8], eax
0x18030a14d  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18030a152  mov     eax, edi
0x18030a154  shr     eax, 1Fh
0x18030a157  test    al, al
0x18030a159  jnz     loc_18030A92B
0x18030a15f  mov     rax, [rbp+57h+pUnk]
0x18030a163  lea     rdx, [rbp+57h+var_94]; enum Windows::Foundation::PropertyType *
0x18030a167  mov     [rbp+57h+var_40], rax
0x18030a16b  lea     rcx, [rbp+57h+var_40]; this
0x18030a16f  mov     eax, [rbp+57h+var_A0]
0x18030a172  mov     [rbp+57h+var_38], eax
0x18030a175  call    ?get_Type@Accessor@RoVariant@@QEBAJPEAW4PropertyType@Foundation@Windows@@@Z; RoVariant::Accessor::get_Type(Windows::Foundation::PropertyType *)
0x18030a17a  mov     edi, eax
0x18030a17c  test    eax, eax
0x18030a17e  js      loc_18030A899
0x18030a184  mov     eax, [rbp+57h+var_94]
0x18030a187  cmp     eax, 40Dh
0x18030a18c  jz      loc_18030A32F
0x18030a192  cmp     eax, 14h
0x18030a195  jz      loc_18030A32F
0x18030a19b  cmp     eax, 414h
0x18030a1a0  jz      loc_18030A32F
0x18030a1a6  test    eax, eax
0x18030a1a8  jz      loc_18030A32F
0x18030a1ae  cmp     eax, 0Dh
0x18030a1b1  jnz     short loc_18030A1BC
0x18030a1b3  test    r15b, r15b
0x18030a1b6  jz      loc_18030A32F
0x18030a1bc  test    r14d, r14d
0x18030a1bf  jnz     short loc_18030A1C9
0x18030a1c1  inc     [rbp+57h+arg_18]
0x18030a1c4  jmp     loc_18030A32F
0x18030a1c9  mov     rcx, [rbp+57h+string]; string
0x18030a1cd  call    cs:__imp_WindowsGetStringLen
0x18030a1d4  nop     dword ptr [rax+rax+00h]
0x18030a1d9  lea     r9, [rbp+57h+var_88]
0x18030a1dd  mov     [rbp+57h+var_88], r12d
0x18030a1e1  mov     [rbp+57h+length], eax
0x18030a1e4  lea     rdx, [rbp+57h+length]
0x18030a1e8  mov     rax, [rsi]
0x18030a1eb  mov     r8d, 4
0x18030a1f1  mov     rcx, rsi
0x18030a1f4  mov     rax, [rax+20h]
0x18030a1f8  call    cs:__guard_dispatch_icall_fptr
0x18030a1fe  mov     edi, eax
0x18030a200  test    eax, eax
0x18030a202  js      loc_18030A775
0x18030a208  mov     ecx, [rbp+57h+length]
0x18030a20b  lea     rdx, [rbp+57h+length]; length
0x18030a20f  mov     rax, [rsi]
0x18030a212  lea     ebx, [rcx+rcx]
0x18030a215  mov     rcx, [rbp+57h+string]; string
0x18030a219  mov     rdi, [rax+20h]
0x18030a21d  call    cs:__imp_WindowsGetStringRawBuffer
0x18030a224  nop     dword ptr [rax+rax+00h]
0x18030a229  lea     r9, [rbp+57h+var_88]
0x18030a22d  mov     r8d, ebx
0x18030a230  mov     rdx, rax
0x18030a233  mov     rcx, rsi
0x18030a236  mov     rax, rdi
0x18030a239  call    cs:__guard_dispatch_icall_fptr
0x18030a23f  mov     edi, eax
  ... truncated ...
```
