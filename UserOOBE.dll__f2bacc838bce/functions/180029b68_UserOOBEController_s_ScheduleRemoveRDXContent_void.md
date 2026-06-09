# UserOOBEController::s_ScheduleRemoveRDXContent(void)

- ea: `0x180029b68`
- end: `0x18002a477`
- name: `?s_ScheduleRemoveRDXContent@UserOOBEController@@CAJXZ`
- size: `2319`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x1800032b0`
- `0x1800067b0`
- `0x180007134`
- `0x180007710`
- `0x180018c78`
- `0x18001b5d4`
- `0x18001cf50`
- `0x18001d248`
- `0x180020b70`
- `0x1800248dc`
- `0x180025920`
- `0x180028c7c`
- `0x180029b68`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029bdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029c1d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029bdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029c1d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a124`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a14f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a124`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a14f`

## string_xrefs

- `0x180029c13`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180029bce`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x180029d2f`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <Author>$(@%systemRoot%\system32\rdxtaskfactory.dll,-100)</Author>        <Description>$(@%systemRoot%\system32\rdxtaskfactory.dll,-101)</Description>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>    </RegistrationInfo>    <Principals>        <Principal id="LocalSystem">            <UserId>S-1-5-18</UserId>            <Ru`
- `0x180029cc2`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029d19`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029d58`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029dd4`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029e2f`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029e87`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029f74`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a009`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a063`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a0a6`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a190`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a1de`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a275`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a2b4`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002a37a`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029eb3`: `DeleteDemoContentDelay`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 UserOOBEController::s_ScheduleRemoveRDXContent(void)
{
  const unsigned __int16 *v0; // rdx
  const unsigned __int16 *v1; // rcx
  const struct _GUID *v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int128 v6; // xmm6
  __int64 v7; // xmm7_8
  unsigned __int16 *v8; // rdi
  __int64 (__fastcall *v9)(unsigned __int16 *, _QWORD, struct ITaskFolder **); // rbx
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  struct ITaskFolder *v14; // rdi
  HRESULT (__stdcall *GetFolder)(ITaskFolder *, BSTR, ITaskFolder **); // rbx
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r9d
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD); // rbx
  int v24; // eax
  __int64 (__fastcall ****v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rdi
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, __int64 *); // rbx
  int v33; // eax
  __int64 (__fastcall ****v34)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64, _QWORD); // rbx
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64 *); // rdi
  int v40; // eax
  OOBETaskSchedulerHelper *v41; // rcx
  unsigned __int16 **v42; // r8
  int BoundaryTimeAfterDelay; // eax
  __int64 v44; // rdx
  __int64 v45; // rbx
  struct ITaskFolder *v46; // rsi
  HRESULT (__stdcall *get_Name)(ITaskFolder *, BSTR *); // rdi
  int v48; // eax
  unsigned int v49; // edi
  OOBETaskSchedulerHelper *v50; // rcx
  const unsigned __int16 *v51; // r8
  int v52; // eax
  __int64 v53; // rbx
  struct ITaskServiceVtbl *lpVtbl; // rsi
  __int64 (__fastcall *v55)(struct ITaskServiceVtbl *, __int64, struct ITaskFolder *, __int64); // rdi
  int v56; // eax
  unsigned __int16 *pdwType; // [rsp+28h] [rbp-E0h]
  int pdwTypea; // [rsp+28h] [rbp-E0h]
  struct ITaskFolder **pvData; // [rsp+30h] [rbp-D8h]
  struct ITaskFolder *v61; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+68h] [rbp-A0h] BYREF
  DWORD pcbData[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v65[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-88h] BYREF
  __int64 v67; // [rsp+88h] [rbp-80h] BYREF
  __int64 (__fastcall ***v68)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-78h] BYREF
  ITaskService v69; // [rsp+98h] [rbp-70h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 *v71; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v73; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v75[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v76; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v77[22]; // [rsp+DAh] [rbp-2Eh]
  _QWORD v78[4]; // [rsp+F8h] [rbp-10h] BYREF
  __int16 v79; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v80[22]; // [rsp+11Ah] [rbp+12h]
  unsigned __int16 v81[16]; // [rsp+138h] [rbp+30h] BYREF
  WCHAR pszPathOut[264]; // [rsp+158h] [rbp+50h] BYREF
  WCHAR v83[264]; // [rsp+368h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D0h] [rbp+4C8h]

  LODWORD(v61) = 0;
  pcbData[0] = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &v61,
         pcbData) )
  {
    pcbData[0] = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &v61,
      pcbData);
  }
  if ( (_DWORD)v61 )
    return 0;
  v71 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  v3 = SHExtCoCreateFromRegKey(v1, v0, v2, (void **)&v71);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 894;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v3,
      (int)pdwType);
LABEL_70:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
    return v4;
  }
  v81[0] = 0;
  v6 = *(_OWORD *)v77;
  *(_OWORD *)&v81[1] = *(_OWORD *)v77;
  v7 = *(_QWORD *)&v77[14];
  *(_QWORD *)&v81[8] = *(_QWORD *)&v77[14];
  LOWORD(v78[0]) = 0;
  *(_OWORD *)((char *)v78 + 2) = *(_OWORD *)v77;
  v78[2] = *(_QWORD *)&v77[14];
  v79 = 0;
  *(_OWORD *)v80 = *(_OWORD *)v77;
  *(_QWORD *)&v80[14] = *(_QWORD *)&v77[14];
  v76 = 0;
  pdwType = v81;
  v3 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int16 *, __int16 *, _QWORD *))(*(_QWORD *)v71 + 80LL))(
         v71,
         &v76,
         &v79,
         v78);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = 896;
    goto LABEL_8;
  }
  v61 = 0;
  v8 = v71;
  v9 = *(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, struct ITaskFolder **))(*(_QWORD *)v71 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v10 = v9(v8, 0, &v61);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v10,
      (int)v81);
LABEL_69:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    goto LABEL_70;
  }
  wil::make_bstr_nothrow(
    &v63,
    L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-com:asm"
     ".v3\">    <RegistrationInfo>        <Author>$(@%systemRoot%\\system32\\rdxtaskfactory.dll,-100)</Author>        <De"
     "scription>$(@%systemRoot%\\system32\\rdxtaskfactory.dll,-101)</Description>        <SecurityDescriptor>D:(A;;FA;;;B"
     "A)(A;;FA;;;SY)</SecurityDescriptor>    </RegistrationInfo>    <Principals>        <Principal id=\"LocalSystem\">   "
     "         <UserId>S-1-5-18</UserId>            <RunLevel>HighestAvailable</RunLevel>        </Principal>    </Princi"
     "pals>    <Settings>        <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>        <DisallowStartIfOnBa"
     "tteries>false</DisallowStartIfOnBatteries>        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>        <Al"
     "lowHardTerminate>false</AllowHardTerminate>        <StartWhenAvailable>true</StartWhenAvailable>        <RunOnlyIfN"
     "etworkAvailable>false</RunOnlyIfNetworkAvailable>        <AllowStartOnDemand>false</AllowStartOnDemand>        <Hid"
     "den>true</Hidden>        <WakeToRun>false</WakeToRun>        <RunOnlyIfIdle>false</RunOnlyIfIdle>        <UseUnifie"
     "dSchedulingEngine>true</UseUnifiedSchedulingEngine>    </Settings>    <Actions Context=\"LocalSystem\">        <Com"
     "Handler>            <ClassId>{61f77d5e-afe9-400b-a5e6-e9e80fc8e601}</ClassId>        </ComHandler>    </Actions></Task>");
  if ( !v63 )
  {
    v4 = -2147024882;
    v11 = 2147942414LL;
    v12 = 902;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v11,
      (int)v81);
LABEL_68:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    goto LABEL_69;
  }
  v13 = ((__int64 (__fastcall *)(struct ITaskFolder *))v61->lpVtbl[1].QueryInterface)(v61);
  v4 = v13;
  if ( v13 < 0 )
  {
    v11 = (unsigned int)v13;
    v12 = 903;
    goto LABEL_13;
  }
  v62 = 0;
  v14 = v61;
  GetFolder = v61->lpVtbl->GetFolder;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  v16 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64 *))GetFolder)(v14, &v62);
  v4 = v16;
  if ( v16 < 0 )
  {
    v21 = 906;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v16,
      (int)v81);
LABEL_67:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    goto LABEL_68;
  }
  if ( UserOOBEController::s_IsLowStorageDevice(v18, v17, v19, v20) )
  {
    v68 = 0;
    v22 = v62;
    v23 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v62 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    v24 = v23(v22, 7, &v68);
    v4 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x390,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v24,
        (int)v81);
LABEL_22:
      v25 = &v68;
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
      goto LABEL_67;
    }
    v67 = 0;
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v68;
    v27 = **v68;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    v28 = v27(v26, &GUID_4c8fec3a_c218_4e0c_b23d_629024db91a2, &v67);
    v4 = v28;
    if ( v28 < 0 )
    {
      v29 = 914;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v28,
        (int)v81);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      goto LABEL_22;
    }
    pcbData[0] = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
                L"DeleteDemoContentDelay",
                pcbData) < 0
      || (v30 = pcbData[0], pcbData[0] < 0x1E) )
    {
      v30 = 30;
      pcbData[0] = 30;
    }
    else if ( pcbData[0] > 0x2760 )
    {
      v30 = 10080;
      pcbData[0] = 10080;
    }
    memset(v81, 0, sizeof(v81));
    v28 = StringCchPrintfW(v81, 0x10u, L"PT%dM", v30);
    v4 = v28;
    if ( v28 < 0 )
    {
      v29 = 928;
      goto LABEL_26;
    }
    (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v67 + 168LL))(v67, v81);
    v73 = 0;
    v31 = v67;
    v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    v33 = v32(v31, &v73);
    v4 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A6,
        (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
        (const char *)(unsigned int)v33,
        (int)v81);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      goto LABEL_27;
    }
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v73 + 64LL))(v73, L"PT30M");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
    v34 = &v68;
    goto LABEL_50;
  }
  v66 = 0;
  v35 = v62;
  v36 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v62 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
  v37 = v36(v35, 2, &v66);
  v4 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AC,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v37,
      (int)v81);
LABEL_40:
    v25 = &v66;
    goto LABEL_23;
  }
  v72 = 0;
  v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
  v39 = **v66;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v40 = v39(v38, &GUID_126c5cd8_b288_41d5_8dbf_e491446adc5c, &v72);
  v4 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v40,
      (int)v81);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    goto LABEL_40;
  }
  *(_QWORD *)v65 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v65,
    0);
  BoundaryTimeAfterDelay = OOBETaskSchedulerHelper::GetBoundaryTimeAfterDelay(v41, (unsigned int)v65, v42);
  v4 = BoundaryTimeAfterDelay;
  if ( BoundaryTimeAfterDelay < 0 )
  {
    v44 = 944;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)BoundaryTimeAfterDelay,
      (int)v81);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
    goto LABEL_43;
  }
  BoundaryTimeAfterDelay = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v66)[15])(
                             v66,
                             *(_QWORD *)v65);
  v4 = BoundaryTimeAfterDelay;
  if ( BoundaryTimeAfterDelay < 0 )
  {
    v44 = 945;
    goto LABEL_46;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v34 = &v66;
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
  v16 = PathCchCombine(pszPathOut, 0x104u, L"Microsoft\\Windows", L"RetailDemo");
  v4 = v16;
  if ( v16 < 0 )
  {
    v21 = 949;
    goto LABEL_18;
  }
  v16 = PathCchCombine(v83, 0x104u, pszPathOut, L"CleanupOfflineContent");
  v4 = v16;
  if ( v16 < 0 )
  {
    v21 = 952;
    goto LABEL_18;
  }
  wil::make_bstr_nothrow(v65, v83);
  v45 = *(_QWORD *)v65;
  if ( !*(_QWORD *)v65 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BA,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)0x8007000ELL,
      (int)v81);
LABEL_66:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
    goto LABEL_67;
  }
  v70 = 0;
  v46 = v61;
  get_Name = v61->lpVtbl->get_Name;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  v48 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64 *))get_Name)(v46, &v70);
  v49 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v48,
      (int)v81);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
    v4 = v49;
    goto LABEL_70;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 160LL))(v70, v45);
  v69.lpVtbl = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  v52 = OOBETaskSchedulerHelper::GetOrCreateTaskRootFolder(v50, pszPathOut, v51, v71, &v69, pvData);
  v4 = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v52,
      pdwTypea);
LABEL_65:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    goto LABEL_66;
  }
  wil::make_bstr_nothrow(v75, L"CleanupOfflineContent");
  v53 = v75[0];
  if ( !v75[0] )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C4,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)0x8007000ELL,
      pdwTypea);
LABEL_64:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v75);
    goto LABEL_65;
  }
  (*((void (__fastcall **)(struct ITaskServiceVtbl *, _QWORD, _QWORD))v69.lpVtbl->QueryInterface + 15))(
    v69.lpVtbl,
    v75[0],
    0);
  v74 = 0;
  lpVtbl = v69.lpVtbl;
  v55 = (__int64 (__fastcall *)(struct ITaskServiceVtbl *, __int64, struct ITaskFolder *, __int64))*((_QWORD *)v69.lpVtbl->QueryInterface + 17);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  v76 = 0;
  *(_OWORD *)v77 = v6;
  *(_QWORD *)&v77[14] = v7;
  v79 = 0;
  *(_OWORD *)v80 = v6;
  *(_QWORD *)&v80[14] = v7;
  LOWORD(v78[0]) = 0;
  *(_OWORD *)((char *)v78 + 2) = v6;
  v78[2] = v7;
  v56 = v55(lpVtbl, v53, v61, 6);
  v4 = v56;
  if ( v56 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C9,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v56,
      (int)v78);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    goto LABEL_64;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v75);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  return 0;
}

```

## disassembly

```asm
0x180029b68  mov     rax, rsp
0x180029b6b  push    rbp
0x180029b6c  push    rbx
0x180029b6d  push    rsi
0x180029b6e  push    rdi
0x180029b6f  push    r14
0x180029b71  lea     rbp, [rax-4C8h]
0x180029b78  sub     rsp, 5A0h
0x180029b7f  movaps  xmmword ptr [rax-38h], xmm6
0x180029b83  movaps  xmmword ptr [rax-48h], xmm7
0x180029b87  mov     rax, cs:__security_cookie
0x180029b8e  xor     rax, rsp
0x180029b91  mov     [rbp+4C0h+var_50], rax
0x180029b98  xor     r14d, r14d
0x180029b9b  mov     dword ptr [rsp+5C0h+var_570], r14d
0x180029ba0  lea     ebx, [r14+4]
0x180029ba4  mov     [rsp+5C0h+var_558], ebx
0x180029ba8  lea     rax, [rsp+5C0h+var_558]
0x180029bad  mov     [rsp+5C0h+pcbData], rax; pcbData
0x180029bb2  lea     rax, [rsp+5C0h+var_570]
0x180029bb7  mov     [rsp+5C0h+pvData], rax; pvData
0x180029bbc  mov     [rsp+5C0h+pdwType], r14; pdwType
0x180029bc1  mov     r9d, 10010h; dwFlags
0x180029bc7  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180029bce  lea     rdx, aOsdataSoftware_0; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x180029bd5  mov     rsi, 0FFFFFFFF80000002h
0x180029bdc  mov     rcx, rsi; hkey
0x180029bdf  call    cs:__imp_RegGetValueW
0x180029be5  test    eax, eax
0x180029be7  jz      short loc_180029C23
0x180029be9  mov     [rsp+5C0h+var_558], ebx
0x180029bed  lea     rax, [rsp+5C0h+var_558]
0x180029bf2  mov     [rsp+5C0h+pcbData], rax; pcbData
0x180029bf7  lea     rax, [rsp+5C0h+var_570]
0x180029bfc  mov     [rsp+5C0h+pvData], rax; struct ITaskFolder **
0x180029c01  mov     [rsp+5C0h+pdwType], r14; pdwType
0x180029c06  mov     r9d, 20010010h; dwFlags
0x180029c0c  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x180029c13  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180029c1a  mov     rcx, rsi; hkey
0x180029c1d  call    cs:__imp_RegGetValueW
0x180029c23  cmp     dword ptr [rsp+5C0h+var_570], r14d
0x180029c28  jnz     loc_18002A44A
0x180029c2e  mov     [rbp+4C0h+var_520], r14
0x180029c32  lea     rcx, [rbp+4C0h+var_520]
0x180029c36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029c3b  lea     r9, [rbp+4C0h+var_520]; void **
0x180029c3f  call    ?SHExtCoCreateFromRegKey@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z; SHExtCoCreateFromRegKey(ushort const *,ushort const *,_GUID const &,void * *)
0x180029c44  mov     ebx, eax
0x180029c46  test    eax, eax
0x180029c48  jns     short loc_180029C51
0x180029c4a  mov     edx, 37Eh
0x180029c4f  jmp     short loc_180029CC2
0x180029c51  mov     rcx, [rbp+4C0h+var_520]
0x180029c55  mov     [rbp+4C0h+var_490], r14w
0x180029c5a  movups  xmm6, xmmword ptr [rbp+4C0h+var_4EE]
0x180029c5e  movups  xmmword ptr [rbp+4C0h+var_490+2], xmm6
0x180029c62  movsd   xmm7, qword ptr [rbp+4C0h+var_4EE+0Eh]
0x180029c67  movsd   qword ptr [rbp+4C0h+var_480], xmm7
0x180029c6c  mov     word ptr [rbp+4C0h+var_4D0], r14w
0x180029c71  movups  xmmword ptr [rbp+4C0h+var_4D0+2], xmm6
0x180029c75  movsd   [rbp+4C0h+var_4D0+10h], xmm7
0x180029c7a  mov     [rbp+4C0h+var_4B0], r14w
0x180029c7f  movups  xmmword ptr [rbp+4C0h+var_4AE], xmm6
0x180029c83  movsd   qword ptr [rbp+4C0h+var_4AE+0Eh], xmm7
0x180029c88  mov     [rbp+4C0h+var_4F0], r14w
0x180029c8d  movups  xmmword ptr [rbp+4C0h+var_4EE], xmm6
0x180029c91  movsd   qword ptr [rbp+4C0h+var_4EE+0Eh], xmm7
0x180029c96  mov     rax, [rcx]
0x180029c99  lea     rdx, [rbp+4C0h+var_490]
0x180029c9d  mov     [rsp+5C0h+pdwType], rdx; int
0x180029ca2  lea     r9, [rbp+4C0h+var_4D0]
0x180029ca6  lea     r8, [rbp+4C0h+var_4B0]
0x180029caa  lea     rdx, [rbp+4C0h+var_4F0]
0x180029cae  mov     rax, [rax+50h]
0x180029cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cb7  mov     ebx, eax
0x180029cb9  test    eax, eax
0x180029cbb  jns     short loc_180029CDD
0x180029cbd  mov     edx, 380h; void *
0x180029cc2  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029cc9  mov     r9d, eax; char *
0x180029ccc  mov     rcx, [rbp+4C8h]; this
0x180029cd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029cd8  jmp     loc_18002A3E0
0x180029cdd  mov     [rsp+5C0h+var_570], r14
0x180029ce2  mov     rdi, [rbp+4C0h+var_520]
0x180029ce6  mov     rax, [rdi]
0x180029ce9  mov     rbx, [rax+48h]
0x180029ced  lea     rcx, [rsp+5C0h+var_570]
0x180029cf2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029cf7  lea     r8, [rsp+5C0h+var_570]
0x180029cfc  xor     edx, edx
0x180029cfe  mov     rcx, rdi
0x180029d01  mov     rax, rbx
0x180029d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d09  mov     ebx, eax
0x180029d0b  test    eax, eax
0x180029d0d  jns     short loc_180029D2F
0x180029d0f  mov     rcx, [rbp+4C8h]; this
0x180029d16  mov     r9d, eax; char *
0x180029d19  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029d20  mov     edx, 383h; void *
0x180029d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d2a  jmp     loc_18002A3D5
0x180029d2f  lea     rdx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x180029d36  lea     rcx, [rsp+5C0h+var_560]
0x180029d3b  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180029d40  nop
0x180029d41  mov     rdx, [rsp+5C0h+var_560]
0x180029d46  test    rdx, rdx
0x180029d49  jnz     short loc_180029D70
0x180029d4b  mov     ebx, 8007000Eh
0x180029d50  mov     r9d, ebx; char *
0x180029d53  mov     edx, 386h; void *
0x180029d58  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029d5f  mov     rcx, [rbp+4C8h]; this
0x180029d66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d6b  jmp     loc_18002A3CA
0x180029d70  mov     rcx, [rsp+5C0h+var_570]
0x180029d75  mov     rax, [rcx]
0x180029d78  mov     rax, [rax+0A0h]
0x180029d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d84  mov     ebx, eax
0x180029d86  test    eax, eax
0x180029d88  jns     short loc_180029D94
0x180029d8a  mov     r9d, eax
0x180029d8d  mov     edx, 387h
0x180029d92  jmp     short loc_180029D58
0x180029d94  mov     [rsp+5C0h+var_568], r14
0x180029d99  mov     rdi, [rsp+5C0h+var_570]
0x180029d9e  mov     rax, [rdi]
0x180029da1  mov     rbx, [rax+48h]
0x180029da5  lea     rcx, [rsp+5C0h+var_568]
0x180029daa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029daf  lea     rdx, [rsp+5C0h+var_568]
0x180029db4  mov     rcx, rdi
0x180029db7  mov     rax, rbx
0x180029dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dbf  mov     ebx, eax
0x180029dc1  test    eax, eax
0x180029dc3  jns     short loc_180029DE5
0x180029dc5  mov     edx, 38Ah; void *
0x180029dca  mov     rcx, [rbp+4C8h]; this
0x180029dd1  mov     r9d, eax; char *
0x180029dd4  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029de0  jmp     loc_18002A3BF
0x180029de5  call    ?s_IsLowStorageDevice@UserOOBEController@@CA_NXZ; UserOOBEController::s_IsLowStorageDevice(void)
0x180029dea  test    al, al
0x180029dec  jz      loc_180029FC9
0x180029df2  mov     [rbp+4C0h+var_538], r14
0x180029df6  mov     rdi, [rsp+5C0h+var_568]
0x180029dfb  mov     rax, [rdi]
0x180029dfe  mov     rbx, [rax+50h]
0x180029e02  lea     rcx, [rbp+4C0h+var_538]
0x180029e06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029e0b  lea     r8, [rbp+4C0h+var_538]
0x180029e0f  mov     edx, 7
0x180029e14  mov     rcx, rdi
0x180029e17  mov     rax, rbx
0x180029e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e1f  mov     ebx, eax
0x180029e21  test    eax, eax
0x180029e23  jns     short loc_180029E4F
0x180029e25  mov     rcx, [rbp+4C8h]; this
0x180029e2c  mov     r9d, eax; char *
0x180029e2f  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029e36  mov     edx, 390h; void *
0x180029e3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e40  nop
0x180029e41  lea     rcx, [rbp+4C0h+var_538]
0x180029e45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029e4a  jmp     loc_18002A3BF
0x180029e4f  mov     [rbp+4C0h+var_540], r14
0x180029e53  mov     rbx, [rbp+4C0h+var_538]
0x180029e57  mov     rax, [rbx]
0x180029e5a  mov     rdi, [rax]
0x180029e5d  lea     rcx, [rbp+4C0h+var_540]
0x180029e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029e66  lea     r8, [rbp+4C0h+var_540]
0x180029e6a  lea     rdx, _GUID_4c8fec3a_c218_4e0c_b23d_629024db91a2
0x180029e71  mov     rcx, rbx
0x180029e74  mov     rax, rdi
0x180029e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e7c  mov     ebx, eax
0x180029e7e  test    eax, eax
0x180029e80  jns     short loc_180029EA9
0x180029e82  mov     edx, 392h; void *
0x180029e87  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029e8e  mov     r9d, eax; char *
0x180029e91  mov     rcx, [rbp+4C8h]; this
0x180029e98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e9d  nop
0x180029e9e  lea     rcx, [rbp+4C0h+var_540]
0x180029ea2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029ea7  jmp     short loc_180029E41
0x180029ea9  mov     [rsp+5C0h+var_558], r14d
0x180029eae  lea     r9, [rsp+5C0h+var_558]; unsigned int *
0x180029eb3  lea     r8, aDeletedemocont; "DeleteDemoContentDelay"
0x180029eba  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180029ec1  mov     rcx, rsi; HKEY
0x180029ec4  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180029ec9  test    eax, eax
0x180029ecb  js      short loc_180029EEB
0x180029ecd  mov     r9d, [rsp+5C0h+var_558]
0x180029ed2  cmp     r9d, 1Eh
0x180029ed6  jb      short loc_180029EEB
0x180029ed8  mov     eax, 2760h
0x180029edd  cmp     r9d, eax
0x180029ee0  jbe     short loc_180029EF6
0x180029ee2  mov     r9d, eax
0x180029ee5  mov     [rsp+5C0h+var_558], eax
0x180029ee9  jmp     short loc_180029EF6
0x180029eeb  mov     r9d, 1Eh
0x180029ef1  mov     [rsp+5C0h+var_558], r9d
0x180029ef6  xorps   xmm0, xmm0
0x180029ef9  movups  xmmword ptr [rbp+4C0h+var_490], xmm0
0x180029efd  movups  [rbp+4C0h+var_480], xmm0
0x180029f01  lea     r8, aPtDm; "PT%dM"
0x180029f08  mov     edx, 10h; unsigned __int64
0x180029f0d  lea     rcx, [rbp+4C0h+var_490]; unsigned __int16 *
0x180029f11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029f16  mov     ebx, eax
0x180029f18  test    eax, eax
0x180029f1a  jns     short loc_180029F26
0x180029f1c  mov     edx, 3A0h
0x180029f21  jmp     loc_180029E87
0x180029f26  mov     rcx, [rbp+4C0h+var_540]
0x180029f2a  mov     rax, [rcx]
0x180029f2d  lea     rdx, [rbp+4C0h+var_490]
0x180029f31  mov     rax, [rax+0A8h]
0x180029f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f3d  mov     [rbp+4C0h+var_510], r14
0x180029f41  mov     rdi, [rbp+4C0h+var_540]
0x180029f45  mov     rax, [rdi]
0x180029f48  mov     rbx, [rax+50h]
0x180029f4c  lea     rcx, [rbp+4C0h+var_510]
0x180029f50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029f55  lea     rdx, [rbp+4C0h+var_510]
0x180029f59  mov     rcx, rdi
0x180029f5c  mov     rax, rbx
0x180029f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f64  mov     ebx, eax
0x180029f66  test    eax, eax
0x180029f68  jns     short loc_180029F94
0x180029f6a  mov     rcx, [rbp+4C8h]; this
0x180029f71  mov     r9d, eax; char *
0x180029f74  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029f7b  mov     edx, 3A6h; void *
0x180029f80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f85  nop
0x180029f86  lea     rcx, [rbp+4C0h+var_510]
0x180029f8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029f8f  jmp     loc_180029E9E
0x180029f94  mov     rcx, [rbp+4C0h+var_510]
0x180029f98  mov     rax, [rcx]
0x180029f9b  lea     rdx, aPt30m; "PT30M"
0x180029fa2  mov     rax, [rax+40h]
0x180029fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fab  nop
0x180029fac  lea     rcx, [rbp+4C0h+var_510]
0x180029fb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029fb5  nop
0x180029fb6  lea     rcx, [rbp+4C0h+var_540]
0x180029fba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029fbf  nop
0x180029fc0  lea     rcx, [rbp+4C0h+var_538]
0x180029fc4  jmp     loc_18002A106
0x180029fc9  mov     [rsp+5C0h+var_548], r14
0x180029fce  mov     rdi, [rsp+5C0h+var_568]
0x180029fd3  mov     rax, [rdi]
0x180029fd6  mov     rbx, [rax+50h]
0x180029fda  lea     rcx, [rsp+5C0h+var_548]
0x180029fdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029fe4  lea     r8, [rsp+5C0h+var_548]
0x180029fe9  mov     edx, 2
0x180029fee  mov     rcx, rdi
0x180029ff1  mov     rax, rbx
0x180029ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ff9  mov     ebx, eax
0x180029ffb  test    eax, eax
0x180029ffd  jns     short loc_18002A025
0x180029fff  mov     rcx, [rbp+4C8h]; this
0x18002a006  mov     r9d, eax; char *
0x18002a009  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002a010  mov     edx, 3ACh; void *
0x18002a015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a01a  nop
0x18002a01b  lea     rcx, [rsp+5C0h+var_548]
0x18002a020  jmp     loc_180029E45
0x18002a025  mov     [rbp+4C0h+var_518], r14
0x18002a029  mov     rbx, [rsp+5C0h+var_548]
0x18002a02e  mov     rax, [rbx]
0x18002a031  mov     rdi, [rax]
0x18002a034  lea     rcx, [rbp+4C0h+var_518]
0x18002a038  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a03d  lea     r8, [rbp+4C0h+var_518]
0x18002a041  lea     rdx, _GUID_126c5cd8_b288_41d5_8dbf_e491446adc5c
0x18002a048  mov     rcx, rbx
  ... truncated ...
```
