# SystemSettings::Personalization::ColorSetting_ColorMode::GetPossibleValues(IInspectable * *)

- ea: `0x18012f3e0`
- end: `0x18012f804`
- name: `?GetPossibleValues@ColorSetting_ColorMode@Personalization@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::ColorSetting_ColorMode *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001098c`
- `0x180011bb0`
- `0x180019a20`
- `0x18001f3c8`
- `0x180020170`
- `0x180021398`
- `0x1800251ec`
- `0x18002b5f0`
- `0x18003cdf0`
- `0x18003d280`
- `0x18004d1ac`
- `0x18012f3e0`
- `0x18019dbc8`
- `0x18019ddf0`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f47f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f5df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f47f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f518`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f557`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f5df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012f7ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::Personalization::ColorSetting_ColorMode::GetPossibleValues(
        SystemSettings::Personalization::ColorSetting_ColorMode *this,
        struct IInspectable **a2)
{
  HSTRING v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  HSTRING *v7; // r8
  int ResourceStringById; // eax
  __int64 v9; // rdx
  HSTRING v10; // rbx
  int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rdx
  HSTRING *v14; // r8
  __int64 v15; // r9
  __int64 (__fastcall *v16)(SystemSettings::Personalization::ColorSetting_ColorMode *, HSTRING *); // rdi
  const unsigned __int16 *v17; // r8
  __int64 v18; // rdx
  bool v19; // di
  HSTRING *v20; // r8
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  HSTRING *v24; // r8
  __int64 v25; // r9
  int v27[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  struct IInspectable *v29; // [rsp+68h] [rbp+38h] BYREF
  HSTRING v30; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  *(_QWORD *)v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(v27);
  *(_QWORD *)v27 = 0;
  v4 = (HSTRING)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  string = v4;
  v5 = 0;
  if ( v4 )
  {
    v5 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v4);
    string = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(&string);
  if ( v5 )
  {
    v6 = 0;
    *(_QWORD *)v27 = v5;
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v6 >= 0 )
  {
    v29 = 0;
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Light",
                           &string,
                           v7);
    v6 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v9 = 480;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v27[0]);
LABEL_11:
      WindowsDeleteString(string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      goto LABEL_45;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v10 = string;
    v11 = SystemSettings::DataModel::PropValueHelper::CreateString(string, &v29);
    if ( v11 < 0 )
    {
      v13 = 481;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)v11,
        v27[0]);
LABEL_15:
      WindowsDeleteString(v10);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v6 = v11;
      goto LABEL_45;
    }
    LOBYTE(v12) = 1;
    v11 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
            *(_QWORD *)v27,
            0,
            v29,
            v12);
    if ( v11 < 0 )
    {
      v13 = 482;
      goto LABEL_14;
    }
    WindowsDeleteString(v10);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Dark",
                           &string,
                           v14);
    v6 = ResourceStringById;
    if ( ResourceStringById < 0 )
    {
      v9 = 484;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v10 = string;
    v11 = SystemSettings::DataModel::PropValueHelper::CreateString(string, &v29);
    if ( v11 < 0 )
    {
      v13 = 485;
      goto LABEL_14;
    }
    LOBYTE(v15) = 1;
    v11 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
            *(_QWORD *)v27,
            0,
            v29,
            v15);
    if ( v11 < 0 )
    {
      v13 = 486;
      goto LABEL_14;
    }
    v30 = 0;
    v16 = *(__int64 (__fastcall **)(SystemSettings::Personalization::ColorSetting_ColorMode *, HSTRING *))(*(_QWORD *)this + 48LL);
    WindowsDeleteString(0);
    v30 = 0;
    v11 = v16(this, &v30);
    if ( v11 < 0 )
    {
      v18 = 489;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
        (const char *)(unsigned int)v11,
        v27[0]);
      WindowsDeleteString(v30);
      v30 = 0;
      goto LABEL_15;
    }
    if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)v30, (HSTRING)&stru_1802DFE90, v17) )
    {
      v19 = SystemSettings::Personalization::ColorSingleton::get_AppsUseLightMode() != 0;
      if ( v19 != (SystemSettings::Personalization::ColorSingleton::get_SystemUsesLightMode() != 0) )
      {
        WindowsDeleteString(v10);
        string = 0;
        v21 = SystemSettings::DataModel::GetResourceStringById(
                (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Custom",
                &string,
                v20);
        v6 = v21;
        if ( v21 < 0 )
        {
          v22 = 499;
LABEL_31:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
            (const char *)(unsigned int)v21,
            v27[0]);
          WindowsDeleteString(v30);
          v30 = 0;
          goto LABEL_11;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        v10 = string;
        v11 = SystemSettings::DataModel::PropValueHelper::CreateString(string, &v29);
        if ( v11 < 0 )
        {
          v18 = 500;
          goto LABEL_26;
        }
        LOBYTE(v23) = 1;
        v11 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
                *(_QWORD *)v27,
                0,
                v29,
                v23);
        if ( v11 < 0 )
        {
          v18 = 501;
          goto LABEL_26;
        }
      }
    }
    else
    {
      WindowsDeleteString(v10);
      string = 0;
      v21 = SystemSettings::DataModel::GetResourceStringById(
              (SystemSettings::DataModel *)L"SystemSettings_Personalize_ColorMode_Custom",
              &string,
              v24);
      v6 = v21;
      if ( v21 < 0 )
      {
        v22 = 506;
        goto LABEL_31;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v10 = string;
      v11 = SystemSettings::DataModel::PropValueHelper::CreateString(string, &v29);
      if ( v11 < 0 )
      {
        v18 = 507;
        goto LABEL_26;
      }
      LOBYTE(v25) = 1;
      v11 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
              *(_QWORD *)v27,
              0,
              v29,
              v25);
      if ( v11 < 0 )
      {
        v18 = 508;
        goto LABEL_26;
      }
    }
    v11 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
            *(_QWORD *)v27,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a2);
    if ( v11 >= 0 )
    {
      WindowsDeleteString(v30);
      v30 = 0;
      WindowsDeleteString(v10);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      v6 = 0;
      goto LABEL_45;
    }
    v18 = 511;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1DC,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\color.cpp",
    (const char *)(unsigned int)v6,
    v27[0]);
LABEL_45:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(v27);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18012f3e0  mov     [rsp-28h+arg_0], rbx
0x18012f3e5  push    rbp
0x18012f3e6  push    rsi
0x18012f3e7  push    rdi
0x18012f3e8  push    r14
0x18012f3ea  push    r15
0x18012f3ec  mov     rbp, rsp
0x18012f3ef  sub     rsp, 30h
0x18012f3f3  mov     r14, rdx
0x18012f3f6  mov     rsi, rcx
0x18012f3f9  xor     r15d, r15d
0x18012f3fc  mov     [rdx], r15
0x18012f3ff  mov     qword ptr [rbp+var_10], r15
0x18012f403  lea     rcx, [rbp+var_10]
0x18012f407  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18012f40c  mov     qword ptr [rbp+var_10], r15
0x18012f410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18012f417  mov     ecx, 0B8h; unsigned __int64
0x18012f41c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18012f421  mov     [rbp+string], rax
0x18012f425  mov     edi, r15d
0x18012f428  test    rax, rax
0x18012f42b  jz      short loc_18012F43C
0x18012f42d  mov     rcx, rax
0x18012f430  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x18012f435  mov     rdi, rax
0x18012f438  mov     [rbp+string], r15
0x18012f43c  lea     rcx, [rbp+string]
0x18012f440  call    ??1?$MakeAllocator@VCBrailleTableLanguageOutputSetting@Accessibility@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(void)
0x18012f445  test    rdi, rdi
0x18012f448  jnz     short loc_18012F451
0x18012f44a  mov     ebx, 8007000Eh
0x18012f44f  jmp     short loc_18012F458
0x18012f451  mov     ebx, r15d
0x18012f454  mov     qword ptr [rbp+var_10], rdi
0x18012f458  test    ebx, ebx
0x18012f45a  jns     short loc_18012F479
0x18012f45c  mov     rcx, [rbp+28h]; this
0x18012f460  mov     r9d, ebx; char *
0x18012f463  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012f46a  mov     edx, 1DCh; void *
0x18012f46f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f474  jmp     loc_18012F7E7
0x18012f479  mov     [rbp+arg_8], r15
0x18012f47d  xor     ecx, ecx; string
0x18012f47f  call    cs:__imp_WindowsDeleteString
0x18012f486  nop     dword ptr [rax+rax+00h]
0x18012f48b  mov     [rbp+string], r15
0x18012f48f  lea     rdx, [rbp+string]; HSTRING *
0x18012f493  lea     rcx, aSystemsettings_68; "SystemSettings_Personalize_ColorMode_Li"...
0x18012f49a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012f49f  mov     ebx, eax
0x18012f4a1  test    eax, eax
0x18012f4a3  jns     short loc_18012F4DD
0x18012f4a5  mov     edx, 1E0h; void *
0x18012f4aa  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012f4b1  mov     r9d, eax; char *
0x18012f4b4  mov     rcx, [rbp+28h]; this
0x18012f4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f4bd  nop
0x18012f4be  mov     rcx, [rbp+string]; string
0x18012f4c2  call    cs:__imp_WindowsDeleteString
0x18012f4c9  nop     dword ptr [rax+rax+00h]
0x18012f4ce  nop
0x18012f4cf  lea     rcx, [rbp+arg_8]
0x18012f4d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f4d8  jmp     loc_18012F7E7
0x18012f4dd  lea     rcx, [rbp+arg_8]
0x18012f4e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f4e6  lea     rdx, [rbp+arg_8]; struct IInspectable **
0x18012f4ea  mov     rbx, [rbp+string]
0x18012f4ee  mov     rcx, rbx; HSTRING
0x18012f4f1  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012f4f6  mov     edi, eax
0x18012f4f8  test    eax, eax
0x18012f4fa  jns     short loc_18012F535
0x18012f4fc  mov     edx, 1E1h; void *
0x18012f501  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012f508  mov     r9d, edi; char *
0x18012f50b  mov     rcx, [rbp+28h]; this
0x18012f50f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f514  nop
0x18012f515  mov     rcx, rbx; string
0x18012f518  call    cs:__imp_WindowsDeleteString
0x18012f51f  nop     dword ptr [rax+rax+00h]
0x18012f524  nop
0x18012f525  lea     rcx, [rbp+arg_8]
0x18012f529  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f52e  mov     ebx, edi
0x18012f530  jmp     loc_18012F7E7
0x18012f535  mov     r9b, 1
0x18012f538  mov     r8, [rbp+arg_8]
0x18012f53c  xor     edx, edx
0x18012f53e  mov     rcx, qword ptr [rbp+var_10]
0x18012f542  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x18012f547  mov     edi, eax
0x18012f549  test    eax, eax
0x18012f54b  jns     short loc_18012F554
0x18012f54d  mov     edx, 1E2h
0x18012f552  jmp     short loc_18012F501
0x18012f554  mov     rcx, rbx; string
0x18012f557  call    cs:__imp_WindowsDeleteString
0x18012f55e  nop     dword ptr [rax+rax+00h]
0x18012f563  mov     [rbp+string], r15
0x18012f567  lea     rdx, [rbp+string]; HSTRING *
0x18012f56b  lea     rcx, aSystemsettings_111; "SystemSettings_Personalize_ColorMode_Da"...
0x18012f572  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012f577  mov     ebx, eax
0x18012f579  test    eax, eax
0x18012f57b  jns     short loc_18012F587
0x18012f57d  mov     edx, 1E4h
0x18012f582  jmp     loc_18012F4AA
0x18012f587  lea     rcx, [rbp+arg_8]
0x18012f58b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f590  lea     rdx, [rbp+arg_8]; struct IInspectable **
0x18012f594  mov     rbx, [rbp+string]
0x18012f598  mov     rcx, rbx; HSTRING
0x18012f59b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012f5a0  mov     edi, eax
0x18012f5a2  test    eax, eax
0x18012f5a4  jns     short loc_18012F5B0
0x18012f5a6  mov     edx, 1E5h
0x18012f5ab  jmp     loc_18012F501
0x18012f5b0  mov     r9b, 1
0x18012f5b3  mov     r8, [rbp+arg_8]
0x18012f5b7  xor     edx, edx
0x18012f5b9  mov     rcx, qword ptr [rbp+var_10]
0x18012f5bd  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x18012f5c2  mov     edi, eax
0x18012f5c4  test    eax, eax
0x18012f5c6  jns     short loc_18012F5D2
0x18012f5c8  mov     edx, 1E6h
0x18012f5cd  jmp     loc_18012F501
0x18012f5d2  mov     [rbp+arg_10], r15
0x18012f5d6  mov     rax, [rsi]
0x18012f5d9  mov     rdi, [rax+30h]
0x18012f5dd  xor     ecx, ecx; string
0x18012f5df  call    cs:__imp_WindowsDeleteString
0x18012f5e6  nop     dword ptr [rax+rax+00h]
0x18012f5eb  mov     [rbp+arg_10], r15
0x18012f5ef  lea     rdx, [rbp+arg_10]
0x18012f5f3  mov     rcx, rsi
0x18012f5f6  mov     rax, rdi
0x18012f5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f5fe  mov     edi, eax
0x18012f600  test    eax, eax
0x18012f602  jns     short loc_18012F636
0x18012f604  mov     edx, 1E9h; void *
0x18012f609  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012f610  mov     r9d, edi; char *
0x18012f613  mov     rcx, [rbp+28h]; this
0x18012f617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f61c  nop
0x18012f61d  mov     rcx, [rbp+arg_10]; string
0x18012f621  call    cs:__imp_WindowsDeleteString
0x18012f628  nop     dword ptr [rax+rax+00h]
0x18012f62d  mov     [rbp+arg_10], r15
0x18012f631  jmp     loc_18012F515
0x18012f636  lea     rdx, stru_1802DFE90; HSTRING
0x18012f63d  mov     rcx, [rbp+arg_10]; this
0x18012f641  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18012f646  test    al, al
0x18012f648  jz      loc_18012F716
0x18012f64e  call    ?get_AppsUseLightMode@ColorSingleton@Personalization@SystemSettings@@SAEXZ; SystemSettings::Personalization::ColorSingleton::get_AppsUseLightMode(void)
0x18012f653  test    al, al
0x18012f655  setnz   dil
0x18012f659  call    ?get_SystemUsesLightMode@ColorSingleton@Personalization@SystemSettings@@SAEXZ; SystemSettings::Personalization::ColorSingleton::get_SystemUsesLightMode(void)
0x18012f65e  test    al, al
0x18012f660  setnz   al
0x18012f663  cmp     dil, al
0x18012f666  jz      loc_18012F794
0x18012f66c  mov     rcx, rbx; string
0x18012f66f  call    cs:__imp_WindowsDeleteString
0x18012f676  nop     dword ptr [rax+rax+00h]
0x18012f67b  mov     [rbp+string], r15
0x18012f67f  lea     rdx, [rbp+string]; HSTRING *
0x18012f683  lea     rcx, aSystemsettings_385; "SystemSettings_Personalize_ColorMode_Cu"...
0x18012f68a  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012f68f  mov     ebx, eax
0x18012f691  test    eax, eax
0x18012f693  jns     short loc_18012F6C7
0x18012f695  mov     edx, 1F3h; void *
0x18012f69a  lea     r8, aShellSystemset_33; "shell\\systemsettingsthreshold\\handler"...
0x18012f6a1  mov     r9d, eax; char *
0x18012f6a4  mov     rcx, [rbp+28h]; this
0x18012f6a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f6ad  nop
0x18012f6ae  mov     rcx, [rbp+arg_10]; string
0x18012f6b2  call    cs:__imp_WindowsDeleteString
0x18012f6b9  nop     dword ptr [rax+rax+00h]
0x18012f6be  mov     [rbp+arg_10], r15
0x18012f6c2  jmp     loc_18012F4BE
0x18012f6c7  lea     rcx, [rbp+arg_8]
0x18012f6cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f6d0  lea     rdx, [rbp+arg_8]; struct IInspectable **
0x18012f6d4  mov     rbx, [rbp+string]
0x18012f6d8  mov     rcx, rbx; HSTRING
0x18012f6db  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012f6e0  mov     edi, eax
0x18012f6e2  test    eax, eax
0x18012f6e4  jns     short loc_18012F6F0
0x18012f6e6  mov     edx, 1F4h
0x18012f6eb  jmp     loc_18012F609
0x18012f6f0  mov     r9b, 1
0x18012f6f3  mov     r8, [rbp+arg_8]
0x18012f6f7  xor     edx, edx
0x18012f6f9  mov     rcx, qword ptr [rbp+var_10]
0x18012f6fd  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x18012f702  mov     edi, eax
0x18012f704  test    eax, eax
0x18012f706  jns     loc_18012F794
0x18012f70c  mov     edx, 1F5h
0x18012f711  jmp     loc_18012F609
0x18012f716  mov     rcx, rbx; string
0x18012f719  call    cs:__imp_WindowsDeleteString
0x18012f720  nop     dword ptr [rax+rax+00h]
0x18012f725  mov     [rbp+string], r15
0x18012f729  lea     rdx, [rbp+string]; HSTRING *
0x18012f72d  lea     rcx, aSystemsettings_385; "SystemSettings_Personalize_ColorMode_Cu"...
0x18012f734  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18012f739  mov     ebx, eax
0x18012f73b  test    eax, eax
0x18012f73d  jns     short loc_18012F749
0x18012f73f  mov     edx, 1FAh
0x18012f744  jmp     loc_18012F69A
0x18012f749  lea     rcx, [rbp+arg_8]
0x18012f74d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f752  lea     rdx, [rbp+arg_8]; struct IInspectable **
0x18012f756  mov     rbx, [rbp+string]
0x18012f75a  mov     rcx, rbx; HSTRING
0x18012f75d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18012f762  mov     edi, eax
0x18012f764  test    eax, eax
0x18012f766  jns     short loc_18012F772
0x18012f768  mov     edx, 1FBh
0x18012f76d  jmp     loc_18012F609
0x18012f772  mov     r9b, 1
0x18012f775  mov     r8, [rbp+arg_8]
0x18012f779  xor     edx, edx
0x18012f77b  mov     rcx, qword ptr [rbp+var_10]
0x18012f77f  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x18012f784  mov     edi, eax
0x18012f786  test    eax, eax
0x18012f788  jns     short loc_18012F794
0x18012f78a  mov     edx, 1FCh
0x18012f78f  jmp     loc_18012F609
0x18012f794  mov     r8, r14
0x18012f797  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18012f79e  mov     rcx, qword ptr [rbp+var_10]
0x18012f7a2  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18012f7a7  mov     edi, eax
0x18012f7a9  test    eax, eax
0x18012f7ab  jns     short loc_18012F7B7
0x18012f7ad  mov     edx, 1FFh
0x18012f7b2  jmp     loc_18012F609
0x18012f7b7  mov     rcx, [rbp+arg_10]; string
0x18012f7bb  call    cs:__imp_WindowsDeleteString
0x18012f7c2  nop     dword ptr [rax+rax+00h]
0x18012f7c7  mov     [rbp+arg_10], r15
0x18012f7cb  mov     rcx, rbx; string
0x18012f7ce  call    cs:__imp_WindowsDeleteString
0x18012f7d5  nop     dword ptr [rax+rax+00h]
0x18012f7da  nop
0x18012f7db  lea     rcx, [rbp+arg_8]
0x18012f7df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18012f7e4  mov     ebx, r15d
0x18012f7e7  lea     rcx, [rbp+var_10]
0x18012f7eb  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18012f7f0  mov     eax, ebx
0x18012f7f2  mov     rbx, [rsp+30h+arg_0]
0x18012f7f7  add     rsp, 30h
0x18012f7fb  pop     r15
0x18012f7fd  pop     r14
0x18012f7ff  pop     rdi
0x18012f800  pop     rsi
0x18012f801  pop     rbp
0x18012f802  retn
```
