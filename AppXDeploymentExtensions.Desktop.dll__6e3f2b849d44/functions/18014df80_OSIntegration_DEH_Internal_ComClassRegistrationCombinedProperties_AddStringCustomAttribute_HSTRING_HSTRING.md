# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute(HSTRING__ *,HSTRING__ *)

- ea: `0x18014df80`
- end: `0x18014e27e`
- name: `?AddStringCustomAttribute@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@UEAAJPEAUHSTRING__@@0@Z`
- size: `766`
- prototype: `int(OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006970`
- `0x180036e7c`
- `0x180048794`
- `0x18004a448`
- `0x1800582c0`
- `0x18006a4c8`
- `0x180087574`
- `0x180133848`
- `0x18014df80`
- `0x180153b90`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e10a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e1a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e10a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e1a7`

## string_xrefs

- `0x18014dfcb`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e0e0`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e170`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e24b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014dfab`: `CreatePropertyValueFactoryIfNecessary()`
- `0x18014e06c`: `_customAttributes->HasKey(name, &alreadyHasKey)`
- `0x18014e03b`: `RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_customAttributes)`
- `0x18014dfc4`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute`
- `0x18014e0d9`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute`
- `0x18014e169`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute`
- `0x18014e244`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute`
- `0x18014e233`: `_customAttributes->Insert(name, propValue.Get(), &replacedIgnored)`
- `0x18014e1fd`: `_propertyValueFactory->CreateString(value, &propValue)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute(
        __int64 **this,
        HSTRING a2,
        Microsoft::WRL::Wrappers::Details *a3)
{
  int PropertyValueFactoryIfNecessary; // ebx
  const char *v7; // rax
  __int64 v8; // rdx
  HSTRING *v10; // rdi
  HSTRING v11; // rsi
  HSTRING v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  HSTRING v15; // r8
  const char *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rax
  const char *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  char *v23; // [rsp+28h] [rbp-40h]
  int v24; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  RoVariant *v26; // [rsp+40h] [rbp-28h] BYREF
  int v27; // [rsp+48h] [rbp-20h]
  RoVariant *v28; // [rsp+50h] [rbp-18h] BYREF
  struct IInspectable *v29[2]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+A8h] [rbp+40h]
  char v31; // [rsp+C8h] [rbp+60h] BYREF

  PropertyValueFactoryIfNecessary = OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreatePropertyValueFactoryIfNecessary((OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *)this);
  if ( PropertyValueFactoryIfNecessary < 0 )
  {
    v7 = "CreatePropertyValueFactoryIfNecessary()";
    v8 = 1066;
LABEL_3:
    LODWORD(v23) = PropertyValueFactoryIfNecessary;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute",
      v7,
      v23,
      v24);
    return (unsigned int)PropertyValueFactoryIfNecessary;
  }
  v10 = (HSTRING *)(this + 86);
  if ( !this[86] )
  {
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 86);
    *v10 = 0;
    Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(&string);
    v11 = string;
    if ( string )
    {
      PropertyValueFactoryIfNecessary = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(string + 36));
      if ( PropertyValueFactoryIfNecessary >= 0 )
      {
        *((_BYTE *)v11 + 152) = 1;
        string = 0;
        *v10 = v11;
      }
    }
    else
    {
      PropertyValueFactoryIfNecessary = -2147024882;
    }
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&string);
    if ( PropertyValueFactoryIfNecessary < 0 )
    {
      v7 = "RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_customAttributes)";
      v8 = 1070;
      goto LABEL_3;
    }
  }
  v31 = 0;
  PropertyValueFactoryIfNecessary = (*(__int64 (__fastcall **)(HSTRING, HSTRING, char *))(*(_QWORD *)*v10 + 64LL))(
                                      *v10,
                                      a2,
                                      &v31);
  if ( PropertyValueFactoryIfNecessary < 0 )
  {
    v7 = "_customAttributes->HasKey(name, &alreadyHasKey)";
    v8 = 1074;
    goto LABEL_3;
  }
  v26 = 0;
  v27 = 0;
  if ( !v31 )
  {
    v18 = this[81];
    v19 = *v18;
    v28 = (RoVariant *)&v26;
    v29[0] = 0;
    PropertyValueFactoryIfNecessary = (*(__int64 (__fastcall **)(__int64 *, Microsoft::WRL::Wrappers::Details *, struct IInspectable **))(v19 + 144))(
                                        v18,
                                        a3,
                                        v29);
    RoVariant::Attach(v28, v29[0]);
    if ( PropertyValueFactoryIfNecessary >= 0 )
    {
      LOBYTE(v24) = 0;
      v22 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, RoVariant *, int *))(*(_QWORD *)*v10 + 80LL))(
              *v10,
              a2,
              v26,
              &v24);
      PropertyValueFactoryIfNecessary = v22;
      if ( v22 >= 0 )
        goto LABEL_29;
      LODWORD(v23) = v22;
      v20 = "_customAttributes->Insert(name, propValue.Get(), &replacedIgnored)";
      v21 = 1093;
    }
    else
    {
      LODWORD(v23) = PropertyValueFactoryIfNecessary;
      v20 = "_propertyValueFactory->CreateString(value, &propValue)";
      v21 = 1090;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute",
      v20,
      v23,
      v24);
    goto LABEL_22;
  }
  v12 = *v10;
  v13 = *(_QWORD *)*v10;
  v28 = (RoVariant *)&v26;
  v29[0] = 0;
  PropertyValueFactoryIfNecessary = (*(__int64 (__fastcall **)(HSTRING, HSTRING, struct IInspectable **))(v13 + 48))(
                                      v12,
                                      a2,
                                      v29);
  RoVariant::Attach(v28, v29[0]);
  if ( PropertyValueFactoryIfNecessary < 0 )
  {
    LODWORD(v23) = PropertyValueFactoryIfNecessary;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x438,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute",
      "_customAttributes->Lookup(name, &existingPropValue)",
      v23,
      v24);
LABEL_22:
    RoVariant::~RoVariant((RoVariant *)&v26);
    return (unsigned int)PropertyValueFactoryIfNecessary;
  }
  string = 0;
  v28 = v26;
  LODWORD(v29[0]) = v27;
  WindowsDeleteString(0);
  string = 0;
  v14 = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v28, &string);
  PropertyValueFactoryIfNecessary = v14;
  if ( v14 < 0 )
  {
    LODWORD(v23) = v14;
    v16 = "existingPropValue->GetString(existingValue.GetAddressOf())";
    v17 = 1083;
LABEL_21:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddStringCustomAttribute",
      v16,
      v23,
      v24);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_22;
  }
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, string, v15) )
  {
    PropertyValueFactoryIfNecessary = -2147483635;
    LODWORD(v23) = -2147483635;
    v16 = "value != existingValue";
    v17 = 1085;
    goto LABEL_21;
  }
  WindowsDeleteString(string);
  string = 0;
LABEL_29:
  RoVariant::~RoVariant((RoVariant *)&v26);
  return 0;
}

```

## disassembly

```asm
0x18014df80  push    rbp
0x18014df82  push    rbx
0x18014df83  push    rsi
0x18014df84  push    rdi
0x18014df85  push    r12
0x18014df87  push    r13
0x18014df89  push    r14
0x18014df8b  push    r15
0x18014df8d  mov     rbp, rsp
0x18014df90  sub     rsp, 68h
0x18014df94  mov     r12, r8
0x18014df97  mov     r15, rdx
0x18014df9a  mov     r14, rcx
0x18014df9d  call    ?CreatePropertyValueFactoryIfNecessary@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJXZ; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreatePropertyValueFactoryIfNecessary(void)
0x18014dfa2  mov     ebx, eax
0x18014dfa4  xor     r13d, r13d
0x18014dfa7  test    eax, eax
0x18014dfa9  jns     short loc_18014DFDE
0x18014dfab  lea     rax, aCreateproperty; "CreatePropertyValueFactoryIfNecessary()"
0x18014dfb2  mov     edx, 42Ah; void *
0x18014dfb7  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014dfbb  mov     rcx, [rbp+40h]; this
0x18014dfbf  mov     [rsp+68h+var_48], rax; char *
0x18014dfc4  lea     r9, aOsintegrationD_26; "OSIntegration::DEH::Internal::ComClassR"...
0x18014dfcb  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014dfd2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014dfd7  mov     eax, ebx
0x18014dfd9  jmp     loc_18014E26C
0x18014dfde  lea     rdi, [r14+2B0h]
0x18014dfe5  cmp     [rdi], r13
0x18014dfe8  jnz     short loc_18014E04C
0x18014dfea  mov     rcx, rdi
0x18014dfed  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014dff2  mov     [rdi], r13
0x18014dff5  lea     rcx, [rbp+string]
0x18014dff9  call    ??$Make@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@7@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@12@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@5@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x18014dffe  mov     rsi, [rbp+string]
0x18014e002  test    rsi, rsi
0x18014e005  jnz     short loc_18014E00E
0x18014e007  mov     ebx, 8007000Eh
0x18014e00c  jmp     short loc_18014E02E
0x18014e00e  lea     rcx, [rsi+90h]; this
0x18014e015  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18014e01a  mov     ebx, eax
0x18014e01c  test    eax, eax
0x18014e01e  js      short loc_18014E02E
0x18014e020  mov     byte ptr [rsi+98h], 1
0x18014e027  mov     [rbp+string], r13
0x18014e02b  mov     [rdi], rsi
0x18014e02e  lea     rcx, [rbp+string]
0x18014e032  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014e037  test    ebx, ebx
0x18014e039  jns     short loc_18014E04C
0x18014e03b  lea     rax, aRegistrymapfac; "RegistryMapFactory<IInspectable*>::Regi"...
0x18014e042  mov     edx, 42Eh
0x18014e047  jmp     loc_18014DFB7
0x18014e04c  mov     [rbp+arg_18], r13b
0x18014e050  mov     rcx, [rdi]
0x18014e053  mov     rax, [rcx]
0x18014e056  lea     r8, [rbp+arg_18]
0x18014e05a  mov     rdx, r15
0x18014e05d  mov     rax, [rax+40h]
0x18014e061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e066  mov     ebx, eax
0x18014e068  test    eax, eax
0x18014e06a  jns     short loc_18014E07D
0x18014e06c  lea     rax, aCustomattribut_1; "_customAttributes->HasKey(name, &alread"...
0x18014e073  mov     edx, 432h
0x18014e078  jmp     loc_18014DFB7
0x18014e07d  mov     [rbp+var_28], r13
0x18014e081  mov     [rbp+var_20], r13d
0x18014e085  cmp     [rbp+arg_18], r13b
0x18014e089  jz      loc_18014E1BC
0x18014e08f  mov     rcx, [rdi]
0x18014e092  mov     rax, [rcx]
0x18014e095  lea     rdx, [rbp+var_28]
0x18014e099  mov     [rbp+var_18], rdx
0x18014e09d  mov     [rbp+var_10], r13
0x18014e0a1  lea     r8, [rbp+var_10]
0x18014e0a5  mov     rdx, r15
0x18014e0a8  mov     rax, [rax+30h]
0x18014e0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e0b1  mov     ebx, eax
0x18014e0b3  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014e0b7  mov     rcx, [rbp+var_18]; this
0x18014e0bb  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014e0c0  nop
0x18014e0c1  test    ebx, ebx
0x18014e0c3  jns     short loc_18014E0F6
0x18014e0c5  mov     rcx, [rbp+40h]; this
0x18014e0c9  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014e0cd  lea     rax, aCustomattribut; "_customAttributes->Lookup(name, &existi"...
0x18014e0d4  mov     [rsp+68h+var_48], rax; char *
0x18014e0d9  lea     r9, aOsintegrationD_26; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e0e0  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e0e7  mov     edx, 438h; void *
0x18014e0ec  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e0f1  jmp     loc_18014E195
0x18014e0f6  mov     [rbp+string], r13
0x18014e0fa  mov     rax, [rbp+var_28]
0x18014e0fe  mov     [rbp+var_18], rax
0x18014e102  mov     eax, [rbp+var_20]
0x18014e105  mov     dword ptr [rbp+var_10], eax
0x18014e108  xor     ecx, ecx; string
0x18014e10a  call    cs:__imp_WindowsDeleteString
0x18014e111  nop     dword ptr [rax+rax+00h]
0x18014e116  mov     [rbp+string], r13
0x18014e11a  lea     rdx, [rbp+string]; HSTRING *
0x18014e11e  lea     rcx, [rbp+var_18]; this
0x18014e122  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18014e127  mov     ebx, eax
0x18014e129  test    eax, eax
0x18014e12b  jns     short loc_18014E13F
0x18014e12d  mov     dword ptr [rsp+68h+var_40], eax
0x18014e131  lea     rax, aExistingpropva_0; "existingPropValue->GetString(existingVa"...
0x18014e138  mov     edx, 43Bh
0x18014e13d  jmp     short loc_18014E164
0x18014e13f  mov     rdx, [rbp+string]; HSTRING
0x18014e143  mov     rcx, r12; this
0x18014e146  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18014e14b  test    eax, eax
0x18014e14d  jz      short loc_18014E1A3
0x18014e14f  mov     ebx, 8000000Dh
0x18014e154  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014e158  lea     rax, aValueExistingv; "value != existingValue"
0x18014e15f  mov     edx, 43Dh; void *
0x18014e164  mov     [rsp+68h+var_48], rax; char *
0x18014e169  lea     r9, aOsintegrationD_26; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e170  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e177  mov     rcx, [rbp+40h]; this
0x18014e17b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e180  nop
0x18014e181  mov     rcx, [rbp+string]; string
0x18014e185  call    cs:__imp_WindowsDeleteString
0x18014e18c  nop     dword ptr [rax+rax+00h]
0x18014e191  mov     [rbp+string], r13
0x18014e195  lea     rcx, [rbp+var_28]; this
0x18014e199  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014e19e  jmp     loc_18014DFD7
0x18014e1a3  mov     rcx, [rbp+string]; string
0x18014e1a7  call    cs:__imp_WindowsDeleteString
0x18014e1ae  nop     dword ptr [rax+rax+00h]
0x18014e1b3  mov     [rbp+string], r13
0x18014e1b7  jmp     loc_18014E261
0x18014e1bc  mov     rcx, [r14+288h]
0x18014e1c3  mov     rax, [rcx]
0x18014e1c6  lea     rdx, [rbp+var_28]
0x18014e1ca  mov     [rbp+var_18], rdx
0x18014e1ce  mov     [rbp+var_10], r13
0x18014e1d2  lea     r8, [rbp+var_10]
0x18014e1d6  mov     rdx, r12
0x18014e1d9  mov     rax, [rax+90h]
0x18014e1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e1e5  mov     ebx, eax
0x18014e1e7  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014e1eb  mov     rcx, [rbp+var_18]; this
0x18014e1ef  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014e1f4  nop
0x18014e1f5  test    ebx, ebx
0x18014e1f7  jns     short loc_18014E20B
0x18014e1f9  mov     dword ptr [rsp+68h+var_40], ebx
0x18014e1fd  lea     rax, aPropertyvaluef_5; "_propertyValueFactory->CreateString(val"...
0x18014e204  mov     edx, 442h
0x18014e209  jmp     short loc_18014E23F
0x18014e20b  mov     byte ptr [rbp+var_38], r13b
0x18014e20f  mov     rcx, [rdi]
0x18014e212  mov     rax, [rcx]
0x18014e215  lea     r9, [rbp+var_38]
0x18014e219  mov     r8, [rbp+var_28]
0x18014e21d  mov     rdx, r15
0x18014e220  mov     rax, [rax+50h]
0x18014e224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e229  mov     ebx, eax
0x18014e22b  test    eax, eax
0x18014e22d  jns     short loc_18014E261
0x18014e22f  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18014e233  lea     rax, aCustomattribut_0; "_customAttributes->Insert(name, propVal"...
0x18014e23a  mov     edx, 445h; void *
0x18014e23f  mov     [rsp+68h+var_48], rax; char *
0x18014e244  lea     r9, aOsintegrationD_26; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e24b  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e252  mov     rcx, [rbp+40h]; this
0x18014e256  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e25b  nop
0x18014e25c  jmp     loc_18014E195
0x18014e261  lea     rcx, [rbp+var_28]; this
0x18014e265  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014e26a  xor     eax, eax
0x18014e26c  add     rsp, 68h
0x18014e270  pop     r15
0x18014e272  pop     r14
0x18014e274  pop     r13
0x18014e276  pop     r12
0x18014e278  pop     rdi
0x18014e279  pop     rsi
0x18014e27a  pop     rbx
0x18014e27b  pop     rbp
0x18014e27c  retn
```
