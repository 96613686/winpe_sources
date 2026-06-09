# FSSource::OnMediaSourceEvent(IMFAsyncResult *)

- ea: `0x18009cd78`
- end: `0x18009d87c`
- name: `?OnMediaSourceEvent@FSSource@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2820`
- prototype: `void __fastcall(FSSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009aaf0`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009608`
- `0x1800096f4`
- `0x180009b5c`
- `0x180017674`
- `0x180018998`
- `0x180022764`
- `0x18004d714`
- `0x18004da70`
- `0x1800530bc`
- `0x180073610`
- `0x180091b30`
- `0x18009cd78`
- `0x18009d884`
- `0x18009e0e0`
- `0x18009e24c`
- `0x1800a0600`
- `0x1800a6068`
- `0x1800a6aa0`
- `0x1800a6b78`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009d568`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009d568`
- `MFPlat!MFCreateMediaEvent` at `0x18009cf3b`
- `MFPlat!MFCreateMediaEvent` at `0x18009cf3b`

## string_xrefs

- `0x18009d0f2`: `MEUpdatedStream`
- `0x18009d5c9`: `MEVideoCaptureDeviceRemoved`

## pseudocode

```c
void __fastcall FSSource::OnMediaSourceEvent(FSSource *this, struct IMFAsyncResult *a2)
{
  char v2; // r13
  HRESULT v5; // eax
  int v6; // r14d
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  bool v10; // zf
  __int64 (__fastcall *v11)(__int64, struct IMFAsyncResult *, IMFMediaEvent **); // rax
  HRESULT v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  MediaEventType v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // edi
  MediaEventType v19; // esi
  char v20; // bl
  unsigned int v21; // eax
  __int64 v22; // rax
  const char *v23; // rcx
  unsigned int v24; // eax
  __int64 SourceTypeString; // rax
  int v26; // edx
  char v27; // si
  GuidTrace *v28; // rax
  const char *String; // rdi
  const char *v30; // rbx
  unsigned int v31; // eax
  __int64 v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // eax
  const char *v35; // rax
  __int64 v36; // r8
  unsigned int v37; // eax
  __int64 v38; // rax
  int v39; // edx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rax
  const char *v43; // rbx
  unsigned int v44; // eax
  __int64 v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rax
  int v50; // edx
  char v51[4]; // [rsp+40h] [rbp-C0h] BYREF
  char v52; // [rsp+44h] [rbp-BCh]
  MediaEventType met; // [rsp+48h] [rbp-B8h] BYREF
  char v54; // [rsp+4Ch] [rbp-B4h]
  IMFMediaEvent *ppEvent; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v58[32]; // [rsp+68h] [rbp-98h] BYREF
  GUID Buf1; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h]
  _DWORD v61[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h] BYREF
  int v63; // [rsp+B0h] [rbp-50h]

  v2 = 0;
  met = 0;
  *(_DWORD *)v51 = 0;
  ppEvent = 0;
  v57 = 0;
  v56 = 0;
  if ( a2 )
  {
    v5 = ((__int64 (__fastcall *)(struct IMFAsyncResult *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))a2->lpVtbl->GetState)(
           a2,
           &v57);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_124;
      v7 = 421;
      goto LABEL_4;
    }
    v5 = (**v57)(v57, &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66, &v56);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_124;
      v7 = 422;
      goto LABEL_4;
    }
    v52 = 0;
    v10 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(
                             &`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl,
                             v8,
                             v9) == 0;
    v11 = *(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, IMFMediaEvent **))(*(_QWORD *)v56 + 40LL);
    if ( v10 )
    {
      v5 = v11(v56, a2, &ppEvent);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 427;
        goto LABEL_4;
      }
      if ( !ppEvent )
      {
        v5 = -1072875845;
        v6 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 428;
        goto LABEL_4;
      }
      v5 = ((__int64 (__fastcall *)(IMFMediaEvent *, MediaEventType *))ppEvent->lpVtbl->GetType)(ppEvent, &met);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 429;
        goto LABEL_4;
      }
    }
    else
    {
      v12 = v11(v56, a2, &ppEvent);
      if ( v12 < 0 )
      {
        if ( v12 == -1072873822 )
        {
          v15 = 800;
        }
        else
        {
          v15 = 1;
          if ( v12 == -1072873821 )
            v15 = 801;
        }
        met = v15;
        *(_DWORD *)v51 = v12;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          WPP_SF_qdDD(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v14, this, v15, v12, v12);
          v15 = met;
          v12 = *(_DWORD *)v51;
        }
        v5 = MFCreateMediaEvent(v15, &GUID_00000000_0000_0000_0000_000000000000, v12, 0, &ppEvent);
        v6 = v5;
        if ( v5 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_124;
          v7 = 424;
          goto LABEL_4;
        }
        FSSource::SetAsyncStatus(this, *(int *)v51);
        v52 = 1;
        goto LABEL_41;
      }
      if ( !ppEvent )
      {
        v5 = -1072875845;
        v6 = -1072875845;
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 425;
        goto LABEL_4;
      }
      v5 = ((__int64 (__fastcall *)(IMFMediaEvent *, MediaEventType *))ppEvent->lpVtbl->GetType)(ppEvent, &met);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 426;
        goto LABEL_4;
      }
    }
    if ( ((int (__fastcall *)(IMFMediaEvent *, char *))ppEvent->lpVtbl->GetStatus)(ppEvent, v51) >= 0 )
    {
      v18 = *(_DWORD *)v51;
      if ( *(int *)v51 >= 0 )
        goto LABEL_42;
      FSSource::SetAsyncStatus(this, *(int *)v51);
    }
LABEL_41:
    v18 = *(_DWORD *)v51;
LABEL_42:
    v19 = met;
    v20 = 0;
    v54 = 0;
    if ( met <= 0xCF )
    {
      if ( met == 207 )
      {
        if ( (unsigned __int8)byte_18010EC4D < 8u )
          goto LABEL_58;
        v33 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
        SourceTypeString = FSSourceUtils::GetSourceTypeString(v33);
        v26 = 434;
        goto LABEL_57;
      }
      if ( met != 1 )
      {
        if ( met != 2 )
        {
          if ( met != 201 )
          {
            if ( met - 205 <= 1 )
            {
              if ( (unsigned __int8)byte_18010EC4D >= 8u )
              {
                v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
                v22 = FSSourceUtils::GetSourceTypeString(v21);
                v23 = "MENewStream";
                if ( v19 != 205 )
                  v23 = "MEUpdatedStream";
                WPP_SF_qssD(*((_QWORD *)WPP_GLOBAL_Control + 27), v22, (__int64)v23, v18);
              }
              v5 = FSSource::OnNewStream(this, ppEvent);
              v6 = v5;
              if ( v5 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_124;
                v7 = 431;
                goto LABEL_4;
              }
              goto LABEL_116;
            }
LABEL_81:
            if ( (unsigned __int8)byte_18010EC4D >= 8u )
            {
              v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
              FSSourceUtils::GetSourceTypeString(v34);
              v35 = MFTRACE_STRING_FROM_MET(v19);
              WPP_SF_qssD(*((_QWORD *)WPP_GLOBAL_Control + 27), v36, (__int64)v35, v18);
            }
            goto LABEL_116;
          }
          if ( (unsigned __int8)byte_18010EC4D < 8u )
          {
LABEL_58:
            v6 = 0;
            goto LABEL_116;
          }
          v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
          SourceTypeString = FSSourceUtils::GetSourceTypeString(v24);
          v26 = 432;
LABEL_57:
          WPP_SF_qsd(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v26,
            (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
            (_DWORD)this,
            SourceTypeString,
            v18);
          goto LABEL_58;
        }
        Buf1 = GUID_00000000_0000_0000_0000_000000000000;
        v5 = ((__int64 (__fastcall *)(IMFMediaEvent *, GUID *))ppEvent->lpVtbl->GetExtendedType)(ppEvent, &Buf1);
        v6 = v5;
        if ( v5 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_124;
          v7 = 442;
          goto LABEL_4;
        }
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v27 = v51[0];
          v28 = GuidTrace::GuidTrace((GuidTrace *)v58, &Buf1);
          String = GuidTrace::GetString(v28);
          v30 = MFTRACE_STRING_FROM_MET(met);
          v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
          v32 = FSSourceUtils::GetSourceTypeString(v31);
          WPP_SF_qsssD(*((_QWORD *)WPP_GLOBAL_Control + 27), v32, (__int64)v30, (__int64)String, v27);
          v20 = v54;
          v2 = 1;
        }
        if ( (v2 & 1) != 0 )
          FSString::~FSString((FSString *)v58);
        if ( !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_CUSTOM_EVENT, 0x10u)
          || !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_INITIALIZE, 0x10u)
          || !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_START, 0x10u)
          || !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_STOP, 0x10u)
          || !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_SOURCE_UNINITIALIZE, 0x10u)
          || !memcmp_0(&Buf1, &MF_FRAMESERVER_VCAMEVENT_EXTENDED_PIPELINE_SHUTDOWN, 0x10u) )
        {
          v5 = FSSource::QueueMediaEventNotification(this, ppEvent, 0, 4);
          v6 = v5;
          if ( v5 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_124;
            v7 = 444;
            goto LABEL_4;
          }
        }
LABEL_116:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(
                                &`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl,
                                v16,
                                v17) )
        {
          if ( v52 )
          {
            if ( v6 < 0 )
              goto LABEL_124;
          }
          else
          {
            v5 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v56 + 32LL))(
                   v56,
                   (char *)this + 24,
                   v56);
            v6 = v5;
            if ( v5 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_124;
              v7 = 446;
              goto LABEL_4;
            }
          }
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v56 + 32LL))(
                 v56,
                 (char *)this + 24,
                 v56);
          v6 = v5;
          if ( v5 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_124;
            v7 = 447;
            goto LABEL_4;
          }
        }
        v48 = *(_DWORD *)v51;
        if ( v20 || *(int *)v51 >= 0 )
          goto LABEL_127;
        goto LABEL_124;
      }
LABEL_96:
      if ( v18 >= 0 )
      {
        if ( v19 == 1 )
        {
          v18 = -1072875810;
          *(_DWORD *)v51 = -1072875810;
LABEL_103:
          if ( byte_18010EC4D )
          {
            v43 = "MEError";
            if ( v19 != 1 )
              v43 = "MEVideoCaptureDeviceRemoved";
            v44 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
            v45 = FSSourceUtils::GetSourceTypeString(v44);
            WPP_SF_qssD(*((_QWORD *)WPP_GLOBAL_Control + 27), v45, (__int64)v43, v18);
            v19 = met;
            v18 = *(_DWORD *)v51;
          }
          goto LABEL_107;
        }
        v18 = -1072873822;
        *(_DWORD *)v51 = -1072873822;
      }
      if ( v19 == 800 && v56 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 96LL))(v56);
        v19 = met;
        v18 = *(_DWORD *)v51;
      }
      goto LABEL_103;
    }
    if ( met == 800 )
      goto LABEL_96;
    if ( met == 801 )
    {
LABEL_107:
      if ( v18 >= 0 )
      {
        LOBYTE(v18) = -93;
        *(_DWORD *)v51 = -1072873821;
      }
      if ( v19 == 801 && byte_18010EC4D )
      {
        v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
        v47 = FSSourceUtils::GetSourceTypeString(v46);
        WPP_SF_qsd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          440,
          (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
          (_DWORD)this,
          v47,
          v18);
      }
      v5 = FSSource::QueueMediaEventNotification(this, ppEvent, 0, 0);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_124;
        v7 = 441;
        goto LABEL_4;
      }
      v20 = 1;
      goto LABEL_116;
    }
    if ( met != 950 )
    {
      if ( met != 10100 )
        goto LABEL_81;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl'::`2'::impl) )
      {
        (*(void (__fastcall **)(char *, IMFMediaEvent *))(*((_QWORD *)this + 2) + 24LL))((char *)this + 16, ppEvent);
        *(_DWORD *)v51 = 0;
        goto LABEL_116;
      }
    }
    v60 = 0;
    Buf1 = 0;
    if ( ((int (__fastcall *)(IMFMediaEvent *, GUID *))ppEvent->lpVtbl->GetValue)(ppEvent, &Buf1) < 0
      || LOWORD(Buf1.Data1) != 19 )
    {
      if ( byte_18010EC4D )
      {
        v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
        v42 = FSSourceUtils::GetSourceTypeString(v41);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          438,
          (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
          (_DWORD)this,
          v42);
      }
      goto LABEL_95;
    }
    if ( *(_DWORD *)Buf1.Data4 == 1 )
    {
      _InterlockedCompareExchange((volatile signed __int32 *)this + 82, 1, 0);
      if ( byte_18010EC4D )
      {
        v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
        v38 = FSSourceUtils::GetSourceTypeString(v37);
        v39 = 436;
LABEL_92:
        WPP_SF_qsd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v39,
          (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
          (_DWORD)this,
          v38,
          Buf1.Data4[0]);
      }
    }
    else
    {
      _InterlockedCompareExchange((volatile signed __int32 *)this + 82, 0, 1);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 32) + 24LL))(*((_QWORD *)this + 32));
        v38 = FSSourceUtils::GetSourceTypeString(v40);
        v39 = 437;
        goto LABEL_92;
      }
    }
LABEL_95:
    PropVariantClear((PROPVARIANT *)&Buf1);
    v19 = met;
    v18 = *(_DWORD *)v51;
    goto LABEL_96;
  }
  v5 = -1072875845;
  v6 = -1072875845;
  if ( g_wppLevels )
  {
    v7 = 420;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v5);
  }
LABEL_124:
  memset_0(&v62, 0, 0x208u);
  v49 = *(_QWORD *)this;
  v61[1] = 528;
  v61[0] = 1;
  v62 = (*(__int64 (__fastcall **)(FSSource *))(v49 + 536))(this);
  v50 = v6;
  if ( *(int *)v51 < 0 )
    v50 = *(_DWORD *)v51;
  v63 = v50;
  FSSource::SetAsyncStatus(this, v50);
  FSSource::QueueFSNotification(this, v61, 0, 0, 0);
  v48 = *(_DWORD *)v51;
LABEL_127:
  if ( v6 < 0 || v48 < 0 )
  {
    if ( byte_18010EC4D )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        448,
        &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
        this,
        v6,
        v48);
  }
  else if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 449, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v6);
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v56);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v57);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppEvent);
}

```

## disassembly

```asm
0x18009cd78  mov     [rsp-8+arg_10], rbx
0x18009cd7d  push    rbp
0x18009cd7e  push    rsi
0x18009cd7f  push    rdi
0x18009cd80  push    r12
0x18009cd82  push    r13
0x18009cd84  push    r14
0x18009cd86  push    r15
0x18009cd88  lea     rbp, [rsp-1C0h]
0x18009cd90  sub     rsp, 2C0h
0x18009cd97  mov     rax, cs:__security_cookie
0x18009cd9e  xor     rax, rsp
0x18009cda1  mov     [rbp+1F0h+var_40], rax
0x18009cda8  xor     r13d, r13d
0x18009cdab  lea     rdi, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x18009cdb2  mov     [rsp+2F0h+met], r13d
0x18009cdb7  mov     rbx, rdx
0x18009cdba  mov     [rsp+2F0h+met], r13d
0x18009cdbf  mov     r15, rcx
0x18009cdc2  mov     dword ptr [rsp+2F0h+var_2B0], r13d
0x18009cdc7  mov     [rsp+2F0h+var_2A0], r13
0x18009cdcc  mov     [rsp+2F0h+var_290], r13
0x18009cdd1  mov     [rsp+2F0h+var_298], r13
0x18009cdd6  test    rdx, rdx
0x18009cdd9  jnz     short loc_18009CE18
0x18009cddb  mov     eax, 0C00D36BBh
0x18009cde0  mov     r14d, eax
0x18009cde3  lea     r12d, [rdx+1]
0x18009cde7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009cdee  jb      loc_18009D71F
0x18009cdf4  mov     edx, 1A4h
0x18009cdf9  mov     r8, rdi
0x18009cdfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ce03  mov     r9, r15
0x18009ce06  mov     dword ptr [rsp+2F0h+ppEvent], eax
0x18009ce0a  mov     rcx, [rcx+10h]
0x18009ce0e  call    WPP_SF_qD
0x18009ce13  jmp     loc_18009D71F
0x18009ce18  mov     rax, [rdx]
0x18009ce1b  mov     rcx, rbx
0x18009ce1e  lea     rdx, [rsp+2F0h+var_290]
0x18009ce23  mov     rax, [rax+18h]
0x18009ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce2c  mov     r14d, eax
0x18009ce2f  test    eax, eax
0x18009ce31  jns     short loc_18009CE4D
0x18009ce33  mov     r12d, 1
0x18009ce39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009ce40  jb      loc_18009D71F
0x18009ce46  mov     edx, 1A5h
0x18009ce4b  jmp     short loc_18009CDF9
0x18009ce4d  mov     rcx, [rsp+2F0h+var_290]
0x18009ce52  lea     r8, [rsp+2F0h+var_298]
0x18009ce57  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x18009ce5e  mov     rax, [rcx]
0x18009ce61  mov     rax, [rax]
0x18009ce64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce69  mov     r14d, eax
0x18009ce6c  test    eax, eax
0x18009ce6e  jns     short loc_18009CE8D
0x18009ce70  mov     r12d, 1
0x18009ce76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009ce7d  jb      loc_18009D71F
0x18009ce83  mov     edx, 1A6h
0x18009ce88  jmp     loc_18009CDF9
0x18009ce8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl(void)'::`2'::impl
0x18009ce94  mov     [rsp+2F0h+var_2AC], r13b
0x18009ce99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(void)
0x18009ce9e  mov     rcx, [rsp+2F0h+var_298]
0x18009cea3  lea     r8, [rsp+2F0h+var_2A0]
0x18009cea8  test    al, al
0x18009ceaa  mov     esi, 321h
0x18009ceaf  mov     r12d, 1
0x18009ceb5  mov     rdx, rbx
0x18009ceb8  mov     rax, [rcx]
0x18009cebb  mov     rax, [rax+28h]
0x18009cebf  jz      loc_18009CFD4
0x18009cec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ceca  test    eax, eax
0x18009cecc  jns     loc_18009CF75
0x18009ced2  cmp     eax, 0C00D3EA2h
0x18009ced7  jnz     short loc_18009CEDE
0x18009ced9  lea     ecx, [rsi-1]
0x18009cedc  jmp     short loc_18009CEE9
0x18009cede  cmp     eax, 0C00D3EA3h
0x18009cee3  mov     ecx, r12d
0x18009cee6  cmovz   ecx, esi
0x18009cee9  mov     [rsp+2F0h+met], ecx
0x18009ceed  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x18009cef1  cmp     cs:byte_18010EC4D, 8
0x18009cef8  jb      short loc_18009CF24
0x18009cefa  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x18009cefe  mov     r9, r15
0x18009cf01  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x18009cf05  mov     dword ptr [rsp+2F0h+ppEvent], ecx
0x18009cf09  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cf10  mov     rcx, [rcx+0D8h]
0x18009cf17  call    WPP_SF_qdDD
0x18009cf1c  mov     ecx, [rsp+2F0h+met]; met
0x18009cf20  mov     eax, dword ptr [rsp+2F0h+var_2B0]
0x18009cf24  lea     rdx, [rsp+2F0h+var_2A0]
0x18009cf29  xor     r9d, r9d; pvValue
0x18009cf2c  mov     [rsp+2F0h+ppEvent], rdx; ppEvent
0x18009cf31  mov     r8d, eax; hrStatus
0x18009cf34  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18009cf3b  call    cs:__imp_MFCreateMediaEvent
0x18009cf41  mov     r14d, eax
0x18009cf44  test    eax, eax
0x18009cf46  jns     short loc_18009CF5F
0x18009cf48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009cf4f  jb      loc_18009D71F
0x18009cf55  mov     edx, 1A8h
0x18009cf5a  jmp     loc_18009CDF9
0x18009cf5f  mov     edx, dword ptr [rsp+2F0h+var_2B0]; int
0x18009cf63  mov     rcx, r15; this
0x18009cf66  call    ?SetAsyncStatus@FSSource@@IEAAXJ@Z; FSSource::SetAsyncStatus(long)
0x18009cf6b  mov     [rsp+2F0h+var_2AC], r12b
0x18009cf70  jmp     loc_18009D081
0x18009cf75  mov     rcx, [rsp+2F0h+var_2A0]
0x18009cf7a  test    rcx, rcx
0x18009cf7d  jnz     short loc_18009CF9E
0x18009cf7f  mov     eax, 0C00D36BBh
0x18009cf84  mov     r14d, eax
0x18009cf87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009cf8e  jb      loc_18009D71F
0x18009cf94  mov     edx, 1A9h
0x18009cf99  jmp     loc_18009CDF9
0x18009cf9e  mov     rax, [rcx]
0x18009cfa1  lea     rdx, [rsp+2F0h+met]
0x18009cfa6  mov     rax, [rax+108h]
0x18009cfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cfb2  mov     r14d, eax
0x18009cfb5  test    eax, eax
0x18009cfb7  jns     loc_18009D052
0x18009cfbd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009cfc4  jb      loc_18009D71F
0x18009cfca  mov     edx, 1AAh
0x18009cfcf  jmp     loc_18009CDF9
0x18009cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cfd9  mov     r14d, eax
0x18009cfdc  test    eax, eax
0x18009cfde  jns     short loc_18009CFF7
0x18009cfe0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009cfe7  jb      loc_18009D71F
0x18009cfed  mov     edx, 1ABh
0x18009cff2  jmp     loc_18009CDF9
0x18009cff7  mov     rcx, [rsp+2F0h+var_2A0]
0x18009cffc  test    rcx, rcx
0x18009cfff  jnz     short loc_18009D020
0x18009d001  mov     eax, 0C00D36BBh
0x18009d006  mov     r14d, eax
0x18009d009  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009d010  jb      loc_18009D71F
0x18009d016  mov     edx, 1ACh
0x18009d01b  jmp     loc_18009CDF9
0x18009d020  mov     rax, [rcx]
0x18009d023  lea     rdx, [rsp+2F0h+met]
0x18009d028  mov     rax, [rax+108h]
0x18009d02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d034  mov     r14d, eax
0x18009d037  test    eax, eax
0x18009d039  jns     short loc_18009D052
0x18009d03b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009d042  jb      loc_18009D71F
0x18009d048  mov     edx, 1ADh
0x18009d04d  jmp     loc_18009CDF9
0x18009d052  mov     rcx, [rsp+2F0h+var_2A0]
0x18009d057  lea     rdx, [rsp+2F0h+var_2B0]
0x18009d05c  mov     rax, [rcx]
0x18009d05f  mov     rax, [rax+118h]
0x18009d066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d06b  test    eax, eax
0x18009d06d  js      short loc_18009D081
0x18009d06f  mov     edi, dword ptr [rsp+2F0h+var_2B0]
0x18009d073  test    edi, edi
0x18009d075  jns     short loc_18009D085
0x18009d077  mov     edx, edi; int
0x18009d079  mov     rcx, r15; this
0x18009d07c  call    ?SetAsyncStatus@FSSource@@IEAAXJ@Z; FSSource::SetAsyncStatus(long)
0x18009d081  mov     edi, dword ptr [rsp+2F0h+var_2B0]
0x18009d085  mov     esi, [rsp+2F0h+met]
0x18009d089  xor     bl, bl
0x18009d08b  mov     eax, 0CFh
0x18009d090  mov     [rsp+2F0h+var_2A4], bl
0x18009d094  cmp     esi, eax
0x18009d096  ja      loc_18009D388
0x18009d09c  jz      loc_18009D357
0x18009d0a2  mov     eax, esi
0x18009d0a4  sub     eax, r12d
0x18009d0a7  jz      loc_18009D576
0x18009d0ad  sub     eax, r12d
0x18009d0b0  jz      loc_18009D1BF
0x18009d0b6  sub     eax, 0C7h
0x18009d0bb  jz      loc_18009D169
0x18009d0c1  sub     eax, 4
0x18009d0c4  jz      short loc_18009D0CF
0x18009d0c6  cmp     eax, r12d
0x18009d0c9  jnz     loc_18009D3B0
0x18009d0cf  cmp     cs:byte_18010EC4D, 8
0x18009d0d6  jb      short loc_18009D133
0x18009d0d8  mov     rcx, [r15+100h]
0x18009d0df  mov     rax, [rcx]
0x18009d0e2  mov     rax, [rax+18h]
0x18009d0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d0eb  mov     ecx, eax
0x18009d0ed  call    ?GetSourceTypeString@FSSourceUtils@@YAPEBDW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001@@@Z; FSSourceUtils::GetSourceTypeString(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001)
0x18009d0f2  lea     rdx, aMeupdatedstrea; "MEUpdatedStream"
0x18009d0f9  mov     dword ptr [rsp+2F0h+var_2C0], edi; char
0x18009d0fd  cmp     esi, 0CDh
0x18009d103  lea     rcx, aMenewstream; "MENewStream"
0x18009d10a  mov     r9, r15
0x18009d10d  cmovnz  rcx, rdx
0x18009d111  mov     edx, 1AEh
0x18009d116  mov     [rsp+2F0h+var_2C8], rcx; __int64
0x18009d11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d122  mov     [rsp+2F0h+ppEvent], rax; __int64
0x18009d127  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18009d12e  call    WPP_SF_qssD
0x18009d133  mov     rdx, [rsp+2F0h+var_2A0]; struct IMFMediaEvent *
0x18009d138  mov     rcx, r15; this
0x18009d13b  call    ?OnNewStream@FSSource@@IEAAJPEAUIMFMediaEvent@@@Z; FSSource::OnNewStream(IMFMediaEvent *)
0x18009d140  mov     r14d, eax
0x18009d143  test    eax, eax
0x18009d145  jns     loc_18009D6C1
0x18009d14b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009d152  jb      loc_18009D71F
0x18009d158  mov     edx, 1AFh
0x18009d15d  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x18009d164  jmp     loc_18009CDFC
0x18009d169  cmp     cs:byte_18010EC4D, 8
0x18009d170  jb      short loc_18009D1B7
0x18009d172  mov     rcx, [r15+100h]
0x18009d179  mov     rax, [rcx]
0x18009d17c  mov     rax, [rax+18h]
0x18009d180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d185  mov     ecx, eax
0x18009d187  call    ?GetSourceTypeString@FSSourceUtils@@YAPEBDW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001@@@Z; FSSourceUtils::GetSourceTypeString(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001)
0x18009d18c  mov     edx, 1B0h
0x18009d191  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d198  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x18009d19f  mov     dword ptr [rsp+2F0h+var_2C8], edi
0x18009d1a3  mov     r9, r15
0x18009d1a6  mov     [rsp+2F0h+ppEvent], rax
0x18009d1ab  mov     rcx, [rcx+0D8h]
0x18009d1b2  call    WPP_SF_qsd
0x18009d1b7  xor     r14d, r14d
0x18009d1ba  jmp     loc_18009D6C1
0x18009d1bf  mov     rcx, [rsp+2F0h+var_2A0]
0x18009d1c4  lea     rdx, [rbp+1F0h+Buf1]
0x18009d1c8  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009d1cf  movdqu  [rbp+1F0h+Buf1], xmm0
0x18009d1d4  mov     rax, [rcx]
0x18009d1d7  mov     rax, [rax+110h]
0x18009d1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d1e3  mov     r14d, eax
0x18009d1e6  test    eax, eax
0x18009d1e8  jns     short loc_18009D201
0x18009d1ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18009d1f1  jb      loc_18009D71F
0x18009d1f7  mov     edx, 1BAh
0x18009d1fc  jmp     loc_18009D15D
0x18009d201  cmp     cs:byte_18010EC4D, 8
0x18009d208  jb      short loc_18009D27D
0x18009d20a  mov     esi, dword ptr [rsp+2F0h+var_2B0]
0x18009d20e  lea     rdx, [rbp+1F0h+Buf1]; struct _GUID *
0x18009d212  lea     rcx, [rsp+2F0h+var_288]; this
0x18009d217  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18009d21c  mov     rcx, rax; this
0x18009d21f  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18009d224  mov     ecx, [rsp+2F0h+met]; unsigned int
0x18009d228  mov     rdi, rax
0x18009d22b  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x18009d230  mov     rcx, [r15+100h]
0x18009d237  mov     rbx, rax
0x18009d23a  mov     rdx, [rcx]
0x18009d23d  mov     rax, [rdx+18h]
0x18009d241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d246  mov     ecx, eax
0x18009d248  call    ?GetSourceTypeString@FSSourceUtils@@YAPEBDW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001@@@Z; FSSourceUtils::GetSourceTypeString(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0001)
0x18009d24d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d254  mov     r9, r15
0x18009d257  mov     dword ptr [rsp+2F0h+var_2B8], esi; char
0x18009d25b  mov     qword ptr [rsp+2F0h+var_2C0], rdi; __int64
0x18009d260  mov     [rsp+2F0h+var_2C8], rbx; __int64
0x18009d265  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18009d26c  mov     [rsp+2F0h+ppEvent], rax; __int64
0x18009d271  call    WPP_SF_qsssD
0x18009d276  mov     bl, [rsp+2F0h+var_2A4]
0x18009d27a  mov     r13d, r12d
0x18009d27d  test    r12b, r13b
0x18009d280  jz      short loc_18009D28C
0x18009d282  lea     rcx, [rsp+2F0h+var_288]; this
0x18009d287  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18009d28c  mov     edi, 10h
0x18009d291  lea     rdx, MF_FRAMESERVER_VCAMEVENT_EXTENDED_CUSTOM_EVENT; Buf2
0x18009d298  mov     r8d, edi; Size
0x18009d29b  lea     rcx, [rbp+1F0h+Buf1]; Buf1
0x18009d29f  call    memcmp_0
0x18009d2a4  test    eax, eax
0x18009d2a6  jz      short loc_18009D31F
  ... truncated ...
```
