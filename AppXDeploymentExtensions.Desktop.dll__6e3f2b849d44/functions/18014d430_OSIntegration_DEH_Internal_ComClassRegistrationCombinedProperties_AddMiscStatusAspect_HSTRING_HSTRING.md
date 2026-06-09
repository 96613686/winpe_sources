# OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect(HSTRING__ *,HSTRING__ *)

- ea: `0x18014d430`
- end: `0x18014d72e`
- name: `?AddMiscStatusAspect@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@UEAAJPEAUHSTRING__@@0@Z`
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
- `0x18014d430`
- `0x180153b90`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d5ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d5ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014d657`

## string_xrefs

- `0x18014d47b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014d590`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014d620`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014d6fb`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18014d45b`: `CreatePropertyValueFactoryIfNecessary()`
- `0x18014d51c`: `_miscStatusAspects->HasKey(aspect, &alreadyHasKey)`
- `0x18014d4eb`: `RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_miscStatusAspects)`
- `0x18014d6ad`: `_propertyValueFactory->CreateString(miscStatus, &miscStatusPropValue)`
- `0x18014d6e3`: `_miscStatusAspects->Insert(aspect, miscStatusPropValue.Get(), &replacedIgnored)`
- `0x18014d474`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect`
- `0x18014d589`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect`
- `0x18014d619`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect`
- `0x18014d6f4`: `OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect(
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
    v8 = 845;
LABEL_3:
    LODWORD(v23) = PropertyValueFactoryIfNecessary;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect",
      v7,
      v23,
      v24);
    return (unsigned int)PropertyValueFactoryIfNecessary;
  }
  v10 = (HSTRING *)(this + 85);
  if ( !this[85] )
  {
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(this + 85);
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
      v7 = "RegistryMapFactory<IInspectable*>::RegistryMap::Make(&_miscStatusAspects)";
      v8 = 849;
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
    v7 = "_miscStatusAspects->HasKey(aspect, &alreadyHasKey)";
    v8 = 853;
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
      v20 = "_miscStatusAspects->Insert(aspect, miscStatusPropValue.Get(), &replacedIgnored)";
      v21 = 873;
    }
    else
    {
      LODWORD(v23) = PropertyValueFactoryIfNecessary;
      v20 = "_propertyValueFactory->CreateString(miscStatus, &miscStatusPropValue)";
      v21 = 869;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect",
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
      (void *)0x35B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect",
      "_miscStatusAspects->Lookup(aspect, &existingMiscStatusPropValue)",
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
    v16 = "existingMiscStatusPropValue->GetString(existingMiscStatus.GetAddressOf())";
    v17 = 862;
LABEL_21:
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::AddMiscStatusAspect",
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
    v16 = "miscStatus != existingMiscStatus";
    v17 = 864;
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
0x18014d430  push    rbp
0x18014d432  push    rbx
0x18014d433  push    rsi
0x18014d434  push    rdi
0x18014d435  push    r12
0x18014d437  push    r13
0x18014d439  push    r14
0x18014d43b  push    r15
0x18014d43d  mov     rbp, rsp
0x18014d440  sub     rsp, 68h
0x18014d444  mov     r12, r8
0x18014d447  mov     r15, rdx
0x18014d44a  mov     r14, rcx
0x18014d44d  call    ?CreatePropertyValueFactoryIfNecessary@ComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@AEAAJXZ; OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties::CreatePropertyValueFactoryIfNecessary(void)
0x18014d452  mov     ebx, eax
0x18014d454  xor     r13d, r13d
0x18014d457  test    eax, eax
0x18014d459  jns     short loc_18014D48E
0x18014d45b  lea     rax, aCreateproperty; "CreatePropertyValueFactoryIfNecessary()"
0x18014d462  mov     edx, 34Dh; void *
0x18014d467  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014d46b  mov     rcx, [rbp+40h]; this
0x18014d46f  mov     [rsp+68h+var_48], rax; char *
0x18014d474  lea     r9, aOsintegrationD_196; "OSIntegration::DEH::Internal::ComClassR"...
0x18014d47b  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014d482  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014d487  mov     eax, ebx
0x18014d489  jmp     loc_18014D71C
0x18014d48e  lea     rdi, [r14+2A8h]
0x18014d495  cmp     [rdi], r13
0x18014d498  jnz     short loc_18014D4FC
0x18014d49a  mov     rcx, rdi
0x18014d49d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014d4a2  mov     [rdi], r13
0x18014d4a5  lea     rcx, [rbp+string]
0x18014d4a9  call    ??$Make@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@7@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@12@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@5@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x18014d4ae  mov     rsi, [rbp+string]
0x18014d4b2  test    rsi, rsi
0x18014d4b5  jnz     short loc_18014D4BE
0x18014d4b7  mov     ebx, 8007000Eh
0x18014d4bc  jmp     short loc_18014D4DE
0x18014d4be  lea     rcx, [rsi+90h]; this
0x18014d4c5  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18014d4ca  mov     ebx, eax
0x18014d4cc  test    eax, eax
0x18014d4ce  js      short loc_18014D4DE
0x18014d4d0  mov     byte ptr [rsi+98h], 1
0x18014d4d7  mov     [rbp+string], r13
0x18014d4db  mov     [rdi], rsi
0x18014d4de  lea     rcx, [rbp+string]
0x18014d4e2  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18014d4e7  test    ebx, ebx
0x18014d4e9  jns     short loc_18014D4FC
0x18014d4eb  lea     rax, aRegistrymapfac_2; "RegistryMapFactory<IInspectable*>::Regi"...
0x18014d4f2  mov     edx, 351h
0x18014d4f7  jmp     loc_18014D467
0x18014d4fc  mov     [rbp+arg_18], r13b
0x18014d500  mov     rcx, [rdi]
0x18014d503  mov     rax, [rcx]
0x18014d506  lea     r8, [rbp+arg_18]
0x18014d50a  mov     rdx, r15
0x18014d50d  mov     rax, [rax+40h]
0x18014d511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d516  mov     ebx, eax
0x18014d518  test    eax, eax
0x18014d51a  jns     short loc_18014D52D
0x18014d51c  lea     rax, aMiscstatusaspe_3; "_miscStatusAspects->HasKey(aspect, &alr"...
0x18014d523  mov     edx, 355h
0x18014d528  jmp     loc_18014D467
0x18014d52d  mov     [rbp+var_28], r13
0x18014d531  mov     [rbp+var_20], r13d
0x18014d535  cmp     [rbp+arg_18], r13b
0x18014d539  jz      loc_18014D66C
0x18014d53f  mov     rcx, [rdi]
0x18014d542  mov     rax, [rcx]
0x18014d545  lea     rdx, [rbp+var_28]
0x18014d549  mov     [rbp+var_18], rdx
0x18014d54d  mov     [rbp+var_10], r13
0x18014d551  lea     r8, [rbp+var_10]
0x18014d555  mov     rdx, r15
0x18014d558  mov     rax, [rax+30h]
0x18014d55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d561  mov     ebx, eax
0x18014d563  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014d567  mov     rcx, [rbp+var_18]; this
0x18014d56b  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014d570  nop
0x18014d571  test    ebx, ebx
0x18014d573  jns     short loc_18014D5A6
0x18014d575  mov     rcx, [rbp+40h]; this
0x18014d579  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014d57d  lea     rax, aMiscstatusaspe_4; "_miscStatusAspects->Lookup(aspect, &exi"...
0x18014d584  mov     [rsp+68h+var_48], rax; char *
0x18014d589  lea     r9, aOsintegrationD_196; "OSIntegration::DEH::Internal::ComClassR"...
0x18014d590  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014d597  mov     edx, 35Bh; void *
0x18014d59c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014d5a1  jmp     loc_18014D645
0x18014d5a6  mov     [rbp+string], r13
0x18014d5aa  mov     rax, [rbp+var_28]
0x18014d5ae  mov     [rbp+var_18], rax
0x18014d5b2  mov     eax, [rbp+var_20]
0x18014d5b5  mov     dword ptr [rbp+var_10], eax
0x18014d5b8  xor     ecx, ecx; string
0x18014d5ba  call    cs:__imp_WindowsDeleteString
0x18014d5c1  nop     dword ptr [rax+rax+00h]
0x18014d5c6  mov     [rbp+string], r13
0x18014d5ca  lea     rdx, [rbp+string]; HSTRING *
0x18014d5ce  lea     rcx, [rbp+var_18]; this
0x18014d5d2  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x18014d5d7  mov     ebx, eax
0x18014d5d9  test    eax, eax
0x18014d5db  jns     short loc_18014D5EF
0x18014d5dd  mov     dword ptr [rsp+68h+var_40], eax
0x18014d5e1  lea     rax, aExistingmiscst; "existingMiscStatusPropValue->GetString("...
0x18014d5e8  mov     edx, 35Eh
0x18014d5ed  jmp     short loc_18014D614
0x18014d5ef  mov     rdx, [rbp+string]; HSTRING
0x18014d5f3  mov     rcx, r12; this
0x18014d5f6  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18014d5fb  test    eax, eax
0x18014d5fd  jz      short loc_18014D653
0x18014d5ff  mov     ebx, 8000000Dh
0x18014d604  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18014d608  lea     rax, aMiscstatusExis; "miscStatus != existingMiscStatus"
0x18014d60f  mov     edx, 360h; void *
0x18014d614  mov     [rsp+68h+var_48], rax; char *
0x18014d619  lea     r9, aOsintegrationD_196; "OSIntegration::DEH::Internal::ComClassR"...
0x18014d620  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014d627  mov     rcx, [rbp+40h]; this
0x18014d62b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014d630  nop
0x18014d631  mov     rcx, [rbp+string]; string
0x18014d635  call    cs:__imp_WindowsDeleteString
0x18014d63c  nop     dword ptr [rax+rax+00h]
0x18014d641  mov     [rbp+string], r13
0x18014d645  lea     rcx, [rbp+var_28]; this
0x18014d649  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014d64e  jmp     loc_18014D487
0x18014d653  mov     rcx, [rbp+string]; string
0x18014d657  call    cs:__imp_WindowsDeleteString
0x18014d65e  nop     dword ptr [rax+rax+00h]
0x18014d663  mov     [rbp+string], r13
0x18014d667  jmp     loc_18014D711
0x18014d66c  mov     rcx, [r14+288h]
0x18014d673  mov     rax, [rcx]
0x18014d676  lea     rdx, [rbp+var_28]
0x18014d67a  mov     [rbp+var_18], rdx
0x18014d67e  mov     [rbp+var_10], r13
0x18014d682  lea     r8, [rbp+var_10]
0x18014d686  mov     rdx, r12
0x18014d689  mov     rax, [rax+90h]
0x18014d690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d695  mov     ebx, eax
0x18014d697  mov     rdx, [rbp+var_10]; struct IInspectable *
0x18014d69b  mov     rcx, [rbp+var_18]; this
0x18014d69f  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014d6a4  nop
0x18014d6a5  test    ebx, ebx
0x18014d6a7  jns     short loc_18014D6BB
0x18014d6a9  mov     dword ptr [rsp+68h+var_40], ebx
0x18014d6ad  lea     rax, aPropertyvaluef_1; "_propertyValueFactory->CreateString(mis"...
0x18014d6b4  mov     edx, 365h
0x18014d6b9  jmp     short loc_18014D6EF
0x18014d6bb  mov     byte ptr [rbp+var_38], r13b
0x18014d6bf  mov     rcx, [rdi]
0x18014d6c2  mov     rax, [rcx]
0x18014d6c5  lea     r9, [rbp+var_38]
0x18014d6c9  mov     r8, [rbp+var_28]
0x18014d6cd  mov     rdx, r15
0x18014d6d0  mov     rax, [rax+50h]
0x18014d6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d6d9  mov     ebx, eax
0x18014d6db  test    eax, eax
0x18014d6dd  jns     short loc_18014D711
0x18014d6df  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18014d6e3  lea     rax, aMiscstatusaspe_2; "_miscStatusAspects->Insert(aspect, misc"...
0x18014d6ea  mov     edx, 369h; void *
0x18014d6ef  mov     [rsp+68h+var_48], rax; char *
0x18014d6f4  lea     r9, aOsintegrationD_196; "OSIntegration::DEH::Internal::ComClassR"...
0x18014d6fb  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18014d702  mov     rcx, [rbp+40h]; this
0x18014d706  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18014d70b  nop
0x18014d70c  jmp     loc_18014D645
0x18014d711  lea     rcx, [rbp+var_28]; this
0x18014d715  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18014d71a  xor     eax, eax
0x18014d71c  add     rsp, 68h
0x18014d720  pop     r15
0x18014d722  pop     r14
0x18014d724  pop     r13
0x18014d726  pop     r12
0x18014d728  pop     rdi
0x18014d729  pop     rsi
0x18014d72a  pop     rbx
0x18014d72b  pop     rbp
0x18014d72c  retn
```
