# CAudStreamSink::CheckMediaType(IMFMediaType *)

- ea: `0x18007cdd0`
- end: `0x18007d748`
- name: `?CheckMediaType@CAudStreamSink@@UEAAJPEAUIMFMediaType@@@Z`
- size: `2424`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000f278`
- `0x18002c9ac`
- `0x18002fee0`
- `0x18003a41c`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18005a3d4`
- `0x18006b388`
- `0x18007af38`
- `0x18007cb1c`
- `0x18007cdd0`
- `0x18007d750`
- `0x18007df8c`
- `0x180091eb0`
- `0x180092630`
- `0x18009302c`
- `0x1800bb904`
- `0x1800ec0e0`
- `0x180164a4c`
- `0x18019ca74`
- `0x18023e1a0`
- `0x180258480`
- `0x1802de980`
- `0x18031e0d8`
- `0x180344cd8`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ceee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007ceee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d493`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d284`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007d284`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d6ab`
- `MFPlat!FormatTagFromWfx` at `0x18007d216`
- `MFPlat!FormatTagFromWfx` at `0x18007d216`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18007d1c5`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18007d1c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cfaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d06d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d12b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d4c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007cfaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d06d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d12b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007d4c1`

## string_xrefs

- `0x18007ce25`: `CAudStreamSink::CheckMediaType`
- `0x18007d00d`: `CAudStreamSink::CheckMediaType`
- `0x18007d0cb`: `CAudStreamSink::CheckMediaType`
- `0x18007d189`: `CAudStreamSink::CheckMediaType`
- `0x18007d1de`: `CAudStreamSink::CheckMediaType`
- `0x18007d51f`: `CAudStreamSink::CheckMediaType`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::CheckMediaType(CAudStreamSink *this, struct IMFMediaType *a2)
{
  IMFMediaType *v2; // r14
  int v4; // esi
  int v5; // r15d
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v10; // ebx
  __int128 *v11; // rax
  __int128 v12; // xmm0
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  WORD cbSize; // bx
  WORD wBitsPerSample; // di
  WORD nBlockAlign; // si
  DWORD nAvgBytesPerSec; // r14d
  DWORD nSamplesPerSec; // r15d
  WORD nChannels; // r12
  unsigned __int16 v35; // ax
  int v36; // ecx
  __int64 v37; // rcx
  CAudioClientManager *v38; // rcx
  const struct tWAVEFORMATEX *v39; // rdx
  unsigned int v40; // r8d
  int v41; // r9d
  int IsSpatialFormatSupported; // eax
  CAudioClientManager *v43; // rcx
  __int64 v44; // r14
  unsigned int i; // edi
  __int64 (__fastcall *v46)(__int64, __int128 *, PROPVARIANT *); // rax
  int v47; // eax
  int v48; // edi
  int IsSpatialType; // esi
  CAudioClientManager *v50; // rcx
  int v51; // edi
  unsigned __int8 v52; // al
  __int64 v53; // rdx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  const char *String; // rax
  const char *v58; // rax
  __int64 v59; // rdx
  int v60; // edx
  int v61; // ecx
  _BYTE v63[8]; // [rsp+50h] [rbp-B0h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+60h] [rbp-A0h] BYREF
  UINT32 pcbSize; // [rsp+64h] [rbp-9Ch] BYREF
  struct IMFMediaType *v67; // [rsp+68h] [rbp-98h]
  _BYTE v68[192]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v69[192]; // [rsp+130h] [rbp+30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v71; // [rsp+200h] [rbp+100h]
  GUID Buf2; // [rsp+208h] [rbp+108h] BYREF

  v67 = a2;
  v2 = a2;
  ppWF = 0;
  pcbSize = 0;
  v4 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  LOBYTE(v5) = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v63, "CAudStreamSink::CheckMediaType", 2847);
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v11 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**((_QWORD **)this + 825) + 280LL))(
                        *((_QWORD *)this + 825),
                        pvar);
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v12 = *v11;
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    *((_OWORD *)ThreadRelativeContext + 125) = v12;
  }
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
  {
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_CheckMediaType_Enter,
      this);
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( *((_DWORD *)this + 64) )
  {
    if ( !WaitForSingleObject(*((HANDLE *)this + 671), 0) )
      goto LABEL_10;
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  if ( *((_DWORD *)this + 1354) )
  {
LABEL_10:
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        188,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        *((_DWORD *)this + 64),
        *((_DWORD *)this + 1354));
    goto LABEL_102;
  }
  if ( *((_DWORD *)this + 1372) )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        189,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        *((_DWORD *)this + 1372));
    *((_DWORD *)this + 1372) = 0;
    goto LABEL_102;
  }
  if ( !*((_QWORD *)this + 829) )
  {
    v4 = -1072875850;
    if ( !v8 )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
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
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v14 + 499) != -1072875850 )
        CallStackContext::TraceFailure(v14, "CAudStreamSink::CheckMediaType", 2875, -1072875850);
    }
    if ( g_wppLevels )
    {
      v15 = 190;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this, v4);
      goto LABEL_102;
    }
    goto LABEL_102;
  }
  v4 = ((__int64 (__fastcall *)(IMFMediaType *, GUID *))v2->lpVtbl->GetMajorType)(v2, &Buf2);
  if ( v4 >= 0 )
  {
    if ( memcmp_0(&MFMediaType_Audio, &Buf2, 0x10u) )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      v4 = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v25, "CAudStreamSink::CheckMediaType", 2884, -1072875852);
      }
      if ( !g_wppLevels )
        goto LABEL_102;
      v26 = 192;
      goto LABEL_101;
    }
    if ( MFCreateWaveFormatExFromMFMediaType(v2, &ppWF, &pcbSize, 0) < 0 )
    {
      v54 = (__int64 *)CallStackTracing::s_wpInstance;
      v4 = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28);
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
        if ( *((_DWORD *)v56 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v56, "CAudStreamSink::CheckMediaType", 2905, -1072875852);
      }
      if ( !g_wppLevels )
        goto LABEL_102;
      v26 = 193;
LABEL_101:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        -1072875852);
      goto LABEL_102;
    }
    LogWaveFormat(0x10005u, v27, ppWF, "CAudStreamSink::CheckMediaType");
    if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    {
      cbSize = ppWF->cbSize;
      wBitsPerSample = ppWF->wBitsPerSample;
      nBlockAlign = ppWF->nBlockAlign;
      nAvgBytesPerSec = ppWF->nAvgBytesPerSec;
      nSamplesPerSec = ppWF->nSamplesPerSec;
      nChannels = ppWF->nChannels;
      v35 = FormatTagFromWfx(ppWF);
      McTemplateU0pqhqqhhh_EventWriteTransfer(
        v36,
        (unsigned int)&AudStreamSink_WaveFormat,
        (_DWORD)this,
        v35,
        nChannels,
        nSamplesPerSec,
        nAvgBytesPerSec,
        nBlockAlign,
        wBitsPerSample,
        cbSize);
      v2 = v67;
    }
    if ( !(unsigned int)IsUncompressedWaveFormatEx(ppWF) && !*(_WORD *)(v37 + 12) )
      *(_WORD *)(v37 + 12) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
    if ( (unsigned int)CAudioClientManager::IsSpatialType(v38, ppWF) )
      IsSpatialFormatSupported = CAudioClientManager::IsSpatialFormatSupported(
                                   *((CAudioClientManager **)this + 842),
                                   v2,
                                   v39);
    else
      IsSpatialFormatSupported = CAudStreamSink::IsFormatSupported(this, v39, v40, v41);
    v44 = *((_QWORD *)this + 5);
    v5 = IsSpatialFormatSupported;
    if ( !v44 || *((_DWORD *)this + 64) || *((_DWORD *)this + 1354) )
    {
LABEL_89:
      v4 = v5;
    }
    else
    {
      v4 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xA )
        {
          v48 = 1;
          goto LABEL_72;
        }
        v65 = 0;
        v71 = 0;
        v46 = *(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v44 + 24LL);
        *(_OWORD *)pvar = 0;
        v47 = v46(v44, &xmmword_1803CF3D0[i], pvar);
        if ( v47 != -1072875802 )
        {
          if ( v47 < 0 )
          {
            CMFPropVariant::Clear(pvar);
            goto LABEL_74;
          }
          v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *, PROPVARIANT *, int *))v67->lpVtbl->CompareItem)(
                 v67,
                 &xmmword_1803CF3D0[i],
                 pvar,
                 &v65);
          if ( v4 < 0 || !v65 )
            break;
        }
        CMFPropVariant::Clear(pvar);
      }
      v48 = 0;
      CMFPropVariant::Clear(pvar);
LABEL_72:
      if ( v4 < 0 || !v48 )
      {
LABEL_74:
        if ( v5 < 0 )
          goto LABEL_89;
        if ( *((_DWORD *)this + 1799) )
        {
          IsSpatialType = CAudioClientManager::IsSpatialType(v43, ppWF);
          v51 = CAudioClientManager::IsSpatialType(v50, *((const struct tWAVEFORMATEX **)this + 100));
          v52 = (unsigned __int8)byte_1803CECE9;
          if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          {
            WPP_SF_qddd(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              194,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              this,
              IsSpatialType,
              v51,
              *((_DWORD *)this + 1826));
            v52 = (unsigned __int8)byte_1803CECE9;
          }
          if ( !*((_DWORD *)this + 1826) )
            goto LABEL_81;
          if ( IsSpatialType )
          {
            if ( v51 )
            {
LABEL_81:
              v4 = -1072875778;
              if ( v52 < 8u )
                goto LABEL_90;
              v53 = 196;
              goto LABEL_83;
            }
          }
          else if ( !v51 )
          {
            goto LABEL_81;
          }
          v4 = v5;
          if ( v52 >= 8u )
          {
            v53 = 195;
LABEL_83:
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), v53, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
          }
        }
        else
        {
          v4 = v5;
          if ( (unsigned __int8)byte_1803CECE9 >= 8u )
          {
            v53 = 197;
            goto LABEL_83;
          }
        }
      }
    }
LABEL_90:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
    v2 = v67;
    goto LABEL_102;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v4 )
      CallStackContext::TraceFailure(v20, "CAudStreamSink::CheckMediaType", 2880, v4);
  }
  if ( g_wppLevels )
  {
    v15 = 191;
    goto LABEL_27;
  }
LABEL_102:
  CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v69, *((struct IMFAttributes **)this + 5));
  CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v68, (struct IMFAttributes *)v2);
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
  {
    String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v69, 0);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      198,
      (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      (_DWORD)this,
      (__int64)String);
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    {
      v58 = CMFAttributesTrace::GetString((CMFAttributesTrace *)v68, 0);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        199,
        (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (_DWORD)this,
        (__int64)v58);
    }
  }
  CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v68);
  CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v69);
  if ( v4 == -2004287486 && *((_DWORD *)this + 1823) )
  {
    if ( (int)CAudioClientManager::IsFormatSupportedShallow(*((CAudioClientManager **)this + 842), v2) < 0 )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          201,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          this,
          -2004287486);
    }
    else
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          200,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          this,
          -2004287486);
      *((_DWORD *)this + 1798) = 1;
      v4 = CAudStreamSink::QueueAudioSessionChangedEvent(this, v59, 8, 1);
    }
  }
  CoTaskMemFree(ppWF);
  ppWF = 0;
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 202, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this, v4);
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pitqq_EventWriteTransfer(v61, v60, (_DWORD)this, *((_QWORD *)this + 5), *((_DWORD *)this + 64), v5, v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v63);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007cdd0  mov     [rsp-8+arg_10], rbx
0x18007cdd5  push    rbp
0x18007cdd6  push    rsi
0x18007cdd7  push    rdi
0x18007cdd8  push    r12
0x18007cdda  push    r13
0x18007cddc  push    r14
0x18007cdde  push    r15
0x18007cde0  lea     rbp, [rsp-120h]
0x18007cde8  sub     rsp, 220h
0x18007cdef  mov     rax, cs:__security_cookie
0x18007cdf6  xor     rax, rsp
0x18007cdf9  mov     [rbp+150h+var_38], rax
0x18007ce00  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18007ce07  xor     r12d, r12d
0x18007ce0a  mov     [rsp+250h+var_1E8], rdx
0x18007ce0f  mov     r14, rdx
0x18007ce12  mov     [rsp+250h+ppWF], r12
0x18007ce17  mov     r13, rcx
0x18007ce1a  mov     [rsp+250h+pcbSize], r12d
0x18007ce1f  mov     r8d, 0B1Fh; int
0x18007ce25  lea     rdx, aCaudstreamsink_30; "CAudStreamSink::CheckMediaType"
0x18007ce2c  lea     rcx, [rsp+250h+var_200]; this
0x18007ce31  mov     esi, r12d
0x18007ce34  movdqu  [rbp+150h+Buf2], xmm0
0x18007ce3c  mov     r15d, r12d
0x18007ce3f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007ce44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18007ce4b  cmp     [rcx+8], r12b
0x18007ce4f  jz      short loc_18007CEB1
0x18007ce51  cmp     [r13+19C8h], r12
0x18007ce58  jz      short loc_18007CEB1
0x18007ce5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ce5f  mov     rcx, [r13+19C8h]
0x18007ce66  mov     rdi, rax
0x18007ce69  mov     rax, [rcx]
0x18007ce6c  mov     rax, [rax+128h]
0x18007ce73  call    cs:__guard_dispatch_icall_fptr
0x18007ce79  mov     rcx, [r13+19C8h]
0x18007ce80  lea     rdx, [rbp+150h+pvar]
0x18007ce87  mov     ebx, eax
0x18007ce89  mov     rax, [rcx]
0x18007ce8c  mov     rax, [rax+118h]
0x18007ce93  call    cs:__guard_dispatch_icall_fptr
0x18007ce99  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cea0  movups  xmm0, xmmword ptr [rax]
0x18007cea3  mov     [rdi+7E0h], ebx
0x18007cea9  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18007ceb1  mov     edi, 1
0x18007ceb6  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, dil
0x18007cebd  jz      short loc_18007CEDC
0x18007cebf  mov     r8, r13
0x18007cec2  lea     rdx, AudStreamSink_CheckMediaType_Enter
0x18007cec9  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x18007ced0  call    McTemplateU0p_EventWriteTransfer
0x18007ced5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cedc  cmp     [r13+100h], r12d
0x18007cee3  jz      short loc_18007CF05
0x18007cee5  mov     rcx, [r13+14F8h]; hHandle
0x18007ceec  xor     edx, edx; dwMilliseconds
0x18007ceee  call    cs:__imp_WaitForSingleObject
0x18007cef5  nop     dword ptr [rax+rax+00h]
0x18007cefa  test    eax, eax
0x18007cefc  jz      short loc_18007CF0E
0x18007cefe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cf05  cmp     [r13+1528h], r12d
0x18007cf0c  jz      short loc_18007CF55
0x18007cf0e  cmp     cs:byte_1803CECE9, 8
0x18007cf15  jb      loc_18007D560
0x18007cf1b  mov     eax, [r13+1528h]
0x18007cf22  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18007cf29  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf30  mov     edx, 0BCh
0x18007cf35  mov     [rsp+250h+var_228], eax
0x18007cf39  mov     r9, r13
0x18007cf3c  mov     eax, [r13+100h]
0x18007cf43  mov     dword ptr [rsp+250h+var_230], eax
0x18007cf47  mov     rcx, [rcx+38h]
0x18007cf4b  call    WPP_SF_qDD
0x18007cf50  jmp     loc_18007D560
0x18007cf55  mov     eax, [r13+1570h]
0x18007cf5c  test    eax, eax
0x18007cf5e  jz      short loc_18007CF98
0x18007cf60  cmp     cs:byte_1803CECE9, 8
0x18007cf67  jb      short loc_18007CF8C
0x18007cf69  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cf70  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18007cf77  mov     edx, 0BDh
0x18007cf7c  mov     dword ptr [rsp+250h+var_230], eax
0x18007cf80  mov     r9, r13
0x18007cf83  mov     rcx, [rcx+38h]
0x18007cf87  call    WPP_SF_qD
0x18007cf8c  mov     [r13+1570h], r12d
0x18007cf93  jmp     loc_18007D560
0x18007cf98  cmp     [r13+19E8h], r12
0x18007cf9f  jnz     loc_18007D03D
0x18007cfa5  mov     esi, 0C00D36B6h
0x18007cfaa  test    rcx, rcx
0x18007cfad  jnz     short loc_18007CFF7
0x18007cfaf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007cfb6  nop     dword ptr [rax+rax+00h]
0x18007cfbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cfc2  mov     rcx, rax
0x18007cfc5  test    rax, rax
0x18007cfc8  jz      short loc_18007CFE9
0x18007cfca  mov     rax, [rax]
0x18007cfcd  mov     edx, 7F0h
0x18007cfd2  mov     rax, [rax+8]
0x18007cfd6  call    cs:__guard_dispatch_icall_fptr
0x18007cfdc  test    eax, eax
0x18007cfde  jz      short loc_18007CFE9
0x18007cfe0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cfe7  jmp     short loc_18007CFF7
0x18007cfe9  lea     rcx, qword_1803CE250; this
0x18007cff0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007cff7  cmp     [rcx+8], r12b
0x18007cffb  jz      short loc_18007D022
0x18007cffd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007d002  cmp     [rax+7CCh], esi
0x18007d008  jz      short loc_18007D022
0x18007d00a  mov     r9d, esi; int
0x18007d00d  lea     rdx, aCaudstreamsink_30; "CAudStreamSink::CheckMediaType"
0x18007d014  mov     r8d, 0B3Bh; int
0x18007d01a  mov     rcx, rax; this
0x18007d01d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007d022  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007d029  jb      loc_18007D560
0x18007d02f  mov     edx, 0BEh
0x18007d034  mov     dword ptr [rsp+250h+var_230], esi
0x18007d038  jmp     loc_18007D546
0x18007d03d  mov     rax, [r14]
0x18007d040  lea     rdx, [rbp+150h+Buf2]
0x18007d047  mov     rcx, r14
0x18007d04a  mov     rax, [rax+108h]
0x18007d051  call    cs:__guard_dispatch_icall_fptr
0x18007d057  mov     esi, eax
0x18007d059  test    eax, eax
0x18007d05b  jns     loc_18007D0F7
0x18007d061  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d068  test    rcx, rcx
0x18007d06b  jnz     short loc_18007D0B5
0x18007d06d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d074  nop     dword ptr [rax+rax+00h]
0x18007d079  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d080  mov     rcx, rax
0x18007d083  test    rax, rax
0x18007d086  jz      short loc_18007D0A7
0x18007d088  mov     rax, [rax]
0x18007d08b  mov     edx, 7F0h
0x18007d090  mov     rax, [rax+8]
0x18007d094  call    cs:__guard_dispatch_icall_fptr
0x18007d09a  test    eax, eax
0x18007d09c  jz      short loc_18007D0A7
0x18007d09e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d0a5  jmp     short loc_18007D0B5
0x18007d0a7  lea     rcx, qword_1803CE250; this
0x18007d0ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d0b5  cmp     [rcx+8], r12b
0x18007d0b9  jz      short loc_18007D0E0
0x18007d0bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007d0c0  cmp     [rax+7CCh], esi
0x18007d0c6  jz      short loc_18007D0E0
0x18007d0c8  mov     r9d, esi; int
0x18007d0cb  lea     rdx, aCaudstreamsink_30; "CAudStreamSink::CheckMediaType"
0x18007d0d2  mov     r8d, 0B40h; int
0x18007d0d8  mov     rcx, rax; this
0x18007d0db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007d0e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007d0e7  jb      loc_18007D560
0x18007d0ed  mov     edx, 0BFh
0x18007d0f2  jmp     loc_18007D034
0x18007d0f7  mov     r8d, 10h; Size
0x18007d0fd  lea     rdx, [rbp+150h+Buf2]; Buf2
0x18007d104  lea     rcx, MFMediaType_Audio; Buf1
0x18007d10b  call    memcmp_0
0x18007d110  test    eax, eax
0x18007d112  jz      loc_18007D1B5
0x18007d118  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d11f  mov     ebx, 0C00D36B4h
0x18007d124  mov     esi, ebx
0x18007d126  test    rcx, rcx
0x18007d129  jnz     short loc_18007D173
0x18007d12b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007d132  nop     dword ptr [rax+rax+00h]
0x18007d137  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d13e  mov     rcx, rax
0x18007d141  test    rax, rax
0x18007d144  jz      short loc_18007D165
0x18007d146  mov     rax, [rax]
0x18007d149  mov     edx, 7F0h
0x18007d14e  mov     rax, [rax+8]
0x18007d152  call    cs:__guard_dispatch_icall_fptr
0x18007d158  test    eax, eax
0x18007d15a  jz      short loc_18007D165
0x18007d15c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d163  jmp     short loc_18007D173
0x18007d165  lea     rcx, qword_1803CE250; this
0x18007d16c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007d173  cmp     [rcx+8], r12b
0x18007d177  jz      short loc_18007D19E
0x18007d179  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007d17e  cmp     [rax+7CCh], ebx
0x18007d184  jz      short loc_18007D19E
0x18007d186  mov     r9d, ebx; int
0x18007d189  lea     rdx, aCaudstreamsink_30; "CAudStreamSink::CheckMediaType"
0x18007d190  mov     r8d, 0B44h; int
0x18007d196  mov     rcx, rax; this
0x18007d199  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007d19e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18007d1a5  jb      loc_18007D560
0x18007d1ab  mov     edx, 0C0h
0x18007d1b0  jmp     loc_18007D542
0x18007d1b5  xor     r9d, r9d; Flags
0x18007d1b8  lea     r8, [rsp+250h+pcbSize]; pcbSize
0x18007d1bd  lea     rdx, [rsp+250h+ppWF]; ppWF
0x18007d1c2  mov     rcx, r14; pMFType
0x18007d1c5  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18007d1cc  nop     dword ptr [rax+rax+00h]
0x18007d1d1  test    eax, eax
0x18007d1d3  js      loc_18007D4AE
0x18007d1d9  mov     r8, [rsp+250h+ppWF]; struct tWAVEFORMATEX *
0x18007d1de  lea     r9, aCaudstreamsink_30; "CAudStreamSink::CheckMediaType"
0x18007d1e5  mov     ecx, 10005h; unsigned int
0x18007d1ea  call    ?LogWaveFormat@@YAXKKPEBUtWAVEFORMATEX@@PEBD@Z; LogWaveFormat(ulong,ulong,tWAVEFORMATEX const *,char const *)
0x18007d1ef  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, dil
0x18007d1f6  jz      short loc_18007D261
0x18007d1f8  mov     rcx, [rsp+250h+ppWF]
0x18007d1fd  movzx   ebx, word ptr [rcx+10h]
0x18007d201  movzx   edi, word ptr [rcx+0Eh]
0x18007d205  movzx   esi, word ptr [rcx+0Ch]
0x18007d209  mov     r14d, [rcx+8]
0x18007d20d  mov     r15d, [rcx+4]
0x18007d211  movzx   r12d, word ptr [rcx+2]
0x18007d216  call    cs:__imp_?FormatTagFromWfx@@YAGPEBUtWAVEFORMATEX@@@Z; FormatTagFromWfx(tWAVEFORMATEX const *)
0x18007d21d  nop     dword ptr [rax+rax+00h]
0x18007d222  mov     [rsp+250h+var_208], bx
0x18007d227  lea     rdx, AudStreamSink_WaveFormat
0x18007d22e  mov     [rsp+250h+var_210], di
0x18007d233  mov     r8, r13
0x18007d236  mov     [rsp+250h+var_218], si
0x18007d23b  mov     [rsp+250h+var_220], r14d
0x18007d240  mov     [rsp+250h+var_228], r15d
0x18007d245  movzx   r9d, ax
0x18007d249  mov     word ptr [rsp+250h+var_230], r12w
0x18007d24f  call    McTemplateU0pqhqqhhh_EventWriteTransfer
0x18007d254  mov     r14, [rsp+250h+var_1E8]
0x18007d259  xor     r12d, r12d
0x18007d25c  lea     edi, [r12+1]
0x18007d261  mov     rcx, [rsp+250h+ppWF]; struct tWAVEFORMATEX *
0x18007d266  call    ?IsUncompressedWaveFormatEx@@YAHPEBUtWAVEFORMATEX@@@Z; IsUncompressedWaveFormatEx(tWAVEFORMATEX const *)
0x18007d26b  test    eax, eax
0x18007d26d  jnz     short loc_18007D27A
0x18007d26f  cmp     [rcx+0Ch], r12w
0x18007d274  jnz     short loc_18007D27A
0x18007d276  mov     [rcx+0Ch], di
0x18007d27a  lea     rbx, [r13+2C8h]
0x18007d281  mov     rcx, rbx; lpCriticalSection
0x18007d284  call    cs:__imp_EnterCriticalSection
0x18007d28b  nop     dword ptr [rax+rax+00h]
0x18007d290  mov     rdx, [rsp+250h+ppWF]; struct tWAVEFORMATEX *
0x18007d295  call    ?IsSpatialType@CAudioClientManager@@QEAAHPEBUtWAVEFORMATEX@@@Z; CAudioClientManager::IsSpatialType(tWAVEFORMATEX const *)
0x18007d29a  test    eax, eax
0x18007d29c  jz      short loc_18007D2B2
0x18007d29e  mov     rcx, [r13+1A50h]; this
0x18007d2a5  mov     r8, rdx; struct tWAVEFORMATEX *
0x18007d2a8  mov     rdx, r14; struct IMFMediaType *
0x18007d2ab  call    ?IsSpatialFormatSupported@CAudioClientManager@@QEAAJPEAUIMFMediaType@@PEBUtWAVEFORMATEX@@@Z; CAudioClientManager::IsSpatialFormatSupported(IMFMediaType *,tWAVEFORMATEX const *)
0x18007d2b0  jmp     short loc_18007D2BA
0x18007d2b2  mov     rcx, r13; this
0x18007d2b5  call    ?IsFormatSupported@CAudStreamSink@@QEAAJPEBUtWAVEFORMATEX@@KH@Z; CAudStreamSink::IsFormatSupported(tWAVEFORMATEX const *,ulong,int)
0x18007d2ba  mov     r14, [r13+28h]
0x18007d2be  mov     r15d, eax
0x18007d2c1  test    r14, r14
0x18007d2c4  jz      loc_18007D48D
0x18007d2ca  cmp     [r13+100h], r12d
0x18007d2d1  jnz     loc_18007D48D
0x18007d2d7  cmp     [r13+1528h], r12d
0x18007d2de  jnz     loc_18007D48D
0x18007d2e4  mov     esi, r12d
0x18007d2e7  mov     edi, r12d
0x18007d2ea  cmp     edi, 0Ah
0x18007d2ed  jnb     loc_18007D3AA
0x18007d2f3  xor     eax, eax
0x18007d2f5  mov     [rsp+250h+var_1F0], r12d
0x18007d2fa  mov     [rbp+150h+var_50], rax
0x18007d301  lea     rcx, xmmword_1803CF3D0
0x18007d308  mov     rax, [r14]
0x18007d30b  lea     r8, [rbp+150h+pvar]
0x18007d312  xorps   xmm0, xmm0
0x18007d315  mov     r12d, edi
0x18007d318  shl     r12, 4
0x18007d31c  add     r12, rcx
0x18007d31f  mov     rcx, r14
0x18007d322  mov     rax, [rax+18h]
0x18007d326  mov     rdx, r12
0x18007d329  movups  xmmword ptr [rbp+150h+pvar], xmm0
0x18007d330  call    cs:__guard_dispatch_icall_fptr
0x18007d336  cmp     eax, 0C00D36E6h
0x18007d33b  jz      short loc_18007D383
0x18007d33d  test    eax, eax
  ... truncated ...
```
