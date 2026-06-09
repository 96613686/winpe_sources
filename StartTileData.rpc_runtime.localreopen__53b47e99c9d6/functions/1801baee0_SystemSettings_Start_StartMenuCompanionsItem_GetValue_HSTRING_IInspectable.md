# SystemSettings::Start::StartMenuCompanionsItem::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x1801baee0`
- end: `0x1801bb214`
- name: `?GetValue@StartMenuCompanionsItem@Start@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(SystemSettings::Start::StartMenuCompanionsItem *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001aca4`
- `0x1800240ac`
- `0x18002edec`
- `0x1800ffc20`
- `0x18014df5c`
- `0x180167f00`
- `0x1801b04ac`
- `0x1801baee0`
- `0x1801e5530`
- `0x1802a54c0`
- `0x1802acdc4`
- `0x1802ada68`
- `0x1802adabc`
- `0x1802ae310`
- `0x1802b1b40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb09b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb0eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bafbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801baffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb09b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb0d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801bb0eb`

## string_xrefs

- `0x1801baf36`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801baf81`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bafe8`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bb029`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bb085`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bb0c3`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bb13a`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`
- `0x1801bb1d2`: `shellcommon\shell\tiles\systemsettings\lib\start.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::Start::StartMenuCompanionsItem::GetValue(
        SystemSettings::Start::StartMenuCompanionsItem *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  unsigned __int8 Value; // al
  int Boolean; // eax
  unsigned int v9; // ebx
  const unsigned __int16 *v11; // r8
  int v12; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // r8
  int CustomLogoPath; // eax
  unsigned int v16; // ebx
  HSTRING v17; // rbx
  int v18; // eax
  unsigned int v19; // edi
  HSTRING v20; // rcx
  int AppLogoPath; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  const unsigned __int16 *v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  bool IsHstringEqual; // al
  __int64 v30; // rax
  const unsigned __int16 *v31; // rax
  int v32; // eax
  const char *v33; // r9
  unsigned int v34; // ebx
  int v35[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180415CC8, (const unsigned __int16 *)a3) )
  {
    Value = SystemSettings::Start::StartMenuCompanionsItem::GetValue(this);
    Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(Value, a3);
    v9 = Boolean;
    if ( Boolean < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55D,
        (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
        (const char *)(unsigned int)Boolean,
        v35[0]);
      return v9;
    }
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18042EFA0, v6) )
  {
    v12 = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 632), a3);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x561,
        (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
        (const char *)(unsigned int)v12,
        v35[0]);
      return v13;
    }
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18042ED90, v11) )
  {
    if ( *((_BYTE *)this + 632) )
    {
      WindowsDeleteString(0);
      string = 0;
      CustomLogoPath = SystemSettings::Start::StartMenuCompanionsItem::GetCustomLogoPath(this, &string);
      v16 = CustomLogoPath;
      if ( CustomLogoPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x568,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)CustomLogoPath,
          v35[0]);
        WindowsDeleteString(string);
        return v16;
      }
      v17 = string;
      v18 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x569,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)v18,
          v35[0]);
        WindowsDeleteString(v17);
        return v19;
      }
      v20 = v17;
    }
    else
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      AppLogoPath = SystemSettings::Start::StartMenuCompanionsItem::GetAppLogoPath(this, &string);
      v22 = AppLogoPath;
      if ( AppLogoPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56E,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)AppLogoPath,
          v35[0]);
        WindowsDeleteString(string);
        return v22;
      }
      v23 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56F,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)v23,
          v35[0]);
        WindowsDeleteString(string);
        return v24;
      }
      v20 = string;
    }
    WindowsDeleteString(v20);
  }
  else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18042ED70, v14) )
  {
    v26 = *((_QWORD *)this + 101);
    if ( v26 )
    {
      v27 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(
              v26,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a3);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x576,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)v27,
          v35[0]);
        return v28;
      }
    }
  }
  else
  {
    IsHstringEqual = SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18042E338, v25);
    if ( IsHstringEqual && *((_BYTE *)this + 672) )
    {
      try
      {
        v30 = std::optional<std::wstring>::value((char *)this + 640);
        if ( *(_QWORD *)(v30 + 24) > 7u )
          v30 = *(_QWORD *)v30;
        winrt::param::hstring::hstring((winrt::param::hstring *)v35, (const unsigned __int16 *const)v30);
        winrt::impl::consume_Windows_Data_Json_IJsonObjectStatics<winrt::Windows::Data::Json::IJsonObjectStatics>::Parse(
          (char *)this + 800,
          &string,
          v35);
        v31 = winrt::hstring::c_str((winrt::hstring *)&string);
        v32 = SystemSettings::DataModel::PropValueHelper::CreateString(v31, a3);
      }
      catch ( ... )
      {
        LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x581,
                            (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
                            v33);
        return (unsigned int)string;
      }
      v34 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57C,
          (unsigned int)"shellcommon\\shell\\tiles\\systemsettings\\lib\\start.cpp",
          (const char *)(unsigned int)v32,
          v35[0]);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&string);
        return v34;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&string);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801baee0  mov     [rsp+arg_0], rbx
0x1801baee5  mov     [rsp+arg_8], rsi
0x1801baeea  push    rdi
0x1801baeeb  sub     rsp, 40h
0x1801baeef  mov     rdi, r8
0x1801baef2  mov     rsi, rdx
0x1801baef5  mov     rbx, rcx
0x1801baef8  mov     qword ptr [r8], 0
0x1801baeff  lea     rdx, stru_180415CC8; HSTRING
0x1801baf06  mov     rcx, rsi; this
0x1801baf09  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801baf0e  test    al, al
0x1801baf10  jz      short loc_1801BAF4E
0x1801baf12  mov     rcx, rbx; this
0x1801baf15  call    ?GetValue@StartMenuCompanionsItem@Start@SystemSettings@@UEAA_NXZ; SystemSettings::Start::StartMenuCompanionsItem::GetValue(void)
0x1801baf1a  mov     rdx, rdi; struct IInspectable **
0x1801baf1d  mov     cl, al; unsigned __int8
0x1801baf1f  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801baf24  mov     ebx, eax
0x1801baf26  test    eax, eax
0x1801baf28  jns     loc_1801BB1FB
0x1801baf2e  mov     rcx, [rsp+48h]; this
0x1801baf33  mov     r9d, eax; char *
0x1801baf36  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801baf3d  mov     edx, 55Dh; void *
0x1801baf42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801baf47  mov     eax, ebx
0x1801baf49  jmp     loc_1801BB203
0x1801baf4e  lea     rdx, stru_18042EFA0; HSTRING
0x1801baf55  mov     rcx, rsi; this
0x1801baf58  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801baf5d  test    al, al
0x1801baf5f  jz      short loc_1801BAF99
0x1801baf61  mov     rdx, rdi; struct IInspectable **
0x1801baf64  mov     cl, [rbx+278h]; unsigned __int8
0x1801baf6a  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801baf6f  mov     ebx, eax
0x1801baf71  test    eax, eax
0x1801baf73  jns     loc_1801BB1FB
0x1801baf79  mov     rcx, [rsp+48h]; this
0x1801baf7e  mov     r9d, eax; char *
0x1801baf81  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801baf88  mov     edx, 561h; void *
0x1801baf8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801baf92  mov     eax, ebx
0x1801baf94  jmp     loc_1801BB203
0x1801baf99  lea     rdx, stru_18042ED90; HSTRING
0x1801bafa0  mov     rcx, rsi; this
0x1801bafa3  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801bafa8  test    al, al
0x1801bafaa  jz      loc_1801BB0F6
0x1801bafb0  xor     ecx, ecx; string
0x1801bafb2  cmp     [rbx+278h], cl
0x1801bafb8  jz      loc_1801BB052
0x1801bafbe  call    cs:__imp_WindowsDeleteString
0x1801bafc4  mov     [rsp+48h+string], 0
0x1801bafcd  lea     rdx, [rsp+48h+string]; HSTRING *
0x1801bafd2  mov     rcx, rbx; this
0x1801bafd5  call    ?GetCustomLogoPath@StartMenuCompanionsItem@Start@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::Start::StartMenuCompanionsItem::GetCustomLogoPath(HSTRING__ * *)
0x1801bafda  mov     ebx, eax
0x1801bafdc  test    eax, eax
0x1801bafde  jns     short loc_1801BB00B
0x1801bafe0  mov     rcx, [rsp+48h]; this
0x1801bafe5  mov     r9d, eax; char *
0x1801bafe8  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bafef  mov     edx, 568h; void *
0x1801baff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801baff9  mov     rcx, [rsp+48h+string]; string
0x1801baffe  call    cs:__imp_WindowsDeleteString
0x1801bb004  mov     eax, ebx
0x1801bb006  jmp     loc_1801BB203
0x1801bb00b  mov     rdx, rdi; struct IInspectable **
0x1801bb00e  mov     rbx, [rsp+48h+string]
0x1801bb013  mov     rcx, rbx; HSTRING
0x1801bb016  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801bb01b  mov     edi, eax
0x1801bb01d  test    eax, eax
0x1801bb01f  jns     short loc_1801BB04A
0x1801bb021  mov     rcx, [rsp+48h]; this
0x1801bb026  mov     r9d, eax; char *
0x1801bb029  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bb030  mov     edx, 569h; void *
0x1801bb035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb03a  mov     rcx, rbx; string
0x1801bb03d  call    cs:__imp_WindowsDeleteString
0x1801bb043  mov     eax, edi
0x1801bb045  jmp     loc_1801BB203
0x1801bb04a  mov     rcx, rbx
0x1801bb04d  jmp     loc_1801BB0EB
0x1801bb052  mov     [rsp+48h+string], 0
0x1801bb05b  call    cs:__imp_WindowsDeleteString
0x1801bb061  mov     [rsp+48h+string], 0
0x1801bb06a  lea     rdx, [rsp+48h+string]; HSTRING *
0x1801bb06f  mov     rcx, rbx; this
0x1801bb072  call    ?GetAppLogoPath@StartMenuCompanionsItem@Start@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::Start::StartMenuCompanionsItem::GetAppLogoPath(HSTRING__ * *)
0x1801bb077  mov     ebx, eax
0x1801bb079  test    eax, eax
0x1801bb07b  jns     short loc_1801BB0A8
0x1801bb07d  mov     rcx, [rsp+48h]; this
0x1801bb082  mov     r9d, eax; char *
0x1801bb085  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bb08c  mov     edx, 56Eh; void *
0x1801bb091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb096  mov     rcx, [rsp+48h+string]; string
0x1801bb09b  call    cs:__imp_WindowsDeleteString
0x1801bb0a1  mov     eax, ebx
0x1801bb0a3  jmp     loc_1801BB203
0x1801bb0a8  mov     rdx, rdi; struct IInspectable **
0x1801bb0ab  mov     rcx, [rsp+48h+string]; HSTRING
0x1801bb0b0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1801bb0b5  mov     ebx, eax
0x1801bb0b7  test    eax, eax
0x1801bb0b9  jns     short loc_1801BB0E6
0x1801bb0bb  mov     rcx, [rsp+48h]; this
0x1801bb0c0  mov     r9d, eax; char *
0x1801bb0c3  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bb0ca  mov     edx, 56Fh; void *
0x1801bb0cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb0d4  mov     rcx, [rsp+48h+string]; string
0x1801bb0d9  call    cs:__imp_WindowsDeleteString
0x1801bb0df  mov     eax, ebx
0x1801bb0e1  jmp     loc_1801BB203
0x1801bb0e6  mov     rcx, [rsp+48h+string]; string
0x1801bb0eb  call    cs:__imp_WindowsDeleteString
0x1801bb0f1  jmp     loc_1801BB1FB
0x1801bb0f6  lea     rdx, stru_18042ED70; HSTRING
0x1801bb0fd  mov     rcx, rsi; this
0x1801bb100  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801bb105  test    al, al
0x1801bb107  jz      short loc_1801BB152
0x1801bb109  mov     rcx, [rbx+328h]
0x1801bb110  test    rcx, rcx
0x1801bb113  jz      loc_1801BB1FB
0x1801bb119  mov     r8, rdi
0x1801bb11c  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801bb123  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1801bb128  mov     ebx, eax
0x1801bb12a  test    eax, eax
0x1801bb12c  jns     loc_1801BB1FB
0x1801bb132  mov     rcx, [rsp+48h]; this
0x1801bb137  mov     r9d, eax; char *
0x1801bb13a  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bb141  mov     edx, 576h; void *
0x1801bb146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb14b  mov     eax, ebx
0x1801bb14d  jmp     loc_1801BB203
0x1801bb152  lea     rdx, stru_18042E338; HSTRING
0x1801bb159  mov     rcx, rsi; this
0x1801bb15c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801bb161  test    al, al
0x1801bb163  jz      loc_1801BB1FB
0x1801bb169  cmp     byte ptr [rbx+2A0h], 0
0x1801bb170  jz      loc_1801BB1FB
0x1801bb176  lea     rcx, [rbx+280h]
0x1801bb17d  call    ?value@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::optional<std::wstring>::value(void)
0x1801bb182  cmp     qword ptr [rax+18h], 7
0x1801bb187  jbe     short loc_1801BB18C
0x1801bb189  mov     rax, [rax]
0x1801bb18c  mov     rdx, rax; unsigned __int16 *
0x1801bb18f  lea     rcx, [rsp+48h+var_28]; this
0x1801bb194  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801bb199  lea     rcx, [rbx+320h]
0x1801bb1a0  lea     r8, [rsp+48h+var_28]
0x1801bb1a5  lea     rdx, [rsp+48h+string]
0x1801bb1aa  call    ?Parse@?$consume_Windows_Data_Json_IJsonObjectStatics@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectStatics<winrt::Windows::Data::Json::IJsonObjectStatics>::Parse(winrt::param::hstring const &)
0x1801bb1af  lea     rcx, [rsp+48h+string]; this
0x1801bb1b4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801bb1b9  mov     rcx, rax; unsigned __int16 *
0x1801bb1bc  mov     rdx, rdi; struct IInspectable **
0x1801bb1bf  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801bb1c4  mov     ebx, eax
0x1801bb1c6  test    eax, eax
0x1801bb1c8  jns     short loc_1801BB1F1
0x1801bb1ca  mov     rcx, [rsp+48h]; this
0x1801bb1cf  mov     r9d, eax; char *
0x1801bb1d2  lea     r8, aShellcommonShe_8; "shellcommon\\shell\\tiles\\systemsettin"...
0x1801bb1d9  mov     edx, 57Ch; void *
0x1801bb1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801bb1e3  lea     rcx, [rsp+48h+string]
0x1801bb1e8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bb1ed  mov     eax, ebx
0x1801bb1ef  jmp     short loc_1801BB203
0x1801bb1f1  lea     rcx, [rsp+48h+string]
0x1801bb1f6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801bb1fb  xor     eax, eax
0x1801bb1fd  jmp     short loc_1801BB203
0x1801bb1ff  mov     eax, dword ptr [rsp+48h+string]
0x1801bb203  mov     rbx, [rsp+48h+arg_0]
0x1801bb208  mov     rsi, [rsp+48h+arg_8]
0x1801bb20d  add     rsp, 40h
0x1801bb211  pop     rdi
0x1801bb212  retn
```
