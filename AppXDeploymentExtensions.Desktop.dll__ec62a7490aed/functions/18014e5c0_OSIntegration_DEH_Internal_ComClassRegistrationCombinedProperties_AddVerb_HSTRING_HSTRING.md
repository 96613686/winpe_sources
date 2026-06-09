# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb(HSTRING__ *,HSTRING__ *)

- ea: `0x18014e5c0`
- end: `0x18014e8be`
- name: `?AddVerb@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@UEAAJPEAUHSTRING__@@0@Z`
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
- `0x18014e5c0`
- `0x180153b90`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e74a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e74a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e7c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014e7e7`

## string_xrefs

- `0x18014e60b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e720`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e7b0`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e88b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014e5eb`: `CreatePropertyValueFactoryIfNecessary()`
- `0x18014e604`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb`
- `0x18014e719`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb`
- `0x18014e7a9`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb`
- `0x18014e884`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb`
- `0x18014e6ac`: `_verbs->HasKey(verbId, &alreadyHasKey)`
- `0x18014e67b`: `RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_verbs)`
- `0x18014e83d`: `_propertyValueFactory->CreateString(verb, &verbPropValue)`
- `0x18014e873`: `_verbs->Insert(verbId, verbPropValue.Get(), &replacedIgnored)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb(
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
    v8 = 803;
LABEL_3:
    LODWORD(v23) = PropertyValueFactoryIfNecessary;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb",
      v7,
      v23,
      v24);
    return (unsigned int)PropertyValueFactoryIfNecessary;
  }
  v10 = (HSTRING *)(this + 84);
  if ( !this[84] )
  {
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 84);
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
      v7 = "RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_verbs)";
      v8 = 807;
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
    v7 = "_verbs->HasKey(verbId, &alreadyHasKey)";
    v8 = 811;
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
      v20 = "_verbs->Insert(verbId, verbPropValue.Get(), &replacedIgnored)";
      v21 = 830;
    }
    else
    {
      LODWORD(v23) = PropertyValueFactoryIfNecessary;
      v20 = "_propertyValueFactory->CreateString(verb, &verbPropValue)";
      v21 = 827;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb",
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
      (void *)0x331,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb",
      "_verbs->Lookup(verbId, &existingVerbPropValue)",
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
    v16 = "existingVerbPropValue->GetString(existingVerb.GetAddressOf())";
    v17 = 820;
LABEL_21:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddVerb",
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
    v16 = "verb != existingVerb";
    v17 = 822;
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
0x18014e5c0  push    rbp
0x18014e5c2  push    rbx
0x18014e5c3  push    rsi
0x18014e5c4  push    rdi
0x18014e5c5  push    r12
0x18014e5c7  push    r13
0x18014e5c9  push    r14
0x18014e5cb  push    r15
0x18014e5cd  mov     rbp, rsp
0x18014e5d0  sub     rsp, 68h
0x18014e5d4  mov     r12, r8
0x18014e5d7  mov     r15, rdx
0x18014e5da  mov     r14, rcx
0x18014e5dd  call    ?CreatePropertyValueFactoryIfNecessary@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJXZ; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreatePropertyValueFactoryIfNecessary(void)
0x18014e5e2  mov     ebx, eax
0x18014e5e4  xor     r13d, r13d
0x18014e5e7  test    eax, eax
0x18014e5e9  jns     short loc_18014E61E
0x18014e5eb  lea     rax, aCreateproperty; "CreatePropertyValueFactoryIfNecessary()"
0x18014e5f2  mov     edx, 323h; void *
0x18014e5f7  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014e5fb  mov     rcx, [rbp+40h]; this
0x18014e5ff  mov     [rsp+68h+var_48], rax; char *
0x18014e604  lea     r9, aOsintegrationD_279; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e60b  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e612  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e617  mov     eax, ebx
0x18014e619  jmp     loc_18014E8AC
0x18014e61e  lea     rdi, [r14+2A0h]
0x18014e625  cmp     [rdi], r13
0x18014e628  jnz     short loc_18014E68C
0x18014e62a  mov     rcx, rdi
0x18014e62d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014e632  mov     [rdi], r13
0x18014e635  lea     rcx, [rbp+string]
0x18014e639  call    ??$Make@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@7@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@12@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@5@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x18014e63e  mov     rsi, [rbp+string]
0x18014e642  test    rsi, rsi
0x18014e645  jnz     short loc_18014E64E
0x18014e647  mov     ebx, 8007000Eh
0x18014e64c  jmp     short loc_18014E66E
0x18014e64e  lea     rcx, [rsi+90h]; this
0x18014e655  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18014e65a  mov     ebx, eax
0x18014e65c  test    eax, eax
0x18014e65e  js      short loc_18014E66E
0x18014e660  mov     byte ptr [rsi+98h], 1
0x18014e667  mov     [rbp+string], r13
0x18014e66b  mov     [rdi], rsi
0x18014e66e  lea     rcx, [rbp+string]
0x18014e672  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014e677  test    ebx, ebx
0x18014e679  jns     short loc_18014E68C
0x18014e67b  lea     rax, aRegistrymapfac_1; "RegistryMapFactory<IInspectable*>::Regi"...
0x18014e682  mov     edx, 327h
0x18014e687  jmp     loc_18014E5F7
0x18014e68c  mov     [rbp+arg_18], r13b
0x18014e690  mov     rcx, [rdi]
0x18014e693  mov     rax, [rcx]
0x18014e696  lea     r8, [rbp+arg_18]
0x18014e69a  mov     rdx, r15
0x18014e69d  mov     rax, [rax+40h]
0x18014e6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e6a6  mov     ebx, eax
0x18014e6a8  test    eax, eax
0x18014e6aa  jns     short loc_18014E6BD
0x18014e6ac  lea     rax, aVerbsHaskeyVer; "_verbs->HasKey(verbId, &alreadyHasKey)"
0x18014e6b3  mov     edx, 32Bh
0x18014e6b8  jmp     loc_18014E5F7
0x18014e6bd  mov     [rbp+var_28], r13
0x18014e6c1  mov     [rbp+var_20], r13d
0x18014e6c5  cmp     [rbp+arg_18], r13b
0x18014e6c9  jz      loc_18014E7FC
0x18014e6cf  mov     rcx, [rdi]
0x18014e6d2  mov     rax, [rcx]
0x18014e6d5  lea     rdx, [rbp+var_28]
0x18014e6d9  mov     [rbp+var_18], rdx
0x18014e6dd  mov     [rbp+var_10], r13
0x18014e6e1  lea     r8, [rbp+var_10]
0x18014e6e5  mov     rdx, r15
0x18014e6e8  mov     rax, [rax+30h]
0x18014e6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e6f1  mov     ebx, eax
0x18014e6f3  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014e6f7  mov     rcx, [rbp+var_18]; this
0x18014e6fb  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014e700  nop
0x18014e701  test    ebx, ebx
0x18014e703  jns     short loc_18014E736
0x18014e705  mov     rcx, [rbp+40h]; this
0x18014e709  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014e70d  lea     rax, aVerbsLookupVer; "_verbs->Lookup(verbId, &existingVerbPro"...
0x18014e714  mov     [rsp+68h+var_48], rax; char *
0x18014e719  lea     r9, aOsintegrationD_279; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e720  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e727  mov     edx, 331h; void *
0x18014e72c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e731  jmp     loc_18014E7D5
0x18014e736  mov     [rbp+string], r13
0x18014e73a  mov     rax, [rbp+var_28]
0x18014e73e  mov     [rbp+var_18], rax
0x18014e742  mov     eax, [rbp+var_20]
0x18014e745  mov     dword ptr [rbp+var_10], eax
0x18014e748  xor     ecx, ecx; string
0x18014e74a  call    cs:__imp_WindowsDeleteString
0x18014e751  nop     dword ptr [rax+rax+00h]
0x18014e756  mov     [rbp+string], r13
0x18014e75a  lea     rdx, [rbp+string]; HSTRING *
0x18014e75e  lea     rcx, [rbp+var_18]; this
0x18014e762  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18014e767  mov     ebx, eax
0x18014e769  test    eax, eax
0x18014e76b  jns     short loc_18014E77F
0x18014e76d  mov     dword ptr [rsp+68h+var_40], eax
0x18014e771  lea     rax, aExistingverbpr; "existingVerbPropValue->GetString(existi"...
0x18014e778  mov     edx, 334h
0x18014e77d  jmp     short loc_18014E7A4
0x18014e77f  mov     rdx, [rbp+string]; HSTRING
0x18014e783  mov     rcx, r12; this
0x18014e786  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18014e78b  test    eax, eax
0x18014e78d  jz      short loc_18014E7E3
0x18014e78f  mov     ebx, 8000000Dh
0x18014e794  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014e798  lea     rax, aVerbExistingve; "verb != existingVerb"
0x18014e79f  mov     edx, 336h; void *
0x18014e7a4  mov     [rsp+68h+var_48], rax; char *
0x18014e7a9  lea     r9, aOsintegrationD_279; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e7b0  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e7b7  mov     rcx, [rbp+40h]; this
0x18014e7bb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e7c0  nop
0x18014e7c1  mov     rcx, [rbp+string]; string
0x18014e7c5  call    cs:__imp_WindowsDeleteString
0x18014e7cc  nop     dword ptr [rax+rax+00h]
0x18014e7d1  mov     [rbp+string], r13
0x18014e7d5  lea     rcx, [rbp+var_28]; this
0x18014e7d9  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014e7de  jmp     loc_18014E617
0x18014e7e3  mov     rcx, [rbp+string]; string
0x18014e7e7  call    cs:__imp_WindowsDeleteString
0x18014e7ee  nop     dword ptr [rax+rax+00h]
0x18014e7f3  mov     [rbp+string], r13
0x18014e7f7  jmp     loc_18014E8A1
0x18014e7fc  mov     rcx, [r14+288h]
0x18014e803  mov     rax, [rcx]
0x18014e806  lea     rdx, [rbp+var_28]
0x18014e80a  mov     [rbp+var_18], rdx
0x18014e80e  mov     [rbp+var_10], r13
0x18014e812  lea     r8, [rbp+var_10]
0x18014e816  mov     rdx, r12
0x18014e819  mov     rax, [rax+90h]
0x18014e820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e825  mov     ebx, eax
0x18014e827  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014e82b  mov     rcx, [rbp+var_18]; this
0x18014e82f  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014e834  nop
0x18014e835  test    ebx, ebx
0x18014e837  jns     short loc_18014E84B
0x18014e839  mov     dword ptr [rsp+68h+var_40], ebx
0x18014e83d  lea     rax, aPropertyvaluef; "_propertyValueFactory->CreateString(ver"...
0x18014e844  mov     edx, 33Bh
0x18014e849  jmp     short loc_18014E87F
0x18014e84b  mov     byte ptr [rbp+var_38], r13b
0x18014e84f  mov     rcx, [rdi]
0x18014e852  mov     rax, [rcx]
0x18014e855  lea     r9, [rbp+var_38]
0x18014e859  mov     r8, [rbp+var_28]
0x18014e85d  mov     rdx, r15
0x18014e860  mov     rax, [rax+50h]
0x18014e864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e869  mov     ebx, eax
0x18014e86b  test    eax, eax
0x18014e86d  jns     short loc_18014E8A1
0x18014e86f  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18014e873  lea     rax, aVerbsInsertVer; "_verbs->Insert(verbId, verbPropValue.Ge"...
0x18014e87a  mov     edx, 33Eh; void *
0x18014e87f  mov     [rsp+68h+var_48], rax; char *
0x18014e884  lea     r9, aOsintegrationD_279; "OSIntegration::DEH::Internal::ComClassR"...
0x18014e88b  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014e892  mov     rcx, [rbp+40h]; this
0x18014e896  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014e89b  nop
0x18014e89c  jmp     loc_18014E7D5
0x18014e8a1  lea     rcx, [rbp+var_28]; this
0x18014e8a5  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014e8aa  xor     eax, eax
0x18014e8ac  add     rsp, 68h
0x18014e8b0  pop     r15
0x18014e8b2  pop     r14
0x18014e8b4  pop     r13
0x18014e8b6  pop     r12
0x18014e8b8  pop     rdi
0x18014e8b9  pop     rsi
0x18014e8ba  pop     rbx
0x18014e8bb  pop     rbp
0x18014e8bc  retn
```
