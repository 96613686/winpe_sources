# DdcRegistrationController::RegisterDevice(IDdcStoppable *,int,int,int,MdmRegistrationTrigger,void *)

- ea: `0x18000c034`
- end: `0x18000ca44`
- name: `?RegisterDevice@DdcRegistrationController@@SAJPEAVIDdcStoppable@@HHHW4MdmRegistrationTrigger@@PEAX@Z`
- size: `2576`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800040ec`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800036e8`
- `0x180003c2c`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x1800057cc`
- `0x180009164`
- `0x18000a68c`
- `0x18000c034`
- `0x18000f534`
- `0x18001505c`
- `0x180015fbc`
- `0x18001691c`
- `0x18001c8a4`
- `0x180020068`
- `0x18002166c`
- `0x180023f8c`
- `0x180024d9c`
- `0x1800253e0`
- `0x180026474`
- `0x180028ad0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c244`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c244`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c1e2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c1e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca38`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ca38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2b0`
- `MdmCommon!MdmRegisterDevice` at `0x18000c9e1`
- `MdmCommon!MdmRegisterDevice` at `0x18000c9e1`
- `MdmCommon!MdmShouldRegisterDevice` at `0x18000c92a`
- `MdmCommon!MdmShouldRegisterDevice` at `0x18000c92a`
- `MdmCommon!MdmIsRegisteredWithService` at `0x18000c5d2`
- `MdmCommon!MdmIsRegisteredWithService` at `0x18000c5d2`
- `MdmCommon!MdmProtectionStateChanged` at `0x18000c4c5`
- `MdmCommon!MdmProtectionStateChanged` at `0x18000c4c5`
- `MdmCommon!MdmClearAllHashes` at `0x18000c1d1`
- `MdmCommon!MdmClearAllHashes` at `0x18000c1d1`
- `MdmCommon!MdmConnectedAccountsChanged` at `0x18000c631`
- `MdmCommon!MdmConnectedAccountsChanged` at `0x18000c631`

## string_xrefs

- `0x18000c22e`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000c299`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000c45c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`
- `0x18000c5eb`: `CHR(MdmIsRegisteredWithService(MdmDeviceContext_Desktop, &fRegistered))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DdcRegistrationController::RegisterDevice(
        unsigned int (__fastcall ***a1)(_QWORD),
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v10; // rdi
  struct Windows::Data::Json::IJsonValue *v11; // rbx
  unsigned int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // r8
  HANDLE MutexW; // rax
  signed int v16; // eax
  int v17; // edx
  int v18; // ecx
  int ProtectionState; // esi
  int v20; // r14d
  DWORD v21; // eax
  int v22; // edx
  int v23; // ecx
  HANDLE v24; // rbx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  signed int LastError; // eax
  int v29; // ecx
  int v30; // edx
  int v31; // ecx
  int v32; // edx
  int v33; // ecx
  int v34; // ecx
  int v35; // edx
  int v36; // ecx
  int v37; // edx
  int v38; // ecx
  int v39; // edx
  int v40; // ecx
  int v41; // edx
  int v42; // ecx
  int v43; // edx
  int v44; // ecx
  int v45; // edx
  int v46; // ecx
  int v47; // edx
  int v48; // ecx
  int v49; // edx
  int v50; // edx
  int v51; // ecx
  int v52; // edx
  int v53; // edx
  int v54; // ecx
  int v55; // edx
  int v56; // ecx
  int v57; // eax
  int v58; // r13d
  int v59; // edx
  int v60; // ecx
  int v61; // edx
  int v62; // edx
  int v63; // ecx
  const unsigned __int16 *v64; // rax
  int v65; // edx
  int v66; // ecx
  int v67; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  int v69; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v70; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v71; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v72; // [rsp+7Ch] [rbp-84h] BYREF
  int v73; // [rsp+80h] [rbp-80h] BYREF
  int v74; // [rsp+84h] [rbp-7Ch] BYREF
  int v75; // [rsp+88h] [rbp-78h] BYREF
  int v76; // [rsp+8Ch] [rbp-74h] BYREF
  int v77; // [rsp+90h] [rbp-70h] BYREF
  int v78; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v79; // [rsp+98h] [rbp-68h] BYREF
  int v80; // [rsp+9Ch] [rbp-64h]
  int v81; // [rsp+A0h] [rbp-60h]
  unsigned int v82; // [rsp+A4h] [rbp-5Ch]
  struct Windows::Data::Json::IJsonValue *v83; // [rsp+A8h] [rbp-58h] BYREF
  struct Windows::Data::Json::IJsonValue *v84; // [rsp+B0h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v85; // [rsp+B8h] [rbp-48h] BYREF
  struct Windows::Data::Json::IJsonValue *v86; // [rsp+C0h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValue *v87; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v88; // [rsp+D0h] [rbp-30h] BYREF
  int v89; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v90; // [rsp+E0h] [rbp-20h] BYREF
  int v91; // [rsp+E4h] [rbp-1Ch]
  unsigned int v92; // [rsp+E8h] [rbp-18h]
  struct Windows::Data::Json::IJsonValue *v93; // [rsp+F0h] [rbp-10h] BYREF
  struct Windows::Data::Json::IJsonValue *v94; // [rsp+F8h] [rbp-8h] BYREF
  struct Windows::Data::Json::IJsonValue *v95; // [rsp+100h] [rbp+0h] BYREF
  struct Windows::Data::Json::IJsonValue *v96; // [rsp+108h] [rbp+8h] BYREF
  __int64 v97; // [rsp+110h] [rbp+10h] BYREF
  __int64 v98; // [rsp+118h] [rbp+18h] BYREF
  __int64 v99; // [rsp+120h] [rbp+20h]
  __int64 v100; // [rsp+130h] [rbp+30h] BYREF
  unsigned int v101; // [rsp+138h] [rbp+38h]
  __int128 v102; // [rsp+140h] [rbp+40h]
  __int128 v103; // [rsp+150h] [rbp+50h]
  __int128 v104; // [rsp+160h] [rbp+60h]
  __int128 v105; // [rsp+170h] [rbp+70h]
  __int128 v106; // [rsp+180h] [rbp+80h]
  __int128 v107; // [rsp+190h] [rbp+90h]
  int v108; // [rsp+1A0h] [rbp+A0h]
  __int64 v109; // [rsp+1A8h] [rbp+A8h]
  __int64 v110; // [rsp+1B0h] [rbp+B0h]
  _BYTE v111[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v112[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  int *v113; // [rsp+1F0h] [rbp+F0h]
  __int64 v114; // [rsp+1F8h] [rbp+F8h]
  int *v115; // [rsp+200h] [rbp+100h]
  __int64 v116; // [rsp+208h] [rbp+108h]
  HANDLE *p_hObject; // [rsp+210h] [rbp+110h]
  __int64 v118; // [rsp+218h] [rbp+118h]
  unsigned __int16 v119[2048]; // [rsp+220h] [rbp+120h] BYREF

  v80 = a3;
  v92 = a2;
  v10 = 0;
  v82 = 0;
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v78 = 0;
  v79 = 0;
  std::wstring::wstring((__int64)v111);
  v98 = a6;
  v99 = 0;
  v87 = 0;
  v86 = 0;
  v85 = 0;
  v84 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v96 = 0;
  v95 = 0;
  v94 = 0;
  v11 = 0;
  v83 = 0;
  v93 = 0;
  v75 = 0;
  v76 = 0;
  v81 = 0;
  v67 = 0;
  v74 = 0;
  v12 = 0;
  v69 = 0;
  v73 = 0;
  v91 = 0;
  v77 = 0;
  memset_0(v119, 0, sizeof(v119));
  v90 = 2048;
  v97 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
  {
    LODWORD(hObject) = a5;
    v89 = a3;
    v88 = a2;
    v113 = (int *)&v88;
    v114 = 4;
    v115 = &v89;
    v116 = 4;
    p_hObject = &hObject;
    v118 = 4;
    McGenEventWrite_EventWriteTransfer(v13, DEVICE_DIRECTORY_CLIENT_REGISTER_DEVICE_CALLED, v14, 4, v112);
  }
  if ( a2 )
    MdmClearAllHashes(2);
  MutexW = CreateMutexW(0, 0, L"Local\\C9E8AF12-FA27-4748-EC04-38CA71239739_RegisterDevice");
  hObject = MutexW;
  if ( MutexW )
  {
    v21 = WaitForSingleObject(MutexW, 0);
    v20 = 1;
    switch ( v21 )
    {
      case 0u:
      case 0x80u:
        v67 = 1;
        break;
      case 0x102u:
        ProtectionState = 0;
        LODWORD(v10) = 0;
        goto LABEL_16;
      case 0xFFFFFFFF:
        LastError = GetLastError();
        ProtectionState = LastError;
        if ( LastError > 0 )
          ProtectionState = (unsigned __int16)LastError | 0x80070000;
        if ( ProtectionState < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v29,
              v22,
              ProtectionState,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
              110,
              "CHR(HRESULT_FROM_WIN32(GetLastError()))");
          goto LABEL_16;
        }
        break;
      default:
        ProtectionState = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v23,
            v22,
            -2147418113,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            115,
            "CHR(((HRESULT)0x8000FFFFL))");
        goto LABEL_16;
    }
    ProtectionState = DdcDeviceInfoHelper::FmdDisabledByPolicy(&v73, v22);
    if ( ProtectionState < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v31,
          v30,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          118,
          "CHR(DdcDeviceInfoHelper::FmdDisabledByPolicy(&fIsFmdDisabledByPolicy))");
      goto LABEL_115;
    }
    if ( v73 )
      goto LABEL_115;
    if ( a5 == 10 )
    {
      ProtectionState = DdcProtectionStateHelper::GetProtectionState(&v83, v30);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v33,
            v32,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            129,
            "CHR(DdcProtectionStateHelper::GetProtectionState(pProtectionState.GetAddressOf()))");
        goto LABEL_115;
      }
      v11 = v83;
      ProtectionState = MdmProtectionStateChanged(2, v83, &v74);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v34,
            v30,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            130,
            "CHR(MdmProtectionStateChanged(MdmDeviceContext_Desktop, pProtectionState.Get(), &fProtectionStateChanged))");
        goto LABEL_115;
      }
      if ( !v74 )
        goto LABEL_115;
    }
    if ( v80 )
    {
      ProtectionState = IsFreeNetwork(&v69, v30);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v36,
            v35,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            141,
            "CHR(IsFreeNetwork(&fFreeNetwork))");
        goto LABEL_115;
      }
      if ( !v69 )
        goto LABEL_115;
    }
    ProtectionState = DdcAccountHelper::EnumerateUsers(&v87, &v86, &v85, &v84, &v72, &v71, &v70);
    if ( ProtectionState < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v38,
          v37,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          156,
          "CHR(DdcAccountHelper::EnumerateUsers( pAdmins.GetAddressOf(), pDeviceOwners.GetAddressOf(), pStandardUsers.Get"
          "AddressOf(), pConnectedAdmins.GetAddressOf(), &cAdmins, &cDeviceOwners, &cStandardUsers))");
      goto LABEL_115;
    }
    if ( !v72 && !v71 && !v70 )
    {
      ProtectionState = MdmIsRegisteredWithService(2, &v75);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v40,
            v39,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            164,
            "CHR(MdmIsRegisteredWithService(MdmDeviceContext_Desktop, &fRegistered))");
        goto LABEL_115;
      }
      if ( !v75 )
        goto LABEL_115;
      ProtectionState = MdmConnectedAccountsChanged(2, v87, v86, v85, v84, &v76);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v42,
            v41,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            171,
            "CHR(MdmConnectedAccountsChanged(MdmDeviceContext_Desktop, pAdmins.Get(), pDeviceOwners.Get(), pStandardUsers"
            ".Get(), pConnectedAdmins.Get(), &fConnectedAccountsChanged))");
        goto LABEL_115;
      }
      if ( !v76 )
        goto LABEL_115;
      v81 = 1;
    }
    if ( (**a1)(a1) )
    {
LABEL_67:
      v12 = 1;
      goto LABEL_115;
    }
    ProtectionState = DdcDeviceInfoHelper::GetDeviceInfo(&v96, a4);
    if ( ProtectionState < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v44,
          v43,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          185,
          "CHR(DdcDeviceInfoHelper::GetDeviceInfo(pDeviceInfo.GetAddressOf(), fLight))");
      goto LABEL_115;
    }
    if ( (**a1)(a1) )
      goto LABEL_67;
    if ( !a4 )
    {
      ProtectionState = DdcDeviceInfoHelper::GetDeviceHardwareInfo(&v94);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v46,
            v45,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            191,
            "CHR(DdcDeviceInfoHelper::GetDeviceHardwareInfo(pHardwareInfo.GetAddressOf()))");
        goto LABEL_115;
      }
      if ( (**a1)(a1) )
        goto LABEL_67;
    }
    ProtectionState = DdcDrivesHelper::FormatDeviceStorageInfo(&v95);
    if ( ProtectionState < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v48,
          v47,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          196,
          "CHR(DdcDrivesHelper::FormatDeviceStorageInfo(pStorageInfo.GetAddressOf()))");
      goto LABEL_115;
    }
    if ( (**a1)(a1) )
      goto LABEL_67;
    ProtectionState = DdcMobileNetworksHelper::GetMobileNetworksProperties(&v93, v49);
    if ( ProtectionState < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v51,
          v50,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          200,
          "CHR(DdcMobileNetworksHelper::GetMobileNetworksProperties(pMobileNetworks.GetAddressOf()))");
      goto LABEL_115;
    }
    if ( (**a1)(a1) )
      goto LABEL_67;
    if ( !v11 )
    {
      ProtectionState = DdcProtectionStateHelper::GetProtectionState(&v83, v52);
      if ( ProtectionState < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v54,
            v53,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            208,
            "CHR(DdcProtectionStateHelper::GetProtectionState(pProtectionState.GetAddressOf()))");
        goto LABEL_115;
      }
      if ( (**a1)(a1) )
        goto LABEL_67;
      v11 = v83;
    }
    ProtectionState = DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v98, L"RegisterDevice");
    if ( ProtectionState >= 0 )
    {
      if ( (**a1)(a1) )
        goto LABEL_67;
      if ( a4 )
      {
        v58 = v91;
      }
      else
      {
        v57 = DdcWnsListener::RegisterChannel(&v77, v119, &v90, (union FILETIMEEX *)&v97);
        v58 = v77;
        if ( v57 < 0 )
          v58 = 0;
        v10 = v97;
      }
      if ( (**a1)(a1) )
        goto LABEL_67;
      v100 = v92 | 0x200000000LL;
      v101 = a5;
      *(_QWORD *)&v102 = (unsigned __int64)v119 & -(__int64)(v58 != 0);
      *(_QWORD *)&v103 = v96;
      *((_QWORD *)&v103 + 1) = v94;
      *(_QWORD *)&v104 = v95;
      *((_QWORD *)&v104 + 1) = v11;
      *((_QWORD *)&v102 + 1) = v93;
      *(_QWORD *)&v105 = v87;
      *((_QWORD *)&v105 + 1) = v86;
      *(_QWORD *)&v106 = v85;
      *((_QWORD *)&v106 + 1) = v84;
      ProtectionState = MdmShouldRegisterDevice(&v78, (struct MdmRegistrationParameters *)&v100);
      if ( ProtectionState >= 0 )
      {
        if ( !v78 )
          goto LABEL_115;
        if ( (**a1)(a1) )
          goto LABEL_67;
        ProtectionState = DdcMsaHelper::GetDeviceTicket((__int64)v111, v61);
        if ( ProtectionState >= 0 )
        {
          if ( (**a1)(a1) )
            goto LABEL_67;
          v64 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          ProtectionState = MdmRegisterDevice(&v79, v64, (struct MdmRegistrationParameters *)&v100);
          if ( ProtectionState >= 0 )
          {
            if ( v58 )
              DdcWnsListener::UpdateChannelExpiration(v10);
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v66,
              v65,
              ProtectionState,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
              2,
              "CHR(MdmRegisterDevice(&dwHttpStatus, wstrTicket.c_str(), &parameters))");
          }
        }
        else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        {
          McTemplateU0dsqs_EventWriteTransfer(
            v63,
            v62,
            ProtectionState,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
            253,
            "CHR(DdcMsaHelper::GetDeviceTicket(&wstrTicket))");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v60,
          v59,
          ProtectionState,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
          244,
          "CHR(MdmShouldRegisterDevice(&fShouldRegister, &parameters))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v56,
        v55,
        ProtectionState,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        213,
        "CHR(pdcActivationWrapper.ActivateClient(L\"RegisterDevice\"))");
    }
LABEL_115:
    LODWORD(v10) = v67;
    if ( v67 )
    {
      v82 = DdcStateController::ProcessStateChange();
      v24 = hObject;
      ReleaseMutex(hObject);
      goto LABEL_17;
    }
LABEL_16:
    v24 = hObject;
LABEL_17:
    CloseHandle(v24);
    goto LABEL_18;
  }
  v16 = GetLastError();
  ProtectionState = v16;
  if ( v16 > 0 )
    ProtectionState = (unsigned __int16)v16 | 0x80070000;
  v20 = 1;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v18,
      v17,
      ProtectionState,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
      93,
      "CBR(hMutex != 0)");
LABEL_18:
  if ( !v80 || v69 )
    v20 = 0;
  DdcTraceHelper::TraceRegisterDeviceResult(
    v12,
    v99 != 0,
    a5,
    (_DWORD)v10 == 0,
    v72,
    v71,
    v70,
    v81,
    v20,
    v73,
    ProtectionState,
    v79);
  v26 = v82;
  if ( ProtectionState < 0 )
    v26 = ProtectionState;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v25, DEVICE_DIRECTORY_CLIENT_REGISTER_DEVICE_RESULT, v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v93);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v83);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v94);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v95);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v96);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v84);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v85);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v86);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v87);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v98);
  std::wstring::_Tidy_deallocate((__int64)v111);
  return v26;
}

```

## disassembly

```asm
0x18000c034  mov     [rsp-8+arg_10], rbx
0x18000c039  push    rbp
0x18000c03a  push    rsi
0x18000c03b  push    rdi
0x18000c03c  push    r12
0x18000c03e  push    r13
0x18000c040  push    r14
0x18000c042  push    r15
0x18000c044  lea     rbp, [rsp-1130h]
0x18000c04c  mov     eax, 1230h
0x18000c051  call    _alloca_probe
0x18000c056  sub     rsp, rax
0x18000c059  mov     rax, cs:__security_cookie
0x18000c060  xor     rax, rsp
0x18000c063  mov     [rbp+1160h+var_40], rax
0x18000c06a  mov     r13d, r9d
0x18000c06d  mov     r14d, r8d
0x18000c070  mov     [rbp+1160h+var_11C4], r8d
0x18000c074  mov     esi, edx
0x18000c076  mov     [rbp+1160h+var_1178], edx
0x18000c079  mov     r15, rcx
0x18000c07c  xor     edi, edi
0x18000c07e  mov     [rbp+1160h+var_11BC], edi
0x18000c081  mov     [rbp+1160h+var_1130], rdi
0x18000c085  mov     [rbp+1160h+var_1128], edi
0x18000c088  xorps   xmm0, xmm0
0x18000c08b  movdqa  [rbp+1160h+var_1120], xmm0
0x18000c090  xorps   xmm1, xmm1
0x18000c093  movdqa  [rbp+1160h+var_1110], xmm1
0x18000c098  movdqa  [rbp+1160h+var_1100], xmm0
0x18000c09d  movdqa  [rbp+1160h+var_10F0], xmm1
0x18000c0a2  movdqa  [rbp+1160h+var_10E0], xmm0
0x18000c0aa  movdqa  [rbp+1160h+var_10D0], xmm1
0x18000c0b2  mov     [rbp+1160h+var_10C0], edi
0x18000c0b8  mov     [rbp+1160h+var_10B8], rdi
0x18000c0bf  mov     [rbp+1160h+var_10B0], rdi
0x18000c0c6  mov     [rbp+1160h+var_11CC], edi
0x18000c0c9  mov     [rbp+1160h+var_11C8], edi
0x18000c0cc  lea     rcx, [rbp+1160h+var_10A0]
0x18000c0d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000c0d8  nop
0x18000c0d9  mov     rax, [rbp+1160h+arg_28]
0x18000c0e0  mov     [rbp+1160h+var_1148], rax
0x18000c0e4  mov     [rbp+1160h+var_1140], rdi
0x18000c0e8  mov     [rbp+1160h+var_1198], rdi
0x18000c0ec  mov     [rbp+1160h+var_11A0], rdi
0x18000c0f0  mov     [rbp+1160h+var_11A8], rdi
0x18000c0f4  mov     [rbp+1160h+var_11B0], rdi
0x18000c0f8  mov     [rsp+1260h+var_11E4], edi
0x18000c0fc  mov     [rsp+1260h+var_11E8], edi
0x18000c100  mov     [rsp+1260h+var_11EC], edi
0x18000c104  mov     [rbp+1160h+var_1158], rdi
0x18000c108  mov     [rbp+1160h+var_1160], rdi
0x18000c10c  mov     [rbp+1160h+var_1168], rdi
0x18000c110  mov     ebx, edi
0x18000c112  mov     [rbp+1160h+var_11B8], rbx
0x18000c116  mov     [rbp+1160h+var_1170], rdi
0x18000c11a  mov     [rbp+1160h+var_11D8], edi
0x18000c11d  mov     [rbp+1160h+var_11D4], edi
0x18000c120  mov     [rbp+1160h+var_11C0], edi
0x18000c123  mov     [rsp+1260h+var_1200], edi
0x18000c127  mov     [rbp+1160h+var_11DC], edi
0x18000c12a  mov     r12d, edi
0x18000c12d  mov     [rsp+1260h+var_11F0], edi
0x18000c131  mov     [rbp+1160h+var_11E0], edi
0x18000c134  mov     eax, edi
0x18000c136  mov     [rbp+1160h+var_117C], eax
0x18000c139  mov     [rbp+1160h+var_11D0], eax
0x18000c13c  xor     edx, edx; Val
0x18000c13e  mov     r8d, 1000h; Size
0x18000c144  lea     rcx, [rbp+1160h+var_1040]; void *
0x18000c14b  call    memset_0
0x18000c150  mov     [rbp+1160h+var_1180], 800h
0x18000c157  mov     [rbp+1160h+var_1150], rdi
0x18000c15b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000c162  jz      short loc_18000C1C8
0x18000c164  mov     eax, [rbp+1160h+arg_20]
0x18000c16a  mov     dword ptr [rsp+1260h+hObject], eax
0x18000c16e  mov     [rbp+1160h+var_1188], r14d
0x18000c172  mov     [rbp+1160h+var_1190], esi
0x18000c175  lea     rax, [rbp+1160h+var_1190]
0x18000c179  mov     [rbp+1160h+var_1070], rax
0x18000c180  lea     r9d, [rdi+4]
0x18000c184  mov     [rbp+1160h+var_1068], r9
0x18000c18b  lea     rax, [rbp+1160h+var_1188]
0x18000c18f  mov     [rbp+1160h+var_1060], rax
0x18000c196  mov     [rbp+1160h+var_1058], r9
0x18000c19d  lea     rax, [rsp+1260h+hObject]
0x18000c1a2  mov     [rbp+1160h+var_1050], rax
0x18000c1a9  mov     [rbp+1160h+var_1048], r9
0x18000c1b0  lea     rax, [rbp+1160h+var_1080]
0x18000c1b7  mov     [rsp+1260h+var_1240], rax
0x18000c1bc  lea     rdx, DEVICE_DIRECTORY_CLIENT_REGISTER_DEVICE_CALLED
0x18000c1c3  call    McGenEventWrite_EventWriteTransfer
0x18000c1c8  test    esi, esi
0x18000c1ca  jz      short loc_18000C1D7
0x18000c1cc  mov     ecx, 2
0x18000c1d1  call    cs:__imp_?MdmClearAllHashes@@YAXW4MdmDeviceContext@@@Z; MdmClearAllHashes(MdmDeviceContext)
0x18000c1d7  lea     r8, Name; "Local\\C9E8AF12-FA27-4748-EC04-38CA7123"...
0x18000c1de  xor     edx, edx; bInitialOwner
0x18000c1e0  xor     ecx, ecx; lpMutexAttributes
0x18000c1e2  call    cs:__imp_CreateMutexW
0x18000c1e8  mov     [rsp+1260h+hObject], rax
0x18000c1ed  test    rax, rax
0x18000c1f0  jnz     short loc_18000C23F
0x18000c1f2  call    cs:__imp_GetLastError
0x18000c1f8  mov     esi, eax
0x18000c1fa  test    eax, eax
0x18000c1fc  jle     short loc_18000C207
0x18000c1fe  movzx   esi, ax
0x18000c201  or      esi, 80070000h
0x18000c207  mov     r14d, 1
0x18000c20d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c214  jz      loc_18000C2B6
0x18000c21a  lea     rax, aCbrHmutex0; "CBR(hMutex != 0)"
0x18000c221  mov     [rsp+1260h+var_1238], rax
0x18000c226  mov     dword ptr [rsp+1260h+var_1240], 15Dh
0x18000c22e  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000c235  mov     r8d, esi
0x18000c238  call    McTemplateU0dsqs_EventWriteTransfer
0x18000c23d  jmp     short loc_18000C2B6
0x18000c23f  xor     edx, edx; dwMilliseconds
0x18000c241  mov     rcx, rax; hHandle
0x18000c244  call    cs:__imp_WaitForSingleObject
0x18000c24a  mov     r14d, 1
0x18000c250  test    eax, eax
0x18000c252  jz      loc_18000C427
0x18000c258  cmp     eax, 80h
0x18000c25d  jz      loc_18000C427
0x18000c263  cmp     eax, 102h
0x18000c268  jz      loc_18000C41E
0x18000c26e  cmp     eax, 0FFFFFFFFh
0x18000c271  jz      loc_18000C3DE
0x18000c277  mov     esi, 8000FFFFh
0x18000c27c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c283  jz      short loc_18000C2A8
0x18000c285  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8000FFFFL))"
0x18000c28c  mov     [rsp+1260h+var_1238], rax
0x18000c291  mov     dword ptr [rsp+1260h+var_1240], 173h
0x18000c299  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000c2a0  mov     r8d, esi
0x18000c2a3  call    McTemplateU0dsqs_EventWriteTransfer
0x18000c2a8  mov     rbx, [rsp+1260h+hObject]
0x18000c2ad  mov     rcx, rbx; hObject
0x18000c2b0  call    cs:__imp_CloseHandle
0x18000c2b6  mov     ecx, [rbp+1160h+var_11C8]
0x18000c2b9  cmp     [rbp+1160h+var_11C4], 0
0x18000c2bd  jz      short loc_18000C2C6
0x18000c2bf  cmp     [rsp+1260h+var_11F0], 0
0x18000c2c4  jz      short loc_18000C2C9
0x18000c2c6  xor     r14d, r14d
0x18000c2c9  mov     eax, [rsp+1260h+var_11EC]
0x18000c2cd  mov     r10d, [rsp+1260h+var_11E8]
0x18000c2d2  mov     r11d, [rsp+1260h+var_11E4]
0x18000c2d7  xor     r9d, r9d
0x18000c2da  test    edi, edi
0x18000c2dc  setz    r9b
0x18000c2e0  xor     edx, edx
0x18000c2e2  cmp     [rbp+1160h+var_1140], rdx
0x18000c2e6  setnz   dl
0x18000c2e9  mov     [rsp+1260h+var_1208], ecx
0x18000c2ed  mov     [rsp+1260h+var_1210], esi
0x18000c2f1  mov     ecx, [rbp+1160h+var_11E0]
0x18000c2f4  mov     [rsp+1260h+var_1218], ecx
0x18000c2f8  mov     [rsp+1260h+var_1220], r14d
0x18000c2fd  mov     ecx, [rbp+1160h+var_11C0]
0x18000c300  mov     [rsp+1260h+var_1228], ecx
0x18000c304  mov     dword ptr [rsp+1260h+var_1230], eax
0x18000c308  mov     dword ptr [rsp+1260h+var_1238], r10d
0x18000c30d  mov     dword ptr [rsp+1260h+var_1240], r11d
0x18000c312  mov     r8d, [rbp+1160h+arg_20]
0x18000c319  mov     ecx, r12d
0x18000c31c  call    ?TraceRegisterDeviceResult@DdcTraceHelper@@SAXHHW4MdmRegistrationTrigger@@HKKKHHHJK@Z; DdcTraceHelper::TraceRegisterDeviceResult(int,int,MdmRegistrationTrigger,int,ulong,ulong,ulong,int,int,int,long,ulong)
0x18000c321  test    esi, esi
0x18000c323  mov     ebx, [rbp+1160h+var_11BC]
0x18000c326  cmovs   ebx, esi
0x18000c329  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000c330  jz      short loc_18000C342
0x18000c332  mov     r8d, ebx
0x18000c335  lea     rdx, DEVICE_DIRECTORY_CLIENT_REGISTER_DEVICE_RESULT
0x18000c33c  call    McTemplateU0q_EventWriteTransfer
0x18000c341  nop
0x18000c342  lea     rcx, [rbp+1160h+var_1170]
0x18000c346  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c34b  nop
0x18000c34c  lea     rcx, [rbp+1160h+var_11B8]
0x18000c350  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c355  nop
0x18000c356  lea     rcx, [rbp+1160h+var_1168]
0x18000c35a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c35f  nop
0x18000c360  lea     rcx, [rbp+1160h+var_1160]
0x18000c364  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c369  nop
0x18000c36a  lea     rcx, [rbp+1160h+var_1158]
0x18000c36e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c373  nop
0x18000c374  lea     rcx, [rbp+1160h+var_11B0]
0x18000c378  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c37d  nop
0x18000c37e  lea     rcx, [rbp+1160h+var_11A8]
0x18000c382  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c387  nop
0x18000c388  lea     rcx, [rbp+1160h+var_11A0]
0x18000c38c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c391  nop
0x18000c392  lea     rcx, [rbp+1160h+var_1198]
0x18000c396  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c39b  nop
0x18000c39c  lea     rcx, [rbp+1160h+var_1148]; this
0x18000c3a0  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x18000c3a5  nop
0x18000c3a6  lea     rcx, [rbp+1160h+var_10A0]
0x18000c3ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c3b2  mov     eax, ebx
0x18000c3b4  mov     rcx, [rbp+1160h+var_40]
0x18000c3bb  xor     rcx, rsp; StackCookie
0x18000c3be  call    __security_check_cookie
0x18000c3c3  mov     rbx, [rsp+1260h+arg_10]
0x18000c3cb  add     rsp, 1230h
0x18000c3d2  pop     r15
0x18000c3d4  pop     r14
0x18000c3d6  pop     r13
0x18000c3d8  pop     r12
0x18000c3da  pop     rdi
0x18000c3db  pop     rsi
0x18000c3dc  pop     rbp
0x18000c3dd  retn
0x18000c3de  call    cs:__imp_GetLastError
0x18000c3e4  nop
0x18000c3e5  mov     esi, eax
0x18000c3e7  test    eax, eax
0x18000c3e9  jle     short loc_18000C3F4
0x18000c3eb  movzx   esi, ax
0x18000c3ee  or      esi, 80070000h
0x18000c3f4  test    esi, esi
0x18000c3f6  jns     short loc_18000C42C
0x18000c3f8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c3ff  jz      loc_18000C2A8
0x18000c405  lea     rax, aChrHresultFrom_0; "CHR(HRESULT_FROM_WIN32(GetLastError()))"
0x18000c40c  mov     [rsp+1260h+var_1238], rax
0x18000c411  mov     dword ptr [rsp+1260h+var_1240], 16Eh
0x18000c419  jmp     loc_18000C299
0x18000c41e  xor     esi, esi
0x18000c420  mov     edi, esi
0x18000c422  jmp     loc_18000C2A8
0x18000c427  mov     [rsp+1260h+var_1200], r14d
0x18000c42c  lea     rcx, [rbp+1160h+var_11E0]; int *
0x18000c430  call    ?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z; DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)
0x18000c435  mov     esi, eax
0x18000c437  test    eax, eax
0x18000c439  jns     short loc_18000C470
0x18000c43b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c442  jz      loc_18000CA1C
0x18000c448  lea     rax, aChrDdcdevicein; "CHR(DdcDeviceInfoHelper::FmdDisabledByP"...
0x18000c44f  mov     [rsp+1260h+var_1238], rax
0x18000c454  mov     dword ptr [rsp+1260h+var_1240], 176h
0x18000c45c  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000c463  mov     r8d, esi
0x18000c466  call    McTemplateU0dsqs_EventWriteTransfer
0x18000c46b  jmp     loc_18000CA1C
0x18000c470  cmp     [rbp+1160h+var_11E0], r12d
0x18000c474  jnz     loc_18000CA1C
0x18000c47a  cmp     [rbp+1160h+arg_20], 0Ah
0x18000c481  jnz     short loc_18000C501
0x18000c483  lea     rcx, [rbp+1160h+var_11B8]; struct Windows::Data::Json::IJsonValue **
0x18000c487  call    ?GetProtectionState@DdcProtectionStateHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetProtectionState(Windows::Data::Json::IJsonValue * *)
0x18000c48c  mov     esi, eax
0x18000c48e  test    eax, eax
0x18000c490  jns     short loc_18000C4B5
0x18000c492  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c499  jz      loc_18000CA1C
0x18000c49f  lea     rax, aChrDdcprotecti; "CHR(DdcProtectionStateHelper::GetProtec"...
0x18000c4a6  mov     [rsp+1260h+var_1238], rax
0x18000c4ab  mov     dword ptr [rsp+1260h+var_1240], 181h
0x18000c4b3  jmp     short loc_18000C45C
0x18000c4b5  lea     r8, [rbp+1160h+var_11DC]
0x18000c4b9  mov     rbx, [rbp+1160h+var_11B8]
0x18000c4bd  mov     rdx, rbx
0x18000c4c0  mov     ecx, 2
0x18000c4c5  call    cs:__imp_?MdmProtectionStateChanged@@YAJW4MdmDeviceContext@@PEAUIJsonValue@Json@Data@Windows@@PEAH@Z; MdmProtectionStateChanged(MdmDeviceContext,Windows::Data::Json::IJsonValue *,int *)
0x18000c4cb  mov     esi, eax
0x18000c4cd  test    eax, eax
0x18000c4cf  jns     short loc_18000C4F7
0x18000c4d1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
0x18000c4d8  jz      loc_18000CA1C
0x18000c4de  lea     rax, aChrMdmprotecti; "CHR(MdmProtectionStateChanged(MdmDevice"...
0x18000c4e5  mov     [rsp+1260h+var_1238], rax
0x18000c4ea  mov     dword ptr [rsp+1260h+var_1240], 182h
0x18000c4f2  jmp     loc_18000C45C
0x18000c4f7  cmp     [rbp+1160h+var_11DC], r12d
0x18000c4fb  jz      loc_18000CA1C
0x18000c501  cmp     [rbp+1160h+var_11C4], r12d
0x18000c505  jz      short loc_18000C548
0x18000c507  lea     rcx, [rsp+1260h+var_11F0]; int *
0x18000c50c  call    ?IsFreeNetwork@@YAJPEAH@Z; IsFreeNetwork(int *)
0x18000c511  mov     esi, eax
0x18000c513  test    eax, eax
0x18000c515  jns     short loc_18000C53D
0x18000c517  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r14b
  ... truncated ...
```
