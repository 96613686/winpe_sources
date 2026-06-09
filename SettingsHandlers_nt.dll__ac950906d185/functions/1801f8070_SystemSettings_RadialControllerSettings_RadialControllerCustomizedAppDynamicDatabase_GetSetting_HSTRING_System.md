# SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppDynamicDatabase::GetSetting(HSTRING__ *,SystemSettings::DataModel::ISettingItem * *)

- ea: `0x1801f8070`
- end: `0x1801f8765`
- name: `?GetSetting@RadialControllerCustomizedAppDynamicDatabase@RadialControllerSettings@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUISettingItem@DataModel@3@@Z`
- size: `1781`
- prototype: `int(SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppDynamicDatabase *__hidden this, HSTRING, struct SystemSettings::DataModel::ISettingItem **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x180021398`
- `0x180086bc4`
- `0x180122790`
- `0x1801f4080`
- `0x1801f4100`
- `0x1801f4180`
- `0x1801f42a4`
- `0x1801f8070`
- `0x1801f8950`
- `0x1801ff820`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f81f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f82a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f83f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f842b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f84d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f86d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f81f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f82a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f83f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f842b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f84d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f86d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f8708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f8097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801f8097`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppDynamicDatabase::GetSetting(
        SystemSettings::RadialControllerSettings::RadialControllerCustomizedAppDynamicDatabase *this,
        SystemSettings::DataModel *a2,
        struct SystemSettings::DataModel::ISettingItem **a3)
{
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r8
  const unsigned __int16 *v9; // r8
  unsigned int v10; // ebx
  HSTRING v11; // rcx
  int v12; // eax
  HSTRING v13; // rcx
  int v14; // eax
  HSTRING v15; // rcx
  HSTRING v16; // rbx
  __int64 (__fastcall *v17)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **); // rdi
  int v18; // eax
  HSTRING v19; // rcx
  HSTRING v20; // rcx
  const unsigned __int16 *v21; // r8
  HSTRING v22; // rcx
  int v23; // eax
  HSTRING v24; // rcx
  HSTRING v25; // rbx
  __int64 (__fastcall *v26)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **); // rdi
  int v27; // eax
  HSTRING v28; // rcx
  HSTRING v29; // rdi
  int v30; // eax
  __int64 (__fastcall *v31)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **); // rbx
  int v32; // eax
  __int64 (__fastcall **v33)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **); // rax
  HSTRING v34; // rcx
  int v35; // eax
  HSTRING v36; // rcx
  HSTRING v37; // rbx
  __int64 (__fastcall *v38)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **); // rdi
  int v39; // eax
  HSTRING v40; // rcx
  struct SystemSettings::DataModel::ISettingItem *v41; // rax
  int StringRawBuffer; // [rsp+20h] [rbp-40h]
  HSTRING v44; // [rsp+30h] [rbp-30h] BYREF
  struct SystemSettings::DataModel::ISettingItem *v45; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-20h] BYREF
  HSTRING v47; // [rsp+48h] [rbp-18h] BYREF
  HSTRING v48; // [rsp+50h] [rbp-10h] BYREF
  HSTRING v49; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HSTRING v51; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING v52; // [rsp+A8h] [rbp+48h] BYREF

  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer((HSTRING)a2, 0);
  InputDial::InputDialTraceProvider::Info(
    "shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
    "na",
    0x671u,
    "Database::GetSetting: propertyName=%ws");
  *a3 = 0;
  v45 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803270E0, v6)
    || SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180327080, v7) )
  {
    Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::CDevicesRadialControllerGlobalToolList,>(&v44);
    if ( v44 )
    {
      v49 = 0;
      v51 = (HSTRING)*((_QWORD *)this + 4);
      v35 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v49);
      v10 = v35;
      if ( v35 >= 0 )
      {
        v51 = v49;
        Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v44 + 35, &v51);
        v37 = v44;
        v38 = **(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v44;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v39 = v38(v37, &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf, &v45);
        v10 = v39;
        if ( v39 >= 0 )
        {
          WindowsDeleteString(v49);
          v49 = 0;
          v20 = v44;
          if ( v44 )
          {
            v44 = 0;
            goto LABEL_65;
          }
          goto LABEL_67;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67F,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v39,
          StringRawBuffer);
        WindowsDeleteString(v49);
        v49 = 0;
        v40 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v40 + 16LL))(v40);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x67D,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v35,
          StringRawBuffer);
        WindowsDeleteString(v49);
        v49 = 0;
        v36 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 16LL))(v36);
        }
      }
    }
    else
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67A,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
        (const char *)0x8007000ELL,
        StringRawBuffer);
      v34 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
  }
  else
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180327010, v8) )
    {
      Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::CDevicesRadialControllerCustomTool,>(&v51);
      if ( !v51 )
      {
        v10 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x684,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)0x8007000ELL,
          StringRawBuffer);
        v11 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
        }
        goto LABEL_68;
      }
      string = 0;
      v52 = (HSTRING)*((_QWORD *)this + 4);
      v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&string);
      v10 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x687,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v12,
          StringRawBuffer);
        WindowsDeleteString(string);
        string = 0;
        v13 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v13 + 16LL))(v13);
        }
        goto LABEL_68;
      }
      v14 = SystemSettings::RadialControllerSettings::CDevicesRadialControllerCustomTool::SetAppId(
              (SystemSettings::RadialControllerSettings::CDevicesRadialControllerCustomTool *)v51,
              string);
      v10 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v14,
          StringRawBuffer);
        WindowsDeleteString(string);
        string = 0;
        v15 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        }
        goto LABEL_68;
      }
      v51[68] = *(_DWORD *)(HSTRING)((int)this + 40);
      v16 = v51;
      v17 = **(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v51;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v18 = v17(v16, &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf, &v45);
      v10 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x68B,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v18,
          StringRawBuffer);
        WindowsDeleteString(string);
        string = 0;
        v19 = v51;
        if ( v51 )
        {
          v51 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_68;
      }
      WindowsDeleteString(string);
      string = 0;
      v20 = v51;
      if ( v51 )
      {
        v51 = 0;
LABEL_65:
        v33 = *(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v20;
        goto LABEL_66;
      }
      goto LABEL_67;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180327150, v9) )
    {
      Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::CCustomAppToolCollection,>(&v52);
      if ( v52 )
      {
        v47 = 0;
        v51 = (HSTRING)*((_QWORD *)this + 4);
        v23 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v47);
        v10 = v23;
        if ( v23 >= 0 )
        {
          v51 = v47;
          Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v52 + 33, &v51);
          v25 = v52;
          v26 = **(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v52;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          v27 = v26(v25, &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf, &v45);
          v10 = v27;
          if ( v27 >= 0 )
          {
            WindowsDeleteString(v47);
            v47 = 0;
            v20 = v52;
            if ( v52 )
            {
              v52 = 0;
              goto LABEL_65;
            }
LABEL_67:
            v41 = v45;
            v45 = 0;
            *a3 = v41;
            v10 = 0;
            goto LABEL_68;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x697,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
            (const char *)(unsigned int)v27,
            StringRawBuffer);
          WindowsDeleteString(v47);
          v47 = 0;
          v28 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v28 + 16LL))(v28);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x694,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
            (const char *)(unsigned int)v23,
            StringRawBuffer);
          WindowsDeleteString(v47);
          v47 = 0;
          v24 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v24 + 16LL))(v24);
          }
        }
      }
      else
      {
        v10 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x691,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)0x8007000ELL,
          StringRawBuffer);
        v22 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
    }
    else
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802DAE70, v21) )
      {
        v10 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A8,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)0x80070057LL,
          StringRawBuffer);
        goto LABEL_68;
      }
      Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::RadialControllerAddCustomAppToolSetting,>(&v51);
      v29 = v51;
      if ( !v51 )
      {
        v10 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69D,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)0x8007000ELL,
          StringRawBuffer);
        goto LABEL_68;
      }
      v48 = 0;
      v51 = (HSTRING)*((_QWORD *)this + 4);
      v30 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)&v48);
      v10 = v30;
      if ( v30 >= 0 )
      {
        v51 = v48;
        Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v29 + 27, &v51);
        v31 = **(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v29;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v32 = v31(v29, &GUID_40c037cc_d8bf_489e_8697_d66baa3221bf, &v45);
        v10 = v32;
        if ( v32 >= 0 )
        {
          WindowsDeleteString(v48);
          v48 = 0;
          if ( v29 )
          {
            v33 = *(__int64 (__fastcall ***)(HSTRING, GUID *, struct SystemSettings::DataModel::ISettingItem **))v29;
            v20 = v29;
LABEL_66:
            ((void (__fastcall *)(HSTRING))v33[2])(v20);
            goto LABEL_67;
          }
          goto LABEL_67;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A4,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v32,
          StringRawBuffer);
        WindowsDeleteString(v48);
        v48 = 0;
        if ( v29 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v29 + 16LL))(v29);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A0,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollersettingshandlers.cpp",
          (const char *)(unsigned int)v30,
          StringRawBuffer);
        WindowsDeleteString(v48);
        v48 = 0;
        if ( v29 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
  }
LABEL_68:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
  return v10;
}

```

## disassembly

```asm
0x1801f8070  mov     [rsp-28h+arg_0], rbx
0x1801f8075  mov     [rsp-28h+arg_8], rsi
0x1801f807a  push    rbp
0x1801f807b  push    rdi
0x1801f807c  push    r12
0x1801f807e  push    r14
0x1801f8080  push    r15
0x1801f8082  mov     rbp, rsp
0x1801f8085  sub     rsp, 60h
0x1801f8089  mov     r14, r8
0x1801f808c  mov     rbx, rdx
0x1801f808f  mov     rsi, rcx
0x1801f8092  xor     edx, edx; length
0x1801f8094  mov     rcx, rbx; string
0x1801f8097  call    cs:__imp_WindowsGetStringRawBuffer
0x1801f809e  nop     dword ptr [rax+rax+00h]
0x1801f80a3  mov     qword ptr [rsp+60h+var_40], rax; int
0x1801f80a8  lea     r9, aDatabaseGetset; "Database::GetSetting: propertyName=%ws"
0x1801f80af  mov     r8d, 671h; unsigned int
0x1801f80b5  lea     rdx, aNa; "na"
0x1801f80bc  lea     r12, aShellSystemset_55; "shell\\systemsettingsthreshold\\handler"...
0x1801f80c3  mov     rcx, r12; char *
0x1801f80c6  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x1801f80cb  xor     r15d, r15d
0x1801f80ce  mov     [r14], r15
0x1801f80d1  mov     [rbp+var_28], r15
0x1801f80d5  lea     rdx, stru_1803270E0; HSTRING
0x1801f80dc  mov     rcx, rbx; this
0x1801f80df  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801f80e4  test    al, al
0x1801f80e6  jnz     loc_1801F85C6
0x1801f80ec  lea     rdx, stru_180327080; HSTRING
0x1801f80f3  mov     rcx, rbx; this
0x1801f80f6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801f80fb  test    al, al
0x1801f80fd  jnz     loc_1801F85C6
0x1801f8103  lea     rdx, stru_180327010; HSTRING
0x1801f810a  mov     rcx, rbx; this
0x1801f810d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801f8112  test    al, al
0x1801f8114  jz      loc_1801F82CF
0x1801f811a  lea     rcx, [rbp+arg_10]
0x1801f811e  call    ??$Make@VCDevicesRadialControllerCustomTool@RadialControllerSettings@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDevicesRadialControllerCustomTool@RadialControllerSettings@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::CDevicesRadialControllerCustomTool,>(void)
0x1801f8123  cmp     [rbp+arg_10], r15
0x1801f8127  jnz     short loc_1801F8162
0x1801f8129  mov     rcx, [rbp+28h]; this
0x1801f812d  mov     ebx, 8007000Eh
0x1801f8132  mov     r9d, ebx; char *
0x1801f8135  mov     r8, r12; unsigned int
0x1801f8138  mov     edx, 684h; void *
0x1801f813d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f8142  nop
0x1801f8143  mov     rcx, [rbp+arg_10]
0x1801f8147  test    rcx, rcx
0x1801f814a  jz      short loc_1801F815D
0x1801f814c  mov     [rbp+arg_10], r15
0x1801f8150  mov     rax, [rcx]
0x1801f8153  mov     rax, [rax+10h]
0x1801f8157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f815c  nop
0x1801f815d  jmp     loc_1801F8740
0x1801f8162  mov     [rbp+string], r15
0x1801f8166  mov     rax, [rsi+20h]
0x1801f816a  mov     [rbp+arg_18], rax
0x1801f816e  lea     rdx, [rbp+arg_18]
0x1801f8172  lea     rcx, [rbp+string]; this
0x1801f8176  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801f817b  mov     ebx, eax
0x1801f817d  test    eax, eax
0x1801f817f  jns     short loc_1801F81C8
0x1801f8181  mov     rcx, [rbp+28h]; this
0x1801f8185  mov     r9d, eax; char *
0x1801f8188  mov     r8, r12; unsigned int
0x1801f818b  mov     edx, 687h; void *
0x1801f8190  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f8195  mov     rcx, [rbp+string]; string
0x1801f8199  call    cs:__imp_WindowsDeleteString
0x1801f81a0  nop     dword ptr [rax+rax+00h]
0x1801f81a5  mov     [rbp+string], r15
0x1801f81a9  mov     rcx, [rbp+arg_10]
0x1801f81ad  test    rcx, rcx
0x1801f81b0  jz      short loc_1801F81C3
0x1801f81b2  mov     [rbp+arg_10], r15
0x1801f81b6  mov     rax, [rcx]
0x1801f81b9  mov     rax, [rax+10h]
0x1801f81bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f81c2  nop
0x1801f81c3  jmp     loc_1801F8740
0x1801f81c8  mov     rdx, [rbp+string]; HSTRING
0x1801f81cc  mov     rcx, [rbp+arg_10]; this
0x1801f81d0  call    ?SetAppId@CDevicesRadialControllerCustomTool@RadialControllerSettings@SystemSettings@@QEAAJPEAUHSTRING__@@@Z; SystemSettings::RadialControllerSettings::CDevicesRadialControllerCustomTool::SetAppId(HSTRING__ *)
0x1801f81d5  mov     ebx, eax
0x1801f81d7  test    eax, eax
0x1801f81d9  jns     short loc_1801F8222
0x1801f81db  mov     rcx, [rbp+28h]; this
0x1801f81df  mov     r9d, eax; char *
0x1801f81e2  mov     r8, r12; unsigned int
0x1801f81e5  mov     edx, 689h; void *
0x1801f81ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f81ef  mov     rcx, [rbp+string]; string
0x1801f81f3  call    cs:__imp_WindowsDeleteString
0x1801f81fa  nop     dword ptr [rax+rax+00h]
0x1801f81ff  mov     [rbp+string], r15
0x1801f8203  mov     rcx, [rbp+arg_10]
0x1801f8207  test    rcx, rcx
0x1801f820a  jz      short loc_1801F821D
0x1801f820c  mov     [rbp+arg_10], r15
0x1801f8210  mov     rax, [rcx]
0x1801f8213  mov     rax, [rax+10h]
0x1801f8217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f821c  nop
0x1801f821d  jmp     loc_1801F8740
0x1801f8222  mov     ecx, [rsi+28h]
0x1801f8225  mov     rax, [rbp+arg_10]
0x1801f8229  mov     [rax+110h], ecx
0x1801f822f  mov     rbx, [rbp+arg_10]
0x1801f8233  mov     rax, [rbx]
0x1801f8236  mov     rdi, [rax]
0x1801f8239  lea     rcx, [rbp+var_28]
0x1801f823d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f8242  lea     r8, [rbp+var_28]
0x1801f8246  lea     rdx, _GUID_40c037cc_d8bf_489e_8697_d66baa3221bf
0x1801f824d  mov     rcx, rbx
0x1801f8250  mov     rax, rdi
0x1801f8253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8258  mov     ebx, eax
0x1801f825a  test    eax, eax
0x1801f825c  jns     short loc_1801F82A5
0x1801f825e  mov     rcx, [rbp+28h]; this
0x1801f8262  mov     r9d, eax; char *
0x1801f8265  mov     r8, r12; unsigned int
0x1801f8268  mov     edx, 68Bh; void *
0x1801f826d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f8272  mov     rcx, [rbp+string]; string
0x1801f8276  call    cs:__imp_WindowsDeleteString
0x1801f827d  nop     dword ptr [rax+rax+00h]
0x1801f8282  mov     [rbp+string], r15
0x1801f8286  mov     rcx, [rbp+arg_10]
0x1801f828a  test    rcx, rcx
0x1801f828d  jz      short loc_1801F82A0
0x1801f828f  mov     [rbp+arg_10], r15
0x1801f8293  mov     rax, [rcx]
0x1801f8296  mov     rax, [rax+10h]
0x1801f829a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f829f  nop
0x1801f82a0  jmp     loc_1801F8740
0x1801f82a5  mov     rcx, [rbp+string]; string
0x1801f82a9  call    cs:__imp_WindowsDeleteString
0x1801f82b0  nop     dword ptr [rax+rax+00h]
0x1801f82b5  mov     [rbp+string], r15
0x1801f82b9  mov     rcx, [rbp+arg_10]
0x1801f82bd  test    rcx, rcx
0x1801f82c0  jz      loc_1801F8732
0x1801f82c6  mov     [rbp+arg_10], r15
0x1801f82ca  jmp     loc_1801F8725
0x1801f82cf  lea     rdx, stru_180327150; HSTRING
0x1801f82d6  mov     rcx, rbx; this
0x1801f82d9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801f82de  test    al, al
0x1801f82e0  jz      loc_1801F8451
0x1801f82e6  lea     rcx, [rbp+arg_18]
0x1801f82ea  call    ??$Make@VCCustomAppToolCollection@RadialControllerSettings@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCustomAppToolCollection@RadialControllerSettings@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::CCustomAppToolCollection,>(void)
0x1801f82ef  cmp     [rbp+arg_18], r15
0x1801f82f3  jnz     short loc_1801F832E
0x1801f82f5  mov     rcx, [rbp+28h]; this
0x1801f82f9  mov     ebx, 8007000Eh
0x1801f82fe  mov     r9d, ebx; char *
0x1801f8301  mov     r8, r12; unsigned int
0x1801f8304  mov     edx, 691h; void *
0x1801f8309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f830e  nop
0x1801f830f  mov     rcx, [rbp+arg_18]
0x1801f8313  test    rcx, rcx
0x1801f8316  jz      short loc_1801F8329
0x1801f8318  mov     [rbp+arg_18], r15
0x1801f831c  mov     rax, [rcx]
0x1801f831f  mov     rax, [rax+10h]
0x1801f8323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8328  nop
0x1801f8329  jmp     loc_1801F8740
0x1801f832e  mov     [rbp+var_18], r15
0x1801f8332  mov     rax, [rsi+20h]
0x1801f8336  mov     [rbp+arg_10], rax
0x1801f833a  lea     rdx, [rbp+arg_10]
0x1801f833e  lea     rcx, [rbp+var_18]; this
0x1801f8342  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801f8347  mov     ebx, eax
0x1801f8349  test    eax, eax
0x1801f834b  jns     short loc_1801F8394
0x1801f834d  mov     rcx, [rbp+28h]; this
0x1801f8351  mov     r9d, eax; char *
0x1801f8354  mov     r8, r12; unsigned int
0x1801f8357  mov     edx, 694h; void *
0x1801f835c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f8361  mov     rcx, [rbp+var_18]; string
0x1801f8365  call    cs:__imp_WindowsDeleteString
0x1801f836c  nop     dword ptr [rax+rax+00h]
0x1801f8371  mov     [rbp+var_18], r15
0x1801f8375  mov     rcx, [rbp+arg_18]
0x1801f8379  test    rcx, rcx
0x1801f837c  jz      short loc_1801F838F
0x1801f837e  mov     [rbp+arg_18], r15
0x1801f8382  mov     rax, [rcx]
0x1801f8385  mov     rax, [rax+10h]
0x1801f8389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f838e  nop
0x1801f838f  jmp     loc_1801F8740
0x1801f8394  mov     rax, [rbp+var_18]
0x1801f8398  mov     [rbp+arg_10], rax
0x1801f839c  mov     rcx, [rbp+arg_18]
0x1801f83a0  add     rcx, 108h; newString
0x1801f83a7  lea     rdx, [rbp+arg_10]; HSTRING *
0x1801f83ab  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801f83b0  nop
0x1801f83b1  mov     rbx, [rbp+arg_18]
0x1801f83b5  mov     rax, [rbx]
0x1801f83b8  mov     rdi, [rax]
0x1801f83bb  lea     rcx, [rbp+var_28]
0x1801f83bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801f83c4  lea     r8, [rbp+var_28]
0x1801f83c8  lea     rdx, _GUID_40c037cc_d8bf_489e_8697_d66baa3221bf
0x1801f83cf  mov     rcx, rbx
0x1801f83d2  mov     rax, rdi
0x1801f83d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f83da  mov     ebx, eax
0x1801f83dc  test    eax, eax
0x1801f83de  jns     short loc_1801F8427
0x1801f83e0  mov     rcx, [rbp+28h]; this
0x1801f83e4  mov     r9d, eax; char *
0x1801f83e7  mov     r8, r12; unsigned int
0x1801f83ea  mov     edx, 697h; void *
0x1801f83ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f83f4  mov     rcx, [rbp+var_18]; string
0x1801f83f8  call    cs:__imp_WindowsDeleteString
0x1801f83ff  nop     dword ptr [rax+rax+00h]
0x1801f8404  mov     [rbp+var_18], r15
0x1801f8408  mov     rcx, [rbp+arg_18]
0x1801f840c  test    rcx, rcx
0x1801f840f  jz      short loc_1801F8422
0x1801f8411  mov     [rbp+arg_18], r15
0x1801f8415  mov     rax, [rcx]
0x1801f8418  mov     rax, [rax+10h]
0x1801f841c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f8421  nop
0x1801f8422  jmp     loc_1801F8740
0x1801f8427  mov     rcx, [rbp+var_18]; string
0x1801f842b  call    cs:__imp_WindowsDeleteString
0x1801f8432  nop     dword ptr [rax+rax+00h]
0x1801f8437  mov     [rbp+var_18], r15
0x1801f843b  mov     rcx, [rbp+arg_18]
0x1801f843f  test    rcx, rcx
0x1801f8442  jz      loc_1801F8732
0x1801f8448  mov     [rbp+arg_18], r15
0x1801f844c  jmp     loc_1801F8725
0x1801f8451  lea     rdx, stru_1802DAE70; HSTRING
0x1801f8458  mov     rcx, rbx; this
0x1801f845b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801f8460  test    al, al
0x1801f8462  jz      loc_1801F85A8
0x1801f8468  lea     rcx, [rbp+arg_10]
0x1801f846c  call    ??$Make@VRadialControllerAddCustomAppToolSetting@RadialControllerSettings@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VRadialControllerAddCustomAppToolSetting@RadialControllerSettings@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::RadialControllerSettings::RadialControllerAddCustomAppToolSetting,>(void)
0x1801f8471  mov     rdi, [rbp+arg_10]
0x1801f8475  test    rdi, rdi
0x1801f8478  jnz     short loc_1801F8499
0x1801f847a  mov     rcx, [rbp+28h]; this
0x1801f847e  mov     ebx, 8007000Eh
0x1801f8483  mov     r9d, ebx; char *
0x1801f8486  mov     r8, r12; unsigned int
0x1801f8489  mov     edx, 69Dh; void *
0x1801f848e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f8493  nop
0x1801f8494  jmp     loc_1801F8740
0x1801f8499  mov     [rbp+var_10], r15
0x1801f849d  mov     rax, [rsi+20h]
0x1801f84a1  mov     [rbp+arg_10], rax
0x1801f84a5  lea     rdx, [rbp+arg_10]
0x1801f84a9  lea     rcx, [rbp+var_10]; this
0x1801f84ad  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801f84b2  mov     ebx, eax
0x1801f84b4  test    eax, eax
0x1801f84b6  jns     short loc_1801F84FA
0x1801f84b8  mov     rcx, [rbp+28h]; this
0x1801f84bc  mov     r9d, eax; char *
0x1801f84bf  mov     r8, r12; unsigned int
0x1801f84c2  mov     edx, 6A0h; void *
0x1801f84c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801f84cc  mov     rcx, [rbp+var_10]; string
0x1801f84d0  call    cs:__imp_WindowsDeleteString
0x1801f84d7  nop     dword ptr [rax+rax+00h]
0x1801f84dc  mov     [rbp+var_10], r15
0x1801f84e0  test    rdi, rdi
0x1801f84e3  jz      short loc_1801F84F5
0x1801f84e5  mov     rax, [rdi]
0x1801f84e8  mov     rcx, rdi
0x1801f84eb  mov     rax, [rax+10h]
0x1801f84ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f84f4  nop
0x1801f84f5  jmp     loc_1801F8740
0x1801f84fa  mov     rax, [rbp+var_10]
0x1801f84fe  mov     [rbp+arg_10], rax
  ... truncated ...
```
