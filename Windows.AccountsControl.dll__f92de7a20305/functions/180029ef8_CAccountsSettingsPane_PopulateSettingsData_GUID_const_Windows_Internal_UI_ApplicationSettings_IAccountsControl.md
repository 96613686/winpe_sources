# CAccountsSettingsPane::PopulateSettingsData(_GUID const &,Windows::Internal::UI::ApplicationSettings::IAccountsControlData *,Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)

- ea: `0x180029ef8`
- end: `0x18002a25e`
- name: `?PopulateSettingsData@CAccountsSettingsPane@@QEAAJAEBU_GUID@@PEAUIAccountsControlData@ApplicationSettings@UI@Internal@Windows@@PEAUIAccountsSettingsPaneInternal@4567@@Z`
- size: `870`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, const struct _GUID *, struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024888`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180016e40`
- `0x180022744`
- `0x1800235a8`
- `0x18002451c`
- `0x180029ef8`
- `0x18002cc04`
- `0x18002d1d0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a1e9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a018`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002a018`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAccountsSettingsPane::PopulateSettingsData(
        CAccountsSettingsPane *this,
        const struct _GUID *a2,
        struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *a3,
        __int64 (__fastcall ***a4)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *))
{
  __int64 (__fastcall *v8)(struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, __int64 *); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rbx
  int ActivationFactory; // eax
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v19)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  int v26[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v31 = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, __int64 *))(*(_QWORD *)a3 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  v9 = v8(a3, &v31);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)v9,
      v26[0]);
    goto LABEL_28;
  }
  *(_QWORD *)v26 = 0;
  v11 = *((_QWORD *)this + 18);
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.UI.ApplicationSettings.SettingsData",
    0x35u,
    0x34u);
  v12 = v33;
  if ( v11 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
    ActivationFactory = Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::ISettingsDataFactory>(
                          v12,
                          v11,
                          v26);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = 681;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v26[0]);
LABEL_7:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      goto LABEL_28;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
    ActivationFactory = RoGetActivationFactory(v12, &GUID_b64ad501_2228_4844_9335_f16681e2b126, v26);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v14 = 685;
      goto LABEL_6;
    }
  }
  v28 = 0;
  v15 = **a4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v16 = v15(
          (struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)a4,
          &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
          &v28);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 689;
    goto LABEL_12;
  }
  v29 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 72LL))(v28, &v29);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 692;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)v16,
      v26[0]);
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    goto LABEL_7;
  }
  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v34);
  v34[0] = &AccountsControlAPITelemetry::SettingsDataActivity::`vftable';
  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    v34,
    a2);
  AccountsControlAPITelemetry::SettingsDataActivity::StartActivity(
    (AccountsControlAPITelemetry::SettingsDataActivity *)v34,
    v29);
  for ( i = 0; i < v29; ++i )
  {
    string = 0;
    v19 = (*a4)[10];
    WindowsDeleteString(0);
    string = 0;
    v20 = v19(
            (struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)a4,
            (GUID *)i,
            (__int64 *)&string);
    v10 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BD,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v20,
        v26[0]);
      goto LABEL_26;
    }
    v30 = 0;
    v21 = *(_QWORD *)v26;
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(**(_QWORD **)v26 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v23 = v22(v21, string, &v30);
    v10 = v23;
    if ( v23 < 0 )
    {
      v24 = 704;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v23,
        v26[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
LABEL_26:
      WindowsDeleteString(string);
      string = 0;
      AccountsControlAPITelemetry::SettingsDataActivity::~SettingsDataActivity((AccountsControlAPITelemetry::SettingsDataActivity *)v34);
      goto LABEL_13;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 104LL))(v31, v30);
    v10 = v23;
    if ( v23 < 0 )
    {
      v24 = 705;
      goto LABEL_24;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    WindowsDeleteString(string);
  }
  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v34);
  AccountsControlAPITelemetry::SettingsDataActivity::~SettingsDataActivity((AccountsControlAPITelemetry::SettingsDataActivity *)v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  v10 = 0;
LABEL_28:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  return v10;
}

```

## disassembly

```asm
0x180029ef8  push    rbp
0x180029efa  push    rbx
0x180029efb  push    rsi
0x180029efc  push    rdi
0x180029efd  push    r12
0x180029eff  push    r14
0x180029f01  push    r15
0x180029f03  lea     rbp, [rsp-0D0h]
0x180029f0b  sub     rsp, 1D0h
0x180029f12  mov     rax, cs:__security_cookie
0x180029f19  xor     rax, rsp
0x180029f1c  mov     [rbp+100h+var_40], rax
0x180029f23  mov     r14, r9
0x180029f26  mov     rdi, r8
0x180029f29  mov     r15, rdx
0x180029f2c  mov     rsi, rcx
0x180029f2f  xor     r12d, r12d
0x180029f32  mov     [rsp+200h+var_1B8], r12
0x180029f37  mov     rax, [r8]
0x180029f3a  mov     rbx, [rax+40h]
0x180029f3e  lea     rcx, [rsp+200h+var_1B8]
0x180029f43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029f48  lea     rdx, [rsp+200h+var_1B8]
0x180029f4d  mov     rcx, rdi
0x180029f50  mov     rax, rbx
0x180029f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f58  mov     ebx, eax
0x180029f5a  test    eax, eax
0x180029f5c  jns     short loc_180029F7E
0x180029f5e  mov     rcx, [rbp+108h]; this
0x180029f65  mov     r9d, eax; char *
0x180029f68  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029f6f  mov     edx, 2A3h; void *
0x180029f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f79  jmp     loc_18002A231
0x180029f7e  mov     qword ptr [rsp+200h+var_1E0], r12; int
0x180029f83  mov     rdi, [rsi+90h]
0x180029f8a  mov     [rsp+200h+var_198], r12
0x180029f8f  mov     r9d, 34h ; '4'; unsigned int
0x180029f95  lea     r8d, [r9+1]; unsigned int
0x180029f99  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_SettingsData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x180029fa0  lea     rcx, [rsp+200h+hstringHeader]; hstringHeader
0x180029fa5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029faa  mov     rbx, [rsp+200h+var_198]
0x180029faf  test    rdi, rdi
0x180029fb2  jz      short loc_180029FFF
0x180029fb4  lea     rcx, [rsp+200h+var_1E0]
0x180029fb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029fbe  lea     r8, [rsp+200h+var_1E0]
0x180029fc3  mov     rdx, rdi
0x180029fc6  mov     rcx, rbx
0x180029fc9  call    ??$GetActivationFactoryAsUser@UISettingsDataFactory@ApplicationSettings@UI@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUISettingsDataFactory@ApplicationSettings@UI@Internal@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::ISettingsDataFactory>(HSTRING__ *,Windows::System::IUser *,Windows::Internal::UI::ApplicationSettings::ISettingsDataFactory * *)
0x180029fce  mov     ebx, eax
0x180029fd0  test    eax, eax
0x180029fd2  jns     short loc_18002A02B
0x180029fd4  mov     edx, 2A9h; void *
0x180029fd9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029fe0  mov     r9d, eax; char *
0x180029fe3  mov     rcx, [rbp+108h]; this
0x180029fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fef  nop
0x180029ff0  lea     rcx, [rsp+200h+var_1E0]
0x180029ff5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029ffa  jmp     loc_18002A231
0x180029fff  lea     rcx, [rsp+200h+var_1E0]
0x18002a004  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a009  lea     r8, [rsp+200h+var_1E0]
0x18002a00e  lea     rdx, _GUID_b64ad501_2228_4844_9335_f16681e2b126
0x18002a015  mov     rcx, rbx
0x18002a018  call    cs:__imp_RoGetActivationFactory
0x18002a01e  mov     ebx, eax
0x18002a020  test    eax, eax
0x18002a022  jns     short loc_18002A02B
0x18002a024  mov     edx, 2ADh
0x18002a029  jmp     short loc_180029FD9
0x18002a02b  mov     [rsp+200h+var_1D0], r12
0x18002a030  mov     rax, [r14]
0x18002a033  mov     rbx, [rax]
0x18002a036  lea     rcx, [rsp+200h+var_1D0]
0x18002a03b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a040  lea     r8, [rsp+200h+var_1D0]
0x18002a045  lea     rdx, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x18002a04c  mov     rcx, r14
0x18002a04f  mov     rax, rbx
0x18002a052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a057  mov     ebx, eax
0x18002a059  test    eax, eax
0x18002a05b  jns     short loc_18002A088
0x18002a05d  mov     edx, 2B1h; void *
0x18002a062  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002a069  mov     r9d, eax; char *
0x18002a06c  mov     rcx, [rbp+108h]; this
0x18002a073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a078  nop
0x18002a079  lea     rcx, [rsp+200h+var_1D0]
0x18002a07e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a083  jmp     loc_180029FF0
0x18002a088  mov     [rsp+200h+var_1C8], r12d
0x18002a08d  mov     rcx, [rsp+200h+var_1D0]
0x18002a092  mov     rax, [rcx]
0x18002a095  lea     rdx, [rsp+200h+var_1C8]
0x18002a09a  mov     rax, [rax+48h]
0x18002a09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0a3  mov     ebx, eax
0x18002a0a5  test    eax, eax
0x18002a0a7  jns     short loc_18002A0B0
0x18002a0a9  mov     edx, 2B4h
0x18002a0ae  jmp     short loc_18002A062
0x18002a0b0  lea     rdx, aSettingsdataac; "SettingsDataActivity"
0x18002a0b7  lea     rcx, [rsp+200h+var_190]; struct wil::details::IFailureCallback *
0x18002a0bc  call    ??0?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002a0c1  lea     rax, ??_7SettingsDataActivity@AccountsControlAPITelemetry@@6B@; const AccountsControlAPITelemetry::SettingsDataActivity::`vftable'
0x18002a0c8  mov     [rsp+200h+var_190], rax
0x18002a0cd  mov     rdx, r15
0x18002a0d0  lea     rcx, [rsp+200h+var_190]
0x18002a0d5  call    ?SetRelatedActivityId@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x18002a0da  mov     edx, [rsp+200h+var_1C8]; unsigned int
0x18002a0de  lea     rcx, [rsp+200h+var_190]; this
0x18002a0e3  call    ?StartActivity@SettingsDataActivity@AccountsControlAPITelemetry@@QEAAXI@Z; AccountsControlAPITelemetry::SettingsDataActivity::StartActivity(uint)
0x18002a0e8  mov     esi, r12d
0x18002a0eb  cmp     esi, [rsp+200h+var_1C8]
0x18002a0ef  jnb     loc_18002A203
0x18002a0f5  mov     [rsp+200h+string], r12
0x18002a0fa  mov     rax, [r14]
0x18002a0fd  mov     rbx, [rax+50h]
0x18002a101  xor     ecx, ecx; string
0x18002a103  call    cs:__imp_WindowsDeleteString
0x18002a109  mov     [rsp+200h+string], r12
0x18002a10e  lea     r8, [rsp+200h+string]
0x18002a113  mov     edx, esi
0x18002a115  mov     rcx, r14
0x18002a118  mov     rax, rbx
0x18002a11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a120  mov     ebx, eax
0x18002a122  test    eax, eax
0x18002a124  js      loc_18002A1C8
0x18002a12a  mov     [rsp+200h+var_1C0], r12
0x18002a12f  mov     rdi, qword ptr [rsp+200h+var_1E0]
0x18002a134  mov     rax, [rdi]
0x18002a137  mov     rbx, [rax+30h]
0x18002a13b  lea     rcx, [rsp+200h+var_1C0]
0x18002a140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a145  lea     r8, [rsp+200h+var_1C0]
0x18002a14a  mov     rdx, [rsp+200h+string]
0x18002a14f  mov     rcx, rdi
0x18002a152  mov     rax, rbx
0x18002a155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a15a  mov     ebx, eax
0x18002a15c  test    eax, eax
0x18002a15e  js      short loc_18002A1A0
0x18002a160  mov     rcx, [rsp+200h+var_1B8]
0x18002a165  mov     rax, [rcx]
0x18002a168  mov     rdx, [rsp+200h+var_1C0]
0x18002a16d  mov     rax, [rax+68h]
0x18002a171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a176  mov     ebx, eax
0x18002a178  test    eax, eax
0x18002a17a  js      short loc_18002A199
0x18002a17c  lea     rcx, [rsp+200h+var_1C0]
0x18002a181  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a186  nop
0x18002a187  mov     rcx, [rsp+200h+string]; string
0x18002a18c  call    cs:__imp_WindowsDeleteString
0x18002a192  inc     esi
0x18002a194  jmp     loc_18002A0EB
0x18002a199  mov     edx, 2C1h
0x18002a19e  jmp     short loc_18002A1A5
0x18002a1a0  mov     edx, 2C0h; void *
0x18002a1a5  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002a1ac  mov     r9d, eax; char *
0x18002a1af  mov     rcx, [rbp+108h]; this
0x18002a1b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1bb  nop
0x18002a1bc  lea     rcx, [rsp+200h+var_1C0]
0x18002a1c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a1c6  jmp     short loc_18002A1E4
0x18002a1c8  mov     rcx, [rbp+108h]; this
0x18002a1cf  mov     r9d, eax; char *
0x18002a1d2  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002a1d9  mov     edx, 2BDh; void *
0x18002a1de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a1e3  nop
0x18002a1e4  mov     rcx, [rsp+200h+string]; string
0x18002a1e9  call    cs:__imp_WindowsDeleteString
0x18002a1ef  mov     [rsp+200h+string], r12
0x18002a1f4  lea     rcx, [rsp+200h+var_190]; this
0x18002a1f9  call    ??1SettingsDataActivity@AccountsControlAPITelemetry@@QEAA@XZ; AccountsControlAPITelemetry::SettingsDataActivity::~SettingsDataActivity(void)
0x18002a1fe  jmp     loc_18002A079
0x18002a203  lea     rcx, [rsp+200h+var_190]
0x18002a208  call    ?Stop@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002a20d  nop
0x18002a20e  lea     rcx, [rsp+200h+var_190]; this
0x18002a213  call    ??1SettingsDataActivity@AccountsControlAPITelemetry@@QEAA@XZ; AccountsControlAPITelemetry::SettingsDataActivity::~SettingsDataActivity(void)
0x18002a218  nop
0x18002a219  lea     rcx, [rsp+200h+var_1D0]
0x18002a21e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a223  nop
0x18002a224  lea     rcx, [rsp+200h+var_1E0]
0x18002a229  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a22e  mov     ebx, r12d
0x18002a231  lea     rcx, [rsp+200h+var_1B8]
0x18002a236  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a23b  mov     eax, ebx
0x18002a23d  mov     rcx, [rbp+100h+var_40]
0x18002a244  xor     rcx, rsp; StackCookie
0x18002a247  call    __security_check_cookie
0x18002a24c  add     rsp, 1D0h
0x18002a253  pop     r15
0x18002a255  pop     r14
0x18002a257  pop     r12
0x18002a259  pop     rdi
0x18002a25a  pop     rsi
0x18002a25b  pop     rbx
0x18002a25c  pop     rbp
0x18002a25d  retn
```
