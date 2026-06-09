# SensorDevice::GatherRSMT(ushort const *,IMFAttributes *,IMFMediaSource * *)

- ea: `0x180007908`
- end: `0x18000801c`
- name: `?GatherRSMT@SensorDevice@@IEAAJPEBGPEAUIMFAttributes@@PEAPEAUIMFMediaSource@@@Z`
- size: `1812`
- prototype: `__int64 __fastcall(SensorDevice *__hidden this, const unsigned __int16 *, struct IMFAttributes *, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006230`

## callees

- `0x180005fa0`
- `0x180006758`
- `0x18000694c`
- `0x180006dd4`
- `0x180007908`
- `0x180008bd0`
- `0x180008f9c`
- `0x1800349b0`
- `0x180049104`
- `0x18004a360`
- `0x180069ee4`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180007a71`
- `MFPlat!MFCreateAttributes` at `0x180007a71`
- `MFCORE!MFCreateDeviceSource` at `0x180007b71`
- `MFCORE!MFCreateDeviceSource` at `0x180007d21`
- `MFCORE!MFCreateDeviceSource` at `0x180007ec9`
- `MFCORE!MFCreateDeviceSource` at `0x180007b71`
- `MFCORE!MFCreateDeviceSource` at `0x180007d21`
- `MFCORE!MFCreateDeviceSource` at `0x180007ec9`

## pseudocode

```c
__int64 __fastcall SensorDevice::GatherRSMT(
        SensorDevice *this,
        const unsigned __int16 *a2,
        struct IMFAttributes *a3,
        struct IMFMediaSource **a4)
{
  HRESULT ProfileForDevice; // eax
  int CameraProfileV1; // ebx
  __int64 v10; // rdx
  const unsigned __int16 *v12; // rdx
  int v13; // r14d
  __int64 v14; // r8
  int v15; // ecx
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  char *v19; // [rsp+20h] [rbp-49h]
  IMFMediaSource *ppSource; // [rsp+40h] [rbp-29h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-21h] BYREF
  __int64 v22; // [rsp+50h] [rbp-19h] BYREF
  __int64 v23; // [rsp+58h] [rbp-11h] BYREF
  int v24; // [rsp+60h] [rbp-9h]
  __int64 v25; // [rsp+64h] [rbp-5h]
  __int64 v26; // [rsp+70h] [rbp+7h] BYREF
  int v27; // [rsp+78h] [rbp+Fh]
  __int64 v28; // [rsp+7Ch] [rbp+13h]
  __int64 v29; // [rsp+88h] [rbp+1Fh] BYREF
  int v30; // [rsp+90h] [rbp+27h]
  __int64 v31; // [rsp+94h] [rbp+2Bh]
  __int64 v32; // [rsp+D8h] [rbp+6Fh] BYREF

  ppSource = 0;
  ppMFAttributes = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  LODWORD(v32) = 0;
  if ( !a2 )
  {
    ProfileForDevice = -2147024809;
    CameraProfileV1 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_5;
    v10 = 240;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    ProfileForDevice = -2147024809;
    CameraProfileV1 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 241;
LABEL_4:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
        this,
        ProfileForDevice);
      goto LABEL_5;
    }
    goto LABEL_5;
  }
  if ( !a4 )
  {
    CameraProfileV1 = -2147467261;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
        this,
        -2147467261);
    goto LABEL_5;
  }
  ProfileForDevice = MFCreateAttributes(&ppMFAttributes, 5u);
  CameraProfileV1 = ProfileForDevice;
  if ( ProfileForDevice >= 0 )
  {
    ProfileForDevice = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const IID *))ppMFAttributes->lpVtbl->SetGUID)(
                         ppMFAttributes,
                         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
                         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 244;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
                         ppMFAttributes,
                         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
                         a2);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 245;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
                         ppMFAttributes,
                         MF_DEVICESOURCE_ATTRIBUTE_ENABLE_PLUGIN,
                         1);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 246;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    if ( !(unsigned int)ProfileParser::IsProfileAvailable(a2) && !(unsigned int)ProfileParserInf::IsProfileAvailable(a2) )
    {
      ProfileForDevice = MFCreateDeviceSource(ppMFAttributes, &ppSource);
      CameraProfileV1 = ProfileForDevice;
      if ( ProfileForDevice < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 248;
          goto LABEL_4;
        }
        goto LABEL_5;
      }
      SensorDevice::CheckForDShowUse(this, v12, ppSource, a3);
      CameraProfileV1 = SensorDevice::GatherMediaTypes(
                          this,
                          &GUID_00000000_0000_0000_0000_000000000000,
                          ppSource,
                          (__int64)this + 112);
      if ( CameraProfileV1 < 0 )
        goto LABEL_5;
      ProfileForDevice = SensorDevice::LoadProfileForDevice(this, ppSource, a2, (int *)&v32);
      CameraProfileV1 = ProfileForDevice;
      if ( ProfileForDevice < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 249;
          goto LABEL_4;
        }
        goto LABEL_5;
      }
      v13 = v32;
      if ( (_DWORD)v32 )
      {
        ProfileForDevice = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, __int64))a3->lpVtbl->SetUINT32)(
                             a3,
                             MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE,
                             1);
        CameraProfileV1 = ProfileForDevice;
        if ( ProfileForDevice < 0 )
        {
          if ( g_wppLevels )
          {
            v10 = 250;
            goto LABEL_4;
          }
          goto LABEL_5;
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 160LL))(*((_QWORD *)this + 21), 0x40000000);
      }
      v15 = 0;
LABEL_85:
      *a4 = ppSource;
      ppSource = 0;
      if ( CameraProfileV1 >= 0 )
      {
        if ( v15 && v13 )
        {
          if ( !byte_18008D62D )
            goto LABEL_7;
          v18 = 262;
        }
        else
        {
          if ( (unsigned __int8)byte_18008D62D < 8u )
            goto LABEL_7;
          v18 = 263;
        }
        WPP_SF_qDdd(*((_QWORD *)WPP_GLOBAL_Control + 27), v18, v14, this, CameraProfileV1, v15, v13);
        goto LABEL_7;
      }
      goto LABEL_5;
    }
    ProfileForDevice = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, __int64))a3->lpVtbl->SetUINT32)(
                         a3,
                         MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE,
                         1);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 251;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, GUID *))ppMFAttributes->lpVtbl->SetGUID)(
                         ppMFAttributes,
                         &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE,
                         &GUID_00000000_0000_0000_0000_000000000000);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 252;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                         ppMFAttributes,
                         &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE_INDEX,
                         0);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 253;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = MFCreateDeviceSource(ppMFAttributes, &ppSource);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 254;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    ProfileForDevice = SensorDevice::LoadProfileForDevice(this, ppSource, a2, (int *)&v32);
    CameraProfileV1 = ProfileForDevice;
    if ( ProfileForDevice < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 255;
        goto LABEL_4;
      }
      goto LABEL_5;
    }
    v13 = v32;
    v19 = (char *)this + 112;
    if ( (_DWORD)v32 )
    {
      CameraProfileV1 = SensorDevice::GatherMediaTypes(
                          this,
                          &GUID_00000000_0000_0000_0000_000000000000,
                          ppSource,
                          (__int64)v19);
      v15 = 1;
      if ( CameraProfileV1 < 0 )
        goto LABEL_5;
      goto LABEL_85;
    }
    v32 = 0;
    v22 = 0;
    v23 = 0;
    v25 = 0;
    v24 = 0;
    CameraProfileV1 = SensorDevice::GatherMediaTypes(
                        this,
                        &GUID_00000000_0000_0000_0000_000000000000,
                        ppSource,
                        (__int64)v19);
    if ( CameraProfileV1 < 0 )
    {
LABEL_62:
      CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(&v23);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v22);
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v32);
      goto LABEL_5;
    }
    v16 = ((__int64 (__fastcall *)(IMFMediaSource *))ppSource->lpVtbl->Shutdown)(ppSource);
    CameraProfileV1 = v16;
    if ( v16 >= 0 )
    {
      if ( ppSource )
      {
        ((void (__fastcall *)(IMFMediaSource *))ppSource->lpVtbl->Release)(ppSource);
        ppSource = 0;
      }
      v16 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, GUID *))ppMFAttributes->lpVtbl->SetGUID)(
              ppMFAttributes,
              &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE,
              &GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e);
      CameraProfileV1 = v16;
      if ( v16 >= 0 )
      {
        v16 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
                ppMFAttributes,
                &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE_INDEX,
                0);
        CameraProfileV1 = v16;
        if ( v16 >= 0 )
        {
          v16 = MFCreateDeviceSource(ppMFAttributes, &ppSource);
          CameraProfileV1 = v16;
          if ( v16 >= 0 )
          {
            CameraProfileV1 = SensorDevice::GatherMediaTypes(
                                this,
                                &GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e,
                                ppSource,
                                (__int64)&v23);
            if ( CameraProfileV1 < 0 )
              goto LABEL_62;
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 21) + 64LL))(*((_QWORD *)this + 21), 0);
            v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 40LL))(
                    *((_QWORD *)this + 21),
                    v32);
            CameraProfileV1 = v16;
            if ( v16 >= 0 )
            {
              CameraProfileV1 = SensorDevice::LoadCameraProfileV1(this, a2);
              if ( CameraProfileV1 >= 0 )
              {
                CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(&v23);
                wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v22);
                wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v32);
                v15 = 1;
                goto LABEL_85;
              }
              goto LABEL_62;
            }
            if ( !g_wppLevels )
              goto LABEL_62;
            v17 = 260;
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_62;
            v17 = 259;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_62;
          v17 = 258;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_62;
        v17 = 257;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_62;
      v17 = 256;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v16);
    goto LABEL_62;
  }
  if ( g_wppLevels )
  {
    v10 = 243;
    goto LABEL_4;
  }
LABEL_5:
  if ( byte_18008D62D )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      261,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      this,
      CameraProfileV1);
LABEL_7:
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(&v26);
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(&v29);
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  if ( ppSource )
    ((void (__fastcall *)(IMFMediaSource *))ppSource->lpVtbl->Release)(ppSource);
  return (unsigned int)CameraProfileV1;
}

```

## disassembly

```asm
0x180007908  mov     [rsp-8+arg_0], rbx
0x18000790d  mov     [rsp-8+arg_10], rsi
0x180007912  push    rbp
0x180007913  push    r12
0x180007915  push    r13
0x180007917  push    r14
0x180007919  push    r15
0x18000791b  lea     rbp, [rsp-37h]
0x180007920  sub     rsp, 0A0h
0x180007927  xor     r14d, r14d
0x18000792a  mov     r13, r9
0x18000792d  mov     [rbp+57h+ppSource], r14
0x180007931  mov     r12, r8
0x180007934  mov     [rbp+57h+ppMFAttributes], r14
0x180007938  mov     r15, rdx
0x18000793b  mov     [rbp+57h+var_38], r14
0x18000793f  mov     rsi, rcx
0x180007942  mov     [rbp+57h+var_2C], r14
0x180007946  mov     [rbp+57h+var_30], r14d
0x18000794a  mov     [rbp+57h+var_50], r14
0x18000794e  mov     [rbp+57h+var_44], r14
0x180007952  mov     [rbp+57h+var_48], r14d
0x180007956  mov     dword ptr [rbp+57h+arg_8], r14d
0x18000795a  test    rdx, rdx
0x18000795d  jnz     loc_180007A20
0x180007963  mov     eax, 80070057h
0x180007968  mov     ebx, eax
0x18000796a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007971  jb      short loc_180007996
0x180007973  mov     edx, 0F0h
0x180007978  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18000797c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007983  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18000798a  mov     r9, rsi
0x18000798d  mov     rcx, [rcx+10h]
0x180007991  call    WPP_SF_qD
0x180007996  cmp     cs:byte_18008D62D, 1
0x18000799d  jb      short loc_1800079C5
0x18000799f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079a6  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x1800079ad  mov     edx, 105h
0x1800079b2  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800079b6  mov     r9, rsi
0x1800079b9  mov     rcx, [rcx+0D8h]
0x1800079c0  call    WPP_SF_qD
0x1800079c5  lea     rcx, [rbp+57h+var_50]; void *
0x1800079c9  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x1800079ce  lea     rcx, [rbp+57h+var_38]; void *
0x1800079d2  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x1800079d7  mov     rcx, [rbp+57h+ppMFAttributes]
0x1800079db  test    rcx, rcx
0x1800079de  jz      short loc_1800079EC
0x1800079e0  mov     rax, [rcx]
0x1800079e3  mov     rax, [rax+10h]
0x1800079e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ec  mov     rcx, [rbp+57h+ppSource]
0x1800079f0  test    rcx, rcx
0x1800079f3  jz      short loc_180007A01
0x1800079f5  mov     rax, [rcx]
0x1800079f8  mov     rax, [rax+10h]
0x1800079fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a01  lea     r11, [rsp+0C0h+var_20]
0x180007a09  mov     eax, ebx
0x180007a0b  mov     rbx, [r11+30h]
0x180007a0f  mov     rsi, [r11+40h]
0x180007a13  mov     rsp, r11
0x180007a16  pop     r15
0x180007a18  pop     r14
0x180007a1a  pop     r13
0x180007a1c  pop     r12
0x180007a1e  pop     rbp
0x180007a1f  retn
0x180007a20  test    r12, r12
0x180007a23  jnz     short loc_180007A43
0x180007a25  mov     eax, 80070057h
0x180007a2a  mov     ebx, eax
0x180007a2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007a33  jb      loc_180007996
0x180007a39  mov     edx, 0F1h
0x180007a3e  jmp     loc_180007978
0x180007a43  test    r13, r13
0x180007a46  jnz     short loc_180007A68
0x180007a48  mov     ebx, 80004003h
0x180007a4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007a54  jb      loc_180007996
0x180007a5a  mov     edx, 0F2h
0x180007a5f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180007a63  jmp     loc_18000797C
0x180007a68  mov     edx, 5; cInitialSize
0x180007a6d  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x180007a71  call    cs:__imp_MFCreateAttributes
0x180007a77  mov     ebx, eax
0x180007a79  test    eax, eax
0x180007a7b  jns     short loc_180007A94
0x180007a7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007a84  jb      loc_180007996
0x180007a8a  mov     edx, 0F3h
0x180007a8f  jmp     loc_180007978
0x180007a94  mov     rcx, [rbp+57h+ppMFAttributes]
0x180007a98  lea     r8, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID
0x180007a9f  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE
0x180007aa6  mov     rax, [rcx]
0x180007aa9  mov     rax, [rax+0C0h]
0x180007ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab5  mov     ebx, eax
0x180007ab7  test    eax, eax
0x180007ab9  jns     short loc_180007AD2
0x180007abb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007ac2  jb      loc_180007996
0x180007ac8  mov     edx, 0F4h
0x180007acd  jmp     loc_180007978
0x180007ad2  mov     rcx, [rbp+57h+ppMFAttributes]
0x180007ad6  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180007add  mov     r8, r15
0x180007ae0  mov     rax, [rcx]
0x180007ae3  mov     rax, [rax+0C8h]
0x180007aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aef  mov     ebx, eax
0x180007af1  test    eax, eax
0x180007af3  jns     short loc_180007B0C
0x180007af5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007afc  jb      loc_180007996
0x180007b02  mov     edx, 0F5h
0x180007b07  jmp     loc_180007978
0x180007b0c  mov     rcx, [rbp+57h+ppMFAttributes]
0x180007b10  lea     rdx, MF_DEVICESOURCE_ATTRIBUTE_ENABLE_PLUGIN
0x180007b17  mov     r8d, 1
0x180007b1d  mov     rax, [rcx]
0x180007b20  mov     rax, [rax+0A8h]
0x180007b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2c  mov     ebx, eax
0x180007b2e  test    eax, eax
0x180007b30  jns     short loc_180007B49
0x180007b32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007b39  jb      loc_180007996
0x180007b3f  mov     edx, 0F6h
0x180007b44  jmp     loc_180007978
0x180007b49  mov     rcx, r15; unsigned __int16 *
0x180007b4c  call    ?IsProfileAvailable@ProfileParser@@SAHPEBG@Z; ProfileParser::IsProfileAvailable(ushort const *)
0x180007b51  test    eax, eax
0x180007b53  jnz     loc_180007C64
0x180007b59  mov     rcx, r15; unsigned __int16 *
0x180007b5c  call    ?IsProfileAvailable@ProfileParserInf@@SAHPEBG@Z; ProfileParserInf::IsProfileAvailable(ushort const *)
0x180007b61  test    eax, eax
0x180007b63  jnz     loc_180007C64
0x180007b69  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x180007b6d  lea     rdx, [rbp+57h+ppSource]; ppSource
0x180007b71  call    cs:__imp_MFCreateDeviceSource
0x180007b77  mov     ebx, eax
0x180007b79  test    eax, eax
0x180007b7b  jns     short loc_180007B94
0x180007b7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007b84  jb      loc_180007996
0x180007b8a  mov     edx, 0F8h
0x180007b8f  jmp     loc_180007978
0x180007b94  mov     r8, [rbp+57h+ppSource]; struct IMFMediaSource *
0x180007b98  mov     r9, r12; struct IMFAttributes *
0x180007b9b  mov     rcx, rsi; this
0x180007b9e  call    ?CheckForDShowUse@SensorDevice@@IEAAXPEBGPEAUIMFMediaSource@@PEAUIMFAttributes@@@Z; SensorDevice::CheckForDShowUse(ushort const *,IMFMediaSource *,IMFAttributes *)
0x180007ba3  mov     r8, [rbp+57h+ppSource]; struct IMFMediaSource *
0x180007ba7  lea     rax, [rsi+70h]
0x180007bab  xor     r9d, r9d
0x180007bae  mov     [rsp+0C0h+var_A0], rax; __int64
0x180007bb3  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x180007bba  mov     rcx, rsi; this
0x180007bbd  call    ?GatherMediaTypes@SensorDevice@@IEAAJAEBU_GUID@@PEAUIMFMediaSource@@PEAPEAUIMFSensorProfileInternal@@AEAV?$CTUnkArray@UIMFSensorStreamInternal@@@@@Z; SensorDevice::GatherMediaTypes(_GUID const &,IMFMediaSource *,IMFSensorProfileInternal * *,CTUnkArray<IMFSensorStreamInternal> &)
0x180007bc2  mov     ebx, eax
0x180007bc4  test    eax, eax
0x180007bc6  js      loc_180007996
0x180007bcc  mov     rdx, [rbp+57h+ppSource]; struct IMFMediaSource *
0x180007bd0  lea     r9, [rbp+57h+arg_8]; int *
0x180007bd4  mov     r8, r15; unsigned __int16 *
0x180007bd7  mov     rcx, rsi; this
0x180007bda  call    ?LoadProfileForDevice@SensorDevice@@IEAAJPEAUIMFMediaSource@@PEBGPEAH@Z; SensorDevice::LoadProfileForDevice(IMFMediaSource *,ushort const *,int *)
0x180007bdf  mov     ebx, eax
0x180007be1  test    eax, eax
0x180007be3  jns     short loc_180007BFC
0x180007be5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007bec  jb      loc_180007996
0x180007bf2  mov     edx, 0F9h
0x180007bf7  jmp     loc_180007978
0x180007bfc  mov     r14d, dword ptr [rbp+57h+arg_8]
0x180007c00  test    r14d, r14d
0x180007c03  jz      short loc_180007C42
0x180007c05  mov     rax, [r12]
0x180007c09  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE
0x180007c10  mov     r8d, 1
0x180007c16  mov     rcx, r12
0x180007c19  mov     rax, [rax+0A8h]
0x180007c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c25  mov     ebx, eax
0x180007c27  test    eax, eax
0x180007c29  jns     short loc_180007C5D
0x180007c2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007c32  jb      loc_180007996
0x180007c38  mov     edx, 0FAh
0x180007c3d  jmp     loc_180007978
0x180007c42  mov     rcx, [rsi+0A8h]
0x180007c49  mov     edx, 40000000h
0x180007c4e  mov     rax, [rcx]
0x180007c51  mov     rax, [rax+0A0h]
0x180007c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c5d  xor     ecx, ecx
0x180007c5f  jmp     loc_180007FAD
0x180007c64  mov     rax, [r12]
0x180007c68  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE
0x180007c6f  mov     r8d, 1
0x180007c75  mov     rcx, r12
0x180007c78  mov     rax, [rax+0A8h]
0x180007c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c84  mov     ebx, eax
0x180007c86  test    eax, eax
0x180007c88  jns     short loc_180007CA1
0x180007c8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007c91  jb      loc_180007996
0x180007c97  mov     edx, 0FBh
0x180007c9c  jmp     loc_180007978
0x180007ca1  mov     rcx, [rbp+57h+ppMFAttributes]
0x180007ca5  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x180007cac  lea     rdx, MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE
0x180007cb3  mov     rax, [rcx]
0x180007cb6  mov     rax, [rax+0C0h]
0x180007cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc2  mov     ebx, eax
0x180007cc4  test    eax, eax
0x180007cc6  jns     short loc_180007CDF
0x180007cc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007ccf  jb      loc_180007996
0x180007cd5  mov     edx, 0FCh
0x180007cda  jmp     loc_180007978
0x180007cdf  mov     rcx, [rbp+57h+ppMFAttributes]
0x180007ce3  lea     rdx, MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE_INDEX
0x180007cea  xor     r8d, r8d
0x180007ced  mov     rax, [rcx]
0x180007cf0  mov     rax, [rax+0A8h]
0x180007cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cfc  mov     ebx, eax
0x180007cfe  test    eax, eax
0x180007d00  jns     short loc_180007D19
0x180007d02  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007d09  jb      loc_180007996
0x180007d0f  mov     edx, 0FDh
0x180007d14  jmp     loc_180007978
0x180007d19  mov     rcx, [rbp+57h+ppMFAttributes]; pAttributes
0x180007d1d  lea     rdx, [rbp+57h+ppSource]; ppSource
0x180007d21  call    cs:__imp_MFCreateDeviceSource
0x180007d27  mov     ebx, eax
0x180007d29  test    eax, eax
0x180007d2b  jns     short loc_180007D44
0x180007d2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007d34  jb      loc_180007996
0x180007d3a  mov     edx, 0FEh
0x180007d3f  jmp     loc_180007978
0x180007d44  mov     rdx, [rbp+57h+ppSource]; struct IMFMediaSource *
0x180007d48  lea     r9, [rbp+57h+arg_8]; int *
0x180007d4c  mov     r8, r15; unsigned __int16 *
0x180007d4f  mov     rcx, rsi; this
0x180007d52  call    ?LoadProfileForDevice@SensorDevice@@IEAAJPEAUIMFMediaSource@@PEBGPEAH@Z; SensorDevice::LoadProfileForDevice(IMFMediaSource *,ushort const *,int *)
0x180007d57  mov     ebx, eax
0x180007d59  test    eax, eax
0x180007d5b  jns     short loc_180007D74
0x180007d5d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007d64  jb      loc_180007996
0x180007d6a  mov     edx, 0FFh
0x180007d6f  jmp     loc_180007978
0x180007d74  mov     r14d, dword ptr [rbp+57h+arg_8]
0x180007d78  lea     rax, [rsi+70h]
0x180007d7c  mov     r8, [rbp+57h+ppSource]; struct IMFMediaSource *
0x180007d80  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; struct _GUID *
0x180007d87  mov     [rsp+0C0h+var_A0], rax; __int64
0x180007d8c  mov     rcx, rsi; this
0x180007d8f  test    r14d, r14d
0x180007d92  jnz     loc_180007F96
0x180007d98  lea     r9, [rbp+57h+var_70]
0x180007d9c  mov     [rbp+57h+arg_8], 0
0x180007da4  mov     [rbp+57h+var_70], 0
0x180007dac  mov     [rbp+57h+var_68], 0
0x180007db4  mov     [rbp+57h+var_5C], 0
0x180007dbc  mov     [rbp+57h+var_60], r14d
0x180007dc0  call    ?GatherMediaTypes@SensorDevice@@IEAAJAEBU_GUID@@PEAUIMFMediaSource@@PEAPEAUIMFSensorProfileInternal@@AEAV?$CTUnkArray@UIMFSensorStreamInternal@@@@@Z; SensorDevice::GatherMediaTypes(_GUID const &,IMFMediaSource *,IMFSensorProfileInternal * *,CTUnkArray<IMFSensorStreamInternal> &)
0x180007dc5  mov     ebx, eax
0x180007dc7  test    eax, eax
0x180007dc9  jns     short loc_180007DEB
0x180007dcb  lea     rcx, [rbp+57h+var_68]; void *
0x180007dcf  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x180007dd4  lea     rcx, [rbp+57h+var_70]
0x180007dd8  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180007ddd  lea     rcx, [rbp+57h+arg_8]
0x180007de1  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180007de6  jmp     loc_180007996
0x180007deb  mov     rcx, [rbp+57h+ppSource]
0x180007def  mov     rax, [rcx]
0x180007df2  mov     rax, [rax+60h]
0x180007df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfb  mov     ebx, eax
0x180007dfd  test    eax, eax
0x180007dff  jns     short loc_180007E2F
0x180007e01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007e08  jb      short loc_180007DCB
0x180007e0a  mov     edx, 100h
  ... truncated ...
```
