# Windows::Storage::StateABIHelpers::CreatePropertySetHashMap<Windows::Storage::ApplicationDataContainerSettingsServer>(tag_STATE_ENUM_ITEM const *,Windows::Storage::ApplicationDataContainerSettingsServer &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>> * *)

- ea: `0x18000d190`
- end: `0x18000d4b5`
- name: `??$CreatePropertySetHashMap@VApplicationDataContainerSettingsServer@Storage@Windows@@@StateABIHelpers@Storage@Windows@@YAJPEBUtag_STATE_ENUM_ITEM@@AEAVApplicationDataContainerSettingsServer@12@PEAPEAV?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@2@@Z`
- size: `805`
- prototype: `__int64 __fastcall(const tag_STATE_ENUM_ITEM *apisetEnumerationResults, Windows::Storage::ApplicationDataContainerSettingsServer *propertySetServer, Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > **propertySetHashMap)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d050`

## callees

- `0x180003820`
- `0x180009778`
- `0x18000d190`
- `0x18000e4e8`
- `0x180021efc`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d237`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d24a`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::CreatePropertySetHashMap<Windows::Storage::ApplicationDataContainerSettingsServer>(
        const tag_STATE_ENUM_ITEM *apisetEnumerationResults,
        Windows::Storage::ApplicationDataContainerSettingsServer *propertySetServer,
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > **propertySetHashMap)
{
  Windows::Storage::ApplicationDataContainerSettingsServer *v4; // r15
  const Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> *v6; // rdx
  const Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> *v7; // rcx
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *ptr; // rbx
  unsigned __int64 v9; // rdi
  wchar_t *Name; // r14
  Windows::Storage::ApplicationDataContainerSettingsServer_vtbl *v11; // rax
  HRESULT v12; // eax
  IInspectable *v13; // r14
  RoVariant *v14; // r12
  IInspectable_vtbl *v15; // rax
  int v16; // eax
  int v17; // edi
  IInspectable *v18; // r15
  IInspectable *pI; // rcx
  HRESULT hrState; // eax
  HRESULT v21; // edi
  unsigned int v23; // ebx
  unsigned __int8 replaced[8]; // [rsp+30h] [rbp-49h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > > newPropertySetHashMap; // [rsp+38h] [rbp-41h] BYREF
  RoVariant lookupValue; // [rsp+40h] [rbp-39h] BYREF
  Windows::Storage::ApplicationDataContainerSettingsServer *v27; // [rsp+50h] [rbp-29h]
  IInspectable *v28; // [rsp+58h] [rbp-21h] BYREF
  RoVariant *p_lookupValue; // [rsp+60h] [rbp-19h]
  IInspectable *v30; // [rsp+68h] [rbp-11h] BYREF
  Windows::Internal::StringReference key; // [rsp+70h] [rbp-9h] BYREF
  void *retaddr; // [rsp+D8h] [rbp+5Fh]

  v27 = propertySetServer;
  v4 = propertySetServer;
  if ( !propertySetHashMap )
  {
    v23 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x19u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIPropertySetHashMapFactory.hpp",
      -2147024809);
    return v23;
  }
  *propertySetHashMap = 0;
  newPropertySetHashMap.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&newPropertySetHashMap);
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Make(
    v7,
    v6,
    &newPropertySetHashMap.ptr_);
  ptr = newPropertySetHashMap.ptr_;
  if ( !newPropertySetHashMap.ptr_ )
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x1Eu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIPropertySetHashMapFactory.hpp",
      -2147024882,
      "Make");
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&newPropertySetHashMap);
    return v23;
  }
  while ( 1 )
  {
    if ( !apisetEnumerationResults )
    {
      *propertySetHashMap = ptr;
      return 0;
    }
    lookupValue._pI = 0;
    v9 = -1;
    lookupValue._hrState = 0;
    Name = apisetEnumerationResults->Name;
    do
      ++v9;
    while ( Name[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(Name, v9, &key._header, &key._hstring);
    p_lookupValue = &lookupValue;
    v11 = v4->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable;
    v30 = 0;
    v12 = v11->Lookup(v4, key._hstring, &v30);
    v13 = v30;
    v14 = p_lookupValue;
    LODWORD(newPropertySetHashMap.ptr_) = v12;
    if ( v30 )
    {
      v15 = v30->__vftable;
      v28 = 0;
      v16 = v15->QueryInterface(v30, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, (void **)&v28);
      v17 = v16;
      if ( v16 < 0 )
      {
        if ( v16 == -2147467262 )
        {
          v18 = v13;
          v17 = 3;
        }
        else
        {
          v13->Release(v13);
          v18 = 0;
        }
      }
      else
      {
        v18 = v28;
        v13->Release(v13);
        v17 = 7;
      }
    }
    else
    {
      v18 = 0;
      v17 = 0;
    }
    pI = v14->_pI;
    v14->_pI = v18;
    hrState = v14->_hrState;
    v14->_hrState = v17;
    if ( pI && ((hrState - 3) & 0xFFFFFFFB) == 0 )
      pI->Release(pI);
    v21 = (HRESULT)newPropertySetHashMap.ptr_;
    if ( SLODWORD(newPropertySetHashMap.ptr_) < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x2Cu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIPropertySetHashMapFactory.hpp",
        (HRESULT)newPropertySetHashMap.ptr_,
        "Lookup %ws",
        apisetEnumerationResults->Name);
      goto LABEL_22;
    }
    replaced[0] = 0;
    v21 = ptr->Insert(ptr, key._hstring, lookupValue._pI, replaced);
    if ( v21 < 0 )
      break;
    apisetEnumerationResults = (const tag_STATE_ENUM_ITEM *)apisetEnumerationResults->pNext;
    v4 = v27;
    if ( lookupValue._pI )
    {
      if ( ((lookupValue._hrState - 3) & 0xFFFFFFFB) == 0 )
        ((void (*)(void))lookupValue._pI->Release)();
    }
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x32u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\StateABIPropertySetHashMapFactory.hpp",
    v21,
    "Insert %ws",
    apisetEnumerationResults->Name);
LABEL_22:
  if ( lookupValue._pI && ((lookupValue._hrState - 3) & 0xFFFFFFFB) == 0 )
    ((void (*)(void))lookupValue._pI->Release)();
  if ( ptr )
    ptr->Release(ptr);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18000d190  mov     [rsp-8+arg_18], rbx
0x18000d195  push    rbp
0x18000d196  push    rsi
0x18000d197  push    rdi
0x18000d198  push    r12
0x18000d19a  push    r13
0x18000d19c  push    r14
0x18000d19e  push    r15
0x18000d1a0  lea     rbp, [rsp-27h]
0x18000d1a5  sub     rsp, 0A0h
0x18000d1ac  mov     rax, cs:__security_cookie
0x18000d1b3  xor     rax, rsp
0x18000d1b6  mov     [rbp+57h+var_40], rax
0x18000d1ba  xor     r12d, r12d
0x18000d1bd  mov     [rbp+57h+var_80], propertySetServer
0x18000d1c1  mov     r13, propertySetHashMap
0x18000d1c4  mov     r15, propertySetServer
0x18000d1c7  mov     rsi, apisetEnumerationResults
0x18000d1ca  test    propertySetHashMap, propertySetHashMap
0x18000d1cd  jz      loc_18000D45D
0x18000d1d3  lea     apisetEnumerationResults, [rbp+57h+newPropertySetHashMap]; this
0x18000d1d7  mov     [propertySetHashMap], r12
0x18000d1da  mov     [rbp+57h+newPropertySetHashMap.ptr_], r12
0x18000d1de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000d1e3  lea     propertySetHashMap, [rbp+57h+newPropertySetHashMap]; fnEquals
0x18000d1e7  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>> * *)
0x18000d1ec  mov     rbx, [rbp+57h+newPropertySetHashMap.ptr_]
0x18000d1f0  test    rbx, rbx
0x18000d1f3  jz      loc_18000D47C
0x18000d1f9  mov     eax, 0FFFFFFFFh
0x18000d1fe  test    rsi, rsi
0x18000d201  jz      loc_18000D431
0x18000d207  mov     [rbp+57h+lookupValue._pI], r12
0x18000d20b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d20f  mov     [rbp+57h+lookupValue._hrState], r12d
0x18000d213  mov     r14, [rsi+8]
0x18000d217  inc     rdi
0x18000d21a  cmp     [r14+rdi*2], r12w
0x18000d21f  jnz     short loc_18000D217
0x18000d221  cmp     rdi, rax
0x18000d224  jbe     short loc_18000D23D
0x18000d226  xor     r9d, r9d; lpArguments
0x18000d229  xor     r8d, r8d; nNumberOfArguments
0x18000d22c  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000d231  mov     edi, eax
0x18000d233  lea     edx, [r9+1]; dwExceptionFlags
0x18000d237  call    cs:__imp_RaiseException
0x18000d23d  lea     r9, [rbp+57h+key]; string
0x18000d241  mov     edx, edi; length
0x18000d243  lea     propertySetHashMap, [rbp+57h+key._header]; hstringHeader
0x18000d247  mov     apisetEnumerationResults, r14; sourceString
0x18000d24a  call    cs:__imp_WindowsCreateStringReference
0x18000d250  mov     propertySetServer, [rbp+57h+key._hstring]
0x18000d254  lea     rax, [rbp+57h+lookupValue]
0x18000d258  mov     [rbp+57h+var_70], rax
0x18000d25c  lea     propertySetHashMap, [rbp+57h+var_68]
0x18000d260  mov     rax, [r15]
0x18000d263  mov     apisetEnumerationResults, r15
0x18000d266  mov     [rbp+57h+var_68], r12
0x18000d26a  mov     rax, [rax+30h]
0x18000d26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d273  mov     r14, [rbp+57h+var_68]
0x18000d277  mov     r12, [rbp+57h+var_70]
0x18000d27b  mov     dword ptr [rbp+57h+newPropertySetHashMap.ptr_], eax
0x18000d27e  test    r14, r14
0x18000d281  jz      loc_18000D439
0x18000d287  mov     rax, [r14]
0x18000d28a  lea     propertySetHashMap, [rbp+57h+var_78]
0x18000d28e  lea     propertySetServer, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18000d295  mov     [rbp+57h+var_78], 0
0x18000d29d  mov     apisetEnumerationResults, r14
0x18000d2a0  mov     rax, [rax]
0x18000d2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2a8  mov     edi, eax
0x18000d2aa  test    eax, eax
0x18000d2ac  js      loc_18000D376
0x18000d2b2  mov     rax, [r14]
0x18000d2b5  mov     apisetEnumerationResults, r14
0x18000d2b8  mov     r15, [rbp+57h+var_78]
0x18000d2bc  mov     rax, [rax+10h]
0x18000d2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2c5  mov     edi, 7
0x18000d2ca  mov     apisetEnumerationResults, [r12]
0x18000d2ce  mov     r14d, 0FFFFFFFBh
0x18000d2d4  mov     [r12], r15
0x18000d2d8  mov     eax, [r12+8]
0x18000d2dd  mov     [r12+8], edi
0x18000d2e2  xor     r12d, r12d
0x18000d2e5  test    apisetEnumerationResults, apisetEnumerationResults
0x18000d2e8  jnz     short loc_18000D35D
0x18000d2ea  mov     edi, dword ptr [rbp+57h+newPropertySetHashMap.ptr_]
0x18000d2ed  test    edi, edi
0x18000d2ef  js      loc_18000D38E
0x18000d2f5  mov     propertySetHashMap, [rbp+57h+lookupValue._pI]
0x18000d2f9  lea     r9, [rbp+57h+replaced]
0x18000d2fd  mov     propertySetServer, [rbp+57h+key._hstring]
0x18000d301  mov     apisetEnumerationResults, rbx
0x18000d304  mov     [rbp+57h+replaced], r12b
0x18000d308  mov     rax, [rbx]
0x18000d30b  mov     rax, [rax+50h]
0x18000d30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d314  mov     edi, eax
0x18000d316  test    eax, eax
0x18000d318  js      loc_18000D443
0x18000d31e  mov     apisetEnumerationResults, [rbp+57h+lookupValue._pI]
0x18000d322  mov     eax, 0FFFFFFFFh
0x18000d327  mov     rsi, [rsi+10h]
0x18000d32b  mov     r15, [rbp+57h+var_80]
0x18000d32f  test    apisetEnumerationResults, apisetEnumerationResults
0x18000d332  jz      loc_18000D1FE
0x18000d338  mov     eax, [rbp+57h+lookupValue._hrState]
0x18000d33b  add     eax, 0FFFFFFFDh
0x18000d33e  test    r14d, eax
0x18000d341  mov     eax, 0FFFFFFFFh
0x18000d346  jnz     loc_18000D1FE
0x18000d34c  mov     rax, [apisetEnumerationResults]
0x18000d34f  mov     rax, [rax+10h]
0x18000d353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d358  jmp     loc_18000D1F9
0x18000d35d  add     eax, 0FFFFFFFDh
0x18000d360  test    r14d, eax
0x18000d363  jnz     short loc_18000D2EA
0x18000d365  mov     rax, [apisetEnumerationResults]
0x18000d368  mov     rax, [rax+10h]
0x18000d36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d371  jmp     loc_18000D2EA
0x18000d376  cmp     eax, 80004002h
0x18000d37b  jnz     loc_18000D41A
0x18000d381  mov     r15, r14
0x18000d384  mov     edi, 3
0x18000d389  jmp     loc_18000D2CA
0x18000d38e  mov     rax, [rsi+8]
0x18000d392  mov     edx, 2Ch ; ','; lineNumber
0x18000d397  mov     [rsp+0D0h+var_A8], rax
0x18000d39c  lea     rax, aLookupWs; "Lookup %ws"
0x18000d3a3  mov     apisetEnumerationResults, [rbp+5Fh]; callerReturnAddress
0x18000d3a7  lea     propertySetHashMap, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000d3ae  mov     r9d, edi; hr
0x18000d3b1  mov     [rsp+0D0h+formatString], rax; formatString
0x18000d3b6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000d3bb  mov     apisetEnumerationResults, [rbp+57h+lookupValue._pI]
0x18000d3bf  test    apisetEnumerationResults, apisetEnumerationResults
0x18000d3c2  jnz     short loc_18000D401
0x18000d3c4  test    rbx, rbx
0x18000d3c7  jz      short loc_18000D3D8
0x18000d3c9  mov     rax, [rbx]
0x18000d3cc  mov     apisetEnumerationResults, rbx
0x18000d3cf  mov     rax, [rax+10h]
0x18000d3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3d8  mov     eax, edi
0x18000d3da  mov     apisetEnumerationResults, [rbp+57h+var_40]
0x18000d3de  xor     apisetEnumerationResults, rsp; StackCookie
0x18000d3e1  call    __security_check_cookie
0x18000d3e6  mov     rbx, [rsp+0D0h+arg_18]
0x18000d3ee  add     rsp, 0A0h
0x18000d3f5  pop     r15
0x18000d3f7  pop     r14
0x18000d3f9  pop     r13
0x18000d3fb  pop     r12
0x18000d3fd  pop     rdi
0x18000d3fe  pop     rsi
0x18000d3ff  pop     rbp
0x18000d400  retn
0x18000d401  mov     eax, [rbp+57h+lookupValue._hrState]
0x18000d404  add     eax, 0FFFFFFFDh
0x18000d407  test    r14d, eax
0x18000d40a  jnz     short loc_18000D3C4
0x18000d40c  mov     rax, [apisetEnumerationResults]
0x18000d40f  mov     rax, [rax+10h]
0x18000d413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d418  jmp     short loc_18000D3C4
0x18000d41a  mov     rax, [r14]
0x18000d41d  mov     apisetEnumerationResults, r14
0x18000d420  mov     rax, [rax+10h]
0x18000d424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d429  xor     r15d, r15d
0x18000d42c  jmp     loc_18000D2CA
0x18000d431  mov     [r13+0], rbx
0x18000d435  xor     eax, eax
0x18000d437  jmp     short loc_18000D3DA
0x18000d439  xor     r15d, r15d
0x18000d43c  xor     edi, edi
0x18000d43e  jmp     loc_18000D2CA
0x18000d443  mov     rax, [rsi+8]
0x18000d447  mov     edx, 32h ; '2'
0x18000d44c  mov     [rsp+0D0h+var_A8], rax
0x18000d451  lea     rax, aInsertWs; "Insert %ws"
0x18000d458  jmp     loc_18000D3A3
0x18000d45d  mov     apisetEnumerationResults, [rbp+5Fh]; callerReturnAddress
0x18000d461  lea     propertySetHashMap, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000d468  mov     ebx, 80070057h
0x18000d46d  mov     edx, 19h; lineNumber
0x18000d472  mov     r9d, ebx; hr
0x18000d475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d47a  jmp     short loc_18000D4AE
0x18000d47c  mov     apisetEnumerationResults, [rbp+5Fh]; callerReturnAddress
0x18000d480  lea     rax, aMake; "Make"
0x18000d487  mov     ebx, 8007000Eh
0x18000d48c  mov     [rsp+0D0h+formatString], rax; formatString
0x18000d491  mov     r9d, ebx; hr
0x18000d494  lea     propertySetHashMap, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000d49b  mov     edx, 1Eh; lineNumber
0x18000d4a0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000d4a5  lea     apisetEnumerationResults, [rbp+57h+newPropertySetHashMap]; this
0x18000d4a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000d4ae  mov     eax, ebx
0x18000d4b0  jmp     loc_18000D3DA
```
