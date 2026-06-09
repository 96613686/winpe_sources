# CEndpointInstance::CreateDeviceEndpointInstance(AUDIO_DEVICE_PIPE_DESCRIPTOR *,IUnknown *,CEndpointInstance * *)

- ea: `0x140049370`
- end: `0x140049e46`
- name: `?CreateDeviceEndpointInstance@CEndpointInstance@@SAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@PEAUIUnknown@@PEAPEAV1@@Z`
- size: `2774`
- prototype: `__int64 __fastcall(struct AUDIO_DEVICE_PIPE_DESCRIPTOR *, struct IUnknown *, struct CEndpointInstance **)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140049198`

## callees

- `0x140004df0`
- `0x140005a20`
- `0x140008124`
- `0x140008bd4`
- `0x140009aa4`
- `0x14000a39c`
- `0x14000c33c`
- `0x14000e11c`
- `0x14000e280`
- `0x14000e404`
- `0x140011e00`
- `0x1400127bc`
- `0x140014d08`
- `0x140019830`
- `0x14003b9a8`
- `0x140049370`
- `0x140049fa0`
- `0x14005d0e0`
- `0x14005d148`
- `0x14005e150`
- `0x1400b5010`

## import_xrefs

- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140049791`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140049822`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140049791`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140049822`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004976c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400497dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004976c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400497dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400495f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400495f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400498ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400498d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049bf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400498ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400498d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049b22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140049bf0`

## string_xrefs

- `0x1400493b4`: `EndpointInstance_CreateDeviceEndpointInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CEndpointInstance::CreateDeviceEndpointInstance(
        struct AUDIO_DEVICE_PIPE_DESCRIPTOR *a1,
        struct IUnknown *a2,
        struct CEndpointInstance **a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // r8d
  int v16; // ecx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // edi
  int v25; // ecx
  int v26; // r8d
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rdx
  unsigned int *v32; // r14
  _DWORD *v33; // rbx
  int v34; // eax
  __int64 v35; // rcx
  char *v36; // rdi
  __int64 v37; // rdx
  int v38; // eax
  __int64 (__fastcall **v39)(_QWORD, _QWORD, _QWORD); // rax
  int v40; // r15d
  __int64 v41; // rdx
  int v42; // ecx
  int v43; // r8d
  __int64 v44; // rcx
  __int64 (__fastcall **v45)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  int v48; // r14d
  __int64 v49; // rdx
  int v50; // ecx
  int v51; // r8d
  __int64 v52; // rcx
  int v53; // eax
  int v54; // eax
  int v55; // eax
  void *v56; // rax
  CEndpointInstance *v57; // rsi
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, int *); // rbx
  int v60; // eax
  __int64 v61; // rdx
  unsigned int v62; // edx
  int v63; // ecx
  int v64; // r8d
  int ppv; // [rsp+20h] [rbp-F0h]
  int ppvb; // [rsp+20h] [rbp-F0h]
  int ppva; // [rsp+20h] [rbp-F0h]
  __int64 v69; // [rsp+90h] [rbp-80h] BYREF
  __int64 v70; // [rsp+98h] [rbp-78h] BYREF
  struct IAudioEndpointRT *v71; // [rsp+A0h] [rbp-70h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, GUID *, struct IUnknown **); // [rsp+A8h] [rbp-68h] BYREF
  LPVOID v73; // [rsp+B0h] [rbp-60h] BYREF
  struct IUnknown *v74; // [rsp+B8h] [rbp-58h] BYREF
  int v75[2]; // [rsp+C0h] [rbp-50h] BYREF
  int v76[2]; // [rsp+C8h] [rbp-48h] BYREF
  int v77[2]; // [rsp+D0h] [rbp-40h] BYREF
  int v78; // [rsp+D8h] [rbp-38h] BYREF
  __int64 v79; // [rsp+E0h] [rbp-30h] BYREF
  void *v80; // [rsp+E8h] [rbp-28h] BYREF
  char v81; // [rsp+F1h] [rbp-1Fh]
  __int128 v82; // [rsp+F8h] [rbp-18h] BYREF
  char *v83; // [rsp+108h] [rbp-8h]
  LARGE_INTEGER PerformanceCount; // [rsp+110h] [rbp+0h] BYREF
  _QWORD v85[2]; // [rsp+200h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+148h]

  v6 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(&PerformanceCount, v6, "EndpointInstance_CreateDeviceEndpointInstance", 0);
  v9 = (_QWORD *)((char *)a1 + 56);
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v8, v7, *v9, *((unsigned int *)a1 + 25));
  v81 = 1;
  v69 = 0;
  v71 = 0;
  if ( a2 )
  {
    v10 = *((_QWORD *)a1 + 4);
    v11 = *((_QWORD *)a1 + 1);
    v12 = *v9;
    v69 = 0;
    *(_QWORD *)v75 = v10;
    *(_QWORD *)v77 = v11;
    *(_QWORD *)v76 = v12;
    v74 = a2;
    v13 = Microsoft::WRL::Details::MakeAndInitialize<CAudioEndpoint_Dsp,IAudioEndpoint,IUnknown * &,unsigned short const * &,tWAVEFORMATEX * &,__int64 &>(
            (unsigned int)&v69,
            (unsigned int)&v74,
            (unsigned int)v76,
            (unsigned int)v77,
            (__int64)v75);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audioendpoint_dsp.cpp",
        (const char *)(unsigned int)v13,
        ppv);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)v14,
        ppvb);
      if ( v71 )
        ((void (__fastcall *)(struct IAudioEndpointRT *))v71->lpVtbl->Release)(v71);
      v16 = v69;
      if ( v69 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      goto LABEL_17;
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(&v71);
    (**(void (__fastcall ***)(__int64, GUID *, struct IAudioEndpointRT **))v69)(
      v69,
      &GUID_dfd2005f_a6e5_4d39_a265_939ada9fbb4d,
      &v71);
    goto LABEL_96;
  }
  v70 = 0;
  if ( *((_DWORD *)a1 + 25) != 1 )
  {
    v73 = 0;
    v23 = CoCreateInstance(
            &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
            0,
            0x17u,
            &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
            &v73);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v23,
        ppva);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
      if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v25,
          (unsigned int)CreateDeviceEndpointInstance_Task_Stop,
          v26,
          1,
          (__int64)v85);
      v14 = v24;
      goto LABEL_111;
    }
    v72 = 0;
    v27 = *(_QWORD *)v73;
    v72 = 0;
    v28 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(v27 + 40))(v73, *v9, &v72);
    v14 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v28,
        ppva);
LABEL_31:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
      goto LABEL_15;
    }
    v74 = 0;
    v29 = (**v72)(v72, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21, &v74);
    v14 = v29;
    if ( v29 < 0 )
    {
      v30 = (unsigned int)v29;
      v31 = 110;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)v30,
        ppva);
LABEL_35:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
      goto LABEL_31;
    }
    if ( !v74 )
    {
      v14 = -2147024809;
      v30 = 2147942487LL;
      v31 = 111;
      goto LABEL_34;
    }
    v32 = (unsigned int *)*((_QWORD *)a1 + 1);
    v82 = 0;
    v83 = 0;
    LOWORD(v82) = 65;
    v33 = 0;
    v80 = 0;
    *(_QWORD *)v75 = 0;
    v34 = ((__int64 (__fastcall *)(struct IUnknown *))v74->lpVtbl[2].QueryInterface)(v74);
    v35 = *((unsigned __int16 *)v32 + 8);
    if ( v34 )
    {
      v33 = CoTaskMemAlloc(v35 + 32);
      v80 = v33;
      if ( !v33 )
      {
        v37 = 141;
        goto LABEL_44;
      }
      *v33 = *((unsigned __int16 *)v32 + 8) + 32;
      v33[1] = GetSessionIdFromEndpointId(*((_QWORD *)a1 + 7));
      v33[2] = *((_DWORD *)a1 + 25);
      memcpy_0(v33 + 3, v32, *((unsigned __int16 *)v32 + 8) + 18LL);
      v38 = *((unsigned __int16 *)v32 + 8) + 32;
      v83 = (char *)v33;
      v36 = 0;
    }
    else
    {
      v36 = (char *)CoTaskMemAlloc(v35 + 64);
      *(_QWORD *)v75 = v36;
      if ( !v36 )
      {
        v37 = 126;
LABEL_44:
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)0x8007000ELL,
          ppva);
        goto LABEL_35;
      }
      *(_DWORD *)v36 = *((unsigned __int16 *)v32 + 8) + 64;
      *((_DWORD *)v36 + 1) = GetSessionIdFromEndpointId(*((_QWORD *)a1 + 7));
      *((_DWORD *)v36 + 2) = *((_DWORD *)a1 + 25);
      *(_OWORD *)(v36 + 12) = *(_OWORD *)((char *)a1 + 104);
      *(_OWORD *)(v36 + 28) = *(_OWORD *)((char *)a1 + 148);
      memcpy_0(v36 + 44, v32, *((unsigned __int16 *)v32 + 8) + 18LL);
      v38 = *((unsigned __int16 *)v32 + 8) + 64;
      v83 = v36;
    }
    DWORD2(v82) = v38;
    if ( !*((_DWORD *)a1 + 18) )
    {
      *(_QWORD *)v76 = 0;
      v39 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v72;
      *(_QWORD *)v76 = 0;
      v40 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **), GUID *, __int64, __int128 *))v39[3])(
              v72,
              &GUID_8fa906e4_c31c_4e31_932e_19a66385e9aa,
              1,
              &v82);
      if ( v40 < 0 )
      {
        v41 = 162;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
          (const char *)(unsigned int)v40,
          (int)v76);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v76);
LABEL_50:
        if ( v36 )
          CoTaskMemFree(v36);
        if ( v33 )
          CoTaskMemFree(v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
        if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            v42,
            (unsigned int)CreateDeviceEndpointInstance_Task_Stop,
            v43,
            1,
            (__int64)v85);
        v14 = v40;
        goto LABEL_111;
      }
      v44 = v70;
      v70 = 0;
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v40 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v76)(
              *(_QWORD *)v76,
              &GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac,
              &v70);
      if ( v40 < 0 )
      {
        v41 = 164;
        goto LABEL_49;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v76);
LABEL_70:
      AEWMILOG_ENDPOINT_ACTIVATION(
        *((_DWORD *)a1 + 20) != 0,
        0,
        *((_WORD *)v32 + 7),
        *(_WORD *)v32,
        *((_DWORD *)a1 + 34),
        *((_DWORD *)a1 + 25),
        *((_DWORD *)a1 + 18),
        *((_DWORD *)a1 + 35),
        *(unsigned __int16 *)v32,
        v32[1],
        *((unsigned __int16 *)v32 + 7),
        *((unsigned __int16 *)v32 + 1),
        *((_DWORD *)a1 + 8),
        *((_DWORD *)a1 + 19),
        *((_DWORD *)a1 + 20) != 0,
        *((_DWORD *)a1 + 24),
        0);
      wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(&v71);
      v48 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IAudioEndpointRT **))v70)(
              v70,
              &GUID_dfd2005f_a6e5_4d39_a265_939ada9fbb4d,
              &v71);
      if ( v48 >= 0 )
      {
        v52 = v69;
        v69 = 0;
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        v48 = ((__int64 (__fastcall *)(struct IAudioEndpointRT *, GUID *, __int64 *))v71->lpVtbl->QueryInterface)(
                v71,
                &GUID_30a99515_1527_4451_af9f_00c5f0234daf,
                &v69);
        if ( v48 >= 0 )
        {
          if ( v36 )
            CoTaskMemFree(v36);
          if ( v33 )
            CoTaskMemFree(v33);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
          goto LABEL_88;
        }
        v49 = 200;
      }
      else
      {
        v49 = 197;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v48,
        ppv);
      if ( v36 )
        CoTaskMemFree(v36);
      if ( v33 )
        CoTaskMemFree(v33);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v74);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
      if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v50,
          (unsigned int)CreateDeviceEndpointInstance_Task_Stop,
          v51,
          1,
          (__int64)v85);
      v14 = v48;
      goto LABEL_111;
    }
    *(_QWORD *)v77 = 0;
    v45 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v72;
    *(_QWORD *)v77 = 0;
    v40 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **), GUID *, __int64, __int128 *))v45[3])(
            v72,
            &GUID_8026ab61_92b2_43c1_a1df_5c37ebd08d82,
            1,
            &v82);
    if ( v40 >= 0 )
    {
      v47 = v70;
      v70 = 0;
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v40 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v77)(
              *(_QWORD *)v77,
              &GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac,
              &v70);
      if ( v40 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v77);
        goto LABEL_70;
      }
      v46 = 177;
    }
    else
    {
      v46 = 175;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)(unsigned int)v40,
      (int)v77);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v77);
    goto LABEL_50;
  }
  v17 = *((_QWORD *)a1 + 8);
  if ( !v17 )
  {
    v14 = -2147024809;
    v18 = 2147942487LL;
    v19 = 88;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)v18,
      ppv);
LABEL_15:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
LABEL_16:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
LABEL_17:
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v16,
        (unsigned int)CreateDeviceEndpointInstance_Task_Stop,
        v15,
        1,
        (__int64)v85);
    goto LABEL_111;
  }
  wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(&v69, v17);
  v20 = v70;
  v70 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v69)(
          v69,
          &GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac,
          &v70);
  v14 = v21;
  if ( v21 < 0 )
  {
    v18 = (unsigned int)v21;
    v19 = 94;
    goto LABEL_14;
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(&v71);
  v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IAudioEndpointRT **))v69)(
          v69,
          &GUID_dfd2005f_a6e5_4d39_a265_939ada9fbb4d,
          &v71);
  v14 = v22;
  if ( v22 < 0 )
  {
    v18 = (unsigned int)v22;
    v19 = 97;
    goto LABEL_14;
  }
LABEL_88:
  v78 = 0;
  v53 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v70 + 40LL))(v70, &v78);
  v14 = v53;
  if ( v53 < 0 )
  {
    v18 = (unsigned int)v53;
    v19 = 205;
    goto LABEL_14;
  }
  if ( v78 )
  {
    v54 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 48LL))(v69, 0x40000);
    v14 = v54;
    if ( v54 < 0 )
    {
      v18 = (unsigned int)v54;
      v19 = 211;
      goto LABEL_14;
    }
  }
  v55 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v70 + 24LL))(
          v70,
          *((_QWORD *)a1 + 4),
          *((unsigned int *)a1 + 12));
  v14 = v55;
  if ( v55 < 0 )
  {
    v18 = (unsigned int)v55;
    v19 = 218;
    goto LABEL_14;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v70);
LABEL_96:
  v56 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v80 = v56;
  if ( v56 )
    v57 = CEndpointInstance::CEndpointInstance((CEndpointInstance *)v56, v71, *((_QWORD *)a1 + 4));
  else
    v57 = 0;
  v85[0] = v57;
  if ( !v57 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
      (const char *)0x8007000ELL,
      ppv);
    goto LABEL_16;
  }
  v79 = 0;
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v69)(v69, &GUID_44b2c783_5fa3_4983_9d74_9207de1f9e63, &v79) >= 0 )
  {
    *(_QWORD *)v75 = 0;
    v58 = v79;
    v59 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v79 + 64LL);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v75,
      0);
    v60 = v59(v58, v75);
    v14 = v60;
    if ( v60 < 0 )
    {
      v61 = 235;
LABEL_104:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\endpointinstance.cpp",
        (const char *)(unsigned int)v60,
        ppv);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
      CEndpointInstance::`scalar deleting destructor'(v57, v62);
      goto LABEL_16;
    }
    v80 = *(void **)v75;
    v60 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Media::Devices::AudioDeviceModulesManager,Windows::Media::Devices::IAudioDeviceModulesManager,void *>(
            (_QWORD *)v57 + 2,
            &v80);
    v14 = v60;
    if ( v60 < 0 )
    {
      v61 = 238;
      goto LABEL_104;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v75);
  }
  *a3 = v57;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v69);
  if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      v63,
      (unsigned int)CreateDeviceEndpointInstance_Task_Stop,
      v64,
      1,
      (__int64)v85);
  v14 = 0;
LABEL_111:
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  return v14;
}

```

## disassembly

```asm
0x140049370  mov     [rsp-8+arg_18], rbx
0x140049375  push    rbp
0x140049376  push    rsi
0x140049377  push    rdi
0x140049378  push    r12
0x14004937a  push    r13
0x14004937c  push    r14
0x14004937e  push    r15
0x140049380  lea     rbp, [rsp-110h]
0x140049388  sub     rsp, 220h
0x14004938f  mov     rax, cs:__security_cookie
0x140049396  xor     rax, rsp
0x140049399  mov     [rbp+140h+var_40], rax
0x1400493a0  mov     r12, r8
0x1400493a3  mov     r14, rdx
0x1400493a6  mov     rsi, rcx
0x1400493a9  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x1400493ae  mov     rdx, rax; struct _tlgProvider_t *
0x1400493b1  xor     r9d, r9d; char *
0x1400493b4  lea     r8, aEndpointinstan; "EndpointInstance_CreateDeviceEndpointIn"...
0x1400493bb  lea     rcx, [rbp+140h+PerformanceCount]; lpPerformanceCount
0x1400493bf  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x1400493c4  nop
0x1400493c5  lea     rbx, [rsi+38h]
0x1400493c9  test    cs:Microsoft_Windows_AudioEnableBits, 20h
0x1400493d0  jz      short loc_1400493DE
0x1400493d2  mov     r9d, [rsi+64h]
0x1400493d6  mov     r8, [rbx]
0x1400493d9  call    McTemplateU0zq_EtwEventWriteTransfer
0x1400493de  mov     r15d, 1
0x1400493e4  mov     [rbp+140h+var_15F], r15b
0x1400493e8  xor     r13d, r13d
0x1400493eb  mov     [rbp+140h+var_1C0], r13
0x1400493ef  mov     [rbp+140h+var_1B0], r13
0x1400493f3  test    r14, r14
0x1400493f6  jz      loc_1400494CA
0x1400493fc  mov     rax, [rsi+20h]
0x140049400  mov     rcx, [rsi+8]
0x140049404  mov     rdx, [rbx]
0x140049407  mov     [rbp+140h+var_1C0], r13
0x14004940b  mov     qword ptr [rbp+140h+var_190], rax
0x14004940f  mov     qword ptr [rbp+140h+var_180], rcx
0x140049413  mov     qword ptr [rbp+140h+var_188], rdx
0x140049417  mov     [rbp+140h+var_198], r14
0x14004941b  lea     rax, [rbp+140h+var_190]
0x14004941f  mov     [rsp+250h+ppv], rax; int
0x140049424  lea     r9, [rbp+140h+var_180]
0x140049428  lea     r8, [rbp+140h+var_188]
0x14004942c  lea     rdx, [rbp+140h+var_198]
0x140049430  lea     rcx, [rbp+140h+var_1C0]
0x140049434  call    ??$MakeAndInitialize@VCAudioEndpoint_Dsp@@UIAudioEndpoint@@AEAPEAUIUnknown@@AEAPEBGAEAPEAUtWAVEFORMATEX@@AEA_J@Details@WRL@Microsoft@@YAJPEAPEAUIAudioEndpoint@@AEAPEAUIUnknown@@AEAPEBGAEAPEAUtWAVEFORMATEX@@AEA_J@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioEndpoint_Dsp,IAudioEndpoint,IUnknown * &,ushort const * &,tWAVEFORMATEX * &,__int64 &>(IAudioEndpoint * *,IUnknown * &,ushort const * &,tWAVEFORMATEX * &,__int64 &)
0x140049439  mov     ebx, eax
0x14004943b  test    eax, eax
0x14004943d  jns     short loc_1400494A2
0x14004943f  mov     rcx, [rbp+148h]; this
0x140049446  mov     r9d, eax; char *
0x140049449  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140049450  lea     edx, [r15+54h]; void *
0x140049454  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049459  mov     rcx, [rbp+148h]; this
0x140049460  mov     r9d, ebx; char *
0x140049463  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14004946a  lea     edx, [r15+4Dh]; void *
0x14004946e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049473  nop
0x140049474  mov     rcx, [rbp+140h+var_1B0]
0x140049478  test    rcx, rcx
0x14004947b  jz      short loc_14004948A
0x14004947d  mov     rax, [rcx]
0x140049480  mov     rax, [rax+10h]
0x140049484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049489  nop
0x14004948a  mov     rcx, [rbp+140h+var_1C0]
0x14004948e  test    rcx, rcx
0x140049491  jz      short loc_1400494A0
0x140049493  mov     rax, [rcx]
0x140049496  mov     rax, [rax+10h]
0x14004949a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004949f  nop
0x1400494a0  jmp     short loc_140049520
0x1400494a2  lea     rcx, [rbp+140h+var_1B0]
0x1400494a6  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x1400494ab  mov     rcx, [rbp+140h+var_1C0]
0x1400494af  mov     rax, [rcx]
0x1400494b2  lea     r8, [rbp+140h+var_1B0]
0x1400494b6  lea     rdx, _GUID_dfd2005f_a6e5_4d39_a265_939ada9fbb4d
0x1400494bd  mov     rax, [rax]
0x1400494c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400494c5  jmp     loc_140049CA7
0x1400494ca  mov     [rbp+140h+var_1B8], r13
0x1400494ce  cmp     [rsi+64h], r15d
0x1400494d2  jnz     loc_1400495D8
0x1400494d8  mov     rdx, [rsi+40h]
0x1400494dc  test    rdx, rdx
0x1400494df  jnz     short loc_14004954D
0x1400494e1  mov     ebx, 80070057h
0x1400494e6  mov     r9d, ebx; char *
0x1400494e9  mov     edx, 58h ; 'X'; void *
0x1400494ee  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400494f5  mov     rcx, [rbp+148h]; this
0x1400494fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049501  nop
0x140049502  lea     rcx, [rbp+140h+var_1B8]
0x140049506  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004950b  nop
0x14004950c  lea     rcx, [rbp+140h+var_1B0]
0x140049510  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140049515  nop
0x140049516  lea     rcx, [rbp+140h+var_1C0]
0x14004951a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004951f  nop
0x140049520  test    cs:Microsoft_Windows_AudioEnableBits, 20h
0x140049527  jz      loc_140049E11
0x14004952d  lea     rax, [rbp+140h+var_50]
0x140049534  mov     [rsp+250h+ppv], rax
0x140049539  mov     r9d, r15d
0x14004953c  lea     rdx, CreateDeviceEndpointInstance_Task_Stop
0x140049543  call    McGenEventWrite_EtwEventWriteTransfer
0x140049548  jmp     loc_140049E11
0x14004954d  lea     rcx, [rbp+140h+var_1C0]
0x140049551  call    ??4?$com_ptr_t@UISubmix@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUISubmix@@@Z; wil::com_ptr_t<ISubmix,wil::err_returncode_policy>::operator=(ISubmix *)
0x140049556  nop
0x140049557  mov     rcx, [rbp+140h+var_1B8]
0x14004955b  mov     [rbp+140h+var_1B8], r13
0x14004955f  test    rcx, rcx
0x140049562  jz      short loc_140049571
0x140049564  mov     rax, [rcx]
0x140049567  mov     rax, [rax+10h]
0x14004956b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049570  nop
0x140049571  mov     rcx, [rbp+140h+var_1C0]
0x140049575  mov     rax, [rcx]
0x140049578  lea     r8, [rbp+140h+var_1B8]
0x14004957c  lea     rdx, _GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac
0x140049583  mov     rax, [rax]
0x140049586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004958b  mov     ebx, eax
0x14004958d  test    eax, eax
0x14004958f  jns     short loc_14004959E
0x140049591  mov     r9d, eax
0x140049594  mov     edx, 5Eh ; '^'
0x140049599  jmp     loc_1400494EE
0x14004959e  lea     rcx, [rbp+140h+var_1B0]
0x1400495a2  call    ?reset@?$com_ptr_t@U?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *>,wil::err_returncode_policy>::reset(void)
0x1400495a7  mov     rcx, [rbp+140h+var_1C0]
0x1400495ab  mov     rax, [rcx]
0x1400495ae  lea     r8, [rbp+140h+var_1B0]
0x1400495b2  lea     rdx, _GUID_dfd2005f_a6e5_4d39_a265_939ada9fbb4d
0x1400495b9  mov     rax, [rax]
0x1400495bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400495c1  mov     ebx, eax
0x1400495c3  test    eax, eax
0x1400495c5  jns     loc_140049C1A
0x1400495cb  mov     r9d, eax
0x1400495ce  mov     edx, 61h ; 'a'
0x1400495d3  jmp     loc_1400494EE
0x1400495d8  mov     [rbp+140h+var_1A0], r13
0x1400495dc  lea     rax, [rbp+140h+var_1A0]
0x1400495e0  mov     [rsp+250h+ppv], rax; int
0x1400495e5  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1400495ec  xor     edx, edx; pUnkOuter
0x1400495ee  lea     r8d, [rdx+17h]; dwClsContext
0x1400495f2  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1400495f9  call    cs:__imp_CoCreateInstance
0x1400495ff  mov     edi, eax
0x140049601  test    eax, eax
0x140049603  jns     short loc_140049674
0x140049605  mov     rcx, [rbp+148h]; this
0x14004960c  mov     r9d, eax; char *
0x14004960f  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140049616  mov     edx, 67h ; 'g'; void *
0x14004961b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140049620  nop
0x140049621  lea     rcx, [rbp+140h+var_1A0]
0x140049625  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004962a  nop
0x14004962b  lea     rcx, [rbp+140h+var_1B8]
0x14004962f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140049634  nop
0x140049635  lea     rcx, [rbp+140h+var_1B0]
0x140049639  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14004963e  nop
0x14004963f  lea     rcx, [rbp+140h+var_1C0]
0x140049643  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140049648  nop
0x140049649  test    cs:Microsoft_Windows_AudioEnableBits, 20h
0x140049650  jz      short loc_14004966D
0x140049652  lea     rax, [rbp+140h+var_50]
0x140049659  mov     [rsp+250h+ppv], rax
0x14004965e  mov     r9d, r15d
0x140049661  lea     rdx, CreateDeviceEndpointInstance_Task_Stop
0x140049668  call    McGenEventWrite_EtwEventWriteTransfer
0x14004966d  mov     ebx, edi
0x14004966f  jmp     loc_140049E11
0x140049674  mov     [rbp+140h+var_1A8], r13
0x140049678  mov     rcx, [rbp+140h+var_1A0]
0x14004967c  mov     rax, [rcx]
0x14004967f  mov     [rbp+140h+var_1A8], r13
0x140049683  lea     r8, [rbp+140h+var_1A8]
0x140049687  mov     rdx, [rbx]
0x14004968a  mov     rax, [rax+28h]
0x14004968e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049693  mov     ebx, eax
0x140049695  test    eax, eax
0x140049697  jns     short loc_1400496CD
0x140049699  mov     rcx, [rbp+148h]; this
0x1400496a0  mov     r9d, eax; char *
0x1400496a3  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400496aa  mov     edx, 6Bh ; 'k'; void *
0x1400496af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400496b4  nop
0x1400496b5  lea     rcx, [rbp+140h+var_1A8]
0x1400496b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400496be  nop
0x1400496bf  lea     rcx, [rbp+140h+var_1A0]
0x1400496c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400496c8  jmp     loc_140049502
0x1400496cd  mov     [rbp+140h+var_198], r13
0x1400496d1  mov     rcx, [rbp+140h+var_1A8]
0x1400496d5  mov     rax, [rcx]
0x1400496d8  lea     r8, [rbp+140h+var_198]
0x1400496dc  lea     rdx, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21
0x1400496e3  mov     rax, [rax]
0x1400496e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400496eb  mov     ebx, eax
0x1400496ed  test    eax, eax
0x1400496ef  jns     short loc_140049718
0x1400496f1  mov     r9d, eax; char *
0x1400496f4  mov     edx, 6Eh ; 'n'; void *
0x1400496f9  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140049700  mov     rcx, [rbp+148h]; this
0x140049707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004970c  nop
0x14004970d  lea     rcx, [rbp+140h+var_198]
0x140049711  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140049716  jmp     short loc_1400496B5
0x140049718  mov     rcx, [rbp+140h+var_198]
0x14004971c  test    rcx, rcx
0x14004971f  jnz     short loc_14004972E
0x140049721  mov     ebx, 80070057h
0x140049726  mov     r9d, ebx
0x140049729  lea     edx, [rcx+6Fh]
0x14004972c  jmp     short loc_1400496F9
0x14004972e  mov     r14, [rsi+8]
0x140049732  xorps   xmm0, xmm0
0x140049735  xor     eax, eax
0x140049737  movups  [rbp+140h+var_158], xmm0
0x14004973b  mov     [rbp+140h+var_148], rax
0x14004973f  mov     eax, 41h ; 'A'
0x140049744  mov     word ptr [rbp+140h+var_158], ax
0x140049748  mov     rbx, r13
0x14004974b  mov     [rbp+140h+var_168], rbx
0x14004974f  mov     qword ptr [rbp+140h+var_190], r13
0x140049753  mov     rax, [rcx]
0x140049756  mov     rax, [rax+30h]
0x14004975a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004975f  movzx   ecx, word ptr [r14+10h]
0x140049764  test    eax, eax
0x140049766  jnz     short loc_1400497D8
0x140049768  add     rcx, 40h ; '@'; cb
0x14004976c  call    cs:__imp_CoTaskMemAlloc
0x140049772  mov     rdi, rax
0x140049775  mov     qword ptr [rbp+140h+var_190], rax
0x140049779  test    rax, rax
0x14004977c  jnz     short loc_140049783
0x14004977e  lea     edx, [rax+7Eh]
0x140049781  jmp     short loc_1400497F3
0x140049783  movzx   eax, word ptr [r14+10h]
0x140049788  add     eax, 40h ; '@'
0x14004978b  mov     [rdi], eax
0x14004978d  mov     rcx, [rsi+38h]
0x140049791  call    cs:__imp_GetSessionIdFromEndpointId
0x140049797  mov     [rdi+4], eax
0x14004979a  mov     eax, [rsi+64h]
0x14004979d  mov     [rdi+8], eax
0x1400497a0  movups  xmm0, xmmword ptr [rsi+68h]
0x1400497a4  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x1400497a9  movups  xmm1, xmmword ptr [rsi+94h]
0x1400497b0  movdqu  xmmword ptr [rdi+1Ch], xmm1
0x1400497b5  movzx   r8d, word ptr [r14+10h]
0x1400497ba  add     r8, 12h; Size
0x1400497be  lea     rcx, [rdi+2Ch]; void *
0x1400497c2  mov     rdx, r14; Src
0x1400497c5  call    memcpy_0
0x1400497ca  movzx   eax, word ptr [r14+10h]
0x1400497cf  add     eax, 40h ; '@'
0x1400497d2  mov     [rbp+140h+var_148], rdi
0x1400497d6  jmp     short loc_140049855
0x1400497d8  add     rcx, 20h ; ' '; cb
0x1400497dc  call    cs:__imp_CoTaskMemAlloc
0x1400497e2  mov     rbx, rax
0x1400497e5  mov     [rbp+140h+var_168], rax
0x1400497e9  test    rax, rax
0x1400497ec  jnz     short loc_140049814
0x1400497ee  mov     edx, 8Dh; void *
0x1400497f3  mov     ebx, 8007000Eh
0x1400497f8  lea     r8, aAvcoreAudiocor_55; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400497ff  mov     r9d, ebx; char *
0x140049802  mov     rcx, [rbp+148h]; this
0x140049809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
