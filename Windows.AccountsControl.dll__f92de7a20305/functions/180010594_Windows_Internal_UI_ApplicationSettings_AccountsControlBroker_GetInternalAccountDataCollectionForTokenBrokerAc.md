# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetInternalAccountDataCollectionForTokenBrokerAccounts(uint,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Foundation::Collections::IVectorView<Windows::Internal::UI::ApplicationSettings::WebAccountData *> * *)

- ea: `0x180010594`
- end: `0x180010a7b`
- name: `?GetInternalAccountDataCollectionForTokenBrokerAccounts@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJIPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAPEAU?$IVectorView@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@785@@Z`
- size: `1255`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5b0`
- `0x1800137b0`

## callees

- `0x180006eac`
- `0x1800083a8`
- `0x180008634`
- `0x180008ac0`
- `0x180008ea4`
- `0x18000e87c`
- `0x180010594`
- `0x180011ffc`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001088c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001095b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001088c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001095b`

## string_xrefs

- `0x1800105f0`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010647`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010901`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010943`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001096e`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180010992`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800109b9`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800109d6`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800109fa`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetInternalAccountDataCollectionForTokenBrokerAccounts(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  unsigned int i; // esi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, __int64, __int64); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rdi
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, _QWORD, HSTRING); // rbx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  int *v36; // [rsp+20h] [rbp-89h]
  __int64 v37; // [rsp+40h] [rbp-69h] BYREF
  __int64 v38; // [rsp+48h] [rbp-61h] BYREF
  int v39[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v40; // [rsp+58h] [rbp-51h] BYREF
  __int64 v41; // [rsp+60h] [rbp-49h] BYREF
  HSTRING string; // [rsp+68h] [rbp-41h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-39h] BYREF
  __int64 v44; // [rsp+78h] [rbp-31h] BYREF
  __int64 v45; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-21h] BYREF
  __int64 v47; // [rsp+90h] [rbp-19h] BYREF
  __int64 v48; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v50; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *a4 = 0;
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::UI::ApplicationSettings::WebAccountData,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::WebAccountData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,0>>(
         v7,
         &v47);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v38 = 0;
    v50 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.UI.ApplicationSettings.WebAccountData",
      0x37u,
      0x36u);
    v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(
            v50,
            &v38);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v46 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a3 + 56LL))(a3, &v46);
      v9 = v10;
      if ( v10 >= 0 )
      {
        for ( i = 0; i < v46; ++i )
        {
          v37 = 0;
          v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          v14 = v13(a3, i, &v37);
          v9 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2BE,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
              (const char *)(unsigned int)v14,
              (int)v36);
            goto LABEL_42;
          }
          v41 = 0;
          v15 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                  &v37,
                  &v41);
          v9 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2C1,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
              (const char *)(unsigned int)v15,
              (int)v36);
            goto LABEL_40;
          }
          *(_QWORD *)v39 = 0;
          v40 = 0;
          v16 = v41;
          v17 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v41 + 64LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          if ( v17(v16, 64, &v40) >= 0 )
          {
            v45 = 0;
            if ( (int)BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(
                        v40,
                        &v45) >= 0 )
            {
              v48 = 0;
              v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL))(v45, &v48);
              v9 = v18;
              if ( v18 < 0 )
              {
                v33 = 715;
LABEL_29:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v33,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
                  (const char *)(unsigned int)v18,
                  (int)v36);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
LABEL_30:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
LABEL_40:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_42:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                goto LABEL_6;
              }
              if ( v48 )
              {
                v19 = v38;
                v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v38 + 64LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
                v36 = v39;
                v18 = v20(v19, v37, v45, 10);
                v9 = v18;
                if ( v18 < 0 )
                {
                  v33 = 719;
                  goto LABEL_29;
                }
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          }
          if ( !*(_QWORD *)v39 )
          {
            v43 = 0;
            v21 = v37;
            v22 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v37 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            v23 = v22(v21, &v43);
            v9 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D7,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
                (const char *)(unsigned int)v23,
                (int)v36);
              goto LABEL_37;
            }
            v44 = 0;
            v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
            v25 = **v43;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            v26 = v25(v24, &GUID_2b9c347e_56fb_4947_ab47_6982bb2cf28d, &v44);
            v9 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2DA,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
                (const char *)(unsigned int)v26,
                (int)v36);
              goto LABEL_35;
            }
            string = 0;
            v27 = v44;
            v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 48LL);
            WindowsDeleteString(0);
            string = 0;
            v29 = v28(v27, &string);
            v9 = v29;
            if ( v29 < 0 )
            {
              v34 = 733;
LABEL_33:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v34,
                (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
                (const char *)(unsigned int)v29,
                (int)v36);
              WindowsDeleteString(string);
              string = 0;
LABEL_35:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
LABEL_37:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              goto LABEL_30;
            }
            v30 = v38;
            v31 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, HSTRING))(*(_QWORD *)v38 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
            LODWORD(v36) = 10;
            v29 = v31(v30, v37, a2, string);
            v9 = v29;
            if ( v29 < 0 )
            {
              v34 = 735;
              goto LABEL_33;
            }
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          }
          v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 104LL))(v47);
          v9 = v32;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E2,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
              (const char *)(unsigned int)v32,
              (int)v36);
            goto LABEL_30;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v39);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        }
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v47 + 64LL))(v47, a4);
        v9 = v10;
        if ( v10 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
          v9 = 0;
          goto LABEL_46;
        }
        v11 = 741;
      }
      else
      {
        v11 = 697;
      }
    }
    else
    {
      v11 = 694;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v10,
      (int)v36);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B3,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v8,
      (int)v36);
  }
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  return v9;
}

```

## disassembly

```asm
0x180010594  mov     [rsp-8+arg_0], rbx
0x180010599  push    rbp
0x18001059a  push    rsi
0x18001059b  push    rdi
0x18001059c  push    r12
0x18001059e  push    r13
0x1800105a0  push    r14
0x1800105a2  push    r15
0x1800105a4  lea     rbp, [rsp-27h]
0x1800105a9  sub     rsp, 0D0h
0x1800105b0  mov     rax, cs:__security_cookie
0x1800105b7  xor     rax, rsp
0x1800105ba  mov     [rbp+57h+var_40], rax
0x1800105be  mov     r15, r9
0x1800105c1  mov     r14, r8
0x1800105c4  mov     r12d, edx
0x1800105c7  xor     r13d, r13d
0x1800105ca  mov     [r9], r13
0x1800105cd  mov     [rbp+57h+var_70], r13
0x1800105d1  lea     rcx, [rbp+57h+var_70]
0x1800105d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800105da  lea     rdx, [rbp+57h+var_70]
0x1800105de  call    ??$CreateExternalObjectVector@VWebAccountData@ApplicationSettings@UI@Internal@Windows@@V?$AgileVector@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVWebAccountData@ApplicationSettings@UI@Internal@Windows@@@4785@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::UI::ApplicationSettings::WebAccountData,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::WebAccountData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::WebAccountData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::WebAccountData *>,0> * *)
0x1800105e3  mov     ebx, eax
0x1800105e5  test    eax, eax
0x1800105e7  jns     short loc_180010606
0x1800105e9  mov     rcx, [rbp+5Fh]; this
0x1800105ed  mov     r9d, eax; char *
0x1800105f0  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800105f7  mov     edx, 2B3h; void *
0x1800105fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010601  jmp     loc_180010A49
0x180010606  mov     [rbp+57h+var_B8], r13
0x18001060a  mov     [rbp+57h+var_48], r13
0x18001060e  mov     r9d, 36h ; '6'; unsigned int
0x180010614  lea     r8d, [r9+1]; unsigned int
0x180010618  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_WebAccountData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x18001061f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180010623  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180010628  lea     rdx, [rbp+57h+var_B8]
0x18001062c  mov     rcx, [rbp+57h+var_48]
0x180010630  call    ??$GetActivationFactory@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAccountDataFactory@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IWebAccountDataFactory>>)
0x180010635  mov     ebx, eax
0x180010637  test    eax, eax
0x180010639  jns     short loc_180010662
0x18001063b  mov     edx, 2B6h; void *
0x180010640  mov     rcx, [rbp+5Fh]; this
0x180010644  mov     r9d, eax; char *
0x180010647  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001064e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010653  nop
0x180010654  lea     rcx, [rbp+57h+var_B8]
0x180010658  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001065d  jmp     loc_180010A49
0x180010662  mov     [rbp+57h+var_78], r13d
0x180010666  mov     rax, [r14]
0x180010669  lea     rdx, [rbp+57h+var_78]
0x18001066d  mov     rcx, r14
0x180010670  mov     rax, [rax+38h]
0x180010674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010679  mov     ebx, eax
0x18001067b  test    eax, eax
0x18001067d  jns     short loc_180010686
0x18001067f  mov     edx, 2B9h
0x180010684  jmp     short loc_180010640
0x180010686  mov     esi, r13d
0x180010689  cmp     esi, [rbp+57h+var_78]
0x18001068c  jnb     loc_180010A1A
0x180010692  mov     [rbp+57h+var_C0], r13
0x180010696  mov     rax, [r14]
0x180010699  mov     rbx, [rax+30h]
0x18001069d  lea     rcx, [rbp+57h+var_C0]
0x1800106a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800106a6  lea     r8, [rbp+57h+var_C0]
0x1800106aa  mov     edx, esi
0x1800106ac  mov     rcx, r14
0x1800106af  mov     rax, rbx
0x1800106b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106b7  mov     ebx, eax
0x1800106b9  test    eax, eax
0x1800106bb  js      loc_1800109F3
0x1800106c1  mov     [rbp+57h+var_A0], r13
0x1800106c5  lea     rdx, [rbp+57h+var_A0]
0x1800106c9  lea     rcx, [rbp+57h+var_C0]
0x1800106cd  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800106d2  mov     ebx, eax
0x1800106d4  test    eax, eax
0x1800106d6  js      loc_1800109CF
0x1800106dc  mov     qword ptr [rbp+57h+var_B0], r13
0x1800106e0  mov     [rbp+57h+var_A8], r13
0x1800106e4  mov     rdi, [rbp+57h+var_A0]
0x1800106e8  mov     rax, [rdi]
0x1800106eb  mov     rbx, [rax+40h]
0x1800106ef  lea     rcx, [rbp+57h+var_A8]
0x1800106f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800106f8  lea     r8, [rbp+57h+var_A8]
0x1800106fc  mov     edx, 40h ; '@'
0x180010701  mov     rcx, rdi
0x180010704  mov     rax, rbx
0x180010707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001070c  test    eax, eax
0x18001070e  js      loc_18001079A
0x180010714  mov     [rbp+57h+var_80], r13
0x180010718  lea     rdx, [rbp+57h+var_80]
0x18001071c  mov     rcx, [rbp+57h+var_A8]
0x180010720  call    ??$BlockOnCompletionAndGetResults@PEAUIRandomAccessStream@Streams@Storage@Windows@@U1234@@@YAJPEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>,tagCOWAIT_FLAGS,void *)
0x180010725  test    eax, eax
0x180010727  js      short loc_180010791
0x180010729  mov     [rbp+57h+var_68], r13
0x18001072d  mov     rcx, [rbp+57h+var_80]
0x180010731  mov     rax, [rcx]
0x180010734  lea     rdx, [rbp+57h+var_68]
0x180010738  mov     rax, [rax+30h]
0x18001073c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010741  mov     ebx, eax
0x180010743  test    eax, eax
0x180010745  js      loc_1800108FC
0x18001074b  cmp     [rbp+57h+var_68], r13
0x18001074f  jbe     short loc_180010791
0x180010751  mov     rdi, [rbp+57h+var_B8]
0x180010755  mov     rax, [rdi]
0x180010758  mov     rbx, [rax+40h]
0x18001075c  lea     rcx, [rbp+57h+var_B0]
0x180010760  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010765  lea     rax, [rbp+57h+var_B0]
0x180010769  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18001076e  mov     r9d, 0Ah
0x180010774  mov     r8, [rbp+57h+var_80]
0x180010778  mov     rdx, [rbp+57h+var_C0]
0x18001077c  mov     rcx, rdi
0x18001077f  mov     rax, rbx
0x180010782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010787  mov     ebx, eax
0x180010789  test    eax, eax
0x18001078b  js      loc_1800108F5
0x180010791  lea     rcx, [rbp+57h+var_80]
0x180010795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001079a  mov     rdx, qword ptr [rbp+57h+var_B0]
0x18001079e  test    rdx, rdx
0x1800107a1  jnz     loc_1800108AD
0x1800107a7  mov     [rbp+57h+var_90], r13
0x1800107ab  mov     rdi, [rbp+57h+var_C0]
0x1800107af  mov     rax, [rdi]
0x1800107b2  mov     rbx, [rax+30h]
0x1800107b6  lea     rcx, [rbp+57h+var_90]
0x1800107ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800107bf  lea     rdx, [rbp+57h+var_90]
0x1800107c3  mov     rcx, rdi
0x1800107c6  mov     rax, rbx
0x1800107c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ce  mov     ebx, eax
0x1800107d0  test    eax, eax
0x1800107d2  js      loc_18001098B
0x1800107d8  mov     [rbp+57h+var_88], r13
0x1800107dc  mov     rbx, [rbp+57h+var_90]
0x1800107e0  mov     rax, [rbx]
0x1800107e3  mov     rdi, [rax]
0x1800107e6  lea     rcx, [rbp+57h+var_88]
0x1800107ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800107ef  lea     r8, [rbp+57h+var_88]
0x1800107f3  lea     rdx, _GUID_2b9c347e_56fb_4947_ab47_6982bb2cf28d
0x1800107fa  mov     rcx, rbx
0x1800107fd  mov     rax, rdi
0x180010800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010805  mov     ebx, eax
0x180010807  test    eax, eax
0x180010809  js      loc_180010967
0x18001080f  mov     [rbp+57h+string], r13
0x180010813  mov     rdi, [rbp+57h+var_88]
0x180010817  mov     rax, [rdi]
0x18001081a  mov     rbx, [rax+30h]
0x18001081e  xor     ecx, ecx; string
0x180010820  call    cs:__imp_WindowsDeleteString
0x180010826  mov     [rbp+57h+string], r13
0x18001082a  lea     rdx, [rbp+57h+string]
0x18001082e  mov     rcx, rdi
0x180010831  mov     rax, rbx
0x180010834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010839  mov     ebx, eax
0x18001083b  test    eax, eax
0x18001083d  js      loc_18001093E
0x180010843  mov     rdi, [rbp+57h+var_B8]
0x180010847  mov     rax, [rdi]
0x18001084a  mov     rbx, [rax+38h]
0x18001084e  lea     rcx, [rbp+57h+var_B0]
0x180010852  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010857  lea     rax, [rbp+57h+var_B0]
0x18001085b  mov     [rsp+100h+var_D8], rax
0x180010860  mov     [rsp+100h+var_E0], 0Ah; int
0x180010868  mov     r9, [rbp+57h+string]
0x18001086c  mov     r8d, r12d
0x18001086f  mov     rdx, [rbp+57h+var_C0]
0x180010873  mov     rcx, rdi
0x180010876  mov     rax, rbx
0x180010879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001087e  mov     ebx, eax
0x180010880  test    eax, eax
0x180010882  js      loc_180010937
0x180010888  mov     rcx, [rbp+57h+string]; string
0x18001088c  call    cs:__imp_WindowsDeleteString
0x180010892  mov     [rbp+57h+string], r13
0x180010896  lea     rcx, [rbp+57h+var_88]
0x18001089a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001089f  nop
0x1800108a0  lea     rcx, [rbp+57h+var_90]
0x1800108a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108a9  mov     rdx, qword ptr [rbp+57h+var_B0]
0x1800108ad  mov     rcx, [rbp+57h+var_70]
0x1800108b1  mov     rax, [rcx]
0x1800108b4  mov     rax, [rax+68h]
0x1800108b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bd  mov     ebx, eax
0x1800108bf  test    eax, eax
0x1800108c1  js      loc_1800109B2
0x1800108c7  lea     rcx, [rbp+57h+var_A8]
0x1800108cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108d0  nop
0x1800108d1  lea     rcx, [rbp+57h+var_B0]
0x1800108d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108da  nop
0x1800108db  lea     rcx, [rbp+57h+var_A0]
0x1800108df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108e4  nop
0x1800108e5  lea     rcx, [rbp+57h+var_C0]
0x1800108e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800108ee  inc     esi
0x1800108f0  jmp     loc_180010689
0x1800108f5  mov     edx, 2CFh
0x1800108fa  jmp     short loc_180010901
0x1800108fc  mov     edx, 2CBh; void *
0x180010901  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180010908  mov     r9d, eax; char *
0x18001090b  mov     rcx, [rbp+5Fh]; this
0x18001090f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010914  nop
0x180010915  lea     rcx, [rbp+57h+var_80]
0x180010919  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001091e  nop
0x18001091f  lea     rcx, [rbp+57h+var_A8]
0x180010923  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010928  nop
0x180010929  lea     rcx, [rbp+57h+var_B0]
0x18001092d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010932  jmp     loc_1800109E8
0x180010937  mov     edx, 2DFh
0x18001093c  jmp     short loc_180010943
0x18001093e  mov     edx, 2DDh; void *
0x180010943  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001094a  mov     r9d, eax; char *
0x18001094d  mov     rcx, [rbp+5Fh]; this
0x180010951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010956  nop
0x180010957  mov     rcx, [rbp+57h+string]; string
0x18001095b  call    cs:__imp_WindowsDeleteString
0x180010961  mov     [rbp+57h+string], r13
0x180010965  jmp     short loc_180010980
0x180010967  mov     rcx, [rbp+5Fh]; this
0x18001096b  mov     r9d, eax; char *
0x18001096e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180010975  mov     edx, 2DAh; void *
0x18001097a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001097f  nop
0x180010980  lea     rcx, [rbp+57h+var_88]
0x180010984  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010989  jmp     short loc_1800109A4
0x18001098b  mov     rcx, [rbp+5Fh]; this
0x18001098f  mov     r9d, eax; char *
0x180010992  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180010999  mov     edx, 2D7h; void *
0x18001099e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109a3  nop
0x1800109a4  lea     rcx, [rbp+57h+var_90]
0x1800109a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800109ad  jmp     loc_18001091F
0x1800109b2  mov     rcx, [rbp+5Fh]; this
0x1800109b6  mov     r9d, eax; char *
0x1800109b9  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800109c0  mov     edx, 2E2h; void *
0x1800109c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109ca  jmp     loc_18001091F
0x1800109cf  mov     rcx, [rbp+5Fh]; this
0x1800109d3  mov     r9d, eax; char *
0x1800109d6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800109dd  mov     edx, 2C1h; void *
0x1800109e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109e7  nop
0x1800109e8  lea     rcx, [rbp+57h+var_A0]
0x1800109ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800109f1  jmp     short loc_180010A0C
0x1800109f3  mov     rcx, [rbp+5Fh]; this
0x1800109f7  mov     r9d, eax; char *
0x1800109fa  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180010a01  mov     edx, 2BEh; void *
0x180010a06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a0b  nop
0x180010a0c  lea     rcx, [rbp+57h+var_C0]
0x180010a10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180010a15  jmp     loc_180010654
0x180010a1a  mov     rcx, [rbp+57h+var_70]
0x180010a1e  mov     rax, [rcx]
  ... truncated ...
```
