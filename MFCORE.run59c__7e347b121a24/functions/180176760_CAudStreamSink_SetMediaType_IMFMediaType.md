# CAudStreamSink::SetMediaType(IMFMediaType *)

- ea: `0x180176760`
- end: `0x180177990`
- name: `?SetMediaType@CAudStreamSink@@UEAAJPEAUIMFMediaType@@@Z`
- size: `4656`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, struct IMFMediaType *)`
- caller_count: `3`
- callee_count: `42`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e2590`
- `0x180176760`
- `0x1801beb1c`

## callees

- `0x18000e400`
- `0x18000f278`
- `0x18001616c`
- `0x18002c9ac`
- `0x18002fee0`
- `0x18003a41c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x18004e910`
- `0x180050d6c`
- `0x18006b388`
- `0x18007cb1c`
- `0x18007d750`
- `0x18007df8c`
- `0x180082f10`
- `0x18008352c`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x1800b243c`
- `0x1800b3234`
- `0x1800c99fc`
- `0x1800ec0e0`
- `0x18012c440`
- `0x180132f44`
- `0x180151110`
- `0x180163480`
- `0x180168f68`
- `0x180176760`
- `0x180177c04`
- `0x18018dc5c`
- `0x180190a9c`
- `0x1801fb65c`
- `0x180258480`
- `0x1802c6080`
- `0x1802de980`
- `0x18031941c`
- `0x18031cb1c`
- `0x18031e358`
- `0x18031e48c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180176c88`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180176c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176f61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180176f61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801769fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180176fae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801769fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180176fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180176c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180176c16`
- `MFPlat!FormatTagFromWfx` at `0x18017698a`
- `MFPlat!FormatTagFromWfx` at `0x18017698a`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180176938`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180176938`

## string_xrefs

- `0x1801767a1`: `CAudStreamSink::SetMediaType`
- `0x180176890`: `CAudStreamSink::SetMediaType`
- `0x180176953`: `CAudStreamSink::SetMediaType`
- `0x180176fee`: `CAudStreamSink::SetMediaType`
- `0x180177097`: `CAudStreamSink::SetMediaType`
- `0x180177191`: `CAudStreamSink::SetMediaType`
- `0x180177270`: `CAudStreamSink::SetMediaType`
- `0x1801773ea`: `CAudStreamSink::SetMediaType`
- `0x1801774a1`: `CAudStreamSink::SetMediaType`
- `0x18017755e`: `CAudStreamSink::SetMediaType`
- `0x18017760b`: `CAudStreamSink::SetMediaType`
- `0x18017770a`: `CAudStreamSink::SetMediaType`
- `0x1801778fa`: `CAudStreamSink::SetMediaType`
- `0x180177964`: `CAudStreamSink::SetMediaType`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::SetMediaType(CAudStreamSink *this, struct IMFAttributes *a2)
{
  struct IMFAttributes *v2; // rdi
  CAudStreamSink *v3; // rsi
  CallStackTracing *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 *v7; // rax
  __int128 v8; // xmm0
  HRESULT StreamState; // r13d
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  char *v12; // r9
  const char *String; // rax
  unsigned int v14; // edx
  WORD cbSize; // bx
  WORD wBitsPerSample; // di
  WORD nBlockAlign; // si
  DWORD nAvgBytesPerSec; // r14d
  DWORD nSamplesPerSec; // r15d
  WORD nChannels; // r12
  unsigned __int16 v21; // ax
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // ecx
  char *v26; // rbx
  CMMNotificationClient *v27; // rcx
  __int64 v28; // rcx
  WAVEFORMATEX *v29; // rcx
  const struct tWAVEFORMATEX *v30; // rdx
  int v31; // ebx
  CAudioClientManager *v32; // rcx
  __int64 v33; // r9
  int v34; // edi
  __int64 v35; // rcx
  __int64 v36; // r8
  _OWORD *v37; // rax
  __int64 v38; // rcx
  int v39; // r8d
  int v40; // r9d
  int v42; // eax
  __int64 v43; // r15
  unsigned int i; // r14d
  __int64 (__fastcall *v45)(__int64, __int128 *, PROPVARIANT *); // rax
  int v46; // eax
  int v47; // r14d
  CAudioClientManager *v48; // rcx
  const char *v49; // rax
  const char *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  unsigned int IsSpatialType; // edi
  CAudioClientManager *v57; // rcx
  int v58; // eax
  unsigned __int8 v59; // cl
  CallStackTracing *v60; // rcx
  struct CallStackContext *v61; // rax
  __int64 v62; // rcx
  unsigned int v63; // r15d
  CallStackTracing *v64; // rcx
  struct CallStackContext *v65; // rax
  int v66; // eax
  __int64 v67; // rcx
  CAudStreamSink *v68; // rcx
  int v69; // eax
  int AudioStreamInternal; // eax
  int v71; // r13d
  CallStackTracing *v72; // rcx
  struct CallStackContext *v73; // rax
  CallStackTracing *v74; // rcx
  struct CallStackContext *v75; // rax
  void (__fastcall ***v76)(_QWORD, struct IMFAttributes *); // rcx
  CallStackTracing *v77; // rcx
  struct CallStackContext *v78; // rax
  CallStackTracing *v79; // rcx
  struct CallStackContext *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rcx
  CallStackTracing *v84; // rcx
  struct CallStackContext *v85; // rax
  int v86; // r11d
  __int64 v87; // r9
  int IsLateBindingAllowed; // eax
  _DWORD *v89; // r10
  int v90; // r9d
  int v91; // r11d
  __int64 v92; // rcx
  CallStackTracing *v93; // rcx
  struct CallStackContext *v94; // rax
  CallStackTracing *v95; // rcx
  struct CallStackContext *v96; // rax
  int Volume; // [rsp+80h] [rbp-80h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+88h] [rbp-78h] BYREF
  char v99[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v100; // [rsp+98h] [rbp-68h] BYREF
  __int64 v101; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 pcbSize; // [rsp+A8h] [rbp-58h] BYREF
  int v103; // [rsp+ACh] [rbp-54h] BYREF
  int v104; // [rsp+B0h] [rbp-50h] BYREF
  int v105; // [rsp+B4h] [rbp-4Ch] BYREF
  int v106; // [rsp+B8h] [rbp-48h] BYREF
  DWORD v107; // [rsp+BCh] [rbp-44h] BYREF
  DWORD v108; // [rsp+C0h] [rbp-40h] BYREF
  GUID *v109; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v110[192]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v111[192]; // [rsp+190h] [rbp+90h] BYREF
  PROPVARIANT pvar[2]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v113; // [rsp+260h] [rbp+160h]
  _QWORD v114[2]; // [rsp+268h] [rbp+168h] BYREF
  GUID v115; // [rsp+278h] [rbp+178h] BYREF

  v2 = a2;
  v101 = (__int64)a2;
  v3 = this;
  v100 = (__int64)this;
  pcbSize = 0;
  ppWF = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v99, "CAudStreamSink::SetMediaType", 3230);
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)v3 + 821) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 821) + 296LL))(*((_QWORD *)v3 + 821));
    v7 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**((_QWORD **)v3 + 821) + 280LL))(
                       *((_QWORD *)v3 + 821),
                       pvar);
    v4 = CallStackTracing::s_wpInstance;
    v8 = *v7;
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
    v2 = (struct IMFAttributes *)v101;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
  {
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_SetMediaType_Enter,
      (char *)v3 - 32);
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( !v2 )
  {
    StreamState = -2147467261;
    if ( !v4 )
    {
      CallStackTracing::InitInstance();
      v4 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CAudStreamSink::SetMediaType", 3233, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 209;
LABEL_14:
      v12 = (char *)v3 - 32;
LABEL_15:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        v12,
        StreamState);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v110, v2);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
  {
    String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v110, 0);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      210,
      (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      (_DWORD)v3 - 32,
      (__int64)String);
  }
  CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v110);
  StreamState = MFCreateWaveFormatExFromMFMediaType((IMFMediaType *)v2, &ppWF, &pcbSize, 0);
  if ( StreamState >= 0 )
  {
    LogWaveFormat(0x10005u, v14, ppWF, "CAudStreamSink::SetMediaType");
    if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    {
      cbSize = ppWF->cbSize;
      wBitsPerSample = ppWF->wBitsPerSample;
      nBlockAlign = ppWF->nBlockAlign;
      nAvgBytesPerSec = ppWF->nAvgBytesPerSec;
      nSamplesPerSec = ppWF->nSamplesPerSec;
      nChannels = ppWF->nChannels;
      v21 = FormatTagFromWfx(ppWF);
      McTemplateU0pqhqqhhh_EventWriteTransfer(
        v22,
        (unsigned int)&AudStreamSink_WaveFormat,
        v100 - 32,
        v21,
        nChannels,
        nSamplesPerSec,
        nAvgBytesPerSec,
        nBlockAlign,
        wBitsPerSample,
        cbSize);
      v3 = (CAudStreamSink *)v100;
      v2 = (struct IMFAttributes *)v101;
    }
    if ( !(unsigned int)IsUncompressedWaveFormatEx(ppWF) && !*(_WORD *)(v23 + 12) )
      *(_WORD *)(v23 + 12) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)v3 + 17);
    v26 = (char *)v3 - 32;
    if ( *((_DWORD *)v3 + 1346) )
      goto LABEL_25;
    if ( !*((_QWORD *)v3 + 825) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          212,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)v3 - 32);
      *((_DWORD *)v3 + 1346) = 1;
LABEL_25:
      *((_DWORD *)v3 + 56) = 0;
      goto LABEL_26;
    }
    v42 = *((_DWORD *)v3 + 56);
    if ( *((_DWORD *)v3 + 78) )
    {
      if ( !v42 )
      {
        v43 = *((_QWORD *)v3 + 1);
        if ( v43 )
        {
          StreamState = 0;
          for ( i = 0; i < 0xA; ++i )
          {
            Volume = 0;
            v113 = 0;
            v45 = *(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v43 + 24LL);
            *(_OWORD *)pvar = 0;
            v46 = v45(v43, &xmmword_1803CF3D0[i], pvar);
            if ( v46 != -1072875802 )
            {
              if ( v46 < 0 )
              {
                CMFPropVariant::Clear(pvar);
                goto LABEL_70;
              }
              StreamState = ((__int64 (__fastcall *)(struct IMFAttributes *, __int128 *, PROPVARIANT *, int *))v2->lpVtbl->CompareItem)(
                              v2,
                              &xmmword_1803CF3D0[i],
                              pvar,
                              &Volume);
              if ( StreamState < 0 || !Volume )
              {
                v47 = 0;
                CMFPropVariant::Clear(pvar);
                goto LABEL_65;
              }
            }
            CMFPropVariant::Clear(pvar);
          }
          v47 = 1;
LABEL_65:
          if ( StreamState >= 0 && v47 )
          {
            if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                234,
                &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
                (char *)v3 - 32);
            goto LABEL_26;
          }
        }
LABEL_70:
        CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v111, *((struct IMFAttributes **)v3 + 1));
        CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v110, v2);
        LOBYTE(v48) = (_BYTE)byte_1803CECE9;
        if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            223,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            (char *)v3 - 32);
          LOBYTE(v48) = (_BYTE)byte_1803CECE9;
          if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          {
            v49 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v111, 0);
            WPP_SF_qs(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              224,
              (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (_DWORD)v3 - 32,
              (__int64)v49);
            LOBYTE(v48) = (_BYTE)byte_1803CECE9;
            if ( (unsigned __int8)byte_1803CECE9 >= 8u )
            {
              v50 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v110, 0);
              WPP_SF_qs(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                225,
                (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
                (_DWORD)v3 - 32,
                (__int64)v50);
              LOBYTE(v48) = (_BYTE)byte_1803CECE9;
            }
          }
        }
        if ( !*((_DWORD *)v3 + 1791) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 232));
          if ( (unsigned __int8)byte_1803CECE9 >= 8u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              226,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)v3 - 32);
          StreamState = CAudStreamSink::DoInvalidateAudEngineStream((CAudStreamSink *)((char *)v3 - 32), 0xFFFFFFu, 1);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 232));
          if ( StreamState >= 0 )
          {
            if ( (unsigned __int8)byte_1803CECE9 >= 8u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                228,
                &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
                (char *)v3 - 32);
            StreamState = CAudStreamSink::SetMediaType(v3, (struct IMFMediaType *)v2);
            if ( StreamState >= 0 )
              goto LABEL_102;
            v54 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v54 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v54 + 8) )
            {
              v55 = CallStackTracing::GetThreadRelativeContext(v54);
              if ( *((_DWORD *)v55 + 499) != StreamState )
                CallStackContext::TraceFailure(v55, "CAudStreamSink::SetMediaType", 3468, StreamState);
            }
            if ( !g_wppLevels )
              goto LABEL_102;
            v53 = 229;
          }
          else
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
              if ( *((_DWORD *)v52 + 499) != StreamState )
                CallStackContext::TraceFailure(v52, "CAudStreamSink::SetMediaType", 3465, StreamState);
            }
            if ( !g_wppLevels )
              goto LABEL_102;
            v53 = 227;
          }
          goto LABEL_85;
        }
        IsSpatialType = CAudioClientManager::IsSpatialType(v48, ppWF);
        v58 = CAudioClientManager::IsSpatialType(v57, *((const struct tWAVEFORMATEX **)v3 + 96));
        if ( *((_DWORD *)v3 + 1818) )
        {
          if ( IsSpatialType )
          {
            if ( v58 )
              goto LABEL_99;
          }
          else if ( !v58 )
          {
            goto LABEL_99;
          }
          if ( v59 >= 8u )
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              230,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              (char *)v3 - 32);
          StreamState = CAudStreamSink::QueueDynamicFormatChange((CAudStreamSink *)((char *)v3 - 32));
          if ( StreamState >= 0 )
          {
            v62 = *((_QWORD *)v26 + 818);
            if ( v62 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 48LL))(v62, IsSpatialType);
            ++*((_DWORD *)v3 + 196);
            if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                232,
                &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
                (char *)v3 - 32,
                *((_DWORD *)v3 + 196));
            goto LABEL_102;
          }
          v60 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v60 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v60 + 8) )
          {
            v61 = CallStackTracing::GetThreadRelativeContext(v60);
            if ( *((_DWORD *)v61 + 499) != StreamState )
              CallStackContext::TraceFailure(v61, "CAudStreamSink::SetMediaType", 3484, StreamState);
          }
          if ( !g_wppLevels )
          {
LABEL_102:
            CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v110);
            CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v111);
            goto LABEL_26;
          }
          v53 = 231;
LABEL_85:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v53,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            (char *)v3 - 32,
            StreamState);
          goto LABEL_102;
        }
LABEL_99:
        if ( v59 >= 8u )
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            233,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            (char *)v3 - 32);
        StreamState = -1072871856;
        goto LABEL_102;
      }
      Volume = 0;
    }
    else
    {
      Volume = 0;
      v63 = 0;
      if ( !v42 )
      {
        LOBYTE(v66) = 0;
        goto LABEL_130;
      }
    }
    StreamState = CAudStreamSink::GetStreamState((CAudStreamSink *)((char *)v3 - 32), (enum _MFAUDIO_STATE *)&Volume);
    if ( StreamState < 0 )
    {
      v64 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v64 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v64 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext(v64);
        if ( *((_DWORD *)v65 + 499) != StreamState )
          CallStackContext::TraceFailure(v65, "CAudStreamSink::SetMediaType", 3309, StreamState);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          213,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)v3 - 32,
          StreamState);
      goto LABEL_26;
    }
    v66 = *((_DWORD *)v3 + 56);
    v63 = Volume;
LABEL_130:
    if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
      McTemplateU0pttd_EventWriteTransfer(v25, v24, (_DWORD)v3 - 32, *((_DWORD *)v3 + 78) == 0, v66, v63);
    v67 = *((_QWORD *)v3 + 812);
    if ( v67 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 16LL))(v67, 1);
    *((_QWORD *)v3 + 812) = 0;
    if ( !(unsigned int)CAudStreamSink::IsLateBindingAllowed((CAudStreamSink *)((char *)v3 - 32))
      || (v69 = 1, *((_DWORD *)v3 + 1647)) )
    {
      v69 = 0;
    }
    AudioStreamInternal = CAudStreamSink::CreateAudioStreamInternal(
                            v68,
                            (struct IMFMediaType *)v2,
                            ppWF,
                            *((_DWORD *)v3 + 1798),
                            v69,
                            1,
                            (struct ILightWeightSampleConverter **)v3 + 812);
    v71 = AudioStreamInternal;
    Volume = AudioStreamInternal;
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        214,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)v3 - 32,
        AudioStreamInternal);
    if ( v71 < 0 )
    {
      if ( CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
        goto LABEL_230;
      StreamState = Volume;
      if ( Volume < 0 )
      {
        v72 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v72 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v72 + 8) )
        {
          v73 = CallStackTracing::GetThreadRelativeContext(v72);
          if ( StreamState < 0 && *((_DWORD *)v73 + 499) != StreamState )
            CallStackContext::TraceFailure(v73, "CAudStreamSink::SetMediaType", 3326, StreamState);
        }
        if ( !g_wppLevels )
          goto LABEL_26;
        v11 = 215;
        goto LABEL_150;
      }
    }
    *((_DWORD *)v26 + 1657) = CAudioClientManager::IsSpatialType(
                                *((CAudioClientManager **)v26 + 842),
                                (struct IMFMediaType *)v2) != 0;
    Volume = CAudStreamVolume::CaptureReapplyLastVolume((CAudStreamSink *)((char *)v3 + 328));
    StreamState = Volume;
    if ( Volume < 0 )
    {
      if ( CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
        goto LABEL_230;
      StreamState = Volume;
    }
    if ( StreamState < 0 )
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
        if ( *((_DWORD *)v75 + 499) != StreamState )
          CallStackContext::TraceFailure(v75, "CAudStreamSink::SetMediaType", 3340, StreamState);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v11 = 216;
      goto LABEL_150;
    }
    v76 = (void (__fastcall ***)(_QWORD, struct IMFAttributes *))*((_QWORD *)v26 + 816);
    if ( v76 )
      (**v76)(v76, v2);
    if ( !*((_DWORD *)v3 + 56) )
    {
LABEL_213:
      *((_DWORD *)v3 + 1646) = 1;
      *((_DWORD *)v3 + 1790) = 0;
      if ( !*((_DWORD *)v3 + 1647) )
      {
        v92 = *((_QWORD *)v3 + 97);
        if ( v92 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        *((_QWORD *)v3 + 97) = v2;
        ((void (__fastcall *)(struct IMFAttributes *))v2->lpVtbl->AddRef)(v2);
        *((_DWORD *)v3 + 1791) = 0;
      }
      goto LABEL_26;
    }
    Volume = CAudStreamSink::SetLastPolicyOnNewOTAs((CAudStreamSink *)((char *)v3 - 32), 0);
    StreamState = Volume;
    if ( Volume < 0 )
    {
      if ( CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
        goto LABEL_230;
      StreamState = Volume;
    }
    if ( StreamState < 0 )
    {
      v77 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v77 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v78 = CallStackTracing::GetThreadRelativeContext(v77);
        if ( *((_DWORD *)v78 + 499) != StreamState )
          CallStackContext::TraceFailure(v78, "CAudStreamSink::SetMediaType", 3357, StreamState);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v11 = 217;
      goto LABEL_150;
    }
    v101 = 0x7FFFFFFFFFFFFFFFLL;
    v100 = 0x7FFFFFFFFFFFFFFFLL;
    Volume = CAudStreamSink::GetExactTime((CAudStreamSink *)((char *)v3 - 32), &v101, &v100);
    StreamState = Volume;
    if ( Volume < 0 )
    {
      if ( CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
        goto LABEL_230;
      StreamState = Volume;
    }
    if ( StreamState < 0 )
    {
      v79 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v79 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v79 + 8) )
      {
        v80 = CallStackTracing::GetThreadRelativeContext(v79);
        if ( *((_DWORD *)v80 + 499) != StreamState )
          CallStackContext::TraceFailure(v80, "CAudStreamSink::SetMediaType", 3364, StreamState);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v11 = 218;
      goto LABEL_150;
    }
    v81 = *((_QWORD *)v3 + 1);
    *((_QWORD *)v3 + 631) = v100 - *((_QWORD *)v26 + 633);
    if ( v81 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    *((_QWORD *)v3 + 1) = v2;
    ((void (__fastcall *)(struct IMFAttributes *))v2->lpVtbl->AddRef)(v2);
    if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
      McTemplateU0p_EventWriteTransfer(
        &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
        &AudStreamSink_SetStreamInvalidating_Off,
        (char *)v3 - 32);
    v82 = *((_QWORD *)v3 + 630);
    *((_DWORD *)v3 + 56) = 0;
    Volume = CAudStreamSink::UpdateStartTime((CAudStreamSink *)((char *)v3 - 32), v82, 1);
    StreamState = Volume;
    if ( Volume < 0 )
    {
      if ( CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
        goto LABEL_230;
      StreamState = Volume;
    }
    if ( StreamState < 0 )
    {
      v84 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v84 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v84 + 8) )
      {
        v85 = CallStackTracing::GetThreadRelativeContext(v84);
        if ( *((_DWORD *)v85 + 499) != StreamState )
          CallStackContext::TraceFailure(v85, "CAudStreamSink::SetMediaType", 3381, StreamState);
      }
      if ( !g_wppLevels )
        goto LABEL_26;
      v11 = 219;
      goto LABEL_150;
    }
    v86 = *((_DWORD *)v3 + 1280);
    *((_DWORD *)v26 + 1340) = 1;
    *((_DWORD *)v3 + 1360) = 4;
    if ( v86 && !*((_DWORD *)v3 + 1283) && v63 == 2 )
    {
      v87 = *((unsigned int *)v3 + 1647);
      goto LABEL_208;
    }
    if ( (unsigned int)CAudStreamSink::IsLateBindingAllowed((CAudStreamSink *)((char *)v3 - 32)) )
    {
      v87 = *((unsigned int *)v3 + 1647);
      if ( !(_DWORD)v87 )
      {
LABEL_208:
        if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
        {
          IsLateBindingAllowed = CAudStreamSink::IsLateBindingAllowed((CAudStreamSink *)((char *)v3 - 32));
          WPP_SF_qDdddd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            222,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            (char *)v3 - 32,
            v63,
            v91,
            *v89,
            IsLateBindingAllowed,
            v90);
        }
LABEL_210:
        if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 0x10) != 0 )
          McTemplateU0t_EventWriteTransfer(v83, &Audio_Renderer_DynamicFormatChange, 0, v87);
        CAudStreamSink::EnableSampleRequests((CAudStreamSink *)((char *)v3 - 32), 1);
        CAudStreamSink::RequestMoreSamples((CAudStreamSink *)((char *)v3 - 32));
        goto LABEL_213;
      }
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        220,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (char *)v3 - 32,
        v63);
    Volume = CAudStreamSink::SetStreamState((char *)v3 - 32, 0, v63);
    StreamState = Volume;
    if ( Volume >= 0 )
    {
LABEL_222:
      if ( StreamState < 0 )
      {
        v93 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v93 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v93 + 8) )
        {
          v94 = CallStackTracing::GetThreadRelativeContext(v93);
          if ( *((_DWORD *)v94 + 499) != StreamState )
            CallStackContext::TraceFailure(v94, "CAudStreamSink::SetMediaType", 3396, StreamState);
        }
        if ( !g_wppLevels )
          goto LABEL_26;
        v11 = 221;
LABEL_150:
        v12 = (char *)v3 - 32;
        goto LABEL_15;
      }
      goto LABEL_210;
    }
    if ( !CAudStreamSink::SetMediaType_CheckResult((CAudStreamSink *)((char *)v3 - 32), &Volume, ppWF) )
    {
      StreamState = Volume;
      goto LABEL_222;
    }
LABEL_230:
    StreamState = Volume;
    goto LABEL_26;
  }
  v95 = CallStackTracing::s_wpInstance;
  StreamState = -1072875852;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v95 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v95 + 8) )
  {
    v96 = CallStackTracing::GetThreadRelativeContext(v95);
    if ( *((_DWORD *)v96 + 499) != -1072875852 )
      CallStackContext::TraceFailure(v96, "CAudStreamSink::SetMediaType", 3258, -1072875852);
  }
  if ( g_wppLevels )
  {
    v11 = 211;
    goto LABEL_14;
  }
LABEL_26:
  v27 = (CMMNotificationClient *)*((_QWORD *)v3 + 827);
  if ( v27 )
    CMMNotificationClient::SetPendingStreamingEndpointId(v27, 0);
  v28 = *((_QWORD *)v3 + 821);
  if ( v28
    && (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v28 + 320LL))(
         v28,
         &MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT) )
  {
    goto LABEL_38;
  }
  v29 = ppWF;
  if ( ppWF )
  {
    if ( *((_QWORD *)v3 + 1) )
    {
      v30 = (const struct tWAVEFORMATEX *)*((_QWORD *)v3 + 96);
      if ( v30 )
      {
        v115 = GUID_00000000_0000_0000_0000_000000000000;
        v31 = CAudioClientManager::IsSpatialType((CAudioClientManager *)ppWF, v30);
        v34 = CAudioClientManager::IsSpatialType(v32, (const struct tWAVEFORMATEX *)v32);
        (*(void (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)v33 + 80LL))(v33, &MF_MT_SUBTYPE, &v115);
        v35 = *((_QWORD *)v3 + 821);
        v36 = 0;
        *(GUID *)pvar = GUID_00000000_0000_0000_0000_000000000000;
        if ( v35 )
        {
          v37 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v35 + 280LL))(v35, v114, 0);
          v38 = *((_QWORD *)v3 + 821);
          *(_OWORD *)pvar = *v37;
          v36 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v38 + 296LL))(v38);
        }
        if ( (unsigned int)dword_1803A6650 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1803A6650, 0x400000000000LL, v36) )
        {
          Volume = StreamState;
          v103 = v34;
          v104 = v31;
          v105 = ppWF->wBitsPerSample;
          v106 = ppWF->nBlockAlign;
          v107 = ppWF->nAvgBytesPerSec;
          v108 = ppWF->nSamplesPerSec;
          LODWORD(v101) = ppWF->nChannels;
          v109 = &v115;
          v114[0] = pvar;
          LODWORD(v100) = v39;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)ppWF,
            (unsigned int)&unk_180393C37,
            v39,
            v40,
            (__int64)v114,
            (__int64)&v100,
            (__int64)&v109,
            (__int64)&v101,
            (__int64)&v108,
            (__int64)&v107,
            (__int64)&v106,
            (__int64)&v105,
            (__int64)&v104,
            (__int64)&v103,
            (__int64)&Volume);
        }
LABEL_38:
        v29 = ppWF;
      }
    }
  }
  CoTaskMemFree(v29);
  LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 17);
  if ( !*((_DWORD *)v3 + 56) )
  {
    if ( *((_DWORD *)v3 + 1346) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          235,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          (char *)v3 - 32);
      StreamState = CAudStreamSink::InvalidateInternalStream((char *)v3 - 32, 5);
    }
    SetEvent(*((HANDLE *)v3 + 667));
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_SetMediaType_Exit,
      (char *)v3 - 32,
      (unsigned int)StreamState);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      236,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      (char *)v3 - 32,
      StreamState);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v99);
  return (unsigned int)StreamState;
}

```

## disassembly

```asm
0x180176760  mov     [rsp-8+arg_10], rbx
0x180176765  push    rbp
0x180176766  push    rsi
0x180176767  push    rdi
0x180176768  push    r12
0x18017676a  push    r13
0x18017676c  push    r14
0x18017676e  push    r15
0x180176770  lea     rbp, [rsp-190h]
0x180176778  sub     rsp, 290h
0x18017677f  mov     rax, cs:__security_cookie
0x180176786  xor     rax, rsp
0x180176789  mov     [rbp+1C0h+var_38], rax
0x180176790  mov     rdi, rdx
0x180176793  mov     [rbp+1C0h+var_220], rdx
0x180176797  mov     rsi, rcx
0x18017679a  mov     [rbp+1C0h+var_228], rcx
0x18017679e  xor     r12d, r12d
0x1801767a1  lea     rdx, aCaudstreamsink_65; "CAudStreamSink::SetMediaType"
0x1801767a8  lea     rcx, [rbp+1C0h+var_230]; this
0x1801767ac  mov     [rbp+1C0h+pcbSize], r12d
0x1801767b0  mov     r8d, 0C9Eh; int
0x1801767b6  mov     [rbp+1C0h+ppWF], r12
0x1801767ba  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801767bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801767c6  cmp     [rcx+8], r12b
0x1801767ca  jz      short loc_180176830
0x1801767cc  cmp     [rsi+19A8h], r12
0x1801767d3  jz      short loc_180176830
0x1801767d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801767da  mov     rcx, [rsi+19A8h]
0x1801767e1  mov     rdi, rax
0x1801767e4  mov     rdx, [rcx]
0x1801767e7  mov     rax, [rdx+128h]
0x1801767ee  call    cs:__guard_dispatch_icall_fptr
0x1801767f4  mov     rcx, [rsi+19A8h]
0x1801767fb  mov     ebx, eax
0x1801767fd  mov     rdx, [rcx]
0x180176800  mov     rax, [rdx+118h]
0x180176807  lea     rdx, [rbp+1C0h+pvar]
0x18017680e  call    cs:__guard_dispatch_icall_fptr
0x180176814  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18017681b  movups  xmm0, xmmword ptr [rax]
0x18017681e  mov     [rdi+7E0h], ebx
0x180176824  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18017682c  mov     rdi, [rbp+1C0h+var_220]
0x180176830  mov     r14d, 1
0x180176836  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, r14b
0x18017683d  jz      short loc_18017685D
0x18017683f  lea     r8, [rsi-20h]
0x180176843  lea     rdx, AudStreamSink_SetMediaType_Enter
0x18017684a  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x180176851  call    McTemplateU0p_EventWriteTransfer
0x180176856  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18017685d  test    rdi, rdi
0x180176860  jnz     short loc_1801768DC
0x180176862  mov     r13d, 80004003h
0x180176868  test    rcx, rcx
0x18017686b  jnz     short loc_180176879
0x18017686d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180176872  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180176879  cmp     [rcx+8], r12b
0x18017687d  jz      short loc_1801768A5
0x18017687f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180176884  cmp     [rax+7CCh], r13d
0x18017688b  jz      short loc_1801768A5
0x18017688d  mov     r9d, r13d; int
0x180176890  lea     rdx, aCaudstreamsink_65; "CAudStreamSink::SetMediaType"
0x180176897  mov     r8d, 0CA1h; int
0x18017689d  mov     rcx, rax; this
0x1801768a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801768a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x1801768ac  jb      loc_180176A27
0x1801768b2  mov     edx, 0D1h
0x1801768b7  lea     r9, [rsi-20h]
0x1801768bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801768c2  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1801768c9  mov     [rsp+2C0h+var_2A0], r13d
0x1801768ce  mov     rcx, [rcx+10h]
0x1801768d2  call    WPP_SF_qD
0x1801768d7  jmp     loc_180176A27
0x1801768dc  mov     rdx, rdi; struct IMFAttributes *
0x1801768df  lea     rcx, [rbp+1C0h+var_1F0]; this
0x1801768e3  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x1801768e8  cmp     cs:byte_1803CECE9, 8
0x1801768ef  jb      short loc_180176921
0x1801768f1  xor     edx, edx; bool
0x1801768f3  lea     rcx, [rbp+1C0h+var_1F0]; this
0x1801768f7  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x1801768fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180176903  lea     r9, [rsi-20h]
0x180176907  mov     edx, 0D2h
0x18017690c  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180176911  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180176918  mov     rcx, [rcx+38h]
0x18017691c  call    WPP_SF_qs
0x180176921  lea     rcx, [rbp+1C0h+var_1F0]; this
0x180176925  call    ??1CMFAttributesTrace@@QEAA@XZ; CMFAttributesTrace::~CMFAttributesTrace(void)
0x18017692a  xor     r9d, r9d; Flags
0x18017692d  lea     r8, [rbp+1C0h+pcbSize]; pcbSize
0x180176931  lea     rdx, [rbp+1C0h+ppWF]; ppWF
0x180176935  mov     rcx, rdi; pMFType
0x180176938  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18017693f  nop     dword ptr [rax+rax+00h]
0x180176944  mov     r13d, eax
0x180176947  test    eax, eax
0x180176949  js      loc_18017792F
0x18017694f  mov     r8, [rbp+1C0h+ppWF]; struct tWAVEFORMATEX *
0x180176953  lea     r9, aCaudstreamsink_65; "CAudStreamSink::SetMediaType"
0x18017695a  mov     ecx, 10005h; unsigned int
0x18017695f  call    ?LogWaveFormat@@YAXKKPEBUtWAVEFORMATEX@@PEBD@Z; LogWaveFormat(ulong,ulong,tWAVEFORMATEX const *,char const *)
0x180176964  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, r14b
0x18017696b  jz      short loc_1801769DD
0x18017696d  mov     rcx, [rbp+1C0h+ppWF]
0x180176971  movzx   ebx, word ptr [rcx+10h]
0x180176975  movzx   edi, word ptr [rcx+0Eh]
0x180176979  movzx   esi, word ptr [rcx+0Ch]
0x18017697d  mov     r14d, [rcx+8]
0x180176981  mov     r15d, [rcx+4]
0x180176985  movzx   r12d, word ptr [rcx+2]
0x18017698a  call    cs:__imp_?FormatTagFromWfx@@YAGPEBUtWAVEFORMATEX@@@Z; FormatTagFromWfx(tWAVEFORMATEX const *)
0x180176991  nop     dword ptr [rax+rax+00h]
0x180176996  mov     r8, [rbp+1C0h+var_228]
0x18017699a  lea     rdx, AudStreamSink_WaveFormat
0x1801769a1  mov     word ptr [rsp+2C0h+var_278], bx
0x1801769a6  add     r8, 0FFFFFFFFFFFFFFE0h
0x1801769aa  mov     word ptr [rsp+2C0h+var_280], di
0x1801769af  mov     word ptr [rsp+2C0h+var_288], si
0x1801769b4  mov     dword ptr [rsp+2C0h+var_290], r14d
0x1801769b9  mov     [rsp+2C0h+var_298], r15d
0x1801769be  movzx   r9d, ax
0x1801769c2  mov     word ptr [rsp+2C0h+var_2A0], r12w
0x1801769c8  call    McTemplateU0pqhqqhhh_EventWriteTransfer
0x1801769cd  mov     rsi, [rbp+1C0h+var_228]
0x1801769d1  xor     r12d, r12d
0x1801769d4  mov     rdi, [rbp+1C0h+var_220]
0x1801769d8  lea     r14d, [r12+1]
0x1801769dd  mov     rcx, [rbp+1C0h+ppWF]; struct tWAVEFORMATEX *
0x1801769e1  call    ?IsUncompressedWaveFormatEx@@YAHPEBUtWAVEFORMATEX@@@Z; IsUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x1801769e6  test    eax, eax
0x1801769e8  jnz     short loc_1801769F6
0x1801769ea  cmp     [rcx+0Ch], r12w
0x1801769ef  jnz     short loc_1801769F6
0x1801769f1  mov     [rcx+0Ch], r14w
0x1801769f6  lea     rcx, [rsi+2A8h]; lpCriticalSection
0x1801769fd  call    cs:__imp_EnterCriticalSection
0x180176a04  nop     dword ptr [rax+rax+00h]
0x180176a09  lea     rbx, [rsi-20h]
0x180176a0d  cmp     [rbx+1528h], r12d
0x180176a14  jz      loc_180176D1C
0x180176a1a  mov     [rsi+0E0h], r12d
0x180176a21  mov     r14d, 1
0x180176a27  mov     rcx, [rsi+19D8h]; this
0x180176a2e  test    rcx, rcx
0x180176a31  jz      short loc_180176A3A
0x180176a33  xor     edx, edx; unsigned __int16 *
0x180176a35  call    ?SetPendingStreamingEndpointId@CMMNotificationClient@@QEAAXPEBG@Z; CMMNotificationClient::SetPendingStreamingEndpointId(ushort const *)
0x180176a3a  mov     rcx, [rsi+19A8h]
0x180176a41  test    rcx, rcx
0x180176a44  jz      short loc_180176A65
0x180176a46  mov     rax, [rcx]
0x180176a49  lea     rdx, MF_TELEMETRY_EVENT_RATE_EXCEEDED_LIMIT
0x180176a50  mov     rax, [rax+140h]
0x180176a57  call    cs:__guard_dispatch_icall_fptr
0x180176a5d  test    eax, eax
0x180176a5f  jnz     loc_180176C12
0x180176a65  mov     rcx, [rbp+1C0h+ppWF]; this
0x180176a69  test    rcx, rcx
0x180176a6c  jz      loc_180176C16
0x180176a72  mov     r9, [rsi+8]
0x180176a76  test    r9, r9
0x180176a79  jz      loc_180176C16
0x180176a7f  mov     rdx, [rsi+300h]; struct tWAVEFORMATEX *
0x180176a86  test    rdx, rdx
0x180176a89  jz      loc_180176C16
0x180176a8f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180176a96  movdqu  [rbp+1C0h+var_48], xmm0
0x180176a9e  call    ?IsSpatialType@CAudioClientManager@@QEAAHPEBUtWAVEFORMATEX@@@Z; CAudioClientManager::IsSpatialType(tWAVEFORMATEX const *)
0x180176aa3  mov     rdx, rcx; struct tWAVEFORMATEX *
0x180176aa6  mov     ebx, eax
0x180176aa8  call    ?IsSpatialType@CAudioClientManager@@QEAAHPEBUtWAVEFORMATEX@@@Z; CAudioClientManager::IsSpatialType(tWAVEFORMATEX const *)
0x180176aad  mov     rdx, [r9]
0x180176ab0  lea     r8, [rbp+1C0h+var_48]
0x180176ab7  mov     edi, eax
0x180176ab9  mov     rcx, r9
0x180176abc  mov     rax, [rdx+50h]
0x180176ac0  lea     rdx, MF_MT_SUBTYPE
0x180176ac7  call    cs:__guard_dispatch_icall_fptr
0x180176acd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180176ad4  mov     rcx, [rsi+19A8h]
0x180176adb  mov     r8d, r12d
0x180176ade  movdqu  xmmword ptr [rbp+1C0h+pvar], xmm0
0x180176ae6  test    rcx, rcx
0x180176ae9  jz      short loc_180176B27
0x180176aeb  mov     rax, [rcx]
0x180176aee  lea     rdx, [rbp+1C0h+var_58]
0x180176af5  mov     rax, [rax+118h]
0x180176afc  call    cs:__guard_dispatch_icall_fptr
0x180176b02  mov     rcx, [rsi+19A8h]
0x180176b09  movups  xmm0, xmmword ptr [rax]
0x180176b0c  movdqu  xmmword ptr [rbp+1C0h+pvar], xmm0
0x180176b14  mov     rax, [rcx]
0x180176b17  mov     rax, [rax+128h]
0x180176b1e  call    cs:__guard_dispatch_icall_fptr
0x180176b24  mov     r8d, eax
0x180176b27  mov     ecx, cs:dword_1803A6650
0x180176b2d  cmp     ecx, 5
0x180176b30  jbe     loc_180176C12
0x180176b36  mov     rdx, 400000000000h
0x180176b40  lea     rcx, dword_1803A6650
0x180176b47  call    _tlgKeywordOn
0x180176b4c  test    al, al
0x180176b4e  jz      loc_180176C12
0x180176b54  mov     rcx, [rbp+1C0h+ppWF]
0x180176b58  lea     rdx, unk_180393C37
0x180176b5f  mov     [rbp+1C0h+var_240], r13d
0x180176b63  mov     [rbp+1C0h+var_214], edi
0x180176b66  mov     [rbp+1C0h+var_210], ebx
0x180176b69  movzx   eax, word ptr [rcx+0Eh]
0x180176b6d  mov     [rbp+1C0h+var_20C], eax
0x180176b70  movzx   eax, word ptr [rcx+0Ch]
0x180176b74  mov     [rbp+1C0h+var_208], eax
0x180176b77  mov     eax, [rcx+8]
0x180176b7a  mov     [rbp+1C0h+var_204], eax
0x180176b7d  mov     eax, [rcx+4]
0x180176b80  mov     [rbp+1C0h+var_200], eax
0x180176b83  movzx   eax, word ptr [rcx+2]
0x180176b87  mov     dword ptr [rbp+1C0h+var_220], eax
0x180176b8a  lea     rax, [rbp+1C0h+var_48]
0x180176b91  mov     [rbp+1C0h+var_1F8], rax
0x180176b95  lea     rax, [rbp+1C0h+pvar]
0x180176b9c  mov     [rbp+1C0h+var_58], rax
0x180176ba3  lea     rax, [rbp+1C0h+var_240]
0x180176ba7  mov     [rsp+2C0h+var_250], rax
0x180176bac  lea     rax, [rbp+1C0h+var_214]
0x180176bb0  mov     [rsp+2C0h+var_258], rax
0x180176bb5  lea     rax, [rbp+1C0h+var_210]
0x180176bb9  mov     [rsp+2C0h+var_260], rax
0x180176bbe  lea     rax, [rbp+1C0h+var_20C]
0x180176bc2  mov     [rsp+2C0h+var_268], rax
0x180176bc7  lea     rax, [rbp+1C0h+var_208]
0x180176bcb  mov     [rsp+2C0h+var_270], rax
0x180176bd0  lea     rax, [rbp+1C0h+var_204]
0x180176bd4  mov     [rsp+2C0h+var_278], rax
0x180176bd9  lea     rax, [rbp+1C0h+var_200]
0x180176bdd  mov     [rsp+2C0h+var_280], rax
0x180176be2  lea     rax, [rbp+1C0h+var_220]
0x180176be6  mov     [rsp+2C0h+var_288], rax
0x180176beb  lea     rax, [rbp+1C0h+var_1F8]
0x180176bef  mov     [rsp+2C0h+var_290], rax
0x180176bf4  lea     rax, [rbp+1C0h+var_228]
0x180176bf8  mov     qword ptr [rsp+2C0h+var_298], rax
0x180176bfd  lea     rax, [rbp+1C0h+var_58]
0x180176c04  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x180176c09  mov     dword ptr [rbp+1C0h+var_228], r8d
0x180176c0d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U1@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@344444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180176c12  mov     rcx, [rbp+1C0h+ppWF]; pv
0x180176c16  call    cs:__imp_CoTaskMemFree
0x180176c1d  nop     dword ptr [rax+rax+00h]
0x180176c22  lea     rcx, [rsi+2A8h]; lpCriticalSection
0x180176c29  call    cs:__imp_LeaveCriticalSection
0x180176c30  nop     dword ptr [rax+rax+00h]
0x180176c35  cmp     [rsi+0E0h], r12d
0x180176c3c  jnz     short loc_180176C94
0x180176c3e  cmp     [rsi+1508h], r12d
0x180176c45  jz      short loc_180176C81
0x180176c47  cmp     cs:byte_1803CECE9, 10h
0x180176c4e  jb      short loc_180176C70
0x180176c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180176c57  lea     r9, [rsi-20h]
0x180176c5b  mov     edx, 0EBh
0x180176c60  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180176c67  mov     rcx, [rcx+38h]
0x180176c6b  call    WPP_SF_q
0x180176c70  lea     rcx, [rsi-20h]
0x180176c74  mov     edx, 5
0x180176c79  call    ?InvalidateInternalStream@CAudStreamSink@@IEAAJW4AudioSessionEvent@@@Z; CAudStreamSink::InvalidateInternalStream(AudioSessionEvent)
0x180176c7e  mov     r13d, eax
0x180176c81  mov     rcx, [rsi+14D8h]; hEvent
0x180176c88  call    cs:__imp_SetEvent
0x180176c8f  nop     dword ptr [rax+rax+00h]
0x180176c94  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, r14b
0x180176c9b  jz      short loc_180176CB7
0x180176c9d  lea     r8, [rsi-20h]
0x180176ca1  mov     r9d, r13d
0x180176ca4  lea     rdx, AudStreamSink_SetMediaType_Exit
0x180176cab  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x180176cb2  call    McTemplateU0pq_EventWriteTransfer
0x180176cb7  cmp     cs:byte_1803CECE9, 8
0x180176cbe  jb      short loc_180176CE5
0x180176cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180176cc7  lea     r9, [rsi-20h]
0x180176ccb  mov     edx, 0ECh
0x180176cd0  mov     [rsp+2C0h+var_2A0], r13d
0x180176cd5  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180176cdc  mov     rcx, [rcx+38h]
0x180176ce0  call    WPP_SF_qD
0x180176ce5  lea     rcx, [rbp+1C0h+var_230]; this
0x180176ce9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180176cee  mov     eax, r13d
  ... truncated ...
```
