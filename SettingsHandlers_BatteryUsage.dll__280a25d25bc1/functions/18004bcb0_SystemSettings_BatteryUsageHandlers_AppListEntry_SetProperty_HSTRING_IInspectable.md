# SystemSettings::BatteryUsageHandlers::AppListEntry::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x18004bcb0`
- end: `0x18004c1b0`
- name: `?SetProperty@AppListEntry@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `1280`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppListEntry *__hidden this, HSTRING, struct IInspectable *)`
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
- `0x180043908`
- `0x180049ef8`
- `0x180049f74`
- `0x18004b824`
- `0x18004bcb0`
- `0x18005149c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004bed1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004beec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004bf2e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004bed1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004beec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004bf2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bd61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004be1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004be7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bf7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bd61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004be1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004be7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bf7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004bdd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppListEntry::SetProperty(
        SystemSettings::BatteryUsageHandlers::AppListEntry *this,
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
        (void *)0x24B,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
          (void *)0x278,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        if ( SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(this) )
        {
          v31 = std::wstring::wstring((__int64)v47, (__int64)this + 352, v30);
          PackageFullNameFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
                                            &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
                                            v48,
                                            v31);
          v33 = SystemSettings::BatteryUsageHandlers::SetTaskPolicy(PackageFullNameFromFamilyName, 2 * !v27 + 1);
          v34 = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x286,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        v40 = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(
                &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
                v47,
                v39);
        v41 = SystemSettings::BatteryUsageHandlers::SetTaskPolicy(v40, (unsigned int)v27 + 2);
        v42 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x296,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        (void *)0x253,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        (void *)0x25A,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        (void *)0x25C,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
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
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry *, _QWORD, struct IInspectable *))(*(_QWORD *)this + 128LL))(
          this,
          *(_QWORD *)v44,
          v51);
        v23 = v51;
        v22 = *(_QWORD *)v46;
LABEL_18:
        (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry *, __int64, struct IInspectable *))(*(_QWORD *)this + 128LL))(
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
      (*(void (__fastcall **)(SystemSettings::BatteryUsageHandlers::AppListEntry *, _QWORD, struct IInspectable *))(*(_QWORD *)this + 128LL))(
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
                        (void *)0x29E,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applistentry.cpp",
                        v9);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x18004bcb0  mov     r11, rsp
0x18004bcb3  mov     [r11+8], rbx
0x18004bcb7  mov     [r11+10h], rsi
0x18004bcbb  push    rdi
0x18004bcbc  push    r14
0x18004bcbe  push    r15
0x18004bcc0  sub     rsp, 80h
0x18004bcc7  mov     r14, r8
0x18004bcca  mov     rdi, rdx
0x18004bccd  mov     rsi, rcx
0x18004bcd0  xor     r15d, r15d
0x18004bcd3  mov     [r11-78h], r15
0x18004bcd7  mov     rax, [r8]
0x18004bcda  mov     rbx, [rax]
0x18004bcdd  lea     rcx, [r11-78h]
0x18004bce1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bce6  lea     r8, [rsp+98h+var_78]
0x18004bceb  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004bcf2  mov     rcx, r14
0x18004bcf5  mov     rax, rbx
0x18004bcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcfd  mov     ebx, eax
0x18004bcff  test    eax, eax
0x18004bd01  jns     short loc_18004BD31
0x18004bd03  mov     rcx, [rsp+98h]; this
0x18004bd0b  mov     r9d, eax; char *
0x18004bd0e  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004bd15  mov     edx, 24Bh; void *
0x18004bd1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bd1f  nop
0x18004bd20  lea     rcx, [rsp+98h+var_78]
0x18004bd25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bd2a  mov     eax, ebx
0x18004bd2c  jmp     loc_18004C196
0x18004bd31  lea     rdx, stru_1800652A0; HSTRING
0x18004bd38  mov     rcx, rdi; this
0x18004bd3b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004bd40  test    al, al
0x18004bd42  jz      loc_18004BF87
0x18004bd48  mov     [rsp+98h+string], r15
0x18004bd50  mov     rdi, [rsp+98h+var_78]
0x18004bd55  mov     rax, [rdi]
0x18004bd58  mov     rbx, [rax+98h]
0x18004bd5f  xor     ecx, ecx; string
0x18004bd61  call    cs:__imp_WindowsDeleteString
0x18004bd67  mov     [rsp+98h+string], r15
0x18004bd6f  lea     rdx, [rsp+98h+string]
0x18004bd77  mov     rcx, rdi
0x18004bd7a  mov     rax, rbx
0x18004bd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd82  mov     ebx, eax
0x18004bd84  test    eax, eax
0x18004bd86  jns     short loc_18004BDCC
0x18004bd88  mov     rcx, [rsp+98h]; this
0x18004bd90  mov     r9d, eax; char *
0x18004bd93  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004bd9a  mov     edx, 253h; void *
0x18004bd9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bda4  nop
0x18004bda5  mov     rcx, [rsp+98h+string]; string
0x18004bdad  call    cs:__imp_WindowsDeleteString
0x18004bdb3  mov     [rsp+98h+string], r15
0x18004bdbb  lea     rcx, [rsp+98h+var_78]
0x18004bdc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bdc5  mov     eax, ebx
0x18004bdc7  jmp     loc_18004C196
0x18004bdcc  xor     edx, edx; length
0x18004bdce  mov     rcx, [rsp+98h+string]; string
0x18004bdd6  call    cs:__imp_WindowsGetStringRawBuffer
0x18004bddc  mov     rdi, rax
0x18004bddf  mov     [rsp+98h+var_68], r15
0x18004bde4  lea     rdx, [rsp+98h+var_68]; struct IInspectable **
0x18004bde9  mov     cl, 1; unsigned __int8
0x18004bdeb  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004bdf0  mov     ebx, eax
0x18004bdf2  test    eax, eax
0x18004bdf4  jns     short loc_18004BE3A
0x18004bdf6  mov     rcx, [rsp+98h]; this
0x18004bdfe  mov     r9d, eax; char *
0x18004be01  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004be08  mov     edx, 25Ah; void *
0x18004be0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be12  nop
0x18004be13  mov     rcx, [rsp+98h+string]; string
0x18004be1b  call    cs:__imp_WindowsDeleteString
0x18004be21  mov     [rsp+98h+string], r15
0x18004be29  lea     rcx, [rsp+98h+var_78]
0x18004be2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004be33  mov     eax, ebx
0x18004be35  jmp     loc_18004C196
0x18004be3a  mov     [rsp+98h+arg_18], r15
0x18004be42  lea     rdx, [rsp+98h+arg_18]; struct IInspectable **
0x18004be4a  xor     ecx, ecx; unsigned __int8
0x18004be4c  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18004be51  mov     ebx, eax
0x18004be53  test    eax, eax
0x18004be55  jns     short loc_18004BE9B
0x18004be57  mov     rcx, [rsp+98h]; this
0x18004be5f  mov     r9d, eax; char *
0x18004be62  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004be69  mov     edx, 25Ch; void *
0x18004be6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004be73  nop
0x18004be74  mov     rcx, [rsp+98h+string]; string
0x18004be7c  call    cs:__imp_WindowsDeleteString
0x18004be82  mov     [rsp+98h+string], r15
0x18004be8a  lea     rcx, [rsp+98h+var_78]
0x18004be8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004be94  mov     eax, ebx
0x18004be96  jmp     loc_18004C196
0x18004be9b  mov     qword ptr [rsp+98h+var_60], r15
0x18004bea0  mov     qword ptr [rsp+98h+var_70], r15
0x18004bea5  lea     rdx, [rsp+98h+var_60]; unsigned __int16 *
0x18004beaa  lea     rcx, stru_180069AC8; this
0x18004beb1  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004beb6  lea     rdx, [rsp+98h+var_70]; unsigned __int16 *
0x18004bebb  lea     rcx, stru_180069A40; this
0x18004bec2  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004bec7  mov     rdx, rdi; psz2
0x18004beca  lea     rcx, psz1; "SystemSettings_AppBatteryUsage_ManagedB"...
0x18004bed1  call    cs:__imp_StrCmpLogicalW
0x18004bed7  test    eax, eax
0x18004bed9  jnz     short loc_18004BEE2
0x18004bedb  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004bee0  jmp     short loc_18004BF5C
0x18004bee2  mov     rdx, rdi; psz2
0x18004bee5  lea     rcx, aSystemsettings_2; "SystemSettings_AppBatteryUsage_AlwaysAl"...
0x18004beec  call    cs:__imp_StrCmpLogicalW
0x18004bef2  test    eax, eax
0x18004bef4  jnz     short loc_18004BF24
0x18004bef6  mov     rax, [rsi]
0x18004bef9  mov     r8, [rsp+98h+arg_18]
0x18004bf01  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004bf06  mov     rcx, rsi
0x18004bf09  mov     rax, [rax+80h]
0x18004bf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf15  mov     r8, [rsp+98h+arg_18]
0x18004bf1d  mov     rdx, qword ptr [rsp+98h+var_60]
0x18004bf22  jmp     short loc_18004BF61
0x18004bf24  mov     rdx, rdi; psz2
0x18004bf27  lea     rcx, aSystemsettings_30; "SystemSettings_AppBatteryUsage_NeverAll"...
0x18004bf2e  call    cs:__imp_StrCmpLogicalW
0x18004bf34  test    eax, eax
0x18004bf36  jnz     short loc_18004BF74
0x18004bf38  mov     rax, [rsi]
0x18004bf3b  mov     r8, [rsp+98h+arg_18]
0x18004bf43  mov     rdx, qword ptr [rsp+98h+var_70]
0x18004bf48  mov     rcx, rsi
0x18004bf4b  mov     rax, [rax+80h]
0x18004bf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf57  mov     rdx, qword ptr [rsp+98h+var_60]
0x18004bf5c  mov     r8, [rsp+98h+var_68]
0x18004bf61  mov     rax, [rsi]
0x18004bf64  mov     rcx, rsi
0x18004bf67  mov     rax, [rax+80h]
0x18004bf6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf73  nop
0x18004bf74  mov     rcx, [rsp+98h+string]; string
0x18004bf7c  call    cs:__imp_WindowsDeleteString
0x18004bf82  jmp     loc_18004C181
0x18004bf87  mov     byte ptr [rsp+98h+string], r15b
0x18004bf8f  mov     rcx, [rsp+98h+var_78]
0x18004bf94  mov     rax, [rcx]
0x18004bf97  lea     rdx, [rsp+98h+string]
0x18004bf9f  mov     rax, [rax+90h]
0x18004bfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfab  mov     ebx, eax
0x18004bfad  test    eax, eax
0x18004bfaf  jns     short loc_18004BFDF
0x18004bfb1  mov     rcx, [rsp+98h]; this
0x18004bfb9  mov     r9d, eax; char *
0x18004bfbc  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004bfc3  mov     edx, 278h; void *
0x18004bfc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bfcd  nop
0x18004bfce  lea     rcx, [rsp+98h+var_78]
0x18004bfd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bfd8  mov     eax, ebx
0x18004bfda  jmp     loc_18004C196
0x18004bfdf  cmp     byte ptr [rsp+98h+string], r15b
0x18004bfe7  setnz   r14b
0x18004bfeb  mov     byte ptr [rsp+98h+arg_18], r14b
0x18004bff3  lea     rdx, stru_180069A40; HSTRING
0x18004bffa  mov     rcx, rdi; this
0x18004bffd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004c002  test    al, al
0x18004c004  jz      loc_18004C0D3
0x18004c00a  lea     rbx, [rsi+160h]
0x18004c011  mov     rcx, rbx
0x18004c014  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004c019  mov     qword ptr [rsp+98h+var_60], rax
0x18004c01e  lea     rdx, [rsp+98h+var_60]
0x18004c023  lea     rcx, [rsp+98h+arg_18]
0x18004c02b  call    ??$ManagedByWindowsToggled@AEA_NPEBG@UsageGraphTelemetry@@SAXAEA_N$$QEAPEBG@Z; UsageGraphTelemetry::ManagedByWindowsToggled<bool &,ushort const *>(bool &,ushort const * &&)
0x18004c030  mov     rcx, rsi; this
0x18004c033  call    ?IsBackgroundTasksControlUserConfigurable@AppListEntry@BatteryUsageHandlers@SystemSettings@@AEAA_NXZ; SystemSettings::BatteryUsageHandlers::AppListEntry::IsBackgroundTasksControlUserConfigurable(void)
0x18004c038  test    al, al
0x18004c03a  jz      short loc_18004C0B8
0x18004c03c  movzx   eax, r14b
0x18004c040  xor     eax, 1
0x18004c043  lea     edi, ds:1[rax*2]
0x18004c04a  mov     rdx, rbx
0x18004c04d  lea     rcx, [rsp+98h+var_58]
0x18004c052  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c057  mov     r8, rax
0x18004c05a  lea     rdx, [rsp+98h+var_38]
0x18004c05f  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x18004c066  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::wstring)
0x18004c06b  mov     edx, edi
0x18004c06d  mov     rcx, rax
0x18004c070  call    ?SetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPolicy@12@@Z; SystemSettings::BatteryUsageHandlers::SetTaskPolicy(std::wstring,SystemSettings::BatteryUsageHandlers::TaskPolicy)
0x18004c075  mov     ebx, eax
0x18004c077  test    eax, eax
0x18004c079  jns     short loc_18004C0A9
0x18004c07b  mov     rcx, [rsp+98h]; this
0x18004c083  mov     r9d, eax; char *
0x18004c086  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004c08d  mov     edx, 286h; void *
0x18004c092  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c097  nop
0x18004c098  lea     rcx, [rsp+98h+var_78]
0x18004c09d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c0a2  mov     eax, ebx
0x18004c0a4  jmp     loc_18004C196
0x18004c0a9  lea     rdx, stru_180069AC8; unsigned __int16 *
0x18004c0b0  mov     rcx, rsi; this
0x18004c0b3  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004c0b8  lea     rdx, stru_180069B20; unsigned __int16 *
0x18004c0bf  mov     rcx, rsi; this
0x18004c0c2  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004c0c7  lea     rdx, stru_180069A40
0x18004c0ce  jmp     loc_18004C178
0x18004c0d3  lea     rdx, stru_180069AC8; HSTRING
0x18004c0da  mov     rcx, rdi; this
0x18004c0dd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18004c0e2  test    al, al
0x18004c0e4  jz      loc_18004C181
0x18004c0ea  lea     rbx, [rsi+160h]
0x18004c0f1  mov     rcx, rbx
0x18004c0f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004c0f9  mov     qword ptr [rsp+98h+var_60], rax
0x18004c0fe  lea     rdx, [rsp+98h+var_60]
0x18004c103  lea     rcx, [rsp+98h+arg_18]
0x18004c10b  call    ??$IsTasksDisabledToggled@AEA_NPEBG@UsageGraphTelemetry@@SAXAEA_N$$QEAPEBG@Z; UsageGraphTelemetry::IsTasksDisabledToggled<bool &,ushort const *>(bool &,ushort const * &&)
0x18004c110  movzx   edi, r14b
0x18004c114  mov     rdx, rbx
0x18004c117  lea     rcx, [rsp+98h+var_38]
0x18004c11c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004c121  mov     r8, rax
0x18004c124  lea     rdx, [rsp+98h+var_58]
0x18004c129  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x18004c130  call    ?GetPackageFullNameFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V45@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFullNameFromFamilyName(std::wstring)
0x18004c135  lea     edx, [rdi+2]
0x18004c138  mov     rcx, rax
0x18004c13b  call    ?SetTaskPolicy@BatteryUsageHandlers@SystemSettings@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TaskPolicy@12@@Z; SystemSettings::BatteryUsageHandlers::SetTaskPolicy(std::wstring,SystemSettings::BatteryUsageHandlers::TaskPolicy)
0x18004c140  mov     ebx, eax
0x18004c142  test    eax, eax
0x18004c144  jns     short loc_18004C171
0x18004c146  mov     rcx, [rsp+98h]; this
0x18004c14e  mov     r9d, eax; char *
0x18004c151  lea     r8, aOnecoreuapShel_15; "onecoreuap\\shell\\coresettinghandlers"...
0x18004c158  mov     edx, 296h; void *
0x18004c15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c162  nop
0x18004c163  lea     rcx, [rsp+98h+var_78]
0x18004c168  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c16d  mov     eax, ebx
0x18004c16f  jmp     short loc_18004C196
0x18004c171  lea     rdx, stru_180069B20; unsigned __int16 *
0x18004c178  mov     rcx, rsi; this
0x18004c17b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004c180  nop
0x18004c181  lea     rcx, [rsp+98h+var_78]
0x18004c186  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004c18b  xor     eax, eax
0x18004c18d  jmp     short loc_18004C196
0x18004c18f  mov     eax, dword ptr [rsp+98h+string]
0x18004c196  lea     r11, [rsp+98h+var_18]
0x18004c19e  mov     rbx, [r11+20h]
0x18004c1a2  mov     rsi, [r11+28h]
0x18004c1a6  mov     rsp, r11
0x18004c1a9  pop     r15
0x18004c1ab  pop     r14
0x18004c1ad  pop     rdi
0x18004c1ae  retn
```
