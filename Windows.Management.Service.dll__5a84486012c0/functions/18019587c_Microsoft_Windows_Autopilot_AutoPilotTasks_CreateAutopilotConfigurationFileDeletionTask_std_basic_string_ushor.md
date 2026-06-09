# Microsoft::Windows::Autopilot::AutoPilotTasks::CreateAutopilotConfigurationFileDeletionTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18019587c`
- end: `0x180196061`
- name: `?CreateAutopilotConfigurationFileDeletionTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2021`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801ae2c0`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800839bc`
- `0x1800841e8`
- `0x18008939c`
- `0x18008dd00`
- `0x18008dd98`
- `0x18019587c`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180195941`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180195941`
- `OLEAUT32!__imp_VariantInit` at `0x18019599d`
- `OLEAUT32!__imp_VariantInit` at `0x1801959bf`
- `OLEAUT32!__imp_VariantInit` at `0x1801959e1`
- `OLEAUT32!__imp_VariantInit` at `0x180195a01`
- `OLEAUT32!__imp_VariantInit` at `0x180195c2d`
- `OLEAUT32!__imp_VariantInit` at `0x180195e4b`
- `OLEAUT32!__imp_VariantInit` at `0x180195e6b`
- `OLEAUT32!__imp_VariantInit` at `0x180195e8d`
- `OLEAUT32!__imp_VariantInit` at `0x18019599d`
- `OLEAUT32!__imp_VariantInit` at `0x1801959bf`
- `OLEAUT32!__imp_VariantInit` at `0x1801959e1`
- `OLEAUT32!__imp_VariantInit` at `0x180195a01`
- `OLEAUT32!__imp_VariantInit` at `0x180195c2d`
- `OLEAUT32!__imp_VariantInit` at `0x180195e4b`
- `OLEAUT32!__imp_VariantInit` at `0x180195e6b`
- `OLEAUT32!__imp_VariantInit` at `0x180195e8d`
- `OLEAUT32!__imp_VariantClear` at `0x180195a9b`
- `OLEAUT32!__imp_VariantClear` at `0x180195aaa`
- `OLEAUT32!__imp_VariantClear` at `0x180195ab9`
- `OLEAUT32!__imp_VariantClear` at `0x180195ac8`
- `OLEAUT32!__imp_VariantClear` at `0x180195c98`
- `OLEAUT32!__imp_VariantClear` at `0x180195f5a`
- `OLEAUT32!__imp_VariantClear` at `0x180195f69`
- `OLEAUT32!__imp_VariantClear` at `0x180195f78`
- `OLEAUT32!__imp_VariantClear` at `0x180195a9b`
- `OLEAUT32!__imp_VariantClear` at `0x180195aaa`
- `OLEAUT32!__imp_VariantClear` at `0x180195ab9`
- `OLEAUT32!__imp_VariantClear` at `0x180195ac8`
- `OLEAUT32!__imp_VariantClear` at `0x180195c98`
- `OLEAUT32!__imp_VariantClear` at `0x180195f5a`
- `OLEAUT32!__imp_VariantClear` at `0x180195f69`
- `OLEAUT32!__imp_VariantClear` at `0x180195f78`

## string_xrefs

- `0x1801958e3`: `%AutopilotConfigurationFilePathReplaceString%`
- `0x1801958c0`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <URI>\Microsoft\Windows\Management\Autopilot\DeleteConfigurationFile</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>        <LogonTrigger>          <Enabled>true</Enabled>          <Delay>PT15M</Delay>        </LogonTrigger>    </Triggers>    <Principals>        <Principal id="Loca`
- `0x180195958`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195add`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195bc8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195cad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195d40`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195dda`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195f8d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x180195eac`: `DeleteConfigurationFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::CreateAutopilotConfigurationFileDeletionTask(
        __int64 a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v7; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v9; // xmm8
  IRecordInfo *v10; // xmm9_8
  __int128 v11; // xmm6
  IRecordInfo *v12; // xmm7_8
  int v13; // ebx
  LPVOID v14; // rbx
  __int64 (__fastcall *v15)(LPVOID, _QWORD, __int64 *); // rdi
  _QWORD *bstr; // rax
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, _QWORD, __int64 *); // rdi
  _QWORD *v19; // rax
  int v20; // ebx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, _QWORD, VARIANTARG *, __int64 *); // rdi
  __int128 v23; // xmm6
  IRecordInfo *v24; // xmm7_8
  _QWORD *v25; // rax
  int v26; // ebx
  LPVOID v27; // rdi
  __int64 (__fastcall *v28)(LPVOID, _QWORD, __int64 *); // rbx
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, _QWORD); // rdi
  __int64 v33; // rax
  _QWORD *v34; // rax
  int v35; // ebx
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64, __int64); // rsi
  __int128 v38; // xmm6
  IRecordInfo *v39; // xmm7_8
  __int128 v40; // xmm8
  IRecordInfo *v41; // xmm9_8
  __int128 v42; // xmm10
  IRecordInfo *v43; // xmm11_8
  __int64 v44; // rdi
  _QWORD *v45; // rax
  int v46; // ebx
  int ppv; // [rsp+20h] [rbp-1E8h]
  LPVOID v48; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v49; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v51; // [rsp+68h] [rbp-1A0h] BYREF
  _BYTE v52[8]; // [rsp+70h] [rbp-198h] BYREF
  __int64 v53; // [rsp+78h] [rbp-190h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-188h] BYREF
  VARIANTARG v55; // [rsp+A0h] [rbp-168h] BYREF
  VARIANTARG v56; // [rsp+C0h] [rbp-148h] BYREF
  VARIANTARG v57; // [rsp+D8h] [rbp-130h] BYREF
  int v58[4]; // [rsp+F0h] [rbp-118h] BYREF
  IRecordInfo *v59; // [rsp+100h] [rbp-108h]
  __int128 v60; // [rsp+110h] [rbp-F8h] BYREF
  IRecordInfo *v61; // [rsp+120h] [rbp-E8h]
  VARIANTARG v62; // [rsp+130h] [rbp-D8h] BYREF
  int v63[4]; // [rsp+150h] [rbp-B8h] BYREF
  IRecordInfo *v64; // [rsp+160h] [rbp-A8h]
  _BYTE Src[32]; // [rsp+170h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  std::wstring::wstring(
    Src,
    L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\" xmlns:auto-ns1=\"urn:schemas-microsoft-com:asm"
     ".v3\">    <RegistrationInfo>        <URI>\\Microsoft\\Windows\\Management\\Autopilot\\DeleteConfigurationFile</URI>"
     "        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>   "
     "     <LogonTrigger>          <Enabled>true</Enabled>          <Delay>PT15M</Delay>        </LogonTrigger>    </Trig"
     "gers>    <Principals>        <Principal id=\"LocalSystem\">            <UserId>S-1-5-18</UserId>            <RunLev"
     "el>HighestAvailable</RunLevel>        </Principal>    </Principals>    <Settings>        <DisallowStartIfOnBatterie"
     "s>false</DisallowStartIfOnBatteries>        <StartWhenAvailable>true</StartWhenAvailable>        <StopIfGoingOnBatt"
     "eries>false</StopIfGoingOnBatteries>        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>    </Sett"
     "ings>    <Actions Context=\"LocalSystem\">        <Exec>            <Command>%windir%\\system32\\cmd.exe</Command> "
     "           <Arguments>/d /c del \"%AutopilotConfigurationFilePathReplaceString%\" &amp;&amp; schtasks /Delete /F /T"
     "N \"\\Microsoft\\Windows\\Management\\Autopilot\\DeleteConfigurationFile\"</Arguments>        </Exec>    </Actions></Task>");
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  std::wstring::find(Src, L"%AutopilotConfigurationFilePathReplaceString%", 0);
  std::wstring::replace(Src);
  v48 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v2 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v48);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    std::wstring::_Tidy_deallocate(Src);
    return v3;
  }
  v5 = v48;
  v6 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v48 + 80LL);
  VariantInit(&pvarg);
  v7 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v57);
  v9 = *(_OWORD *)&v57.vt;
  v10 = v57.pRecInfo;
  VariantInit(&v56);
  v11 = *(_OWORD *)&v56.vt;
  v12 = v56.pRecInfo;
  VariantInit(&v62);
  *(_OWORD *)v63 = v7;
  v64 = pRecInfo;
  *(_OWORD *)v58 = v9;
  v59 = v10;
  v60 = v11;
  v61 = v12;
  v55 = v62;
  v13 = v6(v5, &v55, &v60, v58);
  VariantClear(&v62);
  VariantClear(&v56);
  VariantClear(&v57);
  VariantClear(&pvarg);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v13,
      (int)v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    std::wstring::_Tidy_deallocate(Src);
    return (unsigned int)v13;
  }
  v49 = 0;
  v14 = v48;
  v15 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v48 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  bstr = (_QWORD *)wil::make_bstr(&v51, L"\\Microsoft\\Windows\\Management\\Autopilot");
  LODWORD(v14) = v15(v14, *bstr, &v49);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v51);
  if ( (int)v14 < 0 )
  {
    v51 = 0;
    v17 = v48;
    v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v48 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v19 = (_QWORD *)wil::make_bstr(v52, L"\\");
    v20 = v18(v17, *v19, &v51);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v52);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v20,
        (int)v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      std::wstring::_Tidy_deallocate(Src);
      return (unsigned int)v20;
    }
    v21 = v51;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *, __int64 *))(*(_QWORD *)v51 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    VariantInit(&pvarg);
    v23 = *(_OWORD *)&pvarg.vt;
    v24 = pvarg.pRecInfo;
    v25 = (_QWORD *)wil::make_bstr(v52, L"\\Microsoft\\Windows\\Management\\Autopilot");
    *(_OWORD *)&v55.vt = v23;
    v55.pRecInfo = v24;
    v26 = v22(v21, *v25, &v55, &v49);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v52);
    VariantClear(&pvarg);
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v26,
        (int)v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      std::wstring::_Tidy_deallocate(Src);
      return (unsigned int)v26;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  }
  v50 = 0;
  v27 = v48;
  v28 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v48 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v29 = v28(v27, 0, &v50);
  v30 = v29;
  if ( v29 >= 0 )
  {
    v31 = v50;
    v32 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 160LL);
    v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    v34 = (_QWORD *)wil::make_bstr(v52, v33);
    v35 = v32(v31, *v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v52);
    if ( v35 >= 0 )
    {
      v53 = 0;
      v36 = v49;
      v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v49 + 136LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      VariantInit(&v56);
      v38 = *(_OWORD *)&v56.vt;
      v39 = v56.pRecInfo;
      VariantInit(&v57);
      v40 = *(_OWORD *)&v57.vt;
      v41 = v57.pRecInfo;
      VariantInit(&pvarg);
      v42 = *(_OWORD *)&pvarg.vt;
      v43 = pvarg.pRecInfo;
      v44 = v50;
      v45 = (_QWORD *)wil::make_bstr(v52, L"DeleteConfigurationFile");
      *(_OWORD *)&v55.vt = v38;
      v55.pRecInfo = v39;
      v60 = v40;
      v61 = v41;
      *(_OWORD *)v58 = v42;
      v59 = v43;
      v46 = v37(v36, *v45, v44, 6);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v52);
      VariantClear(&pvarg);
      VariantClear(&v57);
      VariantClear(&v56);
      if ( v46 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        std::wstring::_Tidy_deallocate(Src);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v46,
          (int)v58);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        std::wstring::_Tidy_deallocate(Src);
        return (unsigned int)v46;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v35,
        (int)v63);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      std::wstring::_Tidy_deallocate(Src);
      return (unsigned int)v35;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v29,
      (int)v63);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    std::wstring::_Tidy_deallocate(Src);
    return v30;
  }
}

```

## disassembly

```asm
0x18019587c  mov     rax, rsp
0x18019587f  mov     [rax+10h], rbx
0x180195883  mov     [rax+18h], rsi
0x180195887  push    rdi
0x180195888  sub     rsp, 200h
0x18019588f  movaps  xmmword ptr [rax-18h], xmm6
0x180195893  movaps  xmmword ptr [rax-28h], xmm7
0x180195897  movaps  xmmword ptr [rax-38h], xmm8
0x18019589c  movaps  xmmword ptr [rax-48h], xmm9
0x1801958a1  movaps  xmmword ptr [rax-58h], xmm10
0x1801958a6  movaps  xmmword ptr [rax-68h], xmm11
0x1801958ab  mov     rax, cs:__security_cookie
0x1801958b2  xor     rax, rsp
0x1801958b5  mov     [rsp+208h+var_78], rax
0x1801958bd  mov     rbx, rcx
0x1801958c0  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x1801958c7  lea     rcx, [rsp+208h+Src]
0x1801958cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801958d4  nop
0x1801958d5  mov     rcx, rbx
0x1801958d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801958dd  mov     rbx, rax
0x1801958e0  xor     r8d, r8d
0x1801958e3  lea     rdx, aAutopilotconfi; "%AutopilotConfigurationFilePathReplaceS"...
0x1801958ea  lea     rcx, [rsp+208h+Src]
0x1801958f2  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1801958f7  mov     r9, rbx
0x1801958fa  mov     r8d, 2Dh ; '-'
0x180195900  mov     rdx, rax
0x180195903  lea     rcx, [rsp+208h+Src]; Src
0x18019590b  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x180195910  mov     [rsp+208h+var_1B8], 0
0x180195919  lea     rcx, [rsp+208h+var_1B8]
0x18019591e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195923  lea     rax, [rsp+208h+var_1B8]
0x180195928  mov     [rsp+208h+ppv], rax; int
0x18019592d  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180195934  xor     edx, edx; pUnkOuter
0x180195936  lea     r8d, [rdx+1]; dwClsContext
0x18019593a  lea     rcx, CLSID_TaskScheduler; rclsid
0x180195941  call    cs:__imp_CoCreateInstance
0x180195947  mov     ebx, eax
0x180195949  test    eax, eax
0x18019594b  jns     short loc_180195989
0x18019594d  mov     rcx, [rsp+208h]; this
0x180195955  mov     r9d, eax; char *
0x180195958  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019595f  mov     edx, 3Ch ; '<'; void *
0x180195964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195969  nop
0x18019596a  lea     rcx, [rsp+208h+var_1B8]
0x18019596f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195974  nop
0x180195975  lea     rcx, [rsp+208h+Src]
0x18019597d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195982  mov     eax, ebx
0x180195984  jmp     loc_18019601D
0x180195989  mov     rdi, [rsp+208h+var_1B8]
0x18019598e  mov     rax, [rdi]
0x180195991  mov     rbx, [rax+50h]
0x180195995  lea     rcx, [rsp+208h+pvarg]; pvarg
0x18019599d  call    cs:__imp_VariantInit
0x1801959a3  nop
0x1801959a4  movups  xmm10, xmmword ptr [rsp+208h+pvarg]
0x1801959ad  movsd   xmm11, qword ptr [rsp+208h+pvarg+10h]
0x1801959b7  lea     rcx, [rsp+208h+var_130]; pvarg
0x1801959bf  call    cs:__imp_VariantInit
0x1801959c5  nop
0x1801959c6  movups  xmm8, xmmword ptr [rsp+208h+var_130]
0x1801959cf  movsd   xmm9, qword ptr [rsp+208h+var_130+10h]
0x1801959d9  lea     rcx, [rsp+208h+var_148]; pvarg
0x1801959e1  call    cs:__imp_VariantInit
0x1801959e7  nop
0x1801959e8  movups  xmm6, xmmword ptr [rsp+208h+var_148]
0x1801959f0  movsd   xmm7, qword ptr [rsp+208h+var_148+10h]
0x1801959f9  lea     rcx, [rsp+208h+var_D8]; pvarg
0x180195a01  call    cs:__imp_VariantInit
0x180195a07  nop
0x180195a08  movups  xmm0, xmmword ptr [rsp+208h+var_D8]
0x180195a10  movsd   xmm1, qword ptr [rsp+208h+var_D8+10h]
0x180195a19  movaps  xmmword ptr [rsp+208h+var_B8], xmm10
0x180195a22  movsd   [rsp+208h+var_A8], xmm11
0x180195a2c  movaps  xmmword ptr [rsp+208h+var_118], xmm8
0x180195a35  movsd   [rsp+208h+var_108], xmm9
0x180195a3f  movaps  [rsp+208h+var_F8], xmm6
0x180195a47  movsd   [rsp+208h+var_E8], xmm7
0x180195a50  movaps  [rsp+208h+var_168], xmm0
0x180195a58  movsd   [rsp+208h+var_158], xmm1
0x180195a61  lea     rax, [rsp+208h+var_B8]
0x180195a69  mov     [rsp+208h+ppv], rax; int
0x180195a6e  lea     r9, [rsp+208h+var_118]
0x180195a76  lea     r8, [rsp+208h+var_F8]
0x180195a7e  lea     rdx, [rsp+208h+var_168]
0x180195a86  mov     rcx, rdi
0x180195a89  mov     rax, rbx
0x180195a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195a91  mov     ebx, eax
0x180195a93  lea     rcx, [rsp+208h+var_D8]; pvarg
0x180195a9b  call    cs:__imp_VariantClear
0x180195aa1  nop
0x180195aa2  lea     rcx, [rsp+208h+var_148]; pvarg
0x180195aaa  call    cs:__imp_VariantClear
0x180195ab0  nop
0x180195ab1  lea     rcx, [rsp+208h+var_130]; pvarg
0x180195ab9  call    cs:__imp_VariantClear
0x180195abf  nop
0x180195ac0  lea     rcx, [rsp+208h+pvarg]; pvarg
0x180195ac8  call    cs:__imp_VariantClear
0x180195ace  test    ebx, ebx
0x180195ad0  jns     short loc_180195B0E
0x180195ad2  mov     rcx, [rsp+208h]; this
0x180195ada  mov     r9d, ebx; char *
0x180195add  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195ae4  mov     edx, 3Dh ; '='; void *
0x180195ae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195aee  nop
0x180195aef  lea     rcx, [rsp+208h+var_1B8]
0x180195af4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195af9  nop
0x180195afa  lea     rcx, [rsp+208h+Src]
0x180195b02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195b07  mov     eax, ebx
0x180195b09  jmp     loc_18019601D
0x180195b0e  mov     [rsp+208h+var_1B0], 0
0x180195b17  mov     rbx, [rsp+208h+var_1B8]
0x180195b1c  mov     rax, [rbx]
0x180195b1f  mov     rdi, [rax+38h]
0x180195b23  lea     rcx, [rsp+208h+var_1B0]
0x180195b28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195b2d  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x180195b34  lea     rcx, [rsp+208h+var_1A0]
0x180195b39  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180195b3e  nop
0x180195b3f  lea     r8, [rsp+208h+var_1B0]
0x180195b44  mov     rdx, [rax]
0x180195b47  mov     rcx, rbx
0x180195b4a  mov     rax, rdi
0x180195b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195b52  mov     ebx, eax
0x180195b54  lea     rcx, [rsp+208h+var_1A0]
0x180195b59  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180195b5e  shr     ebx, 1Fh
0x180195b61  test    bl, bl
0x180195b63  jz      loc_180195CFE
0x180195b69  mov     [rsp+208h+var_1A0], 0
0x180195b72  mov     rbx, [rsp+208h+var_1B8]
0x180195b77  mov     rax, [rbx]
0x180195b7a  mov     rdi, [rax+38h]
0x180195b7e  lea     rcx, [rsp+208h+var_1A0]
0x180195b83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195b88  lea     rdx, SubBlock; "\\"
0x180195b8f  lea     rcx, [rsp+208h+var_198]
0x180195b94  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180195b99  nop
0x180195b9a  lea     r8, [rsp+208h+var_1A0]
0x180195b9f  mov     rdx, [rax]
0x180195ba2  mov     rcx, rbx
0x180195ba5  mov     rax, rdi
0x180195ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195bad  mov     ebx, eax
0x180195baf  lea     rcx, [rsp+208h+var_198]
0x180195bb4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180195bb9  test    ebx, ebx
0x180195bbb  jns     short loc_180195C0F
0x180195bbd  mov     rcx, [rsp+208h]; this
0x180195bc5  mov     r9d, ebx; char *
0x180195bc8  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195bcf  mov     edx, 43h ; 'C'; void *
0x180195bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195bd9  nop
0x180195bda  lea     rcx, [rsp+208h+var_1A0]
0x180195bdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195be4  nop
0x180195be5  lea     rcx, [rsp+208h+var_1B0]
0x180195bea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195bef  nop
0x180195bf0  lea     rcx, [rsp+208h+var_1B8]
0x180195bf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195bfa  nop
0x180195bfb  lea     rcx, [rsp+208h+Src]
0x180195c03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195c08  mov     eax, ebx
0x180195c0a  jmp     loc_18019601D
0x180195c0f  mov     rbx, [rsp+208h+var_1A0]
0x180195c14  mov     rax, [rbx]
0x180195c17  mov     rdi, [rax+58h]
0x180195c1b  lea     rcx, [rsp+208h+var_1B0]
0x180195c20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195c25  lea     rcx, [rsp+208h+pvarg]; pvarg
0x180195c2d  call    cs:__imp_VariantInit
0x180195c33  nop
0x180195c34  movups  xmm6, xmmword ptr [rsp+208h+pvarg]
0x180195c3c  movsd   xmm7, qword ptr [rsp+208h+pvarg+10h]
0x180195c45  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x180195c4c  lea     rcx, [rsp+208h+var_198]
0x180195c51  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180195c56  nop
0x180195c57  movaps  [rsp+208h+var_168], xmm6
0x180195c5f  movsd   [rsp+208h+var_158], xmm7
0x180195c68  lea     r9, [rsp+208h+var_1B0]
0x180195c6d  lea     r8, [rsp+208h+var_168]
0x180195c75  mov     rdx, [rax]
0x180195c78  mov     rcx, rbx
0x180195c7b  mov     rax, rdi
0x180195c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195c83  mov     ebx, eax
0x180195c85  lea     rcx, [rsp+208h+var_198]
0x180195c8a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180195c8f  nop
0x180195c90  lea     rcx, [rsp+208h+pvarg]; pvarg
0x180195c98  call    cs:__imp_VariantClear
0x180195c9e  test    ebx, ebx
0x180195ca0  jns     short loc_180195CF4
0x180195ca2  mov     rcx, [rsp+208h]; this
0x180195caa  mov     r9d, ebx; char *
0x180195cad  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195cb4  mov     edx, 44h ; 'D'; void *
0x180195cb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195cbe  nop
0x180195cbf  lea     rcx, [rsp+208h+var_1A0]
0x180195cc4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195cc9  nop
0x180195cca  lea     rcx, [rsp+208h+var_1B0]
0x180195ccf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195cd4  nop
0x180195cd5  lea     rcx, [rsp+208h+var_1B8]
0x180195cda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195cdf  nop
0x180195ce0  lea     rcx, [rsp+208h+Src]
0x180195ce8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195ced  mov     eax, ebx
0x180195cef  jmp     loc_18019601D
0x180195cf4  lea     rcx, [rsp+208h+var_1A0]
0x180195cf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195cfe  mov     [rsp+208h+var_1A8], 0
0x180195d07  mov     rdi, [rsp+208h+var_1B8]
0x180195d0c  mov     rax, [rdi]
0x180195d0f  mov     rbx, [rax+48h]
0x180195d13  lea     rcx, [rsp+208h+var_1A8]
0x180195d18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195d1d  lea     r8, [rsp+208h+var_1A8]
0x180195d22  xor     edx, edx
0x180195d24  mov     rcx, rdi
0x180195d27  mov     rax, rbx
0x180195d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195d2f  mov     ebx, eax
0x180195d31  test    eax, eax
0x180195d33  jns     short loc_180195D87
0x180195d35  mov     rcx, [rsp+208h]; this
0x180195d3d  mov     r9d, eax; char *
0x180195d40  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195d47  mov     edx, 48h ; 'H'; void *
0x180195d4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195d51  nop
0x180195d52  lea     rcx, [rsp+208h+var_1A8]
0x180195d57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195d5c  nop
0x180195d5d  lea     rcx, [rsp+208h+var_1B0]
0x180195d62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195d67  nop
0x180195d68  lea     rcx, [rsp+208h+var_1B8]
0x180195d6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195d72  nop
0x180195d73  lea     rcx, [rsp+208h+Src]
0x180195d7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180195d80  mov     eax, ebx
0x180195d82  jmp     loc_18019601D
0x180195d87  mov     rbx, [rsp+208h+var_1A8]
0x180195d8c  mov     rax, [rbx]
0x180195d8f  mov     rdi, [rax+0A0h]
0x180195d96  lea     rcx, [rsp+208h+Src]
0x180195d9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180195da3  mov     rdx, rax
0x180195da6  lea     rcx, [rsp+208h+var_198]
0x180195dab  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180195db0  nop
0x180195db1  mov     rdx, [rax]
0x180195db4  mov     rcx, rbx
0x180195db7  mov     rax, rdi
0x180195dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195dbf  mov     ebx, eax
0x180195dc1  lea     rcx, [rsp+208h+var_198]
0x180195dc6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180195dcb  test    ebx, ebx
0x180195dcd  jns     short loc_180195E21
0x180195dcf  mov     rcx, [rsp+208h]; this
0x180195dd7  mov     r9d, ebx; char *
0x180195dda  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x180195de1  mov     edx, 49h ; 'I'; void *
0x180195de6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180195deb  nop
0x180195dec  lea     rcx, [rsp+208h+var_1A8]
0x180195df1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195df6  nop
0x180195df7  lea     rcx, [rsp+208h+var_1B0]
0x180195dfc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195e01  nop
0x180195e02  lea     rcx, [rsp+208h+var_1B8]
0x180195e07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180195e0c  nop
  ... truncated ...
```
