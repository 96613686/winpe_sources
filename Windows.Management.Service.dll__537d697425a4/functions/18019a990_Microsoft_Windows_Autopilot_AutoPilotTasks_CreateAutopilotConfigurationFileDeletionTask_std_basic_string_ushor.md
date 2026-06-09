# Microsoft::Windows::Autopilot::AutoPilotTasks::CreateAutopilotConfigurationFileDeletionTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18019a990`
- end: `0x18019b1db`
- name: `?CreateAutopilotConfigurationFileDeletionTask@AutoPilotTasks@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `2123`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801b3b00`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084574`
- `0x180084d5c`
- `0x18008a26c`
- `0x18008edec`
- `0x18008ee84`
- `0x18019a990`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019aa55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019aa55`
- `OLEAUT32!__imp_VariantInit` at `0x18019aab7`
- `OLEAUT32!__imp_VariantInit` at `0x18019aadf`
- `OLEAUT32!__imp_VariantInit` at `0x18019ab07`
- `OLEAUT32!__imp_VariantInit` at `0x18019ab2d`
- `OLEAUT32!__imp_VariantInit` at `0x18019ad77`
- `OLEAUT32!__imp_VariantInit` at `0x18019afa1`
- `OLEAUT32!__imp_VariantInit` at `0x18019afc7`
- `OLEAUT32!__imp_VariantInit` at `0x18019afef`
- `OLEAUT32!__imp_VariantInit` at `0x18019aab7`
- `OLEAUT32!__imp_VariantInit` at `0x18019aadf`
- `OLEAUT32!__imp_VariantInit` at `0x18019ab07`
- `OLEAUT32!__imp_VariantInit` at `0x18019ab2d`
- `OLEAUT32!__imp_VariantInit` at `0x18019ad77`
- `OLEAUT32!__imp_VariantInit` at `0x18019afa1`
- `OLEAUT32!__imp_VariantInit` at `0x18019afc7`
- `OLEAUT32!__imp_VariantInit` at `0x18019afef`
- `OLEAUT32!__imp_VariantClear` at `0x18019abcd`
- `OLEAUT32!__imp_VariantClear` at `0x18019abe2`
- `OLEAUT32!__imp_VariantClear` at `0x18019abf7`
- `OLEAUT32!__imp_VariantClear` at `0x18019ac0c`
- `OLEAUT32!__imp_VariantClear` at `0x18019ade8`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0c2`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0d7`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0ec`
- `OLEAUT32!__imp_VariantClear` at `0x18019abcd`
- `OLEAUT32!__imp_VariantClear` at `0x18019abe2`
- `OLEAUT32!__imp_VariantClear` at `0x18019abf7`
- `OLEAUT32!__imp_VariantClear` at `0x18019ac0c`
- `OLEAUT32!__imp_VariantClear` at `0x18019ade8`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0c2`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0d7`
- `OLEAUT32!__imp_VariantClear` at `0x18019b0ec`

## string_xrefs

- `0x18019a9f7`: `%AutopilotConfigurationFilePathReplaceString%`
- `0x18019a9d4`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task" xmlns:auto-ns1="urn:schemas-microsoft-com:asm.v3">    <RegistrationInfo>        <URI>\Microsoft\Windows\Management\Autopilot\DeleteConfigurationFile</URI>        <SecurityDescriptor>D:(A;;FA;;;BA)(A;;FA;;;SY)</SecurityDescriptor>    </RegistrationInfo>    <Triggers>        <LogonTrigger>          <Enabled>true</Enabled>          <Delay>PT15M</Delay>        </LogonTrigger>    </Triggers>    <Principals>        <Principal id="Loca`
- `0x18019aa72`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019ac27`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019ad12`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019ae03`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019ae96`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019af30`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b107`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottasks.cpp`
- `0x18019b014`: `DeleteConfigurationFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotTasks::CreateAutopilotConfigurationFileDeletionTask(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v9; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v11; // xmm8
  IRecordInfo *v12; // xmm9_8
  __int128 v13; // xmm6
  IRecordInfo *v14; // xmm7_8
  int v15; // ebx
  LPVOID v16; // rbx
  __int64 (__fastcall *v17)(LPVOID, _QWORD, __int64 *); // rdi
  _QWORD *bstr; // rax
  LPVOID v19; // rbx
  __int64 (__fastcall *v20)(LPVOID, _QWORD, __int64 *); // rdi
  _QWORD *v21; // rax
  int v22; // ebx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, _QWORD, VARIANTARG *, __int64 *); // rdi
  __int128 v25; // xmm6
  IRecordInfo *v26; // xmm7_8
  _QWORD *v27; // rax
  int v28; // ebx
  LPVOID v29; // rdi
  __int64 (__fastcall *v30)(LPVOID, _QWORD, __int64 *); // rbx
  int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, _QWORD); // rdi
  __int64 v35; // rax
  _QWORD *v36; // rax
  int v37; // ebx
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64, __int64); // rsi
  __int128 v40; // xmm6
  IRecordInfo *v41; // xmm7_8
  __int128 v42; // xmm8
  IRecordInfo *v43; // xmm9_8
  __int128 v44; // xmm10
  IRecordInfo *v45; // xmm11_8
  __int64 v46; // rdi
  _QWORD *v47; // rax
  int v48; // ebx
  int ppv; // [rsp+20h] [rbp-1E8h]
  LPVOID v50; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v52; // [rsp+60h] [rbp-1A8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-1A0h] BYREF
  _BYTE v54[8]; // [rsp+70h] [rbp-198h] BYREF
  __int64 v55; // [rsp+78h] [rbp-190h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-188h] BYREF
  VARIANTARG v57; // [rsp+A0h] [rbp-168h] BYREF
  VARIANTARG v58; // [rsp+C0h] [rbp-148h] BYREF
  VARIANTARG v59; // [rsp+D8h] [rbp-130h] BYREF
  int v60[4]; // [rsp+F0h] [rbp-118h] BYREF
  IRecordInfo *v61; // [rsp+100h] [rbp-108h]
  __int128 v62; // [rsp+110h] [rbp-F8h] BYREF
  IRecordInfo *v63; // [rsp+120h] [rbp-E8h]
  VARIANTARG v64; // [rsp+130h] [rbp-D8h] BYREF
  int v65[4]; // [rsp+150h] [rbp-B8h] BYREF
  IRecordInfo *v66; // [rsp+160h] [rbp-A8h]
  _BYTE v67[32]; // [rsp+170h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  std::wstring::wstring(
    v67,
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
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v3 = std::wstring::find(v67, L"%AutopilotConfigurationFilePathReplaceString%", 0);
  std::wstring::replace(v67, v3, 45, v2);
  v50 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v50);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    std::wstring::_Tidy_deallocate(v67);
    return v5;
  }
  v7 = v50;
  v8 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v50 + 80LL);
  VariantInit(&pvarg);
  v9 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  VariantInit(&v59);
  v11 = *(_OWORD *)&v59.vt;
  v12 = v59.pRecInfo;
  VariantInit(&v58);
  v13 = *(_OWORD *)&v58.vt;
  v14 = v58.pRecInfo;
  VariantInit(&v64);
  *(_OWORD *)v65 = v9;
  v66 = pRecInfo;
  *(_OWORD *)v60 = v11;
  v61 = v12;
  v62 = v13;
  v63 = v14;
  v57 = v64;
  v15 = v8(v7, &v57, &v62, v60);
  VariantClear(&v64);
  VariantClear(&v58);
  VariantClear(&v59);
  VariantClear(&pvarg);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v15,
      (int)v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    std::wstring::_Tidy_deallocate(v67);
    return (unsigned int)v15;
  }
  v51 = 0;
  v16 = v50;
  v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v50 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  bstr = (_QWORD *)wil::make_bstr(&v53, L"\\Microsoft\\Windows\\Management\\Autopilot");
  LODWORD(v16) = v17(v16, *bstr, &v51);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
  if ( (int)v16 < 0 )
  {
    v53 = 0;
    v19 = v50;
    v20 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v50 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    v21 = (_QWORD *)wil::make_bstr(v54, L"\\");
    v22 = v20(v19, *v21, &v53);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v54);
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v22,
        (int)v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      std::wstring::_Tidy_deallocate(v67);
      return (unsigned int)v22;
    }
    v23 = v53;
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *, __int64 *))(*(_QWORD *)v53 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    VariantInit(&pvarg);
    v25 = *(_OWORD *)&pvarg.vt;
    v26 = pvarg.pRecInfo;
    v27 = (_QWORD *)wil::make_bstr(v54, L"\\Microsoft\\Windows\\Management\\Autopilot");
    *(_OWORD *)&v57.vt = v25;
    v57.pRecInfo = v26;
    v28 = v24(v23, *v27, &v57, &v51);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v54);
    VariantClear(&pvarg);
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v28,
        (int)v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      std::wstring::_Tidy_deallocate(v67);
      return (unsigned int)v28;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  }
  v52 = 0;
  v29 = v50;
  v30 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v50 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v31 = v30(v29, 0, &v52);
  v32 = v31;
  if ( v31 >= 0 )
  {
    v33 = v52;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 160LL);
    v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
    v36 = (_QWORD *)wil::make_bstr(v54, v35);
    v37 = v34(v33, *v36);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v54);
    if ( v37 >= 0 )
    {
      v55 = 0;
      v38 = v51;
      v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v51 + 136LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      VariantInit(&v58);
      v40 = *(_OWORD *)&v58.vt;
      v41 = v58.pRecInfo;
      VariantInit(&v59);
      v42 = *(_OWORD *)&v59.vt;
      v43 = v59.pRecInfo;
      VariantInit(&pvarg);
      v44 = *(_OWORD *)&pvarg.vt;
      v45 = pvarg.pRecInfo;
      v46 = v52;
      v47 = (_QWORD *)wil::make_bstr(v54, L"DeleteConfigurationFile");
      *(_OWORD *)&v57.vt = v40;
      v57.pRecInfo = v41;
      v62 = v42;
      v63 = v43;
      *(_OWORD *)v60 = v44;
      v61 = v45;
      v48 = v39(v38, *v47, v46, 6);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v54);
      VariantClear(&pvarg);
      VariantClear(&v59);
      VariantClear(&v58);
      if ( v48 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        std::wstring::_Tidy_deallocate(v67);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
          (const char *)(unsigned int)v48,
          (int)v60);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        std::wstring::_Tidy_deallocate(v67);
        return (unsigned int)v48;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
        (const char *)(unsigned int)v37,
        (int)v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      std::wstring::_Tidy_deallocate(v67);
      return (unsigned int)v37;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottasks.cpp",
      (const char *)(unsigned int)v31,
      (int)v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    std::wstring::_Tidy_deallocate(v67);
    return v32;
  }
}

```

## disassembly

```asm
0x18019a990  mov     rax, rsp
0x18019a993  mov     [rax+10h], rbx
0x18019a997  mov     [rax+18h], rsi
0x18019a99b  push    rdi
0x18019a99c  sub     rsp, 200h
0x18019a9a3  movaps  xmmword ptr [rax-18h], xmm6
0x18019a9a7  movaps  xmmword ptr [rax-28h], xmm7
0x18019a9ab  movaps  xmmword ptr [rax-38h], xmm8
0x18019a9b0  movaps  xmmword ptr [rax-48h], xmm9
0x18019a9b5  movaps  xmmword ptr [rax-58h], xmm10
0x18019a9ba  movaps  xmmword ptr [rax-68h], xmm11
0x18019a9bf  mov     rax, cs:__security_cookie
0x18019a9c6  xor     rax, rsp
0x18019a9c9  mov     [rsp+208h+var_78], rax
0x18019a9d1  mov     rbx, rcx
0x18019a9d4  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x18019a9db  lea     rcx, [rsp+208h+var_98]
0x18019a9e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18019a9e8  nop
0x18019a9e9  mov     rcx, rbx
0x18019a9ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019a9f1  mov     rbx, rax
0x18019a9f4  xor     r8d, r8d
0x18019a9f7  lea     rdx, aAutopilotconfi; "%AutopilotConfigurationFilePathReplaceS"...
0x18019a9fe  lea     rcx, [rsp+208h+var_98]
0x18019aa06  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18019aa0b  mov     r9, rbx
0x18019aa0e  mov     r8d, 2Dh ; '-'
0x18019aa14  mov     rdx, rax
0x18019aa17  lea     rcx, [rsp+208h+var_98]
0x18019aa1f  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x18019aa24  mov     [rsp+208h+var_1B8], 0
0x18019aa2d  lea     rcx, [rsp+208h+var_1B8]
0x18019aa32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aa37  lea     rax, [rsp+208h+var_1B8]
0x18019aa3c  mov     [rsp+208h+ppv], rax; int
0x18019aa41  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18019aa48  xor     edx, edx; pUnkOuter
0x18019aa4a  lea     r8d, [rdx+1]; dwClsContext
0x18019aa4e  lea     rcx, CLSID_TaskScheduler; rclsid
0x18019aa55  call    cs:__imp_CoCreateInstance
0x18019aa5c  nop     dword ptr [rax+rax+00h]
0x18019aa61  mov     ebx, eax
0x18019aa63  test    eax, eax
0x18019aa65  jns     short loc_18019AAA3
0x18019aa67  mov     rcx, [rsp+208h]; this
0x18019aa6f  mov     r9d, eax; char *
0x18019aa72  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019aa79  mov     edx, 3Ch ; '<'; void *
0x18019aa7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019aa83  nop
0x18019aa84  lea     rcx, [rsp+208h+var_1B8]
0x18019aa89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aa8e  nop
0x18019aa8f  lea     rcx, [rsp+208h+var_98]
0x18019aa97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019aa9c  mov     eax, ebx
0x18019aa9e  jmp     loc_18019B197
0x18019aaa3  mov     rdi, [rsp+208h+var_1B8]
0x18019aaa8  mov     rax, [rdi]
0x18019aaab  mov     rbx, [rax+50h]
0x18019aaaf  lea     rcx, [rsp+208h+pvarg]; pvarg
0x18019aab7  call    cs:__imp_VariantInit
0x18019aabe  nop     dword ptr [rax+rax+00h]
0x18019aac3  nop
0x18019aac4  movups  xmm10, xmmword ptr [rsp+208h+pvarg]
0x18019aacd  movsd   xmm11, qword ptr [rsp+208h+pvarg+10h]
0x18019aad7  lea     rcx, [rsp+208h+var_130]; pvarg
0x18019aadf  call    cs:__imp_VariantInit
0x18019aae6  nop     dword ptr [rax+rax+00h]
0x18019aaeb  nop
0x18019aaec  movups  xmm8, xmmword ptr [rsp+208h+var_130]
0x18019aaf5  movsd   xmm9, qword ptr [rsp+208h+var_130+10h]
0x18019aaff  lea     rcx, [rsp+208h+var_148]; pvarg
0x18019ab07  call    cs:__imp_VariantInit
0x18019ab0e  nop     dword ptr [rax+rax+00h]
0x18019ab13  nop
0x18019ab14  movups  xmm6, xmmword ptr [rsp+208h+var_148]
0x18019ab1c  movsd   xmm7, qword ptr [rsp+208h+var_148+10h]
0x18019ab25  lea     rcx, [rsp+208h+var_D8]; pvarg
0x18019ab2d  call    cs:__imp_VariantInit
0x18019ab34  nop     dword ptr [rax+rax+00h]
0x18019ab39  nop
0x18019ab3a  movups  xmm0, xmmword ptr [rsp+208h+var_D8]
0x18019ab42  movsd   xmm1, qword ptr [rsp+208h+var_D8+10h]
0x18019ab4b  movaps  xmmword ptr [rsp+208h+var_B8], xmm10
0x18019ab54  movsd   [rsp+208h+var_A8], xmm11
0x18019ab5e  movaps  xmmword ptr [rsp+208h+var_118], xmm8
0x18019ab67  movsd   [rsp+208h+var_108], xmm9
0x18019ab71  movaps  [rsp+208h+var_F8], xmm6
0x18019ab79  movsd   [rsp+208h+var_E8], xmm7
0x18019ab82  movaps  [rsp+208h+var_168], xmm0
0x18019ab8a  movsd   [rsp+208h+var_158], xmm1
0x18019ab93  lea     rax, [rsp+208h+var_B8]
0x18019ab9b  mov     [rsp+208h+ppv], rax; int
0x18019aba0  lea     r9, [rsp+208h+var_118]
0x18019aba8  lea     r8, [rsp+208h+var_F8]
0x18019abb0  lea     rdx, [rsp+208h+var_168]
0x18019abb8  mov     rcx, rdi
0x18019abbb  mov     rax, rbx
0x18019abbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019abc3  mov     ebx, eax
0x18019abc5  lea     rcx, [rsp+208h+var_D8]; pvarg
0x18019abcd  call    cs:__imp_VariantClear
0x18019abd4  nop     dword ptr [rax+rax+00h]
0x18019abd9  nop
0x18019abda  lea     rcx, [rsp+208h+var_148]; pvarg
0x18019abe2  call    cs:__imp_VariantClear
0x18019abe9  nop     dword ptr [rax+rax+00h]
0x18019abee  nop
0x18019abef  lea     rcx, [rsp+208h+var_130]; pvarg
0x18019abf7  call    cs:__imp_VariantClear
0x18019abfe  nop     dword ptr [rax+rax+00h]
0x18019ac03  nop
0x18019ac04  lea     rcx, [rsp+208h+pvarg]; pvarg
0x18019ac0c  call    cs:__imp_VariantClear
0x18019ac13  nop     dword ptr [rax+rax+00h]
0x18019ac18  test    ebx, ebx
0x18019ac1a  jns     short loc_18019AC58
0x18019ac1c  mov     rcx, [rsp+208h]; this
0x18019ac24  mov     r9d, ebx; char *
0x18019ac27  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ac2e  mov     edx, 3Dh ; '='; void *
0x18019ac33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ac38  nop
0x18019ac39  lea     rcx, [rsp+208h+var_1B8]
0x18019ac3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ac43  nop
0x18019ac44  lea     rcx, [rsp+208h+var_98]
0x18019ac4c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019ac51  mov     eax, ebx
0x18019ac53  jmp     loc_18019B197
0x18019ac58  mov     [rsp+208h+var_1B0], 0
0x18019ac61  mov     rbx, [rsp+208h+var_1B8]
0x18019ac66  mov     rax, [rbx]
0x18019ac69  mov     rdi, [rax+38h]
0x18019ac6d  lea     rcx, [rsp+208h+var_1B0]
0x18019ac72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ac77  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x18019ac7e  lea     rcx, [rsp+208h+var_1A0]
0x18019ac83  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019ac88  nop
0x18019ac89  lea     r8, [rsp+208h+var_1B0]
0x18019ac8e  mov     rdx, [rax]
0x18019ac91  mov     rcx, rbx
0x18019ac94  mov     rax, rdi
0x18019ac97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ac9c  mov     ebx, eax
0x18019ac9e  lea     rcx, [rsp+208h+var_1A0]
0x18019aca3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019aca8  shr     ebx, 1Fh
0x18019acab  test    bl, bl
0x18019acad  jz      loc_18019AE54
0x18019acb3  mov     [rsp+208h+var_1A0], 0
0x18019acbc  mov     rbx, [rsp+208h+var_1B8]
0x18019acc1  mov     rax, [rbx]
0x18019acc4  mov     rdi, [rax+38h]
0x18019acc8  lea     rcx, [rsp+208h+var_1A0]
0x18019accd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019acd2  lea     rdx, SubBlock; "\\"
0x18019acd9  lea     rcx, [rsp+208h+var_198]
0x18019acde  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019ace3  nop
0x18019ace4  lea     r8, [rsp+208h+var_1A0]
0x18019ace9  mov     rdx, [rax]
0x18019acec  mov     rcx, rbx
0x18019acef  mov     rax, rdi
0x18019acf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019acf7  mov     ebx, eax
0x18019acf9  lea     rcx, [rsp+208h+var_198]
0x18019acfe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019ad03  test    ebx, ebx
0x18019ad05  jns     short loc_18019AD59
0x18019ad07  mov     rcx, [rsp+208h]; this
0x18019ad0f  mov     r9d, ebx; char *
0x18019ad12  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ad19  mov     edx, 43h ; 'C'; void *
0x18019ad1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ad23  nop
0x18019ad24  lea     rcx, [rsp+208h+var_1A0]
0x18019ad29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ad2e  nop
0x18019ad2f  lea     rcx, [rsp+208h+var_1B0]
0x18019ad34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ad39  nop
0x18019ad3a  lea     rcx, [rsp+208h+var_1B8]
0x18019ad3f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ad44  nop
0x18019ad45  lea     rcx, [rsp+208h+var_98]
0x18019ad4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019ad52  mov     eax, ebx
0x18019ad54  jmp     loc_18019B197
0x18019ad59  mov     rbx, [rsp+208h+var_1A0]
0x18019ad5e  mov     rax, [rbx]
0x18019ad61  mov     rdi, [rax+58h]
0x18019ad65  lea     rcx, [rsp+208h+var_1B0]
0x18019ad6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ad6f  lea     rcx, [rsp+208h+pvarg]; pvarg
0x18019ad77  call    cs:__imp_VariantInit
0x18019ad7e  nop     dword ptr [rax+rax+00h]
0x18019ad83  nop
0x18019ad84  movups  xmm6, xmmword ptr [rsp+208h+pvarg]
0x18019ad8c  movsd   xmm7, qword ptr [rsp+208h+pvarg+10h]
0x18019ad95  lea     rdx, aMicrosoftWindo_84; "\\Microsoft\\Windows\\Management\\Autop"...
0x18019ad9c  lea     rcx, [rsp+208h+var_198]
0x18019ada1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019ada6  nop
0x18019ada7  movaps  [rsp+208h+var_168], xmm6
0x18019adaf  movsd   [rsp+208h+var_158], xmm7
0x18019adb8  lea     r9, [rsp+208h+var_1B0]
0x18019adbd  lea     r8, [rsp+208h+var_168]
0x18019adc5  mov     rdx, [rax]
0x18019adc8  mov     rcx, rbx
0x18019adcb  mov     rax, rdi
0x18019adce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019add3  mov     ebx, eax
0x18019add5  lea     rcx, [rsp+208h+var_198]
0x18019adda  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019addf  nop
0x18019ade0  lea     rcx, [rsp+208h+pvarg]; pvarg
0x18019ade8  call    cs:__imp_VariantClear
0x18019adef  nop     dword ptr [rax+rax+00h]
0x18019adf4  test    ebx, ebx
0x18019adf6  jns     short loc_18019AE4A
0x18019adf8  mov     rcx, [rsp+208h]; this
0x18019ae00  mov     r9d, ebx; char *
0x18019ae03  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ae0a  mov     edx, 44h ; 'D'; void *
0x18019ae0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019ae14  nop
0x18019ae15  lea     rcx, [rsp+208h+var_1A0]
0x18019ae1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ae1f  nop
0x18019ae20  lea     rcx, [rsp+208h+var_1B0]
0x18019ae25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ae2a  nop
0x18019ae2b  lea     rcx, [rsp+208h+var_1B8]
0x18019ae30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ae35  nop
0x18019ae36  lea     rcx, [rsp+208h+var_98]
0x18019ae3e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019ae43  mov     eax, ebx
0x18019ae45  jmp     loc_18019B197
0x18019ae4a  lea     rcx, [rsp+208h+var_1A0]
0x18019ae4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ae54  mov     [rsp+208h+var_1A8], 0
0x18019ae5d  mov     rdi, [rsp+208h+var_1B8]
0x18019ae62  mov     rax, [rdi]
0x18019ae65  mov     rbx, [rax+48h]
0x18019ae69  lea     rcx, [rsp+208h+var_1A8]
0x18019ae6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019ae73  lea     r8, [rsp+208h+var_1A8]
0x18019ae78  xor     edx, edx
0x18019ae7a  mov     rcx, rdi
0x18019ae7d  mov     rax, rbx
0x18019ae80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ae85  mov     ebx, eax
0x18019ae87  test    eax, eax
0x18019ae89  jns     short loc_18019AEDD
0x18019ae8b  mov     rcx, [rsp+208h]; this
0x18019ae93  mov     r9d, eax; char *
0x18019ae96  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019ae9d  mov     edx, 48h ; 'H'; void *
0x18019aea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019aea7  nop
0x18019aea8  lea     rcx, [rsp+208h+var_1A8]
0x18019aead  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aeb2  nop
0x18019aeb3  lea     rcx, [rsp+208h+var_1B0]
0x18019aeb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aebd  nop
0x18019aebe  lea     rcx, [rsp+208h+var_1B8]
0x18019aec3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019aec8  nop
0x18019aec9  lea     rcx, [rsp+208h+var_98]
0x18019aed1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18019aed6  mov     eax, ebx
0x18019aed8  jmp     loc_18019B197
0x18019aedd  mov     rbx, [rsp+208h+var_1A8]
0x18019aee2  mov     rax, [rbx]
0x18019aee5  mov     rdi, [rax+0A0h]
0x18019aeec  lea     rcx, [rsp+208h+var_98]
0x18019aef4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019aef9  mov     rdx, rax
0x18019aefc  lea     rcx, [rsp+208h+var_198]
0x18019af01  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18019af06  nop
0x18019af07  mov     rdx, [rax]
0x18019af0a  mov     rcx, rbx
0x18019af0d  mov     rax, rdi
0x18019af10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019af15  mov     ebx, eax
0x18019af17  lea     rcx, [rsp+208h+var_198]
0x18019af1c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019af21  test    ebx, ebx
0x18019af23  jns     short loc_18019AF77
0x18019af25  mov     rcx, [rsp+208h]; this
0x18019af2d  mov     r9d, ebx; char *
0x18019af30  lea     r8, aOnecoreuapAdmi_96; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019af37  mov     edx, 49h ; 'I'; void *
  ... truncated ...
```
