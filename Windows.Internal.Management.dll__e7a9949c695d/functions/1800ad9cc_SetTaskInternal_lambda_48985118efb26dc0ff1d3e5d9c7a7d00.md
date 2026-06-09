# SetTaskInternal__lambda_48985118efb26dc0ff1d3e5d9c7a7d00_

- ea: `0x1800ad9cc`
- end: `0x1800ae3c3`
- name: `SetTaskInternal__lambda_48985118efb26dc0ff1d3e5d9c7a7d00___`
- size: `2551`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180077330`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015720`
- `0x1800168d0`
- `0x1800168fc`
- `0x180024cd0`
- `0x18003ec00`
- `0x18007a328`
- `0x18009f5e8`
- `0x1800a08e8`
- `0x1800a5eb0`
- `0x1800a6368`
- `0x1800ad96c`
- `0x1800ad9cc`
- `0x1800ae678`
- `0x1800ae6c8`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ada4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ada4e`
- `OLEAUT32!__imp_VariantInit` at `0x1800ada82`
- `OLEAUT32!__imp_VariantInit` at `0x1800ada98`
- `OLEAUT32!__imp_VariantInit` at `0x1800adaae`
- `OLEAUT32!__imp_VariantInit` at `0x1800adac2`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae132`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae20d`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae223`
- `OLEAUT32!__imp_VariantInit` at `0x1800ada82`
- `OLEAUT32!__imp_VariantInit` at `0x1800ada98`
- `OLEAUT32!__imp_VariantInit` at `0x1800adaae`
- `OLEAUT32!__imp_VariantInit` at `0x1800adac2`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae132`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae20d`
- `OLEAUT32!__imp_VariantInit` at `0x1800ae223`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb47`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb52`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb5d`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb68`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae1a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2f0`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb47`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb52`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb5d`
- `OLEAUT32!__imp_VariantClear` at `0x1800adb68`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae1a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae2f0`

## string_xrefs

- `0x1800adbca`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">        <RegistrationInfo>            <Author>$(@%systemRoot%\system32\ProvTool.exe,-101)</Author>            <Description>$(@%systemRoot%\system32\ProvTool.exe,-102)</Description>            <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>        </RegistrationInfo>        <Principals>            <Principal id="LocalSystem">                <UserId>S-1-5-18</Us`
- `0x1800ada62`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adb31`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adba9`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adbf8`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adc7e`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adcd4`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800add26`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800add72`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adda8`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800addf3`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ade3c`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ade6d`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adf94`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800adfe9`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ae038`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ae0fc`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ae182`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ae1c4`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800ae2b6`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
__int64 __fastcall SetTaskInternal__lambda_48985118efb26dc0ff1d3e5d9c7a7d00_(_QWORD *a1)
{
  HRESULT v2; // eax
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v5; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v7; // xmm8
  IRecordInfo *v8; // xmm9_8
  __int128 v9; // xmm6
  IRecordInfo *v10; // xmm7_8
  int v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, _QWORD, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD); // rbx
  _QWORD *bstr; // rax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD); // rbx
  __int64 v24; // rax
  _QWORD *v25; // rax
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, __int64 *); // rbx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *); // rbx
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, __int64 *); // rbx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, _QWORD); // rbx
  __int64 v50; // rax
  _QWORD *v51; // rax
  int v52; // eax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, __int64 *); // rbx
  int v55; // eax
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, _QWORD); // rbx
  _QWORD *v58; // rax
  int v59; // eax
  LPVOID v60; // rdi
  __int64 (__fastcall *v61)(LPVOID, _QWORD, __int64 *); // rbx
  _QWORD *v62; // rax
  int v63; // ebx
  LPVOID v64; // rdi
  __int64 (__fastcall *v65)(LPVOID, _QWORD, __int64 *); // rbx
  _QWORD *v66; // rax
  int v67; // eax
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, _QWORD, VARIANTARG *, __int64 *); // rbx
  __int128 v70; // xmm6
  IRecordInfo *v71; // xmm7_8
  _QWORD *v72; // rax
  int v73; // eax
  __int64 v74; // rsi
  __int64 (__fastcall *v75)(__int64, _QWORD, __int64, __int64); // rdi
  const unsigned __int16 *v76; // rdx
  auto_variant *v77; // rax
  __int128 v78; // xmm10
  IRecordInfo *v79; // xmm11_8
  __int128 v80; // xmm8
  IRecordInfo *v81; // xmm9_8
  __int128 v82; // xmm6
  IRecordInfo *v83; // xmm7_8
  __int64 v84; // rbx
  _QWORD *v85; // rax
  int v86; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  __int64 v89; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v90; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v91; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v92; // [rsp+70h] [rbp-98h] BYREF
  __int64 v93; // [rsp+78h] [rbp-90h] BYREF
  __int64 v94; // [rsp+80h] [rbp-88h] BYREF
  __int64 v95; // [rsp+88h] [rbp-80h] BYREF
  __int64 v96; // [rsp+90h] [rbp-78h] BYREF
  __int64 v97; // [rsp+98h] [rbp-70h] BYREF
  __int64 v98; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v99; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v100; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v101; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG v102; // [rsp+C0h] [rbp-48h] BYREF
  VARIANTARG v103; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v104; // [rsp+F0h] [rbp-18h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG v106; // [rsp+128h] [rbp+20h] BYREF
  int v107[4]; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v108; // [rsp+158h] [rbp+50h]
  __int128 v109; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v110; // [rsp+178h] [rbp+70h]
  VARIANTARG v111; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v112[32]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v113[32]; // [rsp+1C8h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  v91 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v91);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  v3 = v91;
  v4 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v91 + 80LL);
  VariantInit(&pvarg);
  v5 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v102);
  v7 = *(_OWORD *)&v102.vt;
  v8 = v102.pRecInfo;
  VariantInit(&v104);
  v9 = *(_OWORD *)&v104.vt;
  v10 = v104.pRecInfo;
  VariantInit(&v103);
  *(_OWORD *)&v111.vt = v5;
  v111.pRecInfo = pRecInfo;
  *(_OWORD *)v107 = v7;
  v108 = v8;
  v109 = v9;
  v110 = v10;
  v106 = v103;
  v11 = v4(v3, &v106, &v109, v107);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v11,
      (int)&v111);
  VariantClear(&v103);
  VariantClear(&v104);
  VariantClear(&v102);
  VariantClear(&pvarg);
  v90 = 0;
  v12 = v91;
  v13 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v91 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  v14 = v13(v12, 0, &v90);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v14,
      (int)&v111);
  v15 = v90;
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v90 + 160LL);
  bstr = (_QWORD *)wil::make_bstr(
                     &v89,
                     L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-"
                      "microsoft-com:asm.v3\">        <RegistrationInfo>            <Author>$(@%systemRoot%\\system32\\Pr"
                      "ovTool.exe,-101)</Author>            <Description>$(@%systemRoot%\\system32\\ProvTool.exe,-102)</D"
                      "escription>            <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>        "
                      "</RegistrationInfo>        <Principals>            <Principal id=\"LocalSystem\">                <"
                      "UserId>S-1-5-18</UserId>                <RunLevel>HighestAvailable</RunLevel>            </Princip"
                      "al>        </Principals>        <Settings>            <MultipleInstancesPolicy>Queue</MultipleInst"
                      "ancesPolicy>            <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>            "
                      "<StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>            <AllowHardTerminate>false</Allow"
                      "HardTerminate>            <StartWhenAvailable>true</StartWhenAvailable>            <RunOnlyIfNetwo"
                      "rkAvailable>false</RunOnlyIfNetworkAvailable>            <AllowStartOnDemand>false</AllowStartOnDe"
                      "mand>            <Hidden>true</Hidden>            <RunOnlyIfIdle>false</RunOnlyIfIdle>            "
                      "<UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>        </Settings>        <Actions C"
                      "ontext=\"LocalSystem\">            <Exec>                <Command>%windir%\\system32\\ProvTool.exe"
                      "</Command>            </Exec>        </Actions>    </Task>");
  v18 = v16(v15, *bstr);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v18,
      (int)&v111);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
  std::wstring::wstring(v113, L"\\Microsoft\\Windows\\Management\\Provisioning");
  std::wstring::push_back(v113, 92);
  std::wstring::append(v113, *a1);
  v99 = 0;
  v19 = v90;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
  v21 = v20(v19, &v99);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v21,
      (int)&v111);
  v22 = v99;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v99 + 160LL);
  v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v113);
  v25 = (_QWORD *)wil::make_bstr(&v89, v24);
  v26 = v23(v22, *v25);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v26,
      (int)&v111);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
  v98 = 0;
  v27 = v90;
  v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
  v29 = v28(v27, &v98);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v29,
      (int)&v111);
  v97 = 0;
  v30 = v98;
  v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v98 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
  v32 = v31(v30, 7, &v97);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v32,
      (int)&v111);
  v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v97 + 152LL))(v97, 0xFFFFFFFFLL);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v33,
      (int)&v111);
  v96 = 0;
  v34 = v90;
  v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
  v36 = v35(v34, &v96);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v36,
      (int)&v111);
  v95 = 0;
  v37 = v96;
  v38 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v96 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
  v39 = v38(v37, 1, &v95);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v39,
      (int)&v111);
  v101 = 0;
  v40 = Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(&v95, &v101);
  if ( v40 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v40,
      (int)&v111);
  std::wstring::wstring(v112, L"/turn ");
  v41 = std::to_wstring(&v106, *((unsigned int *)a1 + 2));
  std::wstring::append(v112, v41);
  std::wstring::~wstring(&v106);
  v42 = std::wstring::wstring(&pvarg, a1[2]);
  v43 = std::wstring::wstring(&v111, L" /source");
  v45 = std::operator+<unsigned short>(v107, v44, v43);
  v46 = std::operator+<unsigned short>(&v109, v45, L" ");
  v47 = std::operator+<unsigned short>(&v106, v46, v42);
  std::wstring::append(v112, v47);
  std::wstring::~wstring(&v106);
  std::wstring::~wstring(&v109);
  std::wstring::~wstring(v107);
  std::wstring::~wstring(&v111);
  std::wstring::~wstring(&pvarg);
  v48 = v101;
  v49 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v101 + 104LL);
  v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v112);
  v51 = (_QWORD *)wil::make_bstr(&v89, v50);
  v52 = v49(v48, *v51);
  if ( v52 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v52,
      (int)&v111);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
  v94 = 0;
  v53 = v90;
  v54 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  v55 = v54(v53, &v94);
  if ( v55 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v55,
      (int)&v111);
  v56 = v94;
  v57 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v94 + 256LL);
  v58 = (_QWORD *)wil::make_bstr(&v89, L"PT0S");
  v59 = v57(v56, *v58);
  if ( v59 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v59,
      (int)&v111);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
  v92 = 0;
  v60 = v91;
  v61 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v91 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  v62 = (_QWORD *)wil::make_bstr(&v89, L"\\Microsoft\\Windows\\Management\\Provisioning");
  v63 = v61(v60, *v62, &v92);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v89);
  if ( (unsigned int)(v63 + 2147024894) <= 1 )
  {
    v89 = 0;
    v64 = v91;
    v65 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v91 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
    v66 = (_QWORD *)wil::make_bstr(&v93, L"\\");
    v67 = v65(v64, *v66, &v89);
    if ( v67 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
        (const char *)(unsigned int)v67,
        (int)&v111);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
    v68 = v89;
    v69 = *(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *, __int64 *))(*(_QWORD *)v89 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    VariantInit(&pvarg);
    v70 = *(_OWORD *)&pvarg.vt;
    v71 = pvarg.pRecInfo;
    v72 = (_QWORD *)wil::make_bstr(&v93, L"Microsoft\\Windows\\Management\\Provisioning");
    *(_OWORD *)&v106.vt = v70;
    v106.pRecInfo = v71;
    v73 = v69(v68, *v72, &v106, &v92);
    if ( v73 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
        (const char *)(unsigned int)v73,
        (int)&v111);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
    VariantClear(&pvarg);
    v63 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v89);
  }
  if ( v63 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v63,
      (int)&v111);
  v100 = 0;
  v74 = v92;
  v75 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v92 + 136LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
  v77 = auto_variant::auto_variant((auto_variant *)&v111, v76);
  v78 = *(_OWORD *)v77;
  v79 = (IRecordInfo *)*((_QWORD *)v77 + 2);
  VariantInit(&v102);
  v80 = *(_OWORD *)&v102.vt;
  v81 = v102.pRecInfo;
  VariantInit(&pvarg);
  v82 = *(_OWORD *)&pvarg.vt;
  v83 = pvarg.pRecInfo;
  v84 = v90;
  v85 = (_QWORD *)wil::make_bstr(&v93, *a1);
  *(_OWORD *)&v106.vt = v78;
  v106.pRecInfo = v79;
  v109 = v80;
  v110 = v81;
  *(_OWORD *)v107 = v82;
  v108 = v83;
  v86 = v75(v74, *v85, v84, 6);
  if ( v86 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v86,
      (int)v107);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v93);
  VariantClear(&pvarg);
  VariantClear(&v102);
  VariantClear(&v111);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v100);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  std::wstring::~wstring(v112);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v99);
  std::wstring::~wstring(v113);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v90);
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v91);
}

```

## disassembly

```asm
0x1800ad9cc  mov     rax, rsp
0x1800ad9cf  push    rbp
0x1800ad9d0  push    rbx
0x1800ad9d1  push    rsi
0x1800ad9d2  push    rdi
0x1800ad9d3  push    r14
0x1800ad9d5  push    r15
0x1800ad9d7  lea     rbp, [rax-188h]
0x1800ad9de  sub     rsp, 258h
0x1800ad9e5  movaps  xmmword ptr [rax-48h], xmm6
0x1800ad9e9  movaps  xmmword ptr [rax-58h], xmm7
0x1800ad9ed  movaps  xmmword ptr [rax-68h], xmm8
0x1800ad9f2  movaps  xmmword ptr [rax-78h], xmm9
0x1800ad9f7  movaps  xmmword ptr [rax-88h], xmm10
0x1800ad9ff  movaps  xmmword ptr [rax-98h], xmm11
0x1800ada07  mov     rax, cs:__security_cookie
0x1800ada0e  xor     rax, rsp
0x1800ada11  mov     [rbp+180h+var_A0], rax
0x1800ada18  mov     r14, rcx
0x1800ada1b  xor     r15d, r15d
0x1800ada1e  mov     [rsp+280h+var_220], r15
0x1800ada23  lea     rcx, [rsp+280h+var_220]
0x1800ada28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ada2d  lea     rax, [rsp+280h+var_220]
0x1800ada32  mov     [rsp+280h+ppv], rax; int
0x1800ada37  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800ada3e  lea     esi, [r15+1]
0x1800ada42  mov     r8d, esi; dwClsContext
0x1800ada45  xor     edx, edx; pUnkOuter
0x1800ada47  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800ada4e  call    cs:__imp_CoCreateInstance
0x1800ada54  mov     rcx, [rbp+188h]; this
0x1800ada5b  test    eax, eax
0x1800ada5d  jns     short loc_1800ADA72
0x1800ada5f  mov     r9d, eax; char *
0x1800ada62  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800ada69  lea     edx, [rsi+50h]; void *
0x1800ada6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ada72  mov     rdi, [rsp+280h+var_220]
0x1800ada77  mov     rax, [rdi]
0x1800ada7a  mov     rbx, [rax+50h]
0x1800ada7e  lea     rcx, [rbp+180h+pvarg]; pvarg
0x1800ada82  call    cs:__imp_VariantInit
0x1800ada88  nop
0x1800ada89  movups  xmm10, xmmword ptr [rbp+180h+pvarg]
0x1800ada8e  movsd   xmm11, qword ptr [rbp+180h+pvarg+10h]
0x1800ada94  lea     rcx, [rbp+180h+var_1C8]; pvarg
0x1800ada98  call    cs:__imp_VariantInit
0x1800ada9e  nop
0x1800ada9f  movups  xmm8, xmmword ptr [rbp+180h+var_1C8]
0x1800adaa4  movsd   xmm9, qword ptr [rbp+180h+var_1C8+10h]
0x1800adaaa  lea     rcx, [rbp+180h+var_198]; pvarg
0x1800adaae  call    cs:__imp_VariantInit
0x1800adab4  nop
0x1800adab5  movups  xmm6, xmmword ptr [rbp+180h+var_198]
0x1800adab9  movsd   xmm7, qword ptr [rbp+180h+var_198+10h]
0x1800adabe  lea     rcx, [rbp+180h+var_1B0]; pvarg
0x1800adac2  call    cs:__imp_VariantInit
0x1800adac8  nop
0x1800adac9  movups  xmm0, xmmword ptr [rbp+180h+var_1B0]
0x1800adacd  movsd   xmm1, qword ptr [rbp+180h+var_1B0+10h]
0x1800adad2  movaps  xmmword ptr [rbp+180h+var_100], xmm10
0x1800adada  movsd   qword ptr [rbp+180h+var_100+10h], xmm11
0x1800adae3  movaps  xmmword ptr [rbp+180h+var_140], xmm8
0x1800adae8  movsd   [rbp+180h+var_130], xmm9
0x1800adaee  movaps  [rbp+180h+var_120], xmm6
0x1800adaf2  movsd   [rbp+180h+var_110], xmm7
0x1800adaf7  movaps  [rbp+180h+var_160], xmm0
0x1800adafb  movsd   [rbp+180h+var_150], xmm1
0x1800adb00  lea     rax, [rbp+180h+var_100]
0x1800adb07  mov     [rsp+280h+ppv], rax; int
0x1800adb0c  lea     r9, [rbp+180h+var_140]
0x1800adb10  lea     r8, [rbp+180h+var_120]
0x1800adb14  lea     rdx, [rbp+180h+var_160]
0x1800adb18  mov     rcx, rdi
0x1800adb1b  mov     rax, rbx
0x1800adb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb23  mov     rcx, [rbp+188h]; this
0x1800adb2a  test    eax, eax
0x1800adb2c  jns     short loc_1800ADB43
0x1800adb2e  mov     r9d, eax; char *
0x1800adb31  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800adb38  mov     edx, 53h ; 'S'; void *
0x1800adb3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adb43  lea     rcx, [rbp+180h+var_1B0]; pvarg
0x1800adb47  call    cs:__imp_VariantClear
0x1800adb4d  nop
0x1800adb4e  lea     rcx, [rbp+180h+var_198]; pvarg
0x1800adb52  call    cs:__imp_VariantClear
0x1800adb58  nop
0x1800adb59  lea     rcx, [rbp+180h+var_1C8]; pvarg
0x1800adb5d  call    cs:__imp_VariantClear
0x1800adb63  nop
0x1800adb64  lea     rcx, [rbp+180h+pvarg]; pvarg
0x1800adb68  call    cs:__imp_VariantClear
0x1800adb6e  mov     [rsp+280h+var_228], r15
0x1800adb73  mov     rdi, [rsp+280h+var_220]
0x1800adb78  mov     rax, [rdi]
0x1800adb7b  mov     rbx, [rax+48h]
0x1800adb7f  lea     rcx, [rsp+280h+var_228]
0x1800adb84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800adb89  lea     r8, [rsp+280h+var_228]
0x1800adb8e  xor     edx, edx
0x1800adb90  mov     rcx, rdi
0x1800adb93  mov     rax, rbx
0x1800adb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb9b  mov     rcx, [rbp+188h]; this
0x1800adba2  test    eax, eax
0x1800adba4  jns     short loc_1800ADBBB
0x1800adba6  mov     r9d, eax; char *
0x1800adba9  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800adbb0  mov     edx, 56h ; 'V'; void *
0x1800adbb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adbbb  mov     rdi, [rsp+280h+var_228]
0x1800adbc0  mov     rax, [rdi]
0x1800adbc3  mov     rbx, [rax+0A0h]
0x1800adbca  lea     rdx, aTaskXmlnsHttpS_0; "<Task xmlns=\"http://schemas.microsoft."...
0x1800adbd1  lea     rcx, [rsp+280h+var_230]
0x1800adbd6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800adbdb  nop
0x1800adbdc  mov     rdx, [rax]
0x1800adbdf  mov     rcx, rdi
0x1800adbe2  mov     rax, rbx
0x1800adbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adbea  mov     rcx, [rbp+188h]; this
0x1800adbf1  test    eax, eax
0x1800adbf3  jns     short loc_1800ADC0A
0x1800adbf5  mov     r9d, eax; char *
0x1800adbf8  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800adbff  mov     edx, 57h ; 'W'; void *
0x1800adc04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adc0a  lea     rcx, [rsp+280h+var_230]
0x1800adc0f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800adc14  lea     rdx, aMicrosoftWindo_3; "\\Microsoft\\Windows\\Management\\Provi"...
0x1800adc1b  lea     rcx, [rbp+180h+var_C0]
0x1800adc22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800adc27  nop
0x1800adc28  mov     edx, 5Ch ; '\'
0x1800adc2d  lea     rcx, [rbp+180h+var_C0]
0x1800adc34  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800adc39  mov     rdx, [r14]
0x1800adc3c  lea     rcx, [rbp+180h+var_C0]
0x1800adc43  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800adc48  mov     [rbp+180h+var_1E0], r15
0x1800adc4c  mov     rdi, [rsp+280h+var_228]
0x1800adc51  mov     rax, [rdi]
0x1800adc54  mov     rbx, [rax+38h]
0x1800adc58  lea     rcx, [rbp+180h+var_1E0]
0x1800adc5c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800adc61  lea     rdx, [rbp+180h+var_1E0]
0x1800adc65  mov     rcx, rdi
0x1800adc68  mov     rax, rbx
0x1800adc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc70  mov     rcx, [rbp+188h]; this
0x1800adc77  test    eax, eax
0x1800adc79  jns     short loc_1800ADC90
0x1800adc7b  mov     r9d, eax; char *
0x1800adc7e  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800adc85  mov     edx, 5Eh ; '^'; void *
0x1800adc8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adc90  mov     rdi, [rbp+180h+var_1E0]
0x1800adc94  mov     rax, [rdi]
0x1800adc97  mov     rbx, [rax+0A0h]
0x1800adc9e  lea     rcx, [rbp+180h+var_C0]
0x1800adca5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800adcaa  mov     rdx, rax
0x1800adcad  lea     rcx, [rsp+280h+var_230]
0x1800adcb2  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800adcb7  nop
0x1800adcb8  mov     rdx, [rax]
0x1800adcbb  mov     rcx, rdi
0x1800adcbe  mov     rax, rbx
0x1800adcc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adcc6  mov     rcx, [rbp+188h]; this
0x1800adccd  test    eax, eax
0x1800adccf  jns     short loc_1800ADCE6
0x1800adcd1  mov     r9d, eax; char *
0x1800adcd4  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800adcdb  mov     edx, 5Fh ; '_'; void *
0x1800adce0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800adce6  lea     rcx, [rsp+280h+var_230]
0x1800adceb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800adcf0  mov     [rbp+180h+var_1E8], r15
0x1800adcf4  mov     rdi, [rsp+280h+var_228]
0x1800adcf9  mov     rax, [rdi]
0x1800adcfc  mov     rbx, [rax+48h]
0x1800add00  lea     rcx, [rbp+180h+var_1E8]
0x1800add04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800add09  lea     rdx, [rbp+180h+var_1E8]
0x1800add0d  mov     rcx, rdi
0x1800add10  mov     rax, rbx
0x1800add13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add18  mov     rcx, [rbp+188h]; this
0x1800add1f  test    eax, eax
0x1800add21  jns     short loc_1800ADD38
0x1800add23  mov     r9d, eax; char *
0x1800add26  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800add2d  mov     edx, 63h ; 'c'; void *
0x1800add32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800add38  mov     [rbp+180h+var_1F0], r15
0x1800add3c  mov     rdi, [rbp+180h+var_1E8]
0x1800add40  mov     rax, [rdi]
0x1800add43  mov     rbx, [rax+50h]
0x1800add47  lea     rcx, [rbp+180h+var_1F0]
0x1800add4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800add50  lea     r8, [rbp+180h+var_1F0]
0x1800add54  mov     edx, 7
0x1800add59  mov     rcx, rdi
0x1800add5c  mov     rax, rbx
0x1800add5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add64  mov     rcx, [rbp+188h]; this
0x1800add6b  test    eax, eax
0x1800add6d  jns     short loc_1800ADD84
0x1800add6f  mov     r9d, eax; char *
0x1800add72  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800add79  mov     edx, 99h; void *
0x1800add7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800add84  mov     rcx, [rbp+180h+var_1F0]
0x1800add88  mov     rax, [rcx]
0x1800add8b  or      edx, 0FFFFFFFFh
0x1800add8e  mov     rax, [rax+98h]
0x1800add95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add9a  mov     rcx, [rbp+188h]; this
0x1800adda1  test    eax, eax
0x1800adda3  jns     short loc_1800ADDBA
0x1800adda5  mov     r9d, eax; char *
0x1800adda8  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800addaf  mov     edx, 68h ; 'h'; void *
0x1800addb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800addba  mov     [rbp+180h+var_1F8], r15
0x1800addbe  mov     rdi, [rsp+280h+var_228]
0x1800addc3  mov     rax, [rdi]
0x1800addc6  mov     rbx, [rax+88h]
0x1800addcd  lea     rcx, [rbp+180h+var_1F8]
0x1800addd1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800addd6  lea     rdx, [rbp+180h+var_1F8]
0x1800addda  mov     rcx, rdi
0x1800adddd  mov     rax, rbx
0x1800adde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adde5  mov     rcx, [rbp+188h]; this
0x1800addec  test    eax, eax
0x1800addee  jns     short loc_1800ADE05
0x1800addf0  mov     r9d, eax; char *
0x1800addf3  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800addfa  mov     edx, 6Ch ; 'l'; void *
0x1800addff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ade05  mov     [rbp+180h+var_200], r15
0x1800ade09  mov     rdi, [rbp+180h+var_1F8]
0x1800ade0d  mov     rax, [rdi]
0x1800ade10  mov     rbx, [rax+40h]
0x1800ade14  lea     rcx, [rbp+180h+var_200]
0x1800ade18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ade1d  lea     r8, [rbp+180h+var_200]
0x1800ade21  mov     edx, esi
0x1800ade23  mov     rcx, rdi
0x1800ade26  mov     rax, rbx
0x1800ade29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade2e  mov     rcx, [rbp+188h]; this
0x1800ade35  test    eax, eax
0x1800ade37  jns     short loc_1800ADE4E
0x1800ade39  mov     r9d, eax; char *
0x1800ade3c  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800ade43  mov     edx, 6Fh ; 'o'; void *
0x1800ade48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ade4e  mov     [rbp+180h+var_1D0], r15
0x1800ade52  lea     rdx, [rbp+180h+var_1D0]
0x1800ade56  lea     rcx, [rbp+180h+var_200]
0x1800ade5a  call    ??$As@UIExecAction@@@?$ComPtr@UIAction@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExecAction@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IExecAction>>)
0x1800ade5f  mov     rcx, [rbp+188h]; this
0x1800ade66  test    eax, eax
0x1800ade68  jns     short loc_1800ADE7F
0x1800ade6a  mov     r9d, eax; char *
0x1800ade6d  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800ade74  mov     edx, 72h ; 'r'; void *
0x1800ade79  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ade7f  lea     rdx, aTurn; "/turn "
0x1800ade86  lea     rcx, [rbp+180h+var_E0]
0x1800ade8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ade92  nop
0x1800ade93  mov     edx, [r14+8]
0x1800ade97  lea     rcx, [rbp+180h+var_160]
0x1800ade9b  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800adea0  nop
0x1800adea1  mov     rdx, rax
0x1800adea4  lea     rcx, [rbp+180h+var_E0]
0x1800adeab  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800adeb0  nop
0x1800adeb1  lea     rcx, [rbp+180h+var_160]
0x1800adeb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800adeba  mov     rdx, [r14+10h]
0x1800adebe  lea     rcx, [rbp+180h+pvarg]
0x1800adec2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800adec7  mov     rbx, rax
0x1800adeca  lea     rdx, ?c_provSourceCmdLine@@3QBGB; " /source"
0x1800aded1  lea     rcx, [rbp+180h+var_100]
0x1800aded8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800adedd  nop
0x1800adede  mov     r8, rax
0x1800adee1  lea     rcx, [rbp+180h+var_140]
0x1800adee5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
  ... truncated ...
```
