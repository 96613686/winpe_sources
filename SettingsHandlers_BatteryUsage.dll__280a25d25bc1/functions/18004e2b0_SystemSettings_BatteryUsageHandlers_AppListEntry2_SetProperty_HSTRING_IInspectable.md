# SystemSettings::BatteryUsageHandlers::AppListEntry2::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x18004e2b0`
- end: `0x18004e7b0`
- name: `?SetProperty@AppListEntry2@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `1280`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry2 *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x18000e7f0`
- `0x18000fa78`
- `0x18000fbe8`
- `0x18001de40`
- `0x18001e360`
- `0x180023c30`
- `0x180043770`
- `0x180049ef8`
- `0x180049f74`
- `0x18004e044`
- `0x18004e2b0`
- `0x18005149c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e4d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e4ec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e52e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e4d1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e4ec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004e52e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e41b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e41b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004e57c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e3d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004e3d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry2::SetProperty(
        SystemSettings::BatteryUsageHandlers::AppListEntry2 *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  __int64 (*QueryInterface)(void); // rbx
  int v6; // eax
  const unsigned __int16 *v7; // r8
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  const WCHAR *StringRawBuffer; // rdi
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  HSTRING *v19; // r8
  unsigned int v20; // ebx
  HSTRING *v21; // r8
  __int64 v22; // rdx
  struct IInspectable *v23; // r8
  int v24; // eax
  const unsigned __int16 *v25; // r8
  unsigned int v26; // ebx
  bool v27; // r14
  __int64 v28; // rdx
  const unsigned __int16 *v29; // r8
  __int64 v30; // r8
  __int64 v31; // rax
  __int64 PackageFullNameFromFamilyName; // rax
  int v33; // eax
  unsigned int v34; // ebx
  const HSTRING__ *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // eax
  unsigned int v42; // ebx
  __int64 v43; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int16 v44[4]; // [rsp+28h] [rbp-70h] BYREF
  struct IInspectable *v45; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 v46[4]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v47[32]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v48[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING string; // [rsp+B0h] [rbp+18h] BYREF
  struct IInspectable *v51; // [rsp+B8h] [rbp+20h] BYREF

  v43 = 0;
  QueryInterface = (__int64 (*)(void))a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  try
  {
    v6 = QueryInterface();
    v8 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)v6,
        v43);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      return v8;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1800652A0, v7) )
    {
      LOBYTE(string) = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 144LL))(v43, &string);
      v26 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36D,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
          (const char *)(unsigned int)v24,
          v43);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        return v26;
      }
      v27 = (_BYTE)string != 0;
      LOBYTE(v51) = (_BYTE)string != 0;
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069A40, v25) )
      {
        *(_QWORD *)v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 352, v28, v29);
        UsageGraphTelemetry::ManagedByWindowsToggled<bool &,unsigned short const *>(&v51, v46);
        if ( SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(this) )
        {
          v31 = std::wstring::wstring((__int64)v47, (__int64)this + 352, v30);
          PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                                            &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
                                            v48,
                                            v31);
          v33 = SystemSettings::BatteryUsageHandlers::SetTaskPolicy(PackageFullNameFromFamilyName, 2 * !v27 + 1);
          v34 = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x37B,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
              (const char *)(unsigned int)v33,
              v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
            return v34;
          }
          SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180069AC8);
        }
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180069B20);
        v35 = &stru_180069A40;
      }
      else
      {
        if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180069AC8, v29) )
          goto LABEL_33;
        *(_QWORD *)v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 352, v36, v37);
        UsageGraphTelemetry::IsTasksDisabledToggled<bool &,unsigned short const *>((char *)&v51, (__int64 *)v46);
        v39 = std::wstring::wstring((__int64)v48, (__int64)this + 352, v38);
        v40 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(
                &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
                v47,
                v39);
        v41 = SystemSettings::BatteryUsageHandlers::SetTaskPolicy(v40, (unsigned int)v27 + 2);
        v42 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x38B,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
            (const char *)(unsigned int)v41,
            v43);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          return v42;
        }
        v35 = &stru_180069B20;
      }
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)v35);
      goto LABEL_33;
    }
    string = 0;
    v11 = v43;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v13 = v12(v11, &string);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x348,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)v13,
        v43);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      return v14;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v45 = 0;
    v16 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, &v45);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34F,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)v16,
        v43);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      return v17;
    }
    v51 = 0;
    v18 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(0, &v51);
    v20 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x351,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
        (const char *)(unsigned int)v18,
        v43);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
      return v20;
    }
    *(_QWORD *)v46 = 0;
    *(_QWORD *)v44 = 0;
    SystemSettings::DataModel::WindowsCreateString((SystemSettings::DataModel *)&stru_180069AC8, v46, v19);
    SystemSettings::DataModel::WindowsCreateString((SystemSettings::DataModel *)&stru_180069A40, v44, v21);
    if ( StrCmpLogicalW(L"SystemSettings_AppBatteryUsage_ManagedByWindows", StringRawBuffer) )
    {
      if ( !StrCmpLogicalW(L"SystemSettings_AppBatteryUsage_AlwaysAllow", StringRawBuffer) )
      {
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, _QWORD, struct IInspectable *))(*(_QWORD *)this + 128LL))(
          this,
          *(_QWORD *)v44,
          v51);
        v23 = v51;
        v22 = *(_QWORD *)v46;
LABEL_18:
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, __int64, struct IInspectable *))(*(_QWORD *)this + 128LL))(
          this,
          v22,
          v23);
        goto LABEL_19;
      }
      if ( StrCmpLogicalW(L"SystemSettings_AppBatteryUsage_NeverAllow", StringRawBuffer) )
      {
LABEL_19:
        WindowsDeleteString(string);
LABEL_33:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        return 0;
      }
      (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry2 *, _QWORD, struct IInspectable *))(*(_QWORD *)this + 128LL))(
        this,
        *(_QWORD *)v44,
        v51);
      v22 = *(_QWORD *)v46;
    }
    else
    {
      v22 = *(_QWORD *)v44;
    }
    v23 = v45;
    goto LABEL_18;
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x393,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry2.cpp",
                        v9);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x18004e2b0  mov     r11, rsp
0x18004e2b3  mov     [r11+8], rbx
0x18004e2b7  mov     [r11+10h], rsi
0x18004e2bb  push    rdi
0x18004e2bc  push    r14
0x18004e2be  push    r15
0x18004e2c0  sub     rsp, 80h
0x18004e2c7  mov     r14, r8
0x18004e2ca  mov     rdi, rdx
0x18004e2cd  mov     rsi, rcx
0x18004e2d0  xor     r15d, r15d
0x18004e2d3  mov     [r11-78h], r15
0x18004e2d7  mov     rax, [r8]
0x18004e2da  mov     rbx, [rax]
0x18004e2dd  lea     rcx, [r11-78h]
0x18004e2e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e2e6  lea     r8, [rsp+98h+var_78]
0x18004e2eb  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004e2f2  mov     rcx, r14
0x18004e2f5  mov     rax, rbx
0x18004e2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2fd  mov     ebx, eax
0x18004e2ff  test    eax, eax
0x18004e301  jns     short loc_18004E331
0x18004e303  mov     rcx, [rsp+98h]; this
0x18004e30b  mov     r9d, eax; char *
0x18004e30e  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e315  mov     edx, 340h; void *
0x18004e31a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e31f  nop
0x18004e320  lea     rcx, [rsp+98h+var_78]
0x18004e325  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e32a  mov     eax, ebx
0x18004e32c  jmp     loc_18004E796
0x18004e331  lea     rdx, stru_1800652A0; HSTRING
0x18004e338  mov     rcx, rdi; this
0x18004e33b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004e340  test    al, al
0x18004e342  jz      loc_18004E587
0x18004e348  mov     [rsp+98h+string], r15
0x18004e350  mov     rdi, [rsp+98h+var_78]
0x18004e355  mov     rax, [rdi]
0x18004e358  mov     rbx, [rax+98h]
0x18004e35f  xor     ecx, ecx; string
0x18004e361  call    cs:__imp_WindowsDeleteString
0x18004e367  mov     [rsp+98h+string], r15
0x18004e36f  lea     rdx, [rsp+98h+string]
0x18004e377  mov     rcx, rdi
0x18004e37a  mov     rax, rbx
0x18004e37d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e382  mov     ebx, eax
0x18004e384  test    eax, eax
0x18004e386  jns     short loc_18004E3CC
0x18004e388  mov     rcx, [rsp+98h]; this
0x18004e390  mov     r9d, eax; char *
0x18004e393  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e39a  mov     edx, 348h; void *
0x18004e39f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e3a4  nop
0x18004e3a5  mov     rcx, [rsp+98h+string]; string
0x18004e3ad  call    cs:__imp_WindowsDeleteString
0x18004e3b3  mov     [rsp+98h+string], r15
0x18004e3bb  lea     rcx, [rsp+98h+var_78]
0x18004e3c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e3c5  mov     eax, ebx
0x18004e3c7  jmp     loc_18004E796
0x18004e3cc  xor     edx, edx; length
0x18004e3ce  mov     rcx, [rsp+98h+string]; string
0x18004e3d6  call    cs:__imp_WindowsGetStringRawBuffer
0x18004e3dc  mov     rdi, rax
0x18004e3df  mov     [rsp+98h+var_68], r15
0x18004e3e4  lea     rdx, [rsp+98h+var_68]; struct IInspectable **
0x18004e3e9  mov     cl, 1; unsigned __int8
0x18004e3eb  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004e3f0  mov     ebx, eax
0x18004e3f2  test    eax, eax
0x18004e3f4  jns     short loc_18004E43A
0x18004e3f6  mov     rcx, [rsp+98h]; this
0x18004e3fe  mov     r9d, eax; char *
0x18004e401  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e408  mov     edx, 34Fh; void *
0x18004e40d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e412  nop
0x18004e413  mov     rcx, [rsp+98h+string]; string
0x18004e41b  call    cs:__imp_WindowsDeleteString
0x18004e421  mov     [rsp+98h+string], r15
0x18004e429  lea     rcx, [rsp+98h+var_78]
0x18004e42e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e433  mov     eax, ebx
0x18004e435  jmp     loc_18004E796
0x18004e43a  mov     [rsp+98h+arg_18], r15
0x18004e442  lea     rdx, [rsp+98h+arg_18]; struct IInspectable **
0x18004e44a  xor     ecx, ecx; unsigned __int8
0x18004e44c  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004e451  mov     ebx, eax
0x18004e453  test    eax, eax
0x18004e455  jns     short loc_18004E49B
0x18004e457  mov     rcx, [rsp+98h]; this
0x18004e45f  mov     r9d, eax; char *
0x18004e462  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e469  mov     edx, 351h; void *
0x18004e46e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e473  nop
0x18004e474  mov     rcx, [rsp+98h+string]; string
0x18004e47c  call    cs:__imp_WindowsDeleteString
0x18004e482  mov     [rsp+98h+string], r15
0x18004e48a  lea     rcx, [rsp+98h+var_78]
0x18004e48f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e494  mov     eax, ebx
0x18004e496  jmp     loc_18004E796
0x18004e49b  mov     qword ptr [rsp+98h+var_60], r15
0x18004e4a0  mov     qword ptr [rsp+98h+var_70], r15
0x18004e4a5  lea     rdx, [rsp+98h+var_60]; unsigned __int16 *
0x18004e4aa  lea     rcx, stru_180069AC8; this
0x18004e4b1  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004e4b6  lea     rdx, [rsp+98h+var_70]; unsigned __int16 *
0x18004e4bb  lea     rcx, stru_180069A40; this
0x18004e4c2  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004e4c7  mov     rdx, rdi; psz2
0x18004e4ca  lea     rcx, psz1; "SystemSettings_AppBatteryUsage_ManagedB"...
0x18004e4d1  call    cs:__imp_StrCmpLogicalW
0x18004e4d7  test    eax, eax
0x18004e4d9  jnz     short loc_18004E4E2
0x18004e4db  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004e4e0  jmp     short loc_18004E55C
0x18004e4e2  mov     rdx, rdi; psz2
0x18004e4e5  lea     rcx, aSystemsettings_2; "SystemSettings_AppBatteryUsage_AlwaysAl"...
0x18004e4ec  call    cs:__imp_StrCmpLogicalW
0x18004e4f2  test    eax, eax
0x18004e4f4  jnz     short loc_18004E524
0x18004e4f6  mov     rax, [rsi]
0x18004e4f9  mov     r8, [rsp+98h+arg_18]
0x18004e501  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004e506  mov     rcx, rsi
0x18004e509  mov     rax, [rax+80h]
0x18004e510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e515  mov     r8, [rsp+98h+arg_18]
0x18004e51d  mov     rdx, qword ptr [rsp+98h+var_60]
0x18004e522  jmp     short loc_18004E561
0x18004e524  mov     rdx, rdi; psz2
0x18004e527  lea     rcx, aSystemsettings_30; "SystemSettings_AppBatteryUsage_NeverAll"...
0x18004e52e  call    cs:__imp_StrCmpLogicalW
0x18004e534  test    eax, eax
0x18004e536  jnz     short loc_18004E574
0x18004e538  mov     rax, [rsi]
0x18004e53b  mov     r8, [rsp+98h+arg_18]
0x18004e543  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004e548  mov     rcx, rsi
0x18004e54b  mov     rax, [rax+80h]
0x18004e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e557  mov     rdx, qword ptr [rsp+98h+var_60]
0x18004e55c  mov     r8, [rsp+98h+var_68]
0x18004e561  mov     rax, [rsi]
0x18004e564  mov     rcx, rsi
0x18004e567  mov     rax, [rax+80h]
0x18004e56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e573  nop
0x18004e574  mov     rcx, [rsp+98h+string]; string
0x18004e57c  call    cs:__imp_WindowsDeleteString
0x18004e582  jmp     loc_18004E781
0x18004e587  mov     byte ptr [rsp+98h+string], r15b
0x18004e58f  mov     rcx, [rsp+98h+var_78]
0x18004e594  mov     rax, [rcx]
0x18004e597  lea     rdx, [rsp+98h+string]
0x18004e59f  mov     rax, [rax+90h]
0x18004e5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5ab  mov     ebx, eax
0x18004e5ad  test    eax, eax
0x18004e5af  jns     short loc_18004E5DF
0x18004e5b1  mov     rcx, [rsp+98h]; this
0x18004e5b9  mov     r9d, eax; char *
0x18004e5bc  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e5c3  mov     edx, 36Dh; void *
0x18004e5c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e5cd  nop
0x18004e5ce  lea     rcx, [rsp+98h+var_78]
0x18004e5d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e5d8  mov     eax, ebx
0x18004e5da  jmp     loc_18004E796
0x18004e5df  cmp     byte ptr [rsp+98h+string], r15b
0x18004e5e7  setnz   r14b
0x18004e5eb  mov     byte ptr [rsp+98h+arg_18], r14b
0x18004e5f3  lea     rdx, stru_180069A40; HSTRING
0x18004e5fa  mov     rcx, rdi; this
0x18004e5fd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004e602  test    al, al
0x18004e604  jz      loc_18004E6D3
0x18004e60a  lea     rbx, [rsi+160h]
0x18004e611  mov     rcx, rbx
0x18004e614  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e619  mov     qword ptr [rsp+98h+var_60], rax
0x18004e61e  lea     rdx, [rsp+98h+var_60]
0x18004e623  lea     rcx, [rsp+98h+arg_18]
0x18004e62b  call    ??$ManagedByWindowsToggled@AEA_NPEBG@UsageGraphTelemetry@@SAXAEA_N$$QEAPEBG@Z; UsageGraphTelemetry::ManagedByWindowsToggled<bool &,ushort const *>(bool &,ushort const * &&)
0x18004e630  mov     rcx, rsi; this
0x18004e633  call    ?IsBackgroundTasksControlUserConfigurable@AppListEntry2@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ; SystemSettings::BatteryUsageHandlers::AppListEntry2::IsBackgroundTasksControlUserConfigurable(void)
0x18004e638  test    al, al
0x18004e63a  jz      short loc_18004E6B8
0x18004e63c  movzx   eax, r14b
0x18004e640  xor     eax, 1
0x18004e643  lea     edi, ds:1[rax*2]
0x18004e64a  mov     rdx, rbx
0x18004e64d  lea     rcx, [rsp+98h+var_58]
0x18004e652  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e657  mov     r8, rax
0x18004e65a  lea     rdx, [rsp+98h+var_38]
0x18004e65f  lea     rcx, ?g_UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton2@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2
0x18004e666  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::wstring)
0x18004e66b  mov     edx, edi
0x18004e66d  mov     rcx, rax
0x18004e670  call    ?SetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPolicy@12@@Z; SystemSettings::BatteryUsageHandlers::SetTaskPolicy(std::wstring,SystemSettings::BatteryUsageHandlers::TaskPolicy)
0x18004e675  mov     ebx, eax
0x18004e677  test    eax, eax
0x18004e679  jns     short loc_18004E6A9
0x18004e67b  mov     rcx, [rsp+98h]; this
0x18004e683  mov     r9d, eax; char *
0x18004e686  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e68d  mov     edx, 37Bh; void *
0x18004e692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e697  nop
0x18004e698  lea     rcx, [rsp+98h+var_78]
0x18004e69d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e6a2  mov     eax, ebx
0x18004e6a4  jmp     loc_18004E796
0x18004e6a9  lea     rdx, stru_180069AC8; unsigned __int16 *
0x18004e6b0  mov     rcx, rsi; this
0x18004e6b3  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004e6b8  lea     rdx, stru_180069B20; unsigned __int16 *
0x18004e6bf  mov     rcx, rsi; this
0x18004e6c2  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004e6c7  lea     rdx, stru_180069A40
0x18004e6ce  jmp     loc_18004E778
0x18004e6d3  lea     rdx, stru_180069AC8; HSTRING
0x18004e6da  mov     rcx, rdi; this
0x18004e6dd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004e6e2  test    al, al
0x18004e6e4  jz      loc_18004E781
0x18004e6ea  lea     rbx, [rsi+160h]
0x18004e6f1  mov     rcx, rbx
0x18004e6f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004e6f9  mov     qword ptr [rsp+98h+var_60], rax
0x18004e6fe  lea     rdx, [rsp+98h+var_60]
0x18004e703  lea     rcx, [rsp+98h+arg_18]
0x18004e70b  call    ??$IsTasksDisabledToggled@AEA_NPEBG@UsageGraphTelemetry@@SAXAEA_N$$QEAPEBG@Z; UsageGraphTelemetry::IsTasksDisabledToggled<bool &,ushort const *>(bool &,ushort const * &&)
0x18004e710  movzx   edi, r14b
0x18004e714  mov     rdx, rbx
0x18004e717  lea     rcx, [rsp+98h+var_38]
0x18004e71c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004e721  mov     r8, rax
0x18004e724  lea     rdx, [rsp+98h+var_58]
0x18004e729  lea     rcx, ?g_UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton2@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2
0x18004e730  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFullNameFromFamilyName(std::wstring)
0x18004e735  lea     edx, [rdi+2]
0x18004e738  mov     rcx, rax
0x18004e73b  call    ?SetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPolicy@12@@Z; SystemSettings::BatteryUsageHandlers::SetTaskPolicy(std::wstring,SystemSettings::BatteryUsageHandlers::TaskPolicy)
0x18004e740  mov     ebx, eax
0x18004e742  test    eax, eax
0x18004e744  jns     short loc_18004E771
0x18004e746  mov     rcx, [rsp+98h]; this
0x18004e74e  mov     r9d, eax; char *
0x18004e751  lea     r8, aOnecoreuapShel_7; "onecoreuap\\shell\\coresettinghandlers"...
0x18004e758  mov     edx, 38Bh; void *
0x18004e75d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e762  nop
0x18004e763  lea     rcx, [rsp+98h+var_78]
0x18004e768  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e76d  mov     eax, ebx
0x18004e76f  jmp     short loc_18004E796
0x18004e771  lea     rdx, stru_180069B20; unsigned __int16 *
0x18004e778  mov     rcx, rsi; this
0x18004e77b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004e780  nop
0x18004e781  lea     rcx, [rsp+98h+var_78]
0x18004e786  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004e78b  xor     eax, eax
0x18004e78d  jmp     short loc_18004E796
0x18004e78f  mov     eax, dword ptr [rsp+98h+string]
0x18004e796  lea     r11, [rsp+98h+var_18]
0x18004e79e  mov     rbx, [r11+20h]
0x18004e7a2  mov     rsi, [r11+28h]
0x18004e7a6  mov     rsp, r11
0x18004e7a9  pop     r15
0x18004e7ab  pop     r14
0x18004e7ad  pop     rdi
0x18004e7ae  retn
```
