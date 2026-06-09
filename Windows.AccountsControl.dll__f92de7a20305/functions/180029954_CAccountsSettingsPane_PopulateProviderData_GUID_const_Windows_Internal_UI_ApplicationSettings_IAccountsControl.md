# CAccountsSettingsPane::PopulateProviderData(_GUID const &,Windows::Internal::UI::ApplicationSettings::IAccountsControlData *,Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *,uint)

- ea: `0x180029954`
- end: `0x180029ef0`
- name: `?PopulateProviderData@CAccountsSettingsPane@@QEAAJAEBU_GUID@@PEAUIAccountsControlData@ApplicationSettings@UI@Internal@Windows@@PEAUIAccountsSettingsPaneInternal@4567@I@Z`
- size: `1436`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, const struct _GUID *, struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024888`

## callees

- `0x180006eac`
- `0x180008634`
- `0x18000e87c`
- `0x180011ffc`
- `0x180016e40`
- `0x18001b8d8`
- `0x180022b8c`
- `0x1800235a8`
- `0x180024498`
- `0x180029954`
- `0x18002c9f4`
- `0x18002d1d0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029b02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029b02`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CAccountsSettingsPane::PopulateProviderData(
        CAccountsSettingsPane *this,
        const struct _GUID *a2,
        struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *a3,
        __int64 (__fastcall ***a4)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *),
        unsigned int a5)
{
  __int64 (__fastcall *v9)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 (__fastcall *v13)(struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rbx
  int ActivationFactory; // eax
  __int64 v18; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v20)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, _QWORD, _QWORD); // rbx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, __int64, _QWORD, _QWORD); // rbx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, _QWORD, _QWORD); // rbx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v37; // [rsp+20h] [rbp-E0h]
  HSTRING *p_string; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-68h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  _QWORD v52[42]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v49 = 0;
  v9 = **a4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v10 = v9(
          (struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)a4,
          &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
          &v49);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v45 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 32LL))(v49, &v45);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 497;
      goto LABEL_5;
    }
    if ( v45 )
    {
      v42 = 0;
      v13 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, __int64 *))(*(_QWORD *)a3 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v14 = v13(a3, &v42);
      v11 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F6,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v14,
          v37);
LABEL_9:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        goto LABEL_48;
      }
      v40 = 0;
      v15 = *((_QWORD *)this + 18);
      v51 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.UI.ApplicationSettings.WebAccountProviderData",
        0x3Fu,
        0x3Eu);
      v16 = v51;
      if ( v15 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        ActivationFactory = Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::IWebAccountProviderDataFactory>(
                              v16,
                              v15,
                              &v40);
        v11 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v18 = 508;
          goto LABEL_13;
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        ActivationFactory = RoGetActivationFactory(v16, &GUID_6805c2b9_f466_4de3_91d4_c7b059435b45, &v40);
        v11 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v18 = 512;
LABEL_13:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v37);
LABEL_14:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          goto LABEL_9;
        }
      }
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v52);
      v52[0] = &AccountsControlAPITelemetry::ProviderDataActivity::`vftable';
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v52,
        a2);
      AccountsControlAPITelemetry::ProviderDataActivity::StartActivity(
        (AccountsControlAPITelemetry::ProviderDataActivity *)v52,
        v45);
      for ( i = 0; i < v45; ++i )
      {
        v43 = 0;
        v44 = 0;
        string = 0;
        v20 = (*a4)[7];
        WindowsDeleteString(0);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        p_string = &string;
        v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *), _QWORD, __int64 *, __int64 *))v20)(
                a4,
                i,
                &v43,
                &v44);
        v11 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
            (const char *)(unsigned int)v21,
            (int)&string);
          goto LABEL_45;
        }
        v41 = 0;
        if ( v44 )
        {
          v46 = 0;
          v22 = BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(
                  v44,
                  &v46);
          v11 = v22;
          if ( v22 < 0 )
          {
            v34 = 530;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v34,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
              (const char *)(unsigned int)v22,
              (int)p_string);
            goto LABEL_39;
          }
          if ( *((_QWORD *)this + 18) )
          {
            v48 = 0;
            v47 = 0;
            v23 = v46;
            v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            v25 = v24(v23, 0, &v47);
            v11 = v25;
            if ( v25 < 0 )
            {
              v33 = 538;
LABEL_35:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v33,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
                (const char *)(unsigned int)v25,
                (int)p_string);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_39:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              goto LABEL_40;
            }
            v25 = BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(
                    v47,
                    &v48);
            v11 = v25;
            if ( v25 < 0 )
            {
              v33 = 539;
              goto LABEL_35;
            }
            v26 = v40;
            v27 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v40 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
            LODWORD(p_string) = v48;
            v25 = v27(v26, v43, 0, 0);
            v11 = v25;
            if ( v25 < 0 )
            {
              v33 = 540;
              goto LABEL_35;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          }
          else
          {
            v28 = v40;
            v29 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v40 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
            LODWORD(p_string) = v46;
            v22 = v29(v28, v43, 0, 0);
            v11 = v22;
            if ( v22 < 0 )
            {
              v34 = 544;
              goto LABEL_38;
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        }
        else
        {
          v30 = v40;
          v31 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v40 + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          LODWORD(p_string) = a5;
          v32 = v31(v30, v43, 0, 0);
          v11 = v32;
          if ( v32 < 0 )
          {
            v35 = 550;
LABEL_43:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v35,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
              (const char *)(unsigned int)v32,
              (int)p_string);
LABEL_40:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_45:
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            AccountsControlAPITelemetry::ProviderDataActivity::~ProviderDataActivity((AccountsControlAPITelemetry::ProviderDataActivity *)v52);
            goto LABEL_14;
          }
        }
        v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 104LL))(v42, v41);
        v11 = v32;
        if ( v32 < 0 )
        {
          v35 = 553;
          goto LABEL_43;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      }
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
      AccountsControlAPITelemetry::ProviderDataActivity::~ProviderDataActivity((AccountsControlAPITelemetry::ProviderDataActivity *)v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    }
    v11 = 0;
    goto LABEL_48;
  }
  v12 = 494;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
    (const char *)(unsigned int)v10,
    v37);
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  return v11;
}

```

## disassembly

```asm
0x180029954  mov     [rsp-8+arg_8], rbx
0x180029959  push    rbp
0x18002995a  push    rsi
0x18002995b  push    rdi
0x18002995c  push    r12
0x18002995e  push    r13
0x180029960  push    r14
0x180029962  push    r15
0x180029964  lea     rbp, [rsp-120h]
0x18002996c  sub     rsp, 220h
0x180029973  mov     rax, cs:__security_cookie
0x18002997a  xor     rax, rsp
0x18002997d  mov     [rbp+150h+var_40], rax
0x180029984  mov     r12, r9
0x180029987  mov     rdi, r8
0x18002998a  mov     rsi, rdx
0x18002998d  mov     r14, rcx
0x180029990  xor     r13d, r13d
0x180029993  mov     [rbp+150h+var_1C0], r13
0x180029997  mov     rax, [r9]
0x18002999a  mov     rbx, [rax]
0x18002999d  lea     rcx, [rbp+150h+var_1C0]
0x1800299a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800299a6  lea     r8, [rbp+150h+var_1C0]
0x1800299aa  lea     rdx, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x1800299b1  mov     rcx, r12
0x1800299b4  mov     rax, rbx
0x1800299b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299bc  mov     ebx, eax
0x1800299be  test    eax, eax
0x1800299c0  jns     short loc_1800299C9
0x1800299c2  mov     edx, 1EEh
0x1800299c7  jmp     short loc_1800299EE
0x1800299c9  mov     [rsp+250h+var_1E0], r13d
0x1800299ce  mov     rcx, [rbp+150h+var_1C0]
0x1800299d2  mov     rax, [rcx]
0x1800299d5  lea     rdx, [rsp+250h+var_1E0]
0x1800299da  mov     rax, [rax+20h]
0x1800299de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299e3  mov     ebx, eax
0x1800299e5  test    eax, eax
0x1800299e7  jns     short loc_180029A09
0x1800299e9  mov     edx, 1F1h; void *
0x1800299ee  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800299f5  mov     r9d, eax; char *
0x1800299f8  mov     rcx, [rbp+158h]; this
0x1800299ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a04  jmp     loc_180029EBB
0x180029a09  cmp     [rsp+250h+var_1E0], r13d
0x180029a0e  jz      loc_180029EB8
0x180029a14  mov     [rsp+250h+var_1F8], r13
0x180029a19  mov     rax, [rdi]
0x180029a1c  mov     rbx, [rax+30h]
0x180029a20  lea     rcx, [rsp+250h+var_1F8]
0x180029a25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029a2a  lea     rdx, [rsp+250h+var_1F8]
0x180029a2f  mov     rcx, rdi
0x180029a32  mov     rax, rbx
0x180029a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a3a  mov     ebx, eax
0x180029a3c  test    eax, eax
0x180029a3e  jns     short loc_180029A6B
0x180029a40  mov     rcx, [rbp+158h]; this
0x180029a47  mov     r9d, eax; char *
0x180029a4a  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029a51  mov     edx, 1F6h; void *
0x180029a56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a5b  nop
0x180029a5c  lea     rcx, [rsp+250h+var_1F8]
0x180029a61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029a66  jmp     loc_180029EBB
0x180029a6b  mov     [rsp+250h+var_208], r13
0x180029a70  mov     rdi, [r14+90h]
0x180029a77  mov     [rbp+150h+var_1A0], r13
0x180029a7b  mov     r9d, 3Eh ; '>'; unsigned int
0x180029a81  lea     r8d, [r9+1]; unsigned int
0x180029a85  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_WebAccountProviderData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x180029a8c  lea     rcx, [rbp+150h+hstringHeader]; hstringHeader
0x180029a90  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029a95  mov     rbx, [rbp+150h+var_1A0]
0x180029a99  test    rdi, rdi
0x180029a9c  jz      short loc_180029AE9
0x180029a9e  lea     rcx, [rsp+250h+var_208]
0x180029aa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029aa8  lea     r8, [rsp+250h+var_208]
0x180029aad  mov     rdx, rdi
0x180029ab0  mov     rcx, rbx
0x180029ab3  call    ??$GetActivationFactoryAsUser@UIWebAccountProviderDataFactory@ApplicationSettings@UI@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIWebAccountProviderDataFactory@ApplicationSettings@UI@Internal@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::IWebAccountProviderDataFactory>(HSTRING__ *,Windows::System::IUser *,Windows::Internal::UI::ApplicationSettings::IWebAccountProviderDataFactory * *)
0x180029ab8  mov     ebx, eax
0x180029aba  test    eax, eax
0x180029abc  jns     short loc_180029B15
0x180029abe  mov     edx, 1FCh; void *
0x180029ac3  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029aca  mov     r9d, eax; char *
0x180029acd  mov     rcx, [rbp+158h]; this
0x180029ad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029ad9  nop
0x180029ada  lea     rcx, [rsp+250h+var_208]
0x180029adf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029ae4  jmp     loc_180029A5C
0x180029ae9  lea     rcx, [rsp+250h+var_208]
0x180029aee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029af3  lea     r8, [rsp+250h+var_208]
0x180029af8  lea     rdx, _GUID_6805c2b9_f466_4de3_91d4_c7b059435b45
0x180029aff  mov     rcx, rbx
0x180029b02  call    cs:__imp_RoGetActivationFactory
0x180029b08  mov     ebx, eax
0x180029b0a  test    eax, eax
0x180029b0c  jns     short loc_180029B15
0x180029b0e  mov     edx, 200h
0x180029b13  jmp     short loc_180029AC3
0x180029b15  lea     rdx, aProviderdataac; "ProviderDataActivity"
0x180029b1c  lea     rcx, [rbp+150h+var_190]; struct wil::details::IFailureCallback *
0x180029b20  call    ??0?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180029b25  lea     rax, ??_7ProviderDataActivity@AccountsControlAPITelemetry@@6B@; const AccountsControlAPITelemetry::ProviderDataActivity::`vftable'
0x180029b2c  mov     [rbp+150h+var_190], rax
0x180029b30  mov     rdx, rsi
0x180029b33  lea     rcx, [rbp+150h+var_190]
0x180029b37  call    ?SetRelatedActivityId@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x180029b3c  mov     edx, [rsp+250h+var_1E0]; unsigned int
0x180029b40  lea     rcx, [rbp+150h+var_190]; this
0x180029b44  call    ?StartActivity@ProviderDataActivity@AccountsControlAPITelemetry@@QEAAXI@Z; AccountsControlAPITelemetry::ProviderDataActivity::StartActivity(uint)
0x180029b49  mov     esi, r13d
0x180029b4c  mov     r15d, [rbp+150h+arg_20]
0x180029b53  cmp     esi, [rsp+250h+var_1E0]
0x180029b57  jnb     loc_180029E8F
0x180029b5d  mov     [rsp+250h+var_1F0], r13
0x180029b62  mov     [rsp+250h+var_1E8], r13
0x180029b67  mov     [rsp+250h+string], r13
0x180029b6c  mov     rax, [r12]
0x180029b70  mov     rbx, [rax+38h]
0x180029b74  xor     ecx, ecx; string
0x180029b76  call    cs:__imp_WindowsDeleteString
0x180029b7c  mov     [rsp+250h+string], r13
0x180029b81  lea     rcx, [rsp+250h+var_1E8]
0x180029b86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029b8b  lea     rcx, [rsp+250h+var_1F0]
0x180029b90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029b95  lea     rax, [rsp+250h+string]
0x180029b9a  mov     qword ptr [rsp+250h+var_230], rax; int
0x180029b9f  lea     r9, [rsp+250h+var_1E8]
0x180029ba4  lea     r8, [rsp+250h+var_1F0]
0x180029ba9  mov     edx, esi
0x180029bab  mov     rcx, r12
0x180029bae  mov     rax, rbx
0x180029bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb6  mov     ebx, eax
0x180029bb8  test    eax, eax
0x180029bba  js      loc_180029E3F
0x180029bc0  mov     [rsp+250h+var_200], r13
0x180029bc5  mov     rcx, [rsp+250h+var_1E8]
0x180029bca  test    rcx, rcx
0x180029bcd  jz      loc_180029CFC
0x180029bd3  mov     [rsp+250h+var_1D8], r13
0x180029bd8  lea     rdx, [rsp+250h+var_1D8]
0x180029bdd  call    ??$BlockOnCompletionAndGetResults@PEAVStorageFile@Storage@Windows@@UIStorageFile@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>,tagCOWAIT_FLAGS,void *)
0x180029be2  mov     ebx, eax
0x180029be4  test    eax, eax
0x180029be6  js      loc_180029DE8
0x180029bec  cmp     [r14+90h], r13
0x180029bf3  jz      loc_180029CA6
0x180029bf9  mov     [rbp+150h+var_1C8], r13
0x180029bfd  mov     [rbp+150h+var_1D0], r13
0x180029c01  mov     rdi, [rsp+250h+var_1D8]
0x180029c06  mov     rax, [rdi]
0x180029c09  mov     rbx, [rax+40h]
0x180029c0d  lea     rcx, [rbp+150h+var_1D0]
0x180029c11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029c16  lea     r8, [rbp+150h+var_1D0]
0x180029c1a  xor     edx, edx
0x180029c1c  mov     rcx, rdi
0x180029c1f  mov     rax, rbx
0x180029c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c27  mov     ebx, eax
0x180029c29  test    eax, eax
0x180029c2b  js      loc_180029DB0
0x180029c31  lea     rdx, [rbp+150h+var_1C8]
0x180029c35  mov     rcx, [rbp+150h+var_1D0]
0x180029c39  call    ??$BlockOnCompletionAndGetResults@PEAUIRandomAccessStream@Streams@Storage@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>,tagCOWAIT_FLAGS,void *)
0x180029c3e  mov     ebx, eax
0x180029c40  test    eax, eax
0x180029c42  js      loc_180029DA9
0x180029c48  mov     rdi, [rsp+250h+var_208]
0x180029c4d  mov     rax, [rdi]
0x180029c50  mov     rbx, [rax+40h]
0x180029c54  lea     rcx, [rsp+250h+var_200]
0x180029c59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029c5e  mov     r8, [rbp+150h+var_1C8]
0x180029c62  lea     rax, [rsp+250h+var_200]
0x180029c67  mov     [rsp+250h+var_228], rax
0x180029c6c  mov     qword ptr [rsp+250h+var_230], r8
0x180029c71  xor     r9d, r9d
0x180029c74  xor     r8d, r8d
0x180029c77  mov     rdx, [rsp+250h+var_1F0]
0x180029c7c  mov     rcx, rdi
0x180029c7f  mov     rax, rbx
0x180029c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c87  mov     ebx, eax
0x180029c89  test    eax, eax
0x180029c8b  js      loc_180029DA2
0x180029c91  lea     rcx, [rbp+150h+var_1D0]
0x180029c95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029c9a  nop
0x180029c9b  lea     rcx, [rbp+150h+var_1C8]
0x180029c9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029ca4  jmp     short loc_180029CF0
0x180029ca6  mov     rdi, [rsp+250h+var_208]
0x180029cab  mov     rax, [rdi]
0x180029cae  mov     rbx, [rax+30h]
0x180029cb2  lea     rcx, [rsp+250h+var_200]
0x180029cb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029cbc  mov     r8, [rsp+250h+var_1D8]
0x180029cc1  lea     rax, [rsp+250h+var_200]
0x180029cc6  mov     [rsp+250h+var_228], rax
0x180029ccb  mov     qword ptr [rsp+250h+var_230], r8
0x180029cd0  xor     r9d, r9d
0x180029cd3  xor     r8d, r8d
0x180029cd6  mov     rdx, [rsp+250h+var_1F0]
0x180029cdb  mov     rcx, rdi
0x180029cde  mov     rax, rbx
0x180029ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ce6  mov     ebx, eax
0x180029ce8  test    eax, eax
0x180029cea  js      loc_180029DE1
0x180029cf0  lea     rcx, [rsp+250h+var_1D8]
0x180029cf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029cfa  jmp     short loc_180029D4B
0x180029cfc  mov     rdi, [rsp+250h+var_208]
0x180029d01  mov     rax, [rdi]
0x180029d04  mov     rbx, [rax+38h]
0x180029d08  lea     rcx, [rsp+250h+var_200]
0x180029d0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029d12  mov     r8, [rsp+250h+string]
0x180029d17  lea     rax, [rsp+250h+var_200]
0x180029d1c  mov     [rsp+250h+var_220], rax
0x180029d21  mov     [rsp+250h+var_228], r8
0x180029d26  mov     [rsp+250h+var_230], r15d; int
0x180029d2b  xor     r9d, r9d
0x180029d2e  xor     r8d, r8d
0x180029d31  mov     rdx, [rsp+250h+var_1F0]
0x180029d36  mov     rcx, rdi
0x180029d39  mov     rax, rbx
0x180029d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d41  mov     ebx, eax
0x180029d43  test    eax, eax
0x180029d45  js      loc_180029E22
0x180029d4b  mov     rcx, [rsp+250h+var_1F8]
0x180029d50  mov     rax, [rcx]
0x180029d53  mov     rdx, [rsp+250h+var_200]
0x180029d58  mov     rax, [rax+68h]
0x180029d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d61  mov     ebx, eax
0x180029d63  test    eax, eax
0x180029d65  js      loc_180029E1B
0x180029d6b  lea     rcx, [rsp+250h+var_200]
0x180029d70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029d75  nop
0x180029d76  mov     rcx, [rsp+250h+string]; string
0x180029d7b  call    cs:__imp_WindowsDeleteString
0x180029d81  mov     [rsp+250h+string], r13
0x180029d86  lea     rcx, [rsp+250h+var_1E8]
0x180029d8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029d90  nop
0x180029d91  lea     rcx, [rsp+250h+var_1F0]
0x180029d96  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029d9b  inc     esi
0x180029d9d  jmp     loc_180029B53
0x180029da2  mov     edx, 21Ch
0x180029da7  jmp     short loc_180029DB5
0x180029da9  mov     edx, 21Bh
0x180029dae  jmp     short loc_180029DB5
0x180029db0  mov     edx, 21Ah; void *
0x180029db5  mov     rcx, [rbp+158h]; this
0x180029dbc  mov     r9d, eax; char *
0x180029dbf  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029dcb  nop
0x180029dcc  lea     rcx, [rbp+150h+var_1D0]
0x180029dd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029dd5  nop
0x180029dd6  lea     rcx, [rbp+150h+var_1C8]
0x180029dda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029ddf  jmp     short loc_180029E04
0x180029de1  mov     edx, 220h
0x180029de6  jmp     short loc_180029DED
0x180029de8  mov     edx, 212h; void *
0x180029ded  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029df4  mov     r9d, eax; char *
0x180029df7  mov     rcx, [rbp+158h]; this
0x180029dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e03  nop
0x180029e04  lea     rcx, [rsp+250h+var_1D8]
0x180029e09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029e0e  nop
0x180029e0f  lea     rcx, [rsp+250h+var_200]
0x180029e14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029e19  jmp     short loc_180029E5B
0x180029e1b  mov     edx, 229h
0x180029e20  jmp     short loc_180029E27
0x180029e22  mov     edx, 226h; void *
  ... truncated ...
```
