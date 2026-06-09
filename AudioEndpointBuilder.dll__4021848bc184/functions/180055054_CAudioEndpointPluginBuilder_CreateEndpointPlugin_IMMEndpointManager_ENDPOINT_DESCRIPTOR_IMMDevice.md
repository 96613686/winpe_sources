# CAudioEndpointPluginBuilder::CreateEndpointPlugin(IMMEndpointManager *,ENDPOINT_DESCRIPTOR *,IMMDevice * *)

- ea: `0x180055054`
- end: `0x180055a88`
- name: `?CreateEndpointPlugin@CAudioEndpointPluginBuilder@@CAJPEAUIMMEndpointManager@@PEAUENDPOINT_DESCRIPTOR@@PEAPEAUIMMDevice@@@Z`
- size: `2612`
- prototype: `__int64 __fastcall(struct IMMEndpointManager *, struct ENDPOINT_DESCRIPTOR *, struct IMMDevice **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031ae0`

## callees

- `0x180004680`
- `0x180006b0c`
- `0x1800263ec`
- `0x180029024`
- `0x180034c5c`
- `0x180036f80`
- `0x18003e920`
- `0x180055054`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180055586`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180055586`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055a00`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800559f6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055a00`
- `ext-ms-win-audiocore-pal-l1-2-0!IsEndpointDefaultVolumeOverrideAllowed` at `0x1800557f7`
- `ext-ms-win-audiocore-pal-l1-2-0!IsEndpointDefaultVolumeOverrideAllowed` at `0x1800557f7`

## pseudocode

```c
__int64 __fastcall CAudioEndpointPluginBuilder::CreateEndpointPlugin(
        struct IMMEndpointManager *a1,
        struct ENDPOINT_DESCRIPTOR *a2,
        struct IMMDevice **a3)
{
  HRESULT v6; // ebx
  struct tWAVEFORMATEX *v7; // rdx
  __int64 v8; // rax
  WORD v9; // ax
  __int64 v10; // rcx
  int *v11; // rax
  struct IMMDevice *v12; // rax
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v19; // [rsp+70h] [rbp-90h] BYREF
  PROPVARIANT v20[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h] BYREF
  struct tWAVEFORMATEX *v23; // [rsp+98h] [rbp-68h] BYREF
  LPOLESTR lpsz; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h]
  PROPVARIANT v27[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  PROPVARIANT v29[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-18h]
  PROPVARIANT v31[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v32; // [rsp+100h] [rbp+0h]
  _BYTE v33[20]; // [rsp+108h] [rbp+8h] BYREF
  int v34; // [rsp+120h] [rbp+20h] BYREF
  GUID v35; // [rsp+124h] [rbp+24h]
  int v36; // [rsp+134h] [rbp+34h]
  int v37; // [rsp+138h] [rbp+38h]
  int v38; // [rsp+14Ch] [rbp+4Ch]
  int v39; // [rsp+15Ch] [rbp+5Ch]
  int v40; // [rsp+160h] [rbp+60h]
  int v41; // [rsp+170h] [rbp+70h]
  int v42; // [rsp+184h] [rbp+84h]
  int v43; // [rsp+198h] [rbp+98h]
  int v44; // [rsp+1ACh] [rbp+ACh]
  int v45; // [rsp+1C0h] [rbp+C0h]

  v17 = 0;
  v19 = 0;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  *(_OWORD *)pvar = 0;
  v26 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v22 = 0;
  v23 = 0;
  v18 = 0;
  memset(v33, 0, sizeof(v33));
  lpsz = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
  }
  *(_OWORD *)pvar = 0;
  v26 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, _QWORD, __int64, struct IUnknown **))(*(_QWORD *)a1 + 24LL))(
         a1,
         *((unsigned int *)a2 + 56),
         1,
         &v17);
  if ( v6 < 0 )
    goto LABEL_67;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))v17->lpVtbl[1].AddRef)(v17, 2, &v16);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 16);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &DEVPKEY_AudioEndpointPlugin_PnPInterface,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 7);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_Device_DeviceDesc,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 15);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_Device_EnumeratorName,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 9);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         PKEY_Endpoint_Device_NAME,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 19;
  DWORD2(v14) = *((_DWORD *)a2 + 57);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_AudioEndpoint_FormFactor,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 14);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_DeviceClass_IconPath,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  v15 = 0;
  LOWORD(v14) = 31;
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a2 + 5);
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         PKEY_Endpoint_Devnode,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v15 = 0;
  *(_QWORD *)&v14 = 72;
  *((_QWORD *)&v14 + 1) = (char *)a2 + 200;
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v22 = 100000;
  v14 = 0;
  LOWORD(v14) = 65;
  v15 = &v22;
  DWORD2(v14) = 8;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         PKEY_AudioEngine_Period,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  v14 = 0;
  LOWORD(v14) = 65;
  v15 = (__int64 *)*((_QWORD *)a2 + 33);
  DWORD2(v14) = *((_DWORD *)a2 + 64);
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_AudioEngine_DeviceFormat,
         &v14);
  if ( v6 < 0 )
    goto LABEL_67;
  CloneWaveFormat(*((const struct tWAVEFORMATEX **)a2 + 33), &v23);
  v7 = v23;
  if ( v23 )
  {
    if ( v23->wFormatTag == 1 )
    {
      v23->wFormatTag = 3;
      goto LABEL_26;
    }
    if ( v23->wFormatTag == 0xFFFE )
    {
      v8 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 - *(_QWORD *)((char *)&v23[1].nSamplesPerSec + 2);
      if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *(_QWORD *)((char *)&v23[1].nSamplesPerSec + 2) )
        v8 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 - *(_QWORD *)&v23[1].wBitsPerSample;
      if ( !v8 && (v23[1].wFormatTag & 7) == 0 )
      {
        *(GUID *)((char *)&v23[1].nSamplesPerSec + 2) = GUID_00000003_0000_0010_8000_00aa00389b71;
        v7[1].wFormatTag = 32;
LABEL_26:
        v7->wBitsPerSample = 32;
        v9 = 4 * v7->nChannels;
        v7->nBlockAlign = v9;
        v7->nAvgBytesPerSec = v7->nSamplesPerSec * v9;
      }
    }
  }
  v15 = (__int64 *)v7;
  LOWORD(v27[0]) = 11;
  LOWORD(v27[1]) = -1;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v16 + 48LL))(
         v16,
         PKEY_Endpoint_JackDetection,
         v27);
  if ( v6 < 0 )
    goto LABEL_69;
  LOWORD(v29[0]) = 11;
  LOWORD(v29[1]) = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v16 + 48LL))(
         v16,
         PKEY_Endpoint_InternalJack,
         v29);
  if ( v6 < 0 )
    goto LABEL_69;
  v6 = StringFromCLSID((const IID *const)((char *)a2 + 20), &lpsz);
  if ( v6 < 0 )
    goto LABEL_69;
  v15 = 0;
  *(_QWORD *)&v14 = 31;
  *((_QWORD *)&v14 + 1) = lpsz;
  v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v16 + 48LL))(
         v16,
         &PKEY_AudioEndpoint_JackSubType,
         &v14);
  if ( v6 >= 0 )
  {
    v10 = 180;
    v11 = &v34;
    do
    {
      *(_BYTE *)v11 = 0;
      v11 = (int *)((char *)v11 + 1);
      --v10;
    }
    while ( v10 );
    v36 = 1;
    v37 = 9;
    v38 = 3;
    v34 = 0;
    v35 = GUID_dff220e4_f70f_11d0_b917_00a0c9223196;
    v39 = 3;
    v40 = 2;
    v41 = 10;
    v42 = 10;
    v43 = 10;
    v44 = 10;
    v45 = 10;
    v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, _QWORD, _QWORD, _QWORD, int *, int *))(*(_QWORD *)a1 + 64LL))(
           a1,
           0,
           0,
           0,
           &v34,
           &v18);
    if ( v6 < 0 )
      goto LABEL_69;
    *(_QWORD *)v33 = 0x4924F3675A9125B7LL;
    *(_DWORD *)&v33[8] = 50913964;
    *(_QWORD *)&v33[12] = 1906615204;
    v14 = 0;
    v15 = 0;
    LOWORD(v14) = 19;
    DWORD2(v14) = v18;
    v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *))(*(_QWORD *)v16 + 48LL))(v16, v33, &v14);
    if ( v6 < 0 )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, _QWORD, __int64, _QWORD, int *, int *))(*(_QWORD *)a1 + 64LL))(
           a1,
           0,
           2,
           0,
           &v34,
           &v18);
    if ( v6 < 0 )
      goto LABEL_69;
    *(_QWORD *)v33 = 0x4924F3675A9125B7LL;
    *(_QWORD *)&v33[8] = 0x71A4A3A40308E2ACLL;
    *(_DWORD *)&v33[16] = 2;
    v14 = 0;
    v15 = 0;
    LOWORD(v14) = 19;
    DWORD2(v14) = v18;
    v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int128 *))(*(_QWORD *)v16 + 48LL))(v16, v33, &v14);
    if ( v6 < 0 )
      goto LABEL_69;
    if ( v19 != v17 )
      ATL::AtlComQIPtrAssign(&v19, v17, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21);
    v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *))(*(_QWORD *)a1 + 80LL))(a1);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, struct IUnknown *, __int64))(*(_QWORD *)a1 + 48LL))(
             a1,
             v17,
             1);
      if ( v6 >= 0 )
      {
        LOWORD(pvar[0]) = 11;
        LOWORD(pvar[1]) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v16 + 48LL))(
               v16,
               &PKEY_Devices_AudioDevice_RawProcessingSupported,
               pvar);
        if ( v6 >= 0 )
        {
          if ( !(unsigned int)IsEndpointDefaultVolumeOverrideAllowed()
            || (LOWORD(v31[0]) = 19,
                LODWORD(v31[1]) = -655360,
                v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v16 + 48LL))(
                       v16,
                       &PKEY_AudioEndpoint_Default_VolumeInDb,
                       v31),
                v6 >= 0) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
            }
            v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v16 + 40LL))(
                   v16,
                   PKEY_Endpoint_Flags,
                   v20);
            if ( v6 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
              }
              v6 = (*(__int64 (__fastcall **)(struct IMMEndpointManager *, struct IUnknown *, __int64))(*(_QWORD *)a1 + 40LL))(
                     a1,
                     v17,
                     1);
              if ( v6 >= 0 )
              {
                if ( LOWORD(v20[0]) == 19 && ((__int64)v20[1] & 1) != 0 )
                  goto LABEL_64;
                LOWORD(v20[0]) = 19;
                LODWORD(v20[1]) |= 1u;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
                }
                v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v16 + 48LL))(
                       v16,
                       PKEY_Endpoint_Flags,
                       v20);
                if ( v6 >= 0 )
                {
LABEL_64:
                  if ( (int)CAudioDeviceManager::CreateLocalAudioDevice(
                              (CAudioDeviceManager *)AvEndpointBuilder[2].LockSemaphore,
                              (struct IMMDevice *)v17) < 0
                    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
                  }
                  v12 = (struct IMMDevice *)v17;
                  v17 = 0;
                  *a3 = v12;
                }
              }
            }
          }
        }
      }
      goto LABEL_69;
    }
  }
LABEL_67:
  if ( v17 )
    (*(void (__fastcall **)(struct IMMEndpointManager *))(*(_QWORD *)a1 + 32LL))(a1);
LABEL_69:
  PropVariantClear(pvar);
  PropVariantClear(v27);
  PropVariantClear(v29);
  PropVariantClear(v20);
  PropVariantClear(v31);
  if ( v6 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180055054  push    rbp
0x180055056  push    rbx
0x180055057  push    rsi
0x180055058  push    rdi
0x180055059  push    r12
0x18005505b  push    r13
0x18005505d  push    r14
0x18005505f  lea     rbp, [rsp-0F0h]
0x180055067  sub     rsp, 1F0h
0x18005506e  mov     rax, cs:__security_cookie
0x180055075  xor     rax, rsp
0x180055078  mov     [rbp+120h+var_40], rax
0x18005507f  mov     r14, r8
0x180055082  mov     rdi, rdx
0x180055085  mov     rsi, rcx
0x180055088  mov     [rsp+220h+var_1C0], 0
0x180055091  mov     [rsp+220h+var_1B0], 0
0x18005509a  mov     [rsp+220h+var_1C8], 0
0x1800550a3  xorps   xmm0, xmm0
0x1800550a6  xor     eax, eax
0x1800550a8  movups  [rsp+220h+var_1E0], xmm0
0x1800550ad  mov     [rsp+220h+var_1D0], rax
0x1800550b2  xorps   xmm1, xmm1
0x1800550b5  movups  xmmword ptr [rbp+120h+pvar], xmm1
0x1800550b9  mov     [rbp+120h+var_168], rax
0x1800550bd  movups  xmmword ptr [rbp+120h+var_160], xmm0
0x1800550c1  mov     [rbp+120h+var_150], rax
0x1800550c5  movups  xmmword ptr [rbp+120h+var_148], xmm1
0x1800550c9  mov     [rbp+120h+var_138], rax
0x1800550cd  movups  xmmword ptr [rsp+220h+var_1A8], xmm0
0x1800550d2  mov     [rbp+120h+var_198], rax
0x1800550d6  movups  xmmword ptr [rbp+120h+var_130], xmm1
0x1800550da  mov     [rbp+120h+var_120], rax
0x1800550de  mov     [rbp+120h+var_190], rax
0x1800550e2  mov     [rbp+120h+var_188], rax
0x1800550e6  mov     [rsp+220h+var_1B8], eax
0x1800550ea  movups  [rbp+120h+var_118], xmm0
0x1800550ee  mov     [rbp+120h+var_108], eax
0x1800550f1  mov     [rbp+120h+lpsz], rax
0x1800550f5  lea     rax, WPP_GLOBAL_Control
0x1800550fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180055103  cmp     rcx, rax
0x180055106  jz      short loc_18005512C
0x180055108  test    dword ptr [rcx+1Ch], 80000h
0x18005510f  jz      short loc_18005512C
0x180055111  cmp     byte ptr [rcx+19h], 4
0x180055115  jb      short loc_18005512C
0x180055117  mov     edx, 10h
0x18005511c  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180055123  mov     rcx, [rcx+10h]
0x180055127  call    WPP_SF_
0x18005512c  xorps   xmm0, xmm0
0x18005512f  xor     eax, eax
0x180055131  movups  xmmword ptr [rbp+120h+pvar], xmm0
0x180055135  mov     [rbp+120h+var_168], rax
0x180055139  xorps   xmm1, xmm1
0x18005513c  movups  xmmword ptr [rbp+120h+var_160], xmm1
0x180055140  mov     [rbp+120h+var_150], rax
0x180055144  movups  xmmword ptr [rbp+120h+var_148], xmm0
0x180055148  mov     [rbp+120h+var_138], rax
0x18005514c  movups  xmmword ptr [rsp+220h+var_1A8], xmm1
0x180055151  mov     [rbp+120h+var_198], rax
0x180055155  movups  xmmword ptr [rbp+120h+var_130], xmm0
0x180055159  mov     [rbp+120h+var_120], rax
0x18005515d  mov     rax, [rsi]
0x180055160  lea     r9, [rsp+220h+var_1C0]
0x180055165  mov     r12d, 1
0x18005516b  mov     r8d, r12d
0x18005516e  mov     edx, [rdi+0E0h]
0x180055174  mov     rcx, rsi
0x180055177  mov     rax, [rax+18h]
0x18005517b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055180  mov     ebx, eax
0x180055182  test    eax, eax
0x180055184  js      loc_1800559BA
0x18005518a  mov     rcx, [rsp+220h+var_1C0]
0x18005518f  mov     rax, [rcx]
0x180055192  lea     r8, [rsp+220h+var_1C8]
0x180055197  lea     edx, [r12+1]
0x18005519c  mov     rax, [rax+20h]
0x1800551a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551a5  mov     ebx, eax
0x1800551a7  test    eax, eax
0x1800551a9  js      loc_1800559BA
0x1800551af  xorps   xmm0, xmm0
0x1800551b2  xor     eax, eax
0x1800551b4  movups  [rsp+220h+var_1E0], xmm0
0x1800551b9  mov     [rsp+220h+var_1D0], rax
0x1800551be  lea     r13d, [r12+1Eh]
0x1800551c3  mov     word ptr [rsp+220h+var_1E0], r13w
0x1800551c9  mov     rax, [rdi+80h]
0x1800551d0  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x1800551d5  mov     rcx, [rsp+220h+var_1C8]
0x1800551da  mov     rax, [rcx]
0x1800551dd  lea     r8, [rsp+220h+var_1E0]
0x1800551e2  lea     rdx, DEVPKEY_AudioEndpointPlugin_PnPInterface
0x1800551e9  mov     rax, [rax+30h]
0x1800551ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551f2  mov     ebx, eax
0x1800551f4  test    eax, eax
0x1800551f6  js      loc_1800559BA
0x1800551fc  xorps   xmm0, xmm0
0x1800551ff  xor     eax, eax
0x180055201  movups  [rsp+220h+var_1E0], xmm0
0x180055206  mov     [rsp+220h+var_1D0], rax
0x18005520b  mov     word ptr [rsp+220h+var_1E0], r13w
0x180055211  mov     rax, [rdi+38h]
0x180055215  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x18005521a  mov     rcx, [rsp+220h+var_1C8]
0x18005521f  mov     rax, [rcx]
0x180055222  lea     r8, [rsp+220h+var_1E0]
0x180055227  lea     rdx, PKEY_Device_DeviceDesc
0x18005522e  mov     rax, [rax+30h]
0x180055232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055237  mov     ebx, eax
0x180055239  test    eax, eax
0x18005523b  js      loc_1800559BA
0x180055241  xorps   xmm0, xmm0
0x180055244  xor     eax, eax
0x180055246  movups  [rsp+220h+var_1E0], xmm0
0x18005524b  mov     [rsp+220h+var_1D0], rax
0x180055250  mov     word ptr [rsp+220h+var_1E0], r13w
0x180055256  mov     rax, [rdi+78h]
0x18005525a  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x18005525f  mov     rcx, [rsp+220h+var_1C8]
0x180055264  mov     rax, [rcx]
0x180055267  lea     r8, [rsp+220h+var_1E0]
0x18005526c  lea     rdx, PKEY_Device_EnumeratorName
0x180055273  mov     rax, [rax+30h]
0x180055277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005527c  mov     ebx, eax
0x18005527e  test    eax, eax
0x180055280  js      loc_1800559BA
0x180055286  xorps   xmm0, xmm0
0x180055289  xor     eax, eax
0x18005528b  movups  [rsp+220h+var_1E0], xmm0
0x180055290  mov     [rsp+220h+var_1D0], rax
0x180055295  mov     word ptr [rsp+220h+var_1E0], r13w
0x18005529b  mov     rax, [rdi+48h]
0x18005529f  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x1800552a4  mov     rcx, [rsp+220h+var_1C8]
0x1800552a9  mov     rax, [rcx]
0x1800552ac  lea     r8, [rsp+220h+var_1E0]
0x1800552b1  lea     rdx, PKEY_Endpoint_Device_NAME
0x1800552b8  mov     rax, [rax+30h]
0x1800552bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552c1  mov     ebx, eax
0x1800552c3  test    eax, eax
0x1800552c5  js      loc_1800559BA
0x1800552cb  xorps   xmm0, xmm0
0x1800552ce  xor     eax, eax
0x1800552d0  movups  [rsp+220h+var_1E0], xmm0
0x1800552d5  mov     [rsp+220h+var_1D0], rax
0x1800552da  lea     eax, [r12+12h]
0x1800552df  mov     word ptr [rsp+220h+var_1E0], ax
0x1800552e4  mov     eax, [rdi+0E4h]
0x1800552ea  mov     dword ptr [rsp+220h+var_1E0+8], eax
0x1800552ee  mov     rcx, [rsp+220h+var_1C8]
0x1800552f3  mov     rax, [rcx]
0x1800552f6  lea     r8, [rsp+220h+var_1E0]
0x1800552fb  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x180055302  mov     rax, [rax+30h]
0x180055306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005530b  mov     ebx, eax
0x18005530d  test    eax, eax
0x18005530f  js      loc_1800559BA
0x180055315  xorps   xmm0, xmm0
0x180055318  xor     eax, eax
0x18005531a  movups  [rsp+220h+var_1E0], xmm0
0x18005531f  mov     [rsp+220h+var_1D0], rax
0x180055324  mov     word ptr [rsp+220h+var_1E0], r13w
0x18005532a  mov     rax, [rdi+70h]
0x18005532e  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x180055333  mov     rcx, [rsp+220h+var_1C8]
0x180055338  mov     rax, [rcx]
0x18005533b  lea     r8, [rsp+220h+var_1E0]
0x180055340  lea     rdx, PKEY_DeviceClass_IconPath
0x180055347  mov     rax, [rax+30h]
0x18005534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055350  mov     ebx, eax
0x180055352  test    eax, eax
0x180055354  js      loc_1800559BA
0x18005535a  xorps   xmm0, xmm0
0x18005535d  xor     eax, eax
0x18005535f  movups  [rsp+220h+var_1E0], xmm0
0x180055364  mov     [rsp+220h+var_1D0], rax
0x180055369  mov     word ptr [rsp+220h+var_1E0], r13w
0x18005536f  mov     rax, [rdi+28h]
0x180055373  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x180055378  mov     rcx, [rsp+220h+var_1C8]
0x18005537d  mov     rax, [rcx]
0x180055380  lea     r8, [rsp+220h+var_1E0]
0x180055385  lea     rdx, PKEY_Endpoint_Devnode
0x18005538c  mov     rax, [rax+30h]
0x180055390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055395  mov     ebx, eax
0x180055397  test    eax, eax
0x180055399  js      loc_1800559BA
0x18005539f  xorps   xmm0, xmm0
0x1800553a2  xor     eax, eax
0x1800553a4  movups  [rsp+220h+var_1E0], xmm0
0x1800553a9  mov     [rsp+220h+var_1D0], rax
0x1800553ae  lea     eax, [r12+47h]
0x1800553b3  mov     word ptr [rsp+220h+var_1E0], ax
0x1800553b8  lea     rax, [rdi+0C8h]
0x1800553bf  mov     qword ptr [rsp+220h+var_1E0+8], rax
0x1800553c4  mov     rcx, [rsp+220h+var_1C8]
0x1800553c9  mov     rax, [rcx]
0x1800553cc  lea     r8, [rsp+220h+var_1E0]
0x1800553d1  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x1800553d8  mov     rax, [rax+30h]
0x1800553dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553e1  mov     ebx, eax
0x1800553e3  test    eax, eax
0x1800553e5  js      loc_1800559BA
0x1800553eb  mov     [rbp+120h+var_190], 186A0h
0x1800553f3  xorps   xmm0, xmm0
0x1800553f6  movups  [rsp+220h+var_1E0], xmm0
0x1800553fb  lea     eax, [r12+40h]
0x180055400  mov     word ptr [rsp+220h+var_1E0], ax
0x180055405  lea     rax, [rbp+120h+var_190]
0x180055409  mov     [rsp+220h+var_1D0], rax
0x18005540e  mov     dword ptr [rsp+220h+var_1E0+8], 8
0x180055416  mov     rcx, [rsp+220h+var_1C8]
0x18005541b  mov     rax, [rcx]
0x18005541e  lea     r8, [rsp+220h+var_1E0]
0x180055423  lea     rdx, PKEY_AudioEngine_Period
0x18005542a  mov     rax, [rax+30h]
0x18005542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055433  mov     ebx, eax
0x180055435  test    eax, eax
0x180055437  js      loc_1800559BA
0x18005543d  xorps   xmm0, xmm0
0x180055440  movups  [rsp+220h+var_1E0], xmm0
0x180055445  lea     eax, [r12+40h]
0x18005544a  mov     word ptr [rsp+220h+var_1E0], ax
0x18005544f  mov     rax, [rdi+108h]
0x180055456  mov     [rsp+220h+var_1D0], rax
0x18005545b  mov     eax, [rdi+100h]
0x180055461  mov     dword ptr [rsp+220h+var_1E0+8], eax
0x180055465  mov     rcx, [rsp+220h+var_1C8]
0x18005546a  mov     rax, [rcx]
0x18005546d  lea     r8, [rsp+220h+var_1E0]
0x180055472  lea     rdx, PKEY_AudioEngine_DeviceFormat
0x180055479  mov     rax, [rax+30h]
0x18005547d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055482  mov     ebx, eax
0x180055484  test    eax, eax
0x180055486  js      loc_1800559BA
0x18005548c  lea     rdx, [rbp+120h+var_188]; struct tWAVEFORMATEX **
0x180055490  mov     rcx, [rdi+108h]; Src
0x180055497  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18005549c  mov     rdx, [rbp+120h+var_188]
0x1800554a0  test    rdx, rdx
0x1800554a3  jz      short loc_18005550E
0x1800554a5  lea     ecx, [r12+1Fh]
0x1800554aa  cmp     r12w, [rdx]
0x1800554ae  jz      short loc_1800554EF
0x1800554b0  mov     eax, 0FFFEh
0x1800554b5  cmp     ax, [rdx]
0x1800554b8  jnz     short loc_18005550E
0x1800554ba  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1
0x1800554c1  sub     rax, [rdx+18h]
0x1800554c5  jnz     short loc_1800554D2
0x1800554c7  mov     rax, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4
0x1800554ce  sub     rax, [rdx+20h]
0x1800554d2  test    rax, rax
0x1800554d5  jnz     short loc_18005550E
0x1800554d7  test    byte ptr [rdx+12h], 7
0x1800554db  jnz     short loc_18005550E
0x1800554dd  movups  xmm0, xmmword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1
0x1800554e4  movdqu  xmmword ptr [rdx+18h], xmm0
0x1800554e9  mov     [rdx+12h], cx
0x1800554ed  jmp     short loc_1800554F4
0x1800554ef  mov     word ptr [rdx], 3
0x1800554f4  mov     [rdx+0Eh], cx
0x1800554f8  movzx   eax, word ptr [rdx+2]
0x1800554fc  shl     ax, 2
0x180055500  movzx   ecx, ax
0x180055503  mov     [rdx+0Ch], cx
0x180055507  imul    ecx, [rdx+4]
0x18005550b  mov     [rdx+8], ecx
0x18005550e  mov     [rsp+220h+var_1D0], rdx
0x180055513  mov     eax, 0Bh
0x180055518  mov     word ptr [rbp+120h+var_160], ax
0x18005551c  or      eax, 0FFFFFFFFh
0x18005551f  mov     word ptr [rbp+120h+var_160+8], ax
0x180055523  mov     rcx, [rsp+220h+var_1C8]
0x180055528  mov     rax, [rcx]
0x18005552b  lea     r8, [rbp+120h+var_160]
0x18005552f  lea     rdx, PKEY_Endpoint_JackDetection
0x180055536  mov     rax, [rax+30h]
0x18005553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005553f  mov     ebx, eax
0x180055541  test    eax, eax
0x180055543  js      loc_1800559D3
0x180055549  mov     eax, 0Bh
0x18005554e  mov     word ptr [rbp+120h+var_148], ax
0x180055552  xor     eax, eax
0x180055554  mov     word ptr [rbp+120h+var_148+8], ax
  ... truncated ...
```
