# FaceDetectionMFT::UpdateFormatInfo(_GUID)

- ea: `0x18001b7f0`
- end: `0x18001bede`
- name: `?UpdateFormatInfo@FaceDetectionMFT@@EEAAJU_GUID@@@Z`
- size: `1774`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct _GUID *Buf1)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000396d`
- `0x180005660`
- `0x18000c0f8`
- `0x18001b7f0`
- `0x18001c95c`
- `0x18001c99c`
- `0x18001d784`
- `0x18001d7d8`
- `0x18001d800`
- `0x18001dddc`
- `0x180131b88`
- `0x180131c78`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b952`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bab3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bba0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b952`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bab3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bba0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bac5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bac5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc17`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b9cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bad0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b9cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001bad0`
- `MFPlat!MFCreateMediaType` at `0x18001ba54`
- `MFPlat!MFCreateMediaType` at `0x18001bb35`
- `MFPlat!MFCreateMediaType` at `0x18001bbf8`
- `MFPlat!MFCreateMediaType` at `0x18001bc49`
- `MFPlat!MFCreateMediaType` at `0x18001ba54`
- `MFPlat!MFCreateMediaType` at `0x18001bb35`
- `MFPlat!MFCreateMediaType` at `0x18001bbf8`
- `MFPlat!MFCreateMediaType` at `0x18001bc49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FaceDetectionMFT::UpdateFormatInfo(FaceDetectionMFT *this, struct _GUID *Buf1)
{
  HRESULT v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  HRESULT v11; // eax
  __int64 v12; // rdx
  _QWORD *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // rdx
  struct IMFMediaType **v16; // rbx
  struct IMFMediaType *v17; // rcx
  int v18; // ecx
  int v19; // eax
  _QWORD *v20; // r8
  float v21; // xmm1_4
  __int128 v22; // rax
  char *v24; // [rsp+30h] [rbp-38h]
  __int64 v25; // [rsp+80h] [rbp+18h] BYREF
  int v26; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(v25) = 0;
  v26 = 0;
  if ( memcmp_0(Buf1, &MFVideoFormat_NV12, 0x10u)
    && memcmp_0(Buf1, &MFVideoFormat_YUY2, 0x10u)
    && memcmp_0(Buf1, &MFVideoFormat_420O, 0x10u)
    && memcmp_0(Buf1, &MFVideoFormat_P010, 0x10u)
    && memcmp_0(Buf1, &MFVideoFormat_MJPG, 0x10u) )
  {
    v4 = -1072875852;
    v5 = -1072875852;
    if ( !g_wppLevels )
      return v5;
    v6 = 187;
LABEL_12:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v4);
    return v5;
  }
  if ( !memcmp_0(Buf1, &MFVideoFormat_MJPG, 0x10u) && !*((_BYTE *)this + 568) )
  {
    v4 = -1072875852;
    v5 = -1072875852;
    if ( !g_wppLevels )
      return v5;
    v6 = 188;
    goto LABEL_12;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    if ( *((_BYTE *)this + 624) )
    {
      v14 = -1072861836;
      v5 = -1072861836;
      if ( !g_wppLevels )
      {
LABEL_52:
        v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 424);
        goto LABEL_28;
      }
      v15 = 198;
LABEL_51:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v14);
      goto LABEL_52;
    }
    v13 = (_QWORD *)((char *)this + 720);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 720);
    v14 = MFCreateMediaType((IMFMediaType **)this + 90);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_52;
      v15 = 199;
      goto LABEL_51;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
LABEL_57:
    if ( !memcmp_0(Buf1, &MFVideoFormat_MJPG, 0x10u) )
    {
      v16 = (struct IMFMediaType **)((char *)this + 728);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 728);
      v4 = MFCreateMediaType((IMFMediaType **)this + 91);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 200;
        goto LABEL_12;
      }
      v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))(*v16)->lpVtbl->SetGUID)(
             *v16,
             &MF_MT_MAJOR_TYPE,
             &MFMediaType_Video);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 201;
        goto LABEL_12;
      }
      v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))(*v16)->lpVtbl->SetGUID)(
             *v16,
             &MF_MT_SUBTYPE,
             &MFVideoFormat_NV12);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 202;
        goto LABEL_12;
      }
      v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))(*v16)->lpVtbl->SetUINT64)(
             *v16,
             &MF_MT_FRAME_SIZE,
             *((unsigned int *)this + 21) | ((unsigned __int64)*((unsigned int *)this + 20) << 32));
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 203;
        goto LABEL_12;
      }
      v4 = CCoreMFT::ConfigureMjpgDecoder(this, *((struct IMFMediaType **)this + 14), *v16);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 204;
        goto LABEL_12;
      }
      v17 = *v16;
      v13 = (_QWORD *)((char *)this + 720);
      v4 = ((__int64 (__fastcall *)(struct IMFMediaType *, _QWORD))v17->lpVtbl->CopyAllItems)(
             v17,
             *((_QWORD *)this + 90));
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 205;
        goto LABEL_12;
      }
    }
    else
    {
      CCoreMFT::CleanUpMjpgDecoder(this);
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14) + 256LL))(*((_QWORD *)this + 14), *v13);
      v5 = v4;
      if ( v4 < 0 )
      {
        if ( !g_wppLevels )
          return v5;
        v6 = 206;
        goto LABEL_12;
      }
    }
    if ( (int)MFGetAttribute2UINT32asUINT64(*v13, &MF_MT_FRAME_RATE, &v25, &v26) >= 0 )
    {
      v18 = v25;
      v19 = v26;
    }
    else
    {
      if ( (unsigned __int8)byte_180160805 >= 0x20u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 207, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
      v18 = 30;
      v19 = 1;
    }
    v20 = (_QWORD *)((char *)this + 752);
    v25 = 0;
    v21 = (float)((float)v19 / (float)v18) * 1000.0;
    v22 = (unsigned int)(int)v21 * (__int128)10000LL;
    if ( 10000LL * (unsigned int)(int)v21 >= 0 )
    {
      if ( is_mul_ok((unsigned int)(int)v21, 0x2710u) )
        goto LABEL_89;
    }
    else if ( *((_QWORD *)&v22 + 1) == -1 )
    {
LABEL_89:
      *v20 = v22;
      *((_BYTE *)this + 712) = 1;
      if ( (unsigned __int8)byte_180160805 >= 0x20u )
        WPP_SF_qdd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          208,
          v20,
          this,
          *((unsigned __int8 *)this + 104),
          *((unsigned __int8 *)this + 546));
      return v5;
    }
    *v20 = -1;
    *(_QWORD *)&v22 = 330000;
    goto LABEL_89;
  }
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 189, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
  v24 = (char *)this + 504;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  v8 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl) )
  {
    while ( 1 )
    {
      ++v8;
      if ( (unsigned __int8)byte_180160805 >= 0x20u )
        WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 27), 190, v7, 20000000, v8, 50, v24);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      if ( !*((_BYTE *)this + 624) )
        break;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
      Sleep(0x28u);
      if ( v8 >= 50 )
      {
        if ( v8 != 50 )
          goto LABEL_47;
        if ( byte_180160805 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 192, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
        v5 = -1072861836;
        if ( g_wppLevels )
        {
          v9 = 193;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 720);
    v11 = MFCreateMediaType((IMFMediaType **)this + 90);
    v5 = v11;
    if ( v11 >= 0 )
      goto LABEL_46;
    if ( g_wppLevels )
    {
      v12 = 191;
      goto LABEL_44;
    }
    goto LABEL_45;
  }
  do
  {
    ++v8;
    if ( (unsigned __int8)byte_180160805 >= 0x20u )
      WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 27), 194, v7, 2000000, v8, 5, v24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    if ( !*((_BYTE *)this + 624) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 720);
      v11 = MFCreateMediaType((IMFMediaType **)this + 90);
      v5 = v11;
      if ( v11 < 0 )
      {
        if ( g_wppLevels )
        {
          v12 = 195;
LABEL_44:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            v11);
        }
LABEL_45:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
        goto LABEL_27;
      }
LABEL_46:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
LABEL_47:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
      v13 = (_QWORD *)((char *)this + 720);
      goto LABEL_57;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
    Sleep(0x28u);
  }
  while ( v8 < 5 );
  if ( v8 != 5 )
    goto LABEL_47;
  if ( byte_180160805 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 196, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
  v5 = -1072861836;
  if ( g_wppLevels )
  {
    v9 = 197;
LABEL_26:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
      this,
      -1072861836);
  }
LABEL_27:
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 504);
LABEL_28:
  LeaveCriticalSection(v10);
  return v5;
}

```

## disassembly

```asm
0x18001b7f0  mov     rax, rsp
0x18001b7f3  mov     [rax+8], rbx
0x18001b7f7  mov     [rax+10h], rbp
0x18001b7fb  push    rsi
0x18001b7fc  push    rdi
0x18001b7fd  push    r13
0x18001b7ff  push    r14
0x18001b801  push    r15
0x18001b803  sub     rsp, 40h
0x18001b807  mov     r15, rdx
0x18001b80a  mov     rsi, rcx
0x18001b80d  mov     dword ptr [rax+18h], 0
0x18001b814  mov     dword ptr [rax+20h], 0
0x18001b81b  mov     r13d, 10h
0x18001b821  mov     r8d, r13d; Size
0x18001b824  lea     rdx, MFVideoFormat_NV12; Buf2
0x18001b82b  mov     rcx, r15; Buf1
0x18001b82e  call    memcmp_0
0x18001b833  test    eax, eax
0x18001b835  jz      short loc_18001B8AA
0x18001b837  mov     r8d, r13d; Size
0x18001b83a  lea     rdx, MFVideoFormat_YUY2; Buf2
0x18001b841  mov     rcx, r15; Buf1
0x18001b844  call    memcmp_0
0x18001b849  test    eax, eax
0x18001b84b  jz      short loc_18001B8AA
0x18001b84d  mov     r8d, r13d; Size
0x18001b850  lea     rdx, MFVideoFormat_420O; Buf2
0x18001b857  mov     rcx, r15; Buf1
0x18001b85a  call    memcmp_0
0x18001b85f  test    eax, eax
0x18001b861  jz      short loc_18001B8AA
0x18001b863  mov     r8d, r13d; Size
0x18001b866  lea     rdx, MFVideoFormat_P010; Buf2
0x18001b86d  mov     rcx, r15; Buf1
0x18001b870  call    memcmp_0
0x18001b875  test    eax, eax
0x18001b877  jz      short loc_18001B8AA
0x18001b879  mov     r8d, r13d; Size
0x18001b87c  lea     rdx, MFVideoFormat_MJPG; Buf2
0x18001b883  mov     rcx, r15; Buf1
0x18001b886  call    memcmp_0
0x18001b88b  test    eax, eax
0x18001b88d  jz      short loc_18001B8AA
0x18001b88f  mov     eax, 0C00D36B4h
0x18001b894  mov     edi, eax
0x18001b896  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b89d  jb      loc_18001BEC5
0x18001b8a3  mov     edx, 0BBh
0x18001b8a8  jmp     short loc_18001B8E1
0x18001b8aa  mov     r8, r13; Size
0x18001b8ad  lea     rdx, MFVideoFormat_MJPG; Buf2
0x18001b8b4  mov     rcx, r15; Buf1
0x18001b8b7  call    memcmp_0
0x18001b8bc  test    eax, eax
0x18001b8be  jnz     short loc_18001B904
0x18001b8c0  cmp     [rsi+238h], al
0x18001b8c6  jnz     short loc_18001B904
0x18001b8c8  mov     eax, 0C00D36B4h
0x18001b8cd  mov     edi, eax
0x18001b8cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001b8d6  jb      loc_18001BEC5
0x18001b8dc  mov     edx, 0BCh
0x18001b8e1  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001b8e8  mov     r9, rsi
0x18001b8eb  mov     [rsp+68h+var_48], eax
0x18001b8ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8f6  mov     rcx, [rcx+10h]
0x18001b8fa  call    WPP_SF_qD
0x18001b8ff  jmp     loc_18001BEC5
0x18001b904  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl(void)'::`2'::impl
0x18001b90b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(void)
0x18001b910  lea     rbp, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001b917  test    al, al
0x18001b919  jz      loc_18001BB96
0x18001b91f  cmp     cs:byte_180160805, 20h ; ' '
0x18001b926  jb      short loc_18001B943
0x18001b928  mov     edx, 0BDh
0x18001b92d  mov     r8, rbp
0x18001b930  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b937  mov     rcx, [rcx+0D8h]
0x18001b93e  call    WPP_SF_
0x18001b943  lea     rbx, [rsi+1F8h]
0x18001b94a  mov     [rsp+68h+var_38], rbx
0x18001b94f  mov     rcx, rbx; lpCriticalSection
0x18001b952  call    cs:__imp_EnterCriticalSection
0x18001b958  nop
0x18001b959  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl(void)'::`2'::impl
0x18001b960  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(void)
0x18001b965  xor     edi, edi
0x18001b967  lea     r14, [rsi+1A8h]
0x18001b96e  test    al, al
0x18001b970  jz      loc_18001BA7B
0x18001b976  inc     edi
0x18001b978  cmp     cs:byte_180160805, 20h ; ' '
0x18001b97f  jb      short loc_18001B9AB
0x18001b981  mov     edx, 0BEh
0x18001b986  mov     [rsp+68h+var_40], 32h ; '2'
0x18001b98e  mov     [rsp+68h+var_48], edi
0x18001b992  mov     r9d, 1312D00h
0x18001b998  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b99f  mov     rcx, [rcx+0D8h]
0x18001b9a6  call    WPP_SF_Ddd
0x18001b9ab  mov     rcx, r14; lpCriticalSection
0x18001b9ae  call    cs:__imp_EnterCriticalSection
0x18001b9b4  cmp     byte ptr [rsi+270h], 0
0x18001b9bb  jz      loc_18001BA42
0x18001b9c1  mov     rcx, r14; lpCriticalSection
0x18001b9c4  call    cs:__imp_LeaveCriticalSection
0x18001b9ca  mov     ecx, 28h ; '('; dwMilliseconds
0x18001b9cf  call    cs:__imp_Sleep
0x18001b9d5  cmp     edi, 32h ; '2'
0x18001b9d8  jl      short loc_18001B976
0x18001b9da  jnz     loc_18001BB81
0x18001b9e0  cmp     cs:byte_180160805, 1
0x18001b9e7  jb      short loc_18001BA04
0x18001b9e9  mov     edx, 0C0h
0x18001b9ee  mov     r8, rbp
0x18001b9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9f8  mov     rcx, [rcx+0D8h]
0x18001b9ff  call    WPP_SF_
0x18001ba04  mov     eax, 0C00D6D74h
0x18001ba09  mov     edi, eax
0x18001ba0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ba12  jb      short loc_18001BA34
0x18001ba14  mov     edx, 0C1h
0x18001ba19  mov     [rsp+68h+var_48], eax
0x18001ba1d  mov     r9, rsi
0x18001ba20  mov     r8, rbp
0x18001ba23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba2a  mov     rcx, [rcx+10h]
0x18001ba2e  call    WPP_SF_qD
0x18001ba33  nop
0x18001ba34  mov     rcx, rbx; lpCriticalSection
0x18001ba37  call    cs:__imp_LeaveCriticalSection
0x18001ba3d  jmp     loc_18001BEC5
0x18001ba42  lea     rdi, [rsi+2D0h]
0x18001ba49  mov     rcx, rdi
0x18001ba4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ba51  mov     rcx, rdi; ppMFType
0x18001ba54  call    cs:__imp_MFCreateMediaType
0x18001ba5a  mov     edi, eax
0x18001ba5c  test    eax, eax
0x18001ba5e  jns     loc_18001BB77
0x18001ba64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ba6b  jb      loc_18001BB69
0x18001ba71  mov     edx, 0BFh
0x18001ba76  jmp     loc_18001BB4F
0x18001ba7b  inc     edi
0x18001ba7d  cmp     cs:byte_180160805, 20h ; ' '
0x18001ba84  jb      short loc_18001BAB0
0x18001ba86  mov     edx, 0C2h
0x18001ba8b  mov     [rsp+68h+var_40], 5
0x18001ba93  mov     [rsp+68h+var_48], edi
0x18001ba97  mov     r9d, 1E8480h
0x18001ba9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baa4  mov     rcx, [rcx+0D8h]
0x18001baab  call    WPP_SF_Ddd
0x18001bab0  mov     rcx, r14; lpCriticalSection
0x18001bab3  call    cs:__imp_EnterCriticalSection
0x18001bab9  cmp     byte ptr [rsi+270h], 0
0x18001bac0  jz      short loc_18001BB23
0x18001bac2  mov     rcx, r14; lpCriticalSection
0x18001bac5  call    cs:__imp_LeaveCriticalSection
0x18001bacb  mov     ecx, 28h ; '('; dwMilliseconds
0x18001bad0  call    cs:__imp_Sleep
0x18001bad6  cmp     edi, 5
0x18001bad9  jl      short loc_18001BA7B
0x18001badb  jnz     loc_18001BB81
0x18001bae1  cmp     cs:byte_180160805, 1
0x18001bae8  jb      short loc_18001BB05
0x18001baea  mov     edx, 0C4h
0x18001baef  mov     r8, rbp
0x18001baf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baf9  mov     rcx, [rcx+0D8h]
0x18001bb00  call    WPP_SF_
0x18001bb05  mov     eax, 0C00D6D74h
0x18001bb0a  mov     edi, eax
0x18001bb0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bb13  jb      loc_18001BA34
0x18001bb19  mov     edx, 0C5h
0x18001bb1e  jmp     loc_18001BA19
0x18001bb23  lea     rdi, [rsi+2D0h]
0x18001bb2a  mov     rcx, rdi
0x18001bb2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bb32  mov     rcx, rdi; ppMFType
0x18001bb35  call    cs:__imp_MFCreateMediaType
0x18001bb3b  mov     edi, eax
0x18001bb3d  test    eax, eax
0x18001bb3f  jns     short loc_18001BB77
0x18001bb41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bb48  jb      short loc_18001BB69
0x18001bb4a  mov     edx, 0C3h
0x18001bb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb56  mov     [rsp+68h+var_48], eax
0x18001bb5a  mov     r9, rsi
0x18001bb5d  mov     r8, rbp
0x18001bb60  mov     rcx, [rcx+10h]
0x18001bb64  call    WPP_SF_qD
0x18001bb69  mov     rcx, r14; lpCriticalSection
0x18001bb6c  call    cs:__imp_LeaveCriticalSection
0x18001bb72  jmp     loc_18001BA34
0x18001bb77  mov     rcx, r14; lpCriticalSection
0x18001bb7a  call    cs:__imp_LeaveCriticalSection
0x18001bb80  nop
0x18001bb81  mov     rcx, rbx; lpCriticalSection
0x18001bb84  call    cs:__imp_LeaveCriticalSection
0x18001bb8a  lea     rbx, [rsi+2D0h]
0x18001bb91  jmp     loc_18001BC1D
0x18001bb96  lea     r14, [rsi+1A8h]
0x18001bb9d  mov     rcx, r14; lpCriticalSection
0x18001bba0  call    cs:__imp_EnterCriticalSection
0x18001bba6  cmp     byte ptr [rsi+270h], 0
0x18001bbad  jz      short loc_18001BBE6
0x18001bbaf  mov     eax, 0C00D6D74h
0x18001bbb4  mov     edi, eax
0x18001bbb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bbbd  jb      short loc_18001BBDE
0x18001bbbf  mov     edx, 0C6h
0x18001bbc4  mov     [rsp+68h+var_48], eax
0x18001bbc8  mov     r9, rsi
0x18001bbcb  mov     r8, rbp
0x18001bbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbd5  mov     rcx, [rcx+10h]
0x18001bbd9  call    WPP_SF_qD
0x18001bbde  mov     rcx, r14
0x18001bbe1  jmp     loc_18001BA37
0x18001bbe6  lea     rbx, [rsi+2D0h]
0x18001bbed  mov     rcx, rbx
0x18001bbf0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bbf5  mov     rcx, rbx; ppMFType
0x18001bbf8  call    cs:__imp_MFCreateMediaType
0x18001bbfe  mov     edi, eax
0x18001bc00  test    eax, eax
0x18001bc02  jns     short loc_18001BC14
0x18001bc04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bc0b  jb      short loc_18001BBDE
0x18001bc0d  mov     edx, 0C7h
0x18001bc12  jmp     short loc_18001BBC4
0x18001bc14  mov     rcx, r14; lpCriticalSection
0x18001bc17  call    cs:__imp_LeaveCriticalSection
0x18001bc1d  mov     r8, r13; Size
0x18001bc20  lea     rdx, MFVideoFormat_MJPG; Buf2
0x18001bc27  mov     rcx, r15; Buf1
0x18001bc2a  call    memcmp_0
0x18001bc2f  test    eax, eax
0x18001bc31  jnz     loc_18001BD8C
0x18001bc37  lea     rbx, [rsi+2D8h]
0x18001bc3e  mov     rcx, rbx
0x18001bc41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001bc46  mov     rcx, rbx; ppMFType
0x18001bc49  call    cs:__imp_MFCreateMediaType
0x18001bc4f  mov     edi, eax
0x18001bc51  test    eax, eax
0x18001bc53  jns     short loc_18001BC6F
0x18001bc55  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bc5c  jb      loc_18001BEC5
0x18001bc62  mov     edx, 0C8h
0x18001bc67  mov     r8, rbp
0x18001bc6a  jmp     loc_18001B8E8
0x18001bc6f  mov     rcx, [rbx]
0x18001bc72  mov     rax, [rcx]
0x18001bc75  lea     r8, MFMediaType_Video
0x18001bc7c  lea     rdx, MF_MT_MAJOR_TYPE
0x18001bc83  mov     rax, [rax+0C0h]
0x18001bc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc8f  mov     edi, eax
0x18001bc91  test    eax, eax
0x18001bc93  jns     short loc_18001BCA9
0x18001bc95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bc9c  jb      loc_18001BEC5
0x18001bca2  mov     edx, 0C9h
0x18001bca7  jmp     short loc_18001BC67
0x18001bca9  mov     rcx, [rbx]
0x18001bcac  mov     rax, [rcx]
0x18001bcaf  lea     r8, MFVideoFormat_NV12
0x18001bcb6  lea     rdx, MF_MT_SUBTYPE
0x18001bcbd  mov     rax, [rax+0C0h]
0x18001bcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc9  mov     edi, eax
0x18001bccb  test    eax, eax
0x18001bccd  jns     short loc_18001BCE3
0x18001bccf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bcd6  jb      loc_18001BEC5
0x18001bcdc  mov     edx, 0CAh
0x18001bce1  jmp     short loc_18001BC67
0x18001bce3  mov     rcx, [rbx]
0x18001bce6  mov     r9, [rcx]
0x18001bce9  mov     r8d, [rsi+50h]
0x18001bced  shl     r8, 20h
0x18001bcf1  mov     eax, [rsi+54h]
0x18001bcf4  or      r8, rax
0x18001bcf7  lea     rdx, MF_MT_FRAME_SIZE
0x18001bcfe  mov     rax, [r9+0B0h]
0x18001bd05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd0a  mov     edi, eax
0x18001bd0c  test    eax, eax
0x18001bd0e  jns     short loc_18001BD27
0x18001bd10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001bd17  jb      loc_18001BEC5
  ... truncated ...
```
