# SystemSettings::DataModel::CHighContrast::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800639e0`
- end: `0x180063d07`
- name: `?GetValue@CHighContrast@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `807`
- prototype: `int(SystemSettings::DataModel::CHighContrast *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180019a20`
- `0x1800201c4`
- `0x180021398`
- `0x1800236e0`
- `0x1800252c4`
- `0x1800496fc`
- `0x180063550`
- `0x1800635ac`
- `0x1800639e0`
- `0x180066828`
- `0x180066978`
- `0x180066bdc`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063ab1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063bfc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063ab1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180063bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800639fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063b5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800639fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180063b5f`

## string_xrefs

- `0x180063cf4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180063a21`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\highcontrast.cpp`
- `0x180063b1b`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\highcontrast.cpp`
- `0x180063b84`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\highcontrast.cpp`
- `0x180063c25`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\highcontrast.cpp`
- `0x180063c61`: `shell\systemsettingsthreshold\handlers\internal\accessibility\lib\highcontrast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CHighContrast::GetValue(
        SystemSettings::DataModel::CHighContrast *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  int InitResultWait; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rdx
  const char *v10; // r9
  const WCHAR *StringRawBuffer; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  const unsigned __int16 *v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  HSTRING *p_string; // rcx
  const unsigned __int16 *v22; // r8
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rcx
  int v28; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-28h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF
  __int64 v34; // [rsp+68h] [rbp+20h] BYREF

  WindowsGetStringRawBuffer((HSTRING)a2, 0);
  *a3 = 0;
  InitResultWait = SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::EThemeOperation>::GetInitResultWait();
  v7 = InitResultWait;
  if ( InitResultWait < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
      (const char *)(unsigned int)InitResultWait,
      bIgnoreCase);
    return v7;
  }
  try
  {
    if ( dword_18039D3C8 != 2 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56960283>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56960283>::GetImpl'::`2'::impl) )
      {
        LOBYTE(v9) = 1;
        (*(void (__fastcall **)(SystemSettings::DataModel::CHighContrast *, __int64))(*(_QWORD *)this + 168LL))(
          this,
          v9);
      }
      if ( !dword_18039D3C8 )
        SystemSettings::DataModel::CHighContrastHelper::_MakeSureHCThemesLoaded(
          (SystemSettings::DataModel::CHighContrastHelper *)&qword_18039D2C0,
          0);
      return 0;
    }
    StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)a2, 0);
    if ( CompareStringOrdinal(StringRawBuffer, -1, L"Value", -1, 1) == 2 )
    {
      SystemSettings::DataModel::CHighContrastHelper::GetPreselectedTheme(v12, &v34);
      string = 0;
      v13 = v34;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v15 = v14(v13, &string);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x375,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
          (const char *)(unsigned int)v15,
          bIgnoreCasea);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v34);
        return v16;
      }
      v17 = WindowsGetStringRawBuffer(string, 0);
      v18 = SystemSettings::DataModel::PropValueHelper::CreateString(v17, a3);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x376,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
          (const char *)(unsigned int)v18,
          bIgnoreCasea);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(&v34);
        return v19;
      }
      v20 = 0;
      WindowsDeleteString(string);
      string = 0;
      p_string = (HSTRING *)&v34;
    }
    else
    {
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"PossibleValues", -1, 1) == 2 )
      {
        v23 = SystemSettings::DataModel::CHighContrast::_PopulateHCThemeList(this, 1);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37E,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCaseb);
          return v24;
        }
        v25 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
                *((_QWORD *)this + 30),
                &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                a3);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x37F,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCaseb);
          return v26;
        }
        return 0;
      }
      v20 = -2147024809;
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802F0DB8, v22) )
        return v20;
      SystemSettings::DataModel::CHighContrastHelper::GetPreselectedTheme(v27, &string);
      if ( string )
      {
        v28 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, struct IInspectable **))string)(
                string,
                &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                a3);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v28,
            bIgnoreCaseb);
      }
      else
      {
        *a3 = 0;
      }
      v20 = 0;
      p_string = &string;
    }
    wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(p_string);
    return v20;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x38C,
                           (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\accessibility\\lib\\highcontrast.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800639e0  mov     [rsp+arg_0], rbx
0x1800639e5  push    rsi
0x1800639e6  push    rdi
0x1800639e7  push    r14
0x1800639e9  sub     rsp, 30h
0x1800639ed  mov     rsi, r8
0x1800639f0  mov     r14, rdx
0x1800639f3  mov     rdi, rcx
0x1800639f6  xor     edx, edx; length
0x1800639f8  mov     rcx, r14; string
0x1800639fb  call    cs:__imp_WindowsGetStringRawBuffer
0x180063a02  nop     dword ptr [rax+rax+00h]
0x180063a07  mov     qword ptr [rsi], 0
0x180063a0e  call    ?GetInitResultWait@?$CSingletonHelper@W4EThemeOperation@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::EThemeOperation>::GetInitResultWait(void)
0x180063a13  mov     ebx, eax
0x180063a15  test    eax, eax
0x180063a17  jns     short loc_180063A39
0x180063a19  mov     rcx, [rsp+48h]; this
0x180063a1e  mov     r9d, eax; char *
0x180063a21  lea     r8, aShellSystemset_91; "shell\\systemsettingsthreshold\\handler"...
0x180063a28  mov     edx, 35Bh; void *
0x180063a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063a32  mov     eax, ebx
0x180063a34  jmp     loc_180063CE2
0x180063a39  cmp     cs:dword_18039D3C8, 2
0x180063a40  jz      short loc_180063A84
0x180063a42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56960283@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56960283@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56960283> `wil::Feature<__WilFeatureTraits_Feature_56960283>::GetImpl(void)'::`2'::impl
0x180063a49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56960283@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56960283>::__private_IsEnabled(void)
0x180063a4e  test    al, al
0x180063a50  jz      short loc_180063A66
0x180063a52  mov     rax, [rdi]
0x180063a55  mov     dl, 1
0x180063a57  mov     rcx, rdi
0x180063a5a  mov     rax, [rax+0A8h]
0x180063a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a66  cmp     cs:dword_18039D3C8, 0
0x180063a6d  jnz     short loc_180063A7D
0x180063a6f  xor     edx, edx; enum SystemSettings::DataModel::ELoadStatus *
0x180063a71  lea     rcx, qword_18039D2C0; this
0x180063a78  call    ?_MakeSureHCThemesLoaded@CHighContrastHelper@DataModel@SystemSettings@@AEAAJPEAW4ELoadStatus@23@@Z; SystemSettings::DataModel::CHighContrastHelper::_MakeSureHCThemesLoaded(SystemSettings::DataModel::ELoadStatus *)
0x180063a7d  xor     eax, eax
0x180063a7f  jmp     loc_180063CE2
0x180063a84  xor     edx, edx; length
0x180063a86  mov     rcx, r14; string
0x180063a89  call    cs:__imp_WindowsGetStringRawBuffer
0x180063a90  nop     dword ptr [rax+rax+00h]
0x180063a95  mov     rbx, rax
0x180063a98  mov     [rsp+48h+bIgnoreCase], 1; int
0x180063aa0  or      r9d, 0FFFFFFFFh; cchCount2
0x180063aa4  lea     r8, aValue_0; "Value"
0x180063aab  or      edx, r9d; cchCount1
0x180063aae  mov     rcx, rax; lpString1
0x180063ab1  call    cs:__imp_CompareStringOrdinal
0x180063ab8  nop     dword ptr [rax+rax+00h]
0x180063abd  cmp     eax, 2
0x180063ac0  jnz     loc_180063BE3
0x180063ac6  lea     rdx, [rsp+48h+arg_18]
0x180063acb  call    ?GetPreselectedTheme@CHighContrastHelper@DataModel@SystemSettings@@QEAA?AV?$com_ptr_t@VCHighContrastTheme@DataModel@SystemSettings@@Uerr_exception_policy@wil@@@wil@@XZ; SystemSettings::DataModel::CHighContrastHelper::GetPreselectedTheme(void)
0x180063ad0  nop
0x180063ad1  mov     [rsp+48h+string], 0
0x180063ada  mov     rdi, [rsp+48h+arg_18]
0x180063adf  mov     rax, [rdi]
0x180063ae2  mov     rbx, [rax+30h]
0x180063ae6  xor     ecx, ecx; string
0x180063ae8  call    cs:__imp_WindowsDeleteString
0x180063aef  nop     dword ptr [rax+rax+00h]
0x180063af4  mov     [rsp+48h+string], 0
0x180063afd  lea     rdx, [rsp+48h+string]
0x180063b02  mov     rcx, rdi
0x180063b05  mov     rax, rbx
0x180063b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b0d  mov     ebx, eax
0x180063b0f  test    eax, eax
0x180063b11  jns     short loc_180063B58
0x180063b13  mov     rcx, [rsp+48h]; this
0x180063b18  mov     r9d, eax; char *
0x180063b1b  lea     r8, aShellSystemset_91; "shell\\systemsettingsthreshold\\handler"...
0x180063b22  mov     edx, 375h; void *
0x180063b27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063b2c  nop
0x180063b2d  mov     rcx, [rsp+48h+string]; string
0x180063b32  call    cs:__imp_WindowsDeleteString
0x180063b39  nop     dword ptr [rax+rax+00h]
0x180063b3e  mov     [rsp+48h+string], 0
0x180063b47  lea     rcx, [rsp+48h+arg_18]
0x180063b4c  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180063b51  mov     eax, ebx
0x180063b53  jmp     loc_180063CE2
0x180063b58  xor     edx, edx; length
0x180063b5a  mov     rcx, [rsp+48h+string]; string
0x180063b5f  call    cs:__imp_WindowsGetStringRawBuffer
0x180063b66  nop     dword ptr [rax+rax+00h]
0x180063b6b  mov     rdx, rsi; struct IInspectable **
0x180063b6e  mov     rcx, rax; unsigned __int16 *
0x180063b71  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180063b76  mov     ebx, eax
0x180063b78  test    eax, eax
0x180063b7a  jns     short loc_180063BC1
0x180063b7c  mov     rcx, [rsp+48h]; this
0x180063b81  mov     r9d, eax; char *
0x180063b84  lea     r8, aShellSystemset_91; "shell\\systemsettingsthreshold\\handler"...
0x180063b8b  mov     edx, 376h; void *
0x180063b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063b95  nop
0x180063b96  mov     rcx, [rsp+48h+string]; string
0x180063b9b  call    cs:__imp_WindowsDeleteString
0x180063ba2  nop     dword ptr [rax+rax+00h]
0x180063ba7  mov     [rsp+48h+string], 0
0x180063bb0  lea     rcx, [rsp+48h+arg_18]
0x180063bb5  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180063bba  mov     eax, ebx
0x180063bbc  jmp     loc_180063CE2
0x180063bc1  xor     ebx, ebx
0x180063bc3  mov     rcx, [rsp+48h+string]; string
0x180063bc8  call    cs:__imp_WindowsDeleteString
0x180063bcf  nop     dword ptr [rax+rax+00h]
0x180063bd4  mov     [rsp+48h+string], rbx
0x180063bd9  lea     rcx, [rsp+48h+arg_18]
0x180063bde  jmp     loc_180063CD5
0x180063be3  mov     [rsp+48h+bIgnoreCase], 1; int
0x180063beb  or      r9d, 0FFFFFFFFh; cchCount2
0x180063bef  lea     r8, aPossiblevalues; "PossibleValues"
0x180063bf6  or      edx, r9d; cchCount1
0x180063bf9  mov     rcx, rbx; lpString1
0x180063bfc  call    cs:__imp_CompareStringOrdinal
0x180063c03  nop     dword ptr [rax+rax+00h]
0x180063c08  cmp     eax, 2
0x180063c0b  jnz     short loc_180063C7A
0x180063c0d  mov     dl, 1; bool
0x180063c0f  mov     rcx, rdi; this
0x180063c12  call    ?_PopulateHCThemeList@CHighContrast@DataModel@SystemSettings@@AEAAJ_N@Z; SystemSettings::DataModel::CHighContrast::_PopulateHCThemeList(bool)
0x180063c17  mov     ebx, eax
0x180063c19  test    eax, eax
0x180063c1b  jns     short loc_180063C3D
0x180063c1d  mov     rcx, [rsp+48h]; this
0x180063c22  mov     r9d, eax; char *
0x180063c25  lea     r8, aShellSystemset_91; "shell\\systemsettingsthreshold\\handler"...
0x180063c2c  mov     edx, 37Eh; void *
0x180063c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063c36  mov     eax, ebx
0x180063c38  jmp     loc_180063CE2
0x180063c3d  mov     r8, rsi
0x180063c40  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180063c47  mov     rcx, [rdi+0F0h]
0x180063c4e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180063c53  mov     ebx, eax
0x180063c55  test    eax, eax
0x180063c57  jns     short loc_180063C76
0x180063c59  mov     rcx, [rsp+48h]; this
0x180063c5e  mov     r9d, eax; char *
0x180063c61  lea     r8, aShellSystemset_91; "shell\\systemsettingsthreshold\\handler"...
0x180063c68  mov     edx, 37Fh; void *
0x180063c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063c72  mov     eax, ebx
0x180063c74  jmp     short loc_180063CE2
0x180063c76  xor     ebx, ebx
0x180063c78  jmp     short loc_180063CDA
0x180063c7a  mov     ebx, 80070057h
0x180063c7f  lea     rdx, stru_1802F0DB8; HSTRING
0x180063c86  mov     rcx, r14; this
0x180063c89  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180063c8e  test    al, al
0x180063c90  jz      short loc_180063CDA
0x180063c92  lea     rdx, [rsp+48h+string]
0x180063c97  call    ?GetPreselectedTheme@CHighContrastHelper@DataModel@SystemSettings@@QEAA?AV?$com_ptr_t@VCHighContrastTheme@DataModel@SystemSettings@@Uerr_exception_policy@wil@@@wil@@XZ; SystemSettings::DataModel::CHighContrastHelper::GetPreselectedTheme(void)
0x180063c9c  nop
0x180063c9d  mov     rcx, [rsp+48h+string]
0x180063ca2  test    rcx, rcx
0x180063ca5  jz      short loc_180063CC7
0x180063ca7  mov     rax, [rcx]
0x180063caa  mov     r8, rsi
0x180063cad  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180063cb4  mov     rax, [rax]
0x180063cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063cbc  mov     rcx, [rsp+48h]; this
0x180063cc1  test    eax, eax
0x180063cc3  js      short loc_180063CF1
0x180063cc5  jmp     short loc_180063CCE
0x180063cc7  mov     qword ptr [rsi], 0
0x180063cce  xor     ebx, ebx
0x180063cd0  lea     rcx, [rsp+48h+string]
0x180063cd5  call    ??1?$com_ptr_t@VRadialControllerAvailableAppSetting@RadialControllerSettings@SystemSettings@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>::~com_ptr_t<SystemSettings::RadialControllerSettings::RadialControllerAvailableAppSetting,wil::err_returncode_policy>(void)
0x180063cda  mov     eax, ebx
0x180063cdc  jmp     short loc_180063CE2
0x180063cde  mov     eax, dword ptr [rsp+48h+string]
0x180063ce2  mov     rbx, [rsp+48h+arg_0]
0x180063ce7  add     rsp, 30h
0x180063ceb  pop     r14
0x180063ced  pop     rdi
0x180063cee  pop     rsi
0x180063cef  retn
0x180063cf1  mov     r9d, eax; char *
0x180063cf4  lea     r8, aOnecoreInterna_15; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180063cfb  mov     edx, 1CBEh; void *
0x180063d00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
