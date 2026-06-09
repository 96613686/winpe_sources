# CAccountsSettingsPane::PopulateAccountData(_GUID const &,Windows::Internal::UI::ApplicationSettings::IAccountsControlData *,Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *,uint)

- ea: `0x180029308`
- end: `0x18002994e`
- name: `?PopulateAccountData@CAccountsSettingsPane@@QEAAJAEBU_GUID@@PEAUIAccountsControlData@ApplicationSettings@UI@Internal@Windows@@PEAUIAccountsSettingsPaneInternal@4567@I@Z`
- size: `1606`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, const struct _GUID *, struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024888`

## callees

- `0x180006eac`
- `0x180008634`
- `0x180008ea4`
- `0x18000e87c`
- `0x180011ffc`
- `0x180016e40`
- `0x18001b8d8`
- `0x180022968`
- `0x1800235a8`
- `0x180024324`
- `0x180027a74`
- `0x180029308`
- `0x18002c7e4`
- `0x18002d1d0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029870`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800295c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029870`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CAccountsSettingsPane::PopulateAccountData(
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
  int v17; // eax
  __int64 v18; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v20)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v21; // eax
  int IconStream; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Storage::Streams::IRandomAccessStream *, _QWORD); // rbx
  __int64 (__fastcall *v25)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *); // rbx
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, struct Windows::Security::Credentials::IWebAccount *, __int64, _QWORD); // rbx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, struct Windows::Security::Credentials::IWebAccount *, __int64, _QWORD); // rbx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, struct Windows::Security::Credentials::IWebAccount *, _QWORD, HSTRING); // rbx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  int *v42; // [rsp+20h] [rbp-E0h]
  int v43[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v46; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v48; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v49; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h]
  _QWORD v58[42]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v55 = 0;
  v9 = **a4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  v10 = v9(
          (struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *)a4,
          &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
          &v55);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v51 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 48LL))(v55, &v51);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = 591;
      goto LABEL_5;
    }
    if ( v51 )
    {
      v47 = 0;
      v13 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::ApplicationSettings::IAccountsControlData *, __int64 *))(*(_QWORD *)a3 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v14 = v13(a3, &v47);
      v11 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x254,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v14,
          (int)v42);
LABEL_9:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        goto LABEL_59;
      }
      v44 = 0;
      v15 = *((_QWORD *)this + 18);
      v57 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.UI.ApplicationSettings.WebAccountData",
        0x37u,
        0x36u);
      if ( v15 )
      {
        v16 = v57;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        v17 = Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>(
                v16,
                v15,
                &v44);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 602;
          goto LABEL_13;
        }
      }
      else
      {
        v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(
                v57,
                &v44);
        v11 = v17;
        if ( v17 < 0 )
        {
          v18 = 606;
LABEL_13:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
            (const char *)(unsigned int)v17,
            (int)v42);
LABEL_14:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
          goto LABEL_9;
        }
      }
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v58);
      v58[0] = &AccountsControlAPITelemetry::AccountDataActivity::`vftable';
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
        v58,
        a2);
      AccountsControlAPITelemetry::AccountDataActivity::StartActivity(
        (AccountsControlAPITelemetry::AccountDataActivity *)v58,
        v51);
      for ( i = 0; i < v51; ++i )
      {
        v46 = 0;
        v49 = 0;
        v20 = (*a4)[8];
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v21 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *), _QWORD, struct Windows::Security::Credentials::IWebAccount **, unsigned int *))v20)(
                a4,
                i,
                &v46,
                &v49);
        v11 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x269,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
            (const char *)(unsigned int)v21,
            (int)v42);
          goto LABEL_56;
        }
        *(_QWORD *)v43 = 0;
        v48 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        IconStream = GetIconStream(v46, &v48);
        v11 = IconStream;
        if ( IconStream < 0 )
        {
          v37 = 623;
LABEL_53:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v37,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
            (const char *)(unsigned int)IconStream,
            (int)v42);
          goto LABEL_54;
        }
        if ( v48 )
        {
          v23 = v44;
          v24 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Storage::Streams::IRandomAccessStream *, _QWORD))(*(_QWORD *)v44 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
          v42 = v43;
          IconStream = v24(v23, v46, v48, v49);
          v11 = IconStream;
          if ( IconStream < 0 )
          {
            v37 = 627;
            goto LABEL_53;
          }
        }
        if ( !*(_QWORD *)v43 )
        {
          v50 = 0;
          string = 0;
          v25 = (*a4)[9];
          WindowsDeleteString(0);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          v26 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal *, GUID *, __int64 *), _QWORD, __int64 *, HSTRING *))v25)(
                  a4,
                  i,
                  &v50,
                  &string);
          v11 = v26;
          if ( v26 < 0 )
          {
            v40 = 635;
LABEL_49:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v40,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
              (const char *)(unsigned int)v26,
              (int)v42);
            goto LABEL_50;
          }
          if ( v50 )
          {
            v52 = 0;
            v27 = BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(
                    v50,
                    &v52);
            v11 = v27;
            if ( v27 < 0 )
            {
              v39 = 640;
LABEL_45:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v39,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
                (const char *)(unsigned int)v27,
                (int)v42);
              goto LABEL_46;
            }
            if ( *((_QWORD *)this + 18) )
            {
              v54 = 0;
              v53 = 0;
              v28 = v52;
              v29 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 64LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
              v30 = v29(v28, 0, &v53);
              v11 = v30;
              if ( v30 < 0 )
              {
                v38 = 648;
LABEL_42:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v38,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
                  (const char *)(unsigned int)v30,
                  (int)v42);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
LABEL_46:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
LABEL_50:
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
LABEL_54:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
LABEL_56:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                AccountsControlAPITelemetry::AccountDataActivity::~AccountDataActivity((AccountsControlAPITelemetry::AccountDataActivity *)v58);
                goto LABEL_14;
              }
              v30 = BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(
                      v53,
                      &v54);
              v11 = v30;
              if ( v30 < 0 )
              {
                v38 = 649;
                goto LABEL_42;
              }
              v31 = v44;
              v32 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *, __int64, _QWORD))(*(_QWORD *)v44 + 64LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
              v42 = v43;
              v30 = v32(v31, v46, v54, v49);
              v11 = v30;
              if ( v30 < 0 )
              {
                v38 = 650;
                goto LABEL_42;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
            }
            else
            {
              v33 = v44;
              v34 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *, __int64, _QWORD))(*(_QWORD *)v44 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
              v42 = v43;
              v27 = v34(v33, v46, v52, v49);
              v11 = v27;
              if ( v27 < 0 )
              {
                v39 = 654;
                goto LABEL_45;
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          }
          else
          {
            v35 = v44;
            v36 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount *, _QWORD, HSTRING))(*(_QWORD *)v44 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
            LODWORD(v42) = v49;
            v26 = v36(v35, v46, a5, string);
            v11 = v26;
            if ( v26 < 0 )
            {
              v40 = 660;
              goto LABEL_49;
            }
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        }
        IconStream = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 104LL))(v47);
        v11 = IconStream;
        if ( IconStream < 0 )
        {
          v37 = 664;
          goto LABEL_53;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v43);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      }
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
      AccountsControlAPITelemetry::AccountDataActivity::~AccountDataActivity((AccountsControlAPITelemetry::AccountDataActivity *)v58);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    }
    v11 = 0;
    goto LABEL_59;
  }
  v12 = 588;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
    (const char *)(unsigned int)v10,
    (int)v42);
LABEL_59:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
  return v11;
}

```

## disassembly

```asm
0x180029308  push    rbp
0x18002930a  push    rbx
0x18002930b  push    rsi
0x18002930c  push    rdi
0x18002930d  push    r12
0x18002930f  push    r14
0x180029311  push    r15
0x180029313  lea     rbp, [rsp-130h]
0x18002931b  sub     rsp, 230h
0x180029322  mov     rax, cs:__security_cookie
0x180029329  xor     rax, rsp
0x18002932c  mov     [rbp+160h+var_40], rax
0x180029333  mov     r14, r9
0x180029336  mov     rdi, r8
0x180029339  mov     rsi, rdx
0x18002933c  mov     r15, rcx
0x18002933f  xor     r12d, r12d
0x180029342  mov     [rbp+160h+var_1C0], r12
0x180029346  mov     rax, [r9]
0x180029349  mov     rbx, [rax]
0x18002934c  lea     rcx, [rbp+160h+var_1C0]
0x180029350  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029355  lea     r8, [rbp+160h+var_1C0]
0x180029359  lea     rdx, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x180029360  mov     rcx, r14
0x180029363  mov     rax, rbx
0x180029366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002936b  mov     ebx, eax
0x18002936d  test    eax, eax
0x18002936f  jns     short loc_180029378
0x180029371  mov     edx, 24Ch
0x180029376  jmp     short loc_18002939B
0x180029378  mov     [rbp+160h+var_1E0], r12d
0x18002937c  mov     rcx, [rbp+160h+var_1C0]
0x180029380  mov     rax, [rcx]
0x180029383  lea     rdx, [rbp+160h+var_1E0]
0x180029387  mov     rax, [rax+30h]
0x18002938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029390  mov     ebx, eax
0x180029392  test    eax, eax
0x180029394  jns     short loc_1800293B6
0x180029396  mov     edx, 24Fh; void *
0x18002939b  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800293a2  mov     r9d, eax; char *
0x1800293a5  mov     rcx, [rbp+168h]; this
0x1800293ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293b1  jmp     loc_180029922
0x1800293b6  cmp     [rbp+160h+var_1E0], r12d
0x1800293ba  jz      loc_18002991F
0x1800293c0  mov     [rsp+260h+var_200], r12
0x1800293c5  mov     rax, [rdi]
0x1800293c8  mov     rbx, [rax+38h]
0x1800293cc  lea     rcx, [rsp+260h+var_200]
0x1800293d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800293d6  lea     rdx, [rsp+260h+var_200]
0x1800293db  mov     rcx, rdi
0x1800293de  mov     rax, rbx
0x1800293e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293e6  mov     ebx, eax
0x1800293e8  test    eax, eax
0x1800293ea  jns     short loc_180029417
0x1800293ec  mov     rcx, [rbp+168h]; this
0x1800293f3  mov     r9d, eax; char *
0x1800293f6  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800293fd  mov     edx, 254h; void *
0x180029402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029407  nop
0x180029408  lea     rcx, [rsp+260h+var_200]
0x18002940d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029412  jmp     loc_180029922
0x180029417  mov     [rsp+260h+var_218], r12
0x18002941c  mov     rdi, [r15+90h]
0x180029423  mov     [rbp+160h+var_1A0], r12
0x180029427  mov     r9d, 36h ; '6'; unsigned int
0x18002942d  lea     r8d, [r9+1]; unsigned int
0x180029431  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_WebAccountData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x180029438  lea     rcx, [rbp+160h+hstringHeader]; hstringHeader
0x18002943c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029441  test    rdi, rdi
0x180029444  jz      short loc_180029495
0x180029446  mov     rbx, [rbp+160h+var_1A0]
0x18002944a  lea     rcx, [rsp+260h+var_218]
0x18002944f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029454  lea     r8, [rsp+260h+var_218]
0x180029459  mov     rdx, rdi
0x18002945c  mov     rcx, rbx
0x18002945f  call    ??$GetActivationFactoryAsUser@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIWebAccountDataFactory@ApplicationSettings@UI@Internal@1@@Z; Windows::Foundation::GetActivationFactoryAsUser<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>(HSTRING__ *,Windows::System::IUser *,Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory * *)
0x180029464  mov     ebx, eax
0x180029466  test    eax, eax
0x180029468  jns     short loc_1800294B0
0x18002946a  mov     edx, 25Ah; void *
0x18002946f  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180029476  mov     r9d, eax; char *
0x180029479  mov     rcx, [rbp+168h]; this
0x180029480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029485  nop
0x180029486  lea     rcx, [rsp+260h+var_218]
0x18002948b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029490  jmp     loc_180029408
0x180029495  lea     rdx, [rsp+260h+var_218]
0x18002949a  mov     rcx, [rbp+160h+var_1A0]
0x18002949e  call    ??$GetActivationFactory@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>)
0x1800294a3  mov     ebx, eax
0x1800294a5  test    eax, eax
0x1800294a7  jns     short loc_1800294B0
0x1800294a9  mov     edx, 25Eh
0x1800294ae  jmp     short loc_18002946F
0x1800294b0  lea     rdx, aAccountdataact; "AccountDataActivity"
0x1800294b7  lea     rcx, [rbp+160h+var_190]; struct wil::details::IFailureCallback *
0x1800294bb  call    ??0?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800294c0  lea     rax, ??_7AccountDataActivity@AccountsControlAPITelemetry@@6B@; const AccountsControlAPITelemetry::AccountDataActivity::`vftable'
0x1800294c7  mov     [rbp+160h+var_190], rax
0x1800294cb  mov     rdx, rsi
0x1800294ce  lea     rcx, [rbp+160h+var_190]
0x1800294d2  call    ?SetRelatedActivityId@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1800294d7  mov     edx, [rbp+160h+var_1E0]; unsigned int
0x1800294da  lea     rcx, [rbp+160h+var_190]; this
0x1800294de  call    ?StartActivity@AccountDataActivity@AccountsControlAPITelemetry@@QEAAXI@Z; AccountsControlAPITelemetry::AccountDataActivity::StartActivity(uint)
0x1800294e3  mov     esi, r12d
0x1800294e6  cmp     esi, [rbp+160h+var_1E0]
0x1800294e9  jnb     loc_1800298F6
0x1800294ef  mov     [rsp+260h+var_208], r12
0x1800294f4  mov     [rsp+260h+var_1F0], r12d
0x1800294f9  mov     rax, [r14]
0x1800294fc  mov     rbx, [rax+40h]
0x180029500  lea     rcx, [rsp+260h+var_208]
0x180029505  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002950a  lea     r9, [rsp+260h+var_1F0]
0x18002950f  lea     r8, [rsp+260h+var_208]
0x180029514  mov     edx, esi
0x180029516  mov     rcx, r14
0x180029519  mov     rax, rbx
0x18002951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029521  mov     ebx, eax
0x180029523  test    eax, eax
0x180029525  js      loc_1800298C1
0x18002952b  mov     qword ptr [rsp+260h+var_220], r12
0x180029530  mov     [rsp+260h+var_1F8], r12
0x180029535  lea     rcx, [rsp+260h+var_1F8]
0x18002953a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002953f  lea     rdx, [rsp+260h+var_1F8]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180029544  mov     rcx, [rsp+260h+var_208]; struct Windows::Security::Credentials::IWebAccount *
0x180029549  call    ?GetIconStream@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAUIRandomAccessStream@Streams@Storage@4@@Z; GetIconStream(Windows::Security::Credentials::IWebAccount *,Windows::Storage::Streams::IRandomAccessStream * *)
0x18002954e  mov     ebx, eax
0x180029550  test    eax, eax
0x180029552  js      loc_18002988E
0x180029558  cmp     [rsp+260h+var_1F8], r12
0x18002955d  jz      short loc_1800295A3
0x18002955f  mov     rdi, [rsp+260h+var_218]
0x180029564  mov     rax, [rdi]
0x180029567  mov     rbx, [rax+40h]
0x18002956b  lea     rcx, [rsp+260h+var_220]
0x180029570  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029575  lea     rax, [rsp+260h+var_220]
0x18002957a  mov     qword ptr [rsp+260h+var_240], rax; int
0x18002957f  mov     r9d, [rsp+260h+var_1F0]
0x180029584  mov     r8, [rsp+260h+var_1F8]
0x180029589  mov     rdx, [rsp+260h+var_208]
0x18002958e  mov     rcx, rdi
0x180029591  mov     rax, rbx
0x180029594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029599  mov     ebx, eax
0x18002959b  test    eax, eax
0x18002959d  js      loc_1800297D1
0x1800295a3  mov     rdx, qword ptr [rsp+260h+var_220]
0x1800295a8  test    rdx, rdx
0x1800295ab  jnz     loc_18002978F
0x1800295b1  mov     [rsp+260h+var_1E8], r12
0x1800295b6  mov     [rsp+260h+string], r12
0x1800295bb  mov     rax, [r14]
0x1800295be  mov     rbx, [rax+48h]
0x1800295c2  xor     ecx, ecx; string
0x1800295c4  call    cs:__imp_WindowsDeleteString
0x1800295ca  mov     [rsp+260h+string], r12
0x1800295cf  lea     rcx, [rsp+260h+var_1E8]
0x1800295d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800295d9  lea     r9, [rsp+260h+string]
0x1800295de  lea     r8, [rsp+260h+var_1E8]
0x1800295e3  mov     edx, esi
0x1800295e5  mov     rcx, r14
0x1800295e8  mov     rax, rbx
0x1800295eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295f0  mov     ebx, eax
0x1800295f2  test    eax, eax
0x1800295f4  js      loc_18002984F
0x1800295fa  mov     rcx, [rsp+260h+var_1E8]
0x1800295ff  test    rcx, rcx
0x180029602  jz      loc_180029720
0x180029608  mov     [rbp+160h+var_1D8], r12
0x18002960c  lea     rdx, [rbp+160h+var_1D8]
0x180029610  call    ??$BlockOnCompletionAndGetResults@PEAVStorageFile@Storage@Windows@@UIStorageFile@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::StorageFile *,Windows::Storage::IStorageFile>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>,tagCOWAIT_FLAGS,void *)
0x180029615  mov     ebx, eax
0x180029617  test    eax, eax
0x180029619  js      loc_180029821
0x18002961f  cmp     [r15+90h], r12
0x180029626  jz      loc_1800296D2
0x18002962c  mov     [rbp+160h+var_1C8], r12
0x180029630  mov     [rbp+160h+var_1D0], r12
0x180029634  mov     rdi, [rbp+160h+var_1D8]
0x180029638  mov     rax, [rdi]
0x18002963b  mov     rbx, [rax+40h]
0x18002963f  lea     rcx, [rbp+160h+var_1D0]
0x180029643  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029648  lea     r8, [rbp+160h+var_1D0]
0x18002964c  xor     edx, edx
0x18002964e  mov     rcx, rdi
0x180029651  mov     rax, rbx
0x180029654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029659  mov     ebx, eax
0x18002965b  test    eax, eax
0x18002965d  js      loc_1800297E9
0x180029663  lea     rdx, [rbp+160h+var_1C8]
0x180029667  mov     rcx, [rbp+160h+var_1D0]
0x18002966b  call    ??$BlockOnCompletionAndGetResults@PEAUIRandomAccessStream@Streams@Storage@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>,tagCOWAIT_FLAGS,void *)
0x180029670  mov     ebx, eax
0x180029672  test    eax, eax
0x180029674  js      loc_1800297E2
0x18002967a  mov     rdi, [rsp+260h+var_218]
0x18002967f  mov     rax, [rdi]
0x180029682  mov     rbx, [rax+40h]
0x180029686  lea     rcx, [rsp+260h+var_220]
0x18002968b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029690  lea     rax, [rsp+260h+var_220]
0x180029695  mov     qword ptr [rsp+260h+var_240], rax
0x18002969a  mov     r9d, [rsp+260h+var_1F0]
0x18002969f  mov     r8, [rbp+160h+var_1C8]
0x1800296a3  mov     rdx, [rsp+260h+var_208]
0x1800296a8  mov     rcx, rdi
0x1800296ab  mov     rax, rbx
0x1800296ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296b3  mov     ebx, eax
0x1800296b5  test    eax, eax
0x1800296b7  js      loc_1800297DB
0x1800296bd  lea     rcx, [rbp+160h+var_1D0]
0x1800296c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800296c6  nop
0x1800296c7  lea     rcx, [rbp+160h+var_1C8]
0x1800296cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800296d0  jmp     short loc_180029715
0x1800296d2  mov     rdi, [rsp+260h+var_218]
0x1800296d7  mov     rax, [rdi]
0x1800296da  mov     rbx, [rax+30h]
0x1800296de  lea     rcx, [rsp+260h+var_220]
0x1800296e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800296e8  lea     rax, [rsp+260h+var_220]
0x1800296ed  mov     qword ptr [rsp+260h+var_240], rax
0x1800296f2  mov     r9d, [rsp+260h+var_1F0]
0x1800296f7  mov     r8, [rbp+160h+var_1D8]
0x1800296fb  mov     rdx, [rsp+260h+var_208]
0x180029700  mov     rcx, rdi
0x180029703  mov     rax, rbx
0x180029706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002970b  mov     ebx, eax
0x18002970d  test    eax, eax
0x18002970f  js      loc_18002981A
0x180029715  lea     rcx, [rbp+160h+var_1D8]
0x180029719  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002971e  jmp     short loc_180029770
0x180029720  mov     rdi, [rsp+260h+var_218]
0x180029725  mov     rax, [rdi]
0x180029728  mov     rbx, [rax+38h]
0x18002972c  lea     rcx, [rsp+260h+var_220]
0x180029731  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029736  mov     r8d, [rsp+260h+var_1F0]
0x18002973b  lea     rax, [rsp+260h+var_220]
0x180029740  mov     [rsp+260h+var_238], rax
0x180029745  mov     [rsp+260h+var_240], r8d
0x18002974a  mov     r9, [rsp+260h+string]
0x18002974f  mov     r8d, [rbp+160h+arg_20]
0x180029756  mov     rdx, [rsp+260h+var_208]
0x18002975b  mov     rcx, rdi
0x18002975e  mov     rax, rbx
0x180029761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029766  mov     ebx, eax
0x180029768  test    eax, eax
0x18002976a  js      loc_180029848
0x180029770  mov     rcx, [rsp+260h+string]; string
0x180029775  call    cs:__imp_WindowsDeleteString
0x18002977b  mov     [rsp+260h+string], r12
0x180029780  lea     rcx, [rsp+260h+var_1E8]
0x180029785  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002978a  mov     rdx, qword ptr [rsp+260h+var_220]
0x18002978f  mov     rcx, [rsp+260h+var_200]
0x180029794  mov     rax, [rcx]
0x180029797  mov     rax, [rax+68h]
0x18002979b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297a0  mov     ebx, eax
0x1800297a2  test    eax, eax
0x1800297a4  js      loc_180029887
0x1800297aa  lea     rcx, [rsp+260h+var_1F8]
0x1800297af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800297b4  nop
0x1800297b5  lea     rcx, [rsp+260h+var_220]
0x1800297ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800297bf  nop
0x1800297c0  lea     rcx, [rsp+260h+var_208]
0x1800297c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800297ca  inc     esi
0x1800297cc  jmp     loc_1800294E6
0x1800297d1  mov     edx, 273h
  ... truncated ...
```
