# CAccountsSettingsPane::DispatchEvent(Windows::Foundation::Collections::IPropertySet *,Windows::Internal::UI::ApplicationSettings::IViewOperation *,_GUID const &)

- ea: `0x18002694c`
- end: `0x180026dc1`
- name: `?DispatchEvent@CAccountsSettingsPane@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAUIViewOperation@ApplicationSettings@UI@Internal@5@AEBU_GUID@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800247ac`

## callees

- `0x180006eac`
- `0x180008fb8`
- `0x180009058`
- `0x18000b6a4`
- `0x18000e5f0`
- `0x18000e87c`
- `0x180011ffc`
- `0x180021960`
- `0x18002694c`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002698d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026cd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002698d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026cd9`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180026a5f`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180026a5f`

## string_xrefs

- `0x180026bb3`: `TokenBrokerAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CAccountsSettingsPane::DispatchEvent(
        CAccountsSettingsPane *this,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        __int64 (__fastcall ***a3)(struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, GUID *, __int64 *),
        const struct _GUID *a4)
{
  unsigned int v7; // edi
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  HSTRING v14; // r8
  int v15; // eax
  HSTRING v16; // r8
  __int64 (__fastcall *v17)(struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, GUID *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  HSTRING v24; // r8
  HSTRING v25; // r8
  int v26; // [rsp+20h] [rbp-59h]
  __int64 v27; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v28; // [rsp+38h] [rbp-41h]
  __int64 v29; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h]
  __int64 v31; // [rsp+50h] [rbp-29h] BYREF
  __int64 v32; // [rsp+58h] [rbp-21h] BYREF
  int v33; // [rsp+60h] [rbp-19h]
  _BYTE v34[8]; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v36; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(
    (Windows::Internal::ShellHelpers::PropertySetHelper *)v34,
    a2);
  WindowsDeleteString(0);
  string = 0;
  v36 = 0;
  v7 = 8;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ItemType", 9u, 8u);
  v8 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
         (Windows::Internal::ShellHelpers::PropertySetHelper *)v34,
         v36);
  v9 = v8;
  if ( v8 == -2147483637 )
    goto LABEL_40;
  if ( v8 >= 0 )
  {
    v28 = 0;
    v36 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Index", 6u, 5u);
    v8 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(
           (Windows::Internal::ShellHelpers::PropertySetHelper *)v34,
           v36);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 1854;
      goto LABEL_4;
    }
    v27 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v11 = CoreQueryWindowService(
            *((_QWORD *)this + 16),
            &IID_IImmersiveAccountsSettings,
            &GUID_82cfe484_6292_4c11_8260_b36817031c9b,
            &v27);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x743,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v11,
        v26);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      goto LABEL_41;
    }
    v29 = 0;
    v12 = Microsoft::WRL::ComPtr<IImmersiveAccountsSettings>::As<Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal>(
            &v27,
            &v29);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 1862;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v12,
        v26);
LABEL_13:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      goto LABEL_9;
    }
    v36 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SavedAccount", 0xDu, 0xCu);
    v15 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal((Microsoft::WRL::Wrappers::Details *)string, v36, v14);
    v36 = 0;
    if ( !v15 )
    {
      v33 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Action", 7u, 6u);
      v12 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)v34,
              v36);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 1868;
        goto LABEL_12;
      }
      if ( v33 )
      {
        if ( v33 == 1 )
        {
          v7 = 2;
        }
        else if ( v33 == 2 )
        {
          v7 = 4;
        }
        else if ( v33 != 3 )
        {
          if ( v33 == 4 )
            v7 = 16;
          else
            v7 = 0;
        }
      }
      else
      {
        v7 = 1;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const struct _GUID *))(*(_QWORD *)v27 + 96LL))(
              v27,
              v28,
              v7,
              a4);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 1872;
        goto LABEL_12;
      }
      goto LABEL_39;
    }
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TokenBrokerAccount", 0x13u, 0x12u);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)string,
                         v36,
                         v16) )
    {
      v36 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Provider", 9u, 8u);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)string,
                           v36,
                           v24) )
      {
        v36 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Setting", 8u, 7u);
        if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                              (Microsoft::WRL::Wrappers::Details *)string,
                              v36,
                              v25) )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *))(*(_QWORD *)v27 + 104LL))(
                  v27,
                  v28,
                  a4);
          v9 = v12;
          if ( v12 < 0 )
          {
            v13 = 1889;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *))(*(_QWORD *)v27 + 88LL))(v27, v28, a4);
        v9 = v12;
        if ( v12 < 0 )
        {
          v13 = 1885;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v31 = 0;
      v17 = **a3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v18 = v17(
              (struct Windows::Internal::UI::ApplicationSettings::IViewOperation *)a3,
              &GUID_c88d8b7a_283f_4129_9c88_df59be5930d0,
              &v31);
      v9 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x755,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v18,
          v26);
LABEL_32:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        goto LABEL_13;
      }
      v32 = 0;
      v19 = v31;
      v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      v21 = v20(v19, &v32);
      v9 = v21;
      if ( v21 < 0 )
      {
        v22 = 1880;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v21,
          v26);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        goto LABEL_32;
      }
      *(struct _GUID *)&hstringHeader.Reserved.Reserved1 = *a4;
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, HSTRING_HEADER *))(*(_QWORD *)v29 + 88LL))(
              v29,
              v28,
              v32,
              &hstringHeader);
      v9 = v21;
      if ( v21 < 0 )
      {
        v22 = 1881;
        goto LABEL_35;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    }
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
LABEL_40:
    v9 = 0;
    goto LABEL_41;
  }
  v10 = 1851;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
    (const char *)(unsigned int)v8,
    v26);
LABEL_41:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34);
  return v9;
}

```

## disassembly

```asm
0x18002694c  push    rbp
0x18002694e  push    rbx
0x18002694f  push    rsi
0x180026950  push    rdi
0x180026951  push    r12
0x180026953  push    r14
0x180026955  push    r15
0x180026957  lea     rbp, [rsp-27h]
0x18002695c  sub     rsp, 0A0h
0x180026963  mov     rax, cs:__security_cookie
0x18002696a  xor     rax, rsp
0x18002696d  mov     [rbp+57h+var_40], rax
0x180026971  mov     rsi, r9
0x180026974  mov     r14, r8
0x180026977  mov     r15, rcx
0x18002697a  lea     rcx, [rbp+57h+var_68]; this
0x18002697e  call    ??0PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA@PEAUIPropertySet@Collections@Foundation@3@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::PropertySetHelper(Windows::Foundation::Collections::IPropertySet *)
0x180026983  nop
0x180026984  xor     r12d, r12d
0x180026987  mov     [rbp+57h+string], r12
0x18002698b  xor     ecx, ecx; string
0x18002698d  call    cs:__imp_WindowsDeleteString
0x180026993  mov     [rbp+57h+string], r12
0x180026997  mov     [rbp+57h+var_48], r12
0x18002699b  lea     edi, [r12+8]
0x1800269a0  mov     r9d, edi; unsigned int
0x1800269a3  lea     r8d, [r12+9]; unsigned int
0x1800269a8  lea     rdx, aItemtype; "ItemType"
0x1800269af  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800269b3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800269b8  nop
0x1800269b9  lea     r9, [rbp+57h+string]
0x1800269bd  mov     rdx, [rbp+57h+var_48]; HSTRING
0x1800269c1  lea     rcx, [rbp+57h+var_68]; this
0x1800269c5  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x1800269ca  mov     ebx, eax
0x1800269cc  cmp     eax, 8000000Bh
0x1800269d1  jz      loc_180026CD2
0x1800269d7  test    eax, eax
0x1800269d9  jns     short loc_1800269F8
0x1800269db  mov     edx, 73Bh; void *
0x1800269e0  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800269e7  mov     r9d, eax; char *
0x1800269ea  mov     rcx, [rbp+5Fh]; this
0x1800269ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800269f3  jmp     loc_180026CD5
0x1800269f8  mov     [rbp+57h+var_98], r12d
0x1800269fc  mov     [rbp+57h+var_48], r12
0x180026a00  mov     r9d, 5; unsigned int
0x180026a06  lea     r8d, [r9+1]; unsigned int
0x180026a0a  lea     rdx, aIndex; "Index"
0x180026a11  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180026a15  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026a1a  nop
0x180026a1b  lea     r9, [rbp+57h+var_98]
0x180026a1f  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026a23  lea     rcx, [rbp+57h+var_68]; this
0x180026a27  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x180026a2c  mov     ebx, eax
0x180026a2e  test    eax, eax
0x180026a30  jns     short loc_180026A39
0x180026a32  mov     edx, 73Eh
0x180026a37  jmp     short loc_1800269E0
0x180026a39  mov     [rbp+57h+var_A0], r12
0x180026a3d  lea     rcx, [rbp+57h+var_A0]
0x180026a41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026a46  lea     r9, [rbp+57h+var_A0]
0x180026a4a  lea     r8, _GUID_82cfe484_6292_4c11_8260_b36817031c9b
0x180026a51  lea     rdx, IID_IImmersiveAccountsSettings
0x180026a58  mov     rcx, [r15+80h]
0x180026a5f  call    cs:__imp_CoreQueryWindowService
0x180026a65  mov     ebx, eax
0x180026a67  test    eax, eax
0x180026a69  jns     short loc_180026A92
0x180026a6b  mov     rcx, [rbp+5Fh]; this
0x180026a6f  mov     r9d, eax; char *
0x180026a72  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180026a79  mov     edx, 743h; void *
0x180026a7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a83  nop
0x180026a84  lea     rcx, [rbp+57h+var_A0]
0x180026a88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026a8d  jmp     loc_180026CD5
0x180026a92  mov     [rbp+57h+var_90], r12
0x180026a96  lea     rdx, [rbp+57h+var_90]
0x180026a9a  lea     rcx, [rbp+57h+var_A0]
0x180026a9e  call    ??$As@UIAccountsSettingsPaneInternal@ApplicationSettings@UI@Internal@Windows@@@?$ComPtr@UIImmersiveAccountsSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAccountsSettingsPaneInternal@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IImmersiveAccountsSettings>::As<Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsSettingsPaneInternal>>)
0x180026aa3  mov     ebx, eax
0x180026aa5  test    eax, eax
0x180026aa7  jns     short loc_180026ACD
0x180026aa9  mov     edx, 746h; void *
0x180026aae  mov     rcx, [rbp+5Fh]; this
0x180026ab2  mov     r9d, eax; char *
0x180026ab5  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180026abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ac1  nop
0x180026ac2  lea     rcx, [rbp+57h+var_90]
0x180026ac6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026acb  jmp     short loc_180026A84
0x180026acd  mov     [rbp+57h+var_48], r12
0x180026ad1  mov     r9d, 0Ch; unsigned int
0x180026ad7  lea     r8d, [r9+1]; unsigned int
0x180026adb  lea     rdx, aSavedaccount; "SavedAccount"
0x180026ae2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180026ae6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026aeb  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026aef  mov     rcx, [rbp+57h+string]; this
0x180026af3  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180026af8  mov     [rbp+57h+var_48], r12
0x180026afc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180026b00  test    eax, eax
0x180026b02  jnz     loc_180026BA9
0x180026b08  mov     [rbp+57h+var_70], r12d
0x180026b0c  lea     r9d, [rax+6]; unsigned int
0x180026b10  lea     r8d, [rax+7]; unsigned int
0x180026b14  lea     rdx, aAction; "Action"
0x180026b1b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026b20  nop
0x180026b21  lea     r9, [rbp+57h+var_70]
0x180026b25  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026b29  lea     rcx, [rbp+57h+var_68]; this
0x180026b2d  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x180026b32  mov     ebx, eax
0x180026b34  test    eax, eax
0x180026b36  jns     short loc_180026B42
0x180026b38  mov     edx, 74Ch
0x180026b3d  jmp     loc_180026AAE
0x180026b42  mov     ecx, [rbp+57h+var_70]
0x180026b45  test    ecx, ecx
0x180026b47  jz      short loc_180026B77
0x180026b49  sub     ecx, 1
0x180026b4c  jz      short loc_180026B70
0x180026b4e  sub     ecx, 1
0x180026b51  jz      short loc_180026B69
0x180026b53  sub     ecx, 1
0x180026b56  jz      short loc_180026B7C
0x180026b58  cmp     ecx, 1
0x180026b5b  jz      short loc_180026B62
0x180026b5d  mov     edi, r12d
0x180026b60  jmp     short loc_180026B7C
0x180026b62  mov     edi, 10h
0x180026b67  jmp     short loc_180026B7C
0x180026b69  mov     edi, 4
0x180026b6e  jmp     short loc_180026B7C
0x180026b70  mov     edi, 2
0x180026b75  jmp     short loc_180026B7C
0x180026b77  mov     edi, 1
0x180026b7c  mov     rcx, [rbp+57h+var_A0]
0x180026b80  mov     rax, [rcx]
0x180026b83  mov     r9, rsi
0x180026b86  mov     r8d, edi
0x180026b89  mov     edx, [rbp+57h+var_98]
0x180026b8c  mov     rax, [rax+60h]
0x180026b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b95  mov     ebx, eax
0x180026b97  test    eax, eax
0x180026b99  jns     loc_180026CBF
0x180026b9f  mov     edx, 750h
0x180026ba4  jmp     loc_180026AAE
0x180026ba9  mov     r9d, 12h; unsigned int
0x180026baf  lea     r8d, [r9+1]; unsigned int
0x180026bb3  lea     rdx, aTokenbrokeracc; "TokenBrokerAccount"
0x180026bba  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026bbf  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026bc3  mov     rcx, [rbp+57h+string]; this
0x180026bc7  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180026bcc  test    eax, eax
0x180026bce  jnz     loc_180026D0C
0x180026bd4  mov     [rbp+57h+var_80], r12
0x180026bd8  mov     rax, [r14]
0x180026bdb  mov     rbx, [rax]
0x180026bde  lea     rcx, [rbp+57h+var_80]
0x180026be2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026be7  lea     r8, [rbp+57h+var_80]
0x180026beb  lea     rdx, _GUID_c88d8b7a_283f_4129_9c88_df59be5930d0
0x180026bf2  mov     rcx, r14
0x180026bf5  mov     rax, rbx
0x180026bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bfd  mov     ebx, eax
0x180026bff  test    eax, eax
0x180026c01  jns     short loc_180026C2A
0x180026c03  mov     rcx, [rbp+5Fh]; this
0x180026c07  mov     r9d, eax; char *
0x180026c0a  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180026c11  mov     edx, 755h; void *
0x180026c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c1b  nop
0x180026c1c  lea     rcx, [rbp+57h+var_80]
0x180026c20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c25  jmp     loc_180026AC2
0x180026c2a  mov     [rbp+57h+var_78], r12
0x180026c2e  mov     rdi, [rbp+57h+var_80]
0x180026c32  mov     rax, [rdi]
0x180026c35  mov     rbx, [rax+40h]
0x180026c39  lea     rcx, [rbp+57h+var_78]
0x180026c3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c42  lea     rdx, [rbp+57h+var_78]
0x180026c46  mov     rcx, rdi
0x180026c49  mov     rax, rbx
0x180026c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c51  mov     ebx, eax
0x180026c53  test    eax, eax
0x180026c55  jns     short loc_180026C7B
0x180026c57  mov     edx, 758h; void *
0x180026c5c  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180026c63  mov     r9d, eax; char *
0x180026c66  mov     rcx, [rbp+5Fh]; this
0x180026c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026c6f  nop
0x180026c70  lea     rcx, [rbp+57h+var_78]
0x180026c74  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c79  jmp     short loc_180026C1C
0x180026c7b  mov     rcx, [rbp+57h+var_90]
0x180026c7f  movups  xmm0, xmmword ptr [rsi]
0x180026c82  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x180026c87  mov     rax, [rcx]
0x180026c8a  lea     r9, [rbp+57h+hstringHeader]
0x180026c8e  mov     r8, [rbp+57h+var_78]
0x180026c92  mov     edx, [rbp+57h+var_98]
0x180026c95  mov     rax, [rax+58h]
0x180026c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c9e  mov     ebx, eax
0x180026ca0  test    eax, eax
0x180026ca2  jns     short loc_180026CAB
0x180026ca4  mov     edx, 759h
0x180026ca9  jmp     short loc_180026C5C
0x180026cab  lea     rcx, [rbp+57h+var_78]
0x180026caf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cb4  nop
0x180026cb5  lea     rcx, [rbp+57h+var_80]
0x180026cb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cbe  nop
0x180026cbf  lea     rcx, [rbp+57h+var_90]
0x180026cc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cc8  nop
0x180026cc9  lea     rcx, [rbp+57h+var_A0]
0x180026ccd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cd2  mov     ebx, r12d
0x180026cd5  mov     rcx, [rbp+57h+string]; string
0x180026cd9  call    cs:__imp_WindowsDeleteString
0x180026cdf  mov     [rbp+57h+string], r12
0x180026ce3  lea     rcx, [rbp+57h+var_68]
0x180026ce7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cec  mov     eax, ebx
0x180026cee  mov     rcx, [rbp+57h+var_40]
0x180026cf2  xor     rcx, rsp; StackCookie
0x180026cf5  call    __security_check_cookie
0x180026cfa  add     rsp, 0A0h
0x180026d01  pop     r15
0x180026d03  pop     r14
0x180026d05  pop     r12
0x180026d07  pop     rdi
0x180026d08  pop     rsi
0x180026d09  pop     rbx
0x180026d0a  pop     rbp
0x180026d0b  retn
0x180026d0c  mov     [rbp+57h+var_48], r12
0x180026d10  mov     r9d, edi; unsigned int
0x180026d13  mov     r8d, 9; unsigned int
0x180026d19  lea     rdx, aProvider; "Provider"
0x180026d20  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180026d24  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026d29  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026d2d  mov     rcx, [rbp+57h+string]; this
0x180026d31  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180026d36  test    eax, eax
0x180026d38  jnz     short loc_180026D64
0x180026d3a  mov     rcx, [rbp+57h+var_A0]
0x180026d3e  mov     rax, [rcx]
0x180026d41  mov     r8, rsi
0x180026d44  mov     edx, [rbp+57h+var_98]
0x180026d47  mov     rax, [rax+58h]
0x180026d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d50  mov     ebx, eax
0x180026d52  test    eax, eax
0x180026d54  jns     loc_180026CBF
0x180026d5a  mov     edx, 75Dh
0x180026d5f  jmp     loc_180026AAE
0x180026d64  mov     [rbp+57h+var_48], r12
0x180026d68  mov     r9d, 7; unsigned int
0x180026d6e  mov     r8d, edi; unsigned int
0x180026d71  lea     rdx, aSetting; "Setting"
0x180026d78  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180026d7c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026d81  mov     rdx, [rbp+57h+var_48]; HSTRING
0x180026d85  mov     rcx, [rbp+57h+string]; this
0x180026d89  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180026d8e  test    eax, eax
0x180026d90  jnz     loc_180026CBF
0x180026d96  mov     rcx, [rbp+57h+var_A0]
0x180026d9a  mov     rax, [rcx]
0x180026d9d  mov     r8, rsi
0x180026da0  mov     edx, [rbp+57h+var_98]
0x180026da3  mov     rax, [rax+68h]
0x180026da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dac  mov     ebx, eax
0x180026dae  test    eax, eax
0x180026db0  jns     loc_180026CBF
0x180026db6  mov     edx, 761h
0x180026dbb  jmp     loc_180026AAE
  ... truncated ...
```
