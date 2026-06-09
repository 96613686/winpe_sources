# Windows::Storage::ApplicationDataCompositeValueServer::Iterator::get_Current(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> * *)

- ea: `0x180006990`
- end: `0x180006c50`
- name: `?get_Current@Iterator@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@@Z`
- size: `704`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer::Iterator *this, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **current)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003820`
- `0x18000648c`
- `0x1800066d0`
- `0x180006910`
- `0x180006990`
- `0x180006c60`
- `0x180007580`
- `0x180009778`
- `0x18000c03c`
- `0x1800127c0`
- `0x180021efc`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800069dc`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800069dc`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800069d2`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800069d2`

## string_xrefs

- `0x180006b44`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x180006b94`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x180006bc2`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x180006c25`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Iterator::get_Current(
        Windows::Storage::ApplicationDataCompositeValueServer::Iterator *this,
        Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **current)
{
  Windows::Storage::ApplicationDataCompositeValueServer::Iterator_vtbl *v4; // rax
  HRESULT v5; // ebx
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *p_currentKeyValuePairInterface; // rbx
  Windows::Storage::ApplicationDataCompositeValueServer *ptr; // rcx
  Windows::Storage::ApplicationDataCompositeValueServer_vtbl *v8; // rax
  HRESULT v9; // r14d
  unsigned __int8 hasCurrent[8]; // [rsp+30h] [rbp-19h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> > newKeyValuePairInstance; // [rsp+38h] [rbp-11h] BYREF
  RoVariant lookupValue; // [rsp+40h] [rbp-9h] BYREF
  RoVariant *p_lookupValue; // [rsp+50h] [rbp+7h] BYREF
  IInspectable *pI; // [rsp+58h] [rbp+Fh] BYREF
  IInspectable *value; // [rsp+60h] [rbp+17h] BYREF
  Windows::Internal::StringReference key; // [rsp+68h] [rbp+1Fh] BYREF
  void *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( !current )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2F8u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      -2147024809);
    return (unsigned int)v5;
  }
  *current = 0;
  RtlAcquireSRWLockShared(&this->iteratorLock);
  RtlReleaseSRWLockShared(&this->iteratorLock);
  v4 = this->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,IWeakReferenceSource>::Windows::Foundation::Collections::IIterator<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::Windows::Foundation::Collections::IIterator_impl<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *,1>::IInspectable::IUnknown::__vftable;
  hasCurrent[0] = 0;
  v5 = v4->get_HasCurrent(this, hasCurrent);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x302u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v5,
      "get_HasCurrent");
    return (unsigned int)v5;
  }
  p_currentKeyValuePairInterface = &this->currentKeyValuePairInterface;
  if ( this->currentKeyValuePairInterface.ptr_ )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&this->currentKeyValuePairInterface);
    *current = p_currentKeyValuePairInterface->ptr_;
    return 0;
  }
  Windows::Internal::StringReference::_ConstructorHelper(&key, this->compositeEnumerationResultCurrent->Name);
  ptr = this->compositeServer.ptr_;
  lookupValue._pI = 0;
  lookupValue._hrState = 0;
  v8 = ptr->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IMap_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable;
  p_lookupValue = &lookupValue;
  pI = 0;
  v9 = v8->Lookup(ptr, key._hstring, &pI);
  RoVariant::Attach(p_lookupValue, pI);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x312u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v9,
      "Lookup %ws",
      this->compositeEnumerationResultCurrent->Name);
    if ( lookupValue._pI && ((lookupValue._hrState - 3) & 0xFFFFFFFB) == 0 )
      ((void (*)(void))lookupValue._pI->Release)();
  }
  else
  {
    newKeyValuePairInstance.ptr_ = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(&newKeyValuePairInstance);
    value = lookupValue._pI;
    p_lookupValue = (RoVariant *)key._hstring;
    v9 = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::Make(
           (HSTRING *)&p_lookupValue,
           &value,
           &newKeyValuePairInstance.ptr_);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x316u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v9,
        "Make %ws",
        this->compositeEnumerationResultCurrent->Name);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&this->currentKeyValuePairInterface);
      v9 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>>(
             newKeyValuePairInstance.ptr_,
             &GUID_09335560_6c6b_5a26_9348_97b781132b20,
             (void **)&this->currentKeyValuePairInterface.ptr_);
      if ( v9 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&this->currentKeyValuePairInterface);
        *current = p_currentKeyValuePairInterface->ptr_;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(&newKeyValuePairInstance);
        if ( lookupValue._pI )
        {
          if ( ((lookupValue._hrState - 3) & 0xFFFFFFFB) == 0 )
            ((void (*)(void))lookupValue._pI->Release)();
        }
        return 0;
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x319u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v9,
        "As %ws",
        this->compositeEnumerationResultCurrent->Name);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(&newKeyValuePairInstance);
    RoVariant::~RoVariant(&lookupValue);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006990  mov     [rsp-8+arg_10], rbx
0x180006995  mov     [rsp-8+arg_18], rsi
0x18000699a  push    rbp
0x18000699b  push    rdi
0x18000699c  push    r14
0x18000699e  lea     rbp, [rsp-47h]
0x1800069a3  sub     rsp, 90h
0x1800069aa  mov     rax, cs:__security_cookie
0x1800069b1  xor     rax, rsp
0x1800069b4  mov     [rbp+57h+var_18], rax
0x1800069b8  mov     rsi, current
0x1800069bb  mov     rdi, this
0x1800069be  test    current, current
0x1800069c1  jz      loc_180006B90
0x1800069c7  add     this, 28h ; '('
0x1800069cb  mov     qword ptr [current], 0
0x1800069d2  call    cs:__imp_RtlAcquireSRWLockShared
0x1800069d8  lea     this, [rdi+28h]
0x1800069dc  call    cs:__imp_RtlReleaseSRWLockShared
0x1800069e2  mov     rax, [rdi]
0x1800069e5  lea     current, [rbp+57h+hasCurrent]
0x1800069e9  mov     this, rdi
0x1800069ec  mov     [rbp+57h+hasCurrent], 0
0x1800069f0  mov     rax, [rax+38h]
0x1800069f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f9  mov     ebx, eax
0x1800069fb  test    eax, eax
0x1800069fd  js      loc_180006BAF
0x180006a03  lea     rbx, [rdi+40h]
0x180006a07  cmp     qword ptr [rbx], 0
0x180006a0b  jnz     loc_180006BDA
0x180006a11  mov     current, [rdi+38h]
0x180006a15  lea     this, [rbp+57h+key]; this
0x180006a19  mov     current, [current+8]; stringRef
0x180006a1d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180006a22  mov     this, [rdi+20h]
0x180006a26  lea     current, [rbp+57h+lookupValue]
0x180006a2a  mov     [rbp+57h+lookupValue._pI], 0
0x180006a32  lea     r8, [rbp+57h+pI]
0x180006a36  mov     [rbp+57h+lookupValue._hrState], 0
0x180006a3d  mov     rax, [this]
0x180006a40  mov     [rbp+57h+var_50], current
0x180006a44  mov     current, [rbp+57h+key._hstring]
0x180006a48  mov     [rbp+57h+pI], 0
0x180006a50  mov     rax, [rax+30h]
0x180006a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a59  mov     current, [rbp+57h+pI]; pI
0x180006a5d  mov     r14d, eax
0x180006a60  mov     this, [rbp+57h+var_50]; this
0x180006a64  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180006a69  test    r14d, r14d
0x180006a6c  js      loc_180006B36
0x180006a72  lea     this, [rbp+57h+newKeyValuePairInstance]; this
0x180006a76  mov     [rbp+57h+newKeyValuePairInstance.ptr_], 0
0x180006a7e  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x180006a83  mov     rax, [rbp+57h+lookupValue._pI]
0x180006a87  lea     r8, [rbp+57h+newKeyValuePairInstance]; ppPair
0x180006a8b  mov     [rbp+57h+value], rax
0x180006a8f  lea     current, [rbp+57h+value]; value
0x180006a93  mov     rax, [rbp+57h+key._hstring]
0x180006a97  lea     this, [rbp+57h+var_50]; key
0x180006a9b  mov     [rbp+57h+var_50], rax
0x180006a9f  call    ?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::Make(HSTRING__ * const &,IInspectable * const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> * *)
0x180006aa4  mov     r14d, eax
0x180006aa7  test    eax, eax
0x180006aa9  js      loc_180006BED
0x180006aaf  mov     this, rbx; this
0x180006ab2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180006ab7  mov     this, [rbp+57h+newKeyValuePairInstance.ptr_]; implements
0x180006abb  lea     current, _GUID_09335560_6c6b_5a26_9348_97b781132b20; riid
0x180006ac2  mov     r8, rbx; ppvObject
0x180006ac5  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>> *,_GUID const &,void * *)
0x180006aca  mov     r14d, eax
0x180006acd  test    eax, eax
0x180006acf  js      loc_180006C08
0x180006ad5  mov     this, rbx; this
0x180006ad8  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef(void)
0x180006add  mov     rax, [rbx]
0x180006ae0  lea     this, [rbp+57h+newKeyValuePairInstance]; this
0x180006ae4  mov     [rsi], rax
0x180006ae7  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x180006aec  mov     this, [rbp+57h+lookupValue._pI]
0x180006af0  test    this, this
0x180006af3  jnz     short loc_180006B1B
0x180006af5  xor     eax, eax
0x180006af7  mov     this, [rbp+57h+var_18]
0x180006afb  xor     this, rsp; StackCookie
0x180006afe  call    __security_check_cookie
0x180006b03  lea     r11, [rsp+0A0h+var_10]
0x180006b0b  mov     rbx, [r11+30h]
0x180006b0f  mov     rsi, [r11+38h]
0x180006b13  mov     rsp, r11
0x180006b16  pop     r14
0x180006b18  pop     rdi
0x180006b19  pop     rbp
0x180006b1a  retn
0x180006b1b  mov     eax, [rbp+57h+lookupValue._hrState]
0x180006b1e  add     eax, 0FFFFFFFDh
0x180006b21  test    eax, 0FFFFFFFBh
0x180006b26  jnz     short loc_180006AF5
0x180006b28  mov     rax, [this]
0x180006b2b  mov     rax, [rax+10h]
0x180006b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b34  jmp     short loc_180006AF5
0x180006b36  mov     this, [rdi+38h]
0x180006b3a  lea     rax, aLookupWs; "Lookup %ws"
0x180006b41  mov     r9d, r14d; hr
0x180006b44  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180006b4b  mov     current, [this+8]
0x180006b4f  mov     this, [rbp+5Fh]; callerReturnAddress
0x180006b53  mov     [rsp+0A0h+var_78], current
0x180006b58  mov     edx, 312h; lineNumber
0x180006b5d  mov     [rsp+0A0h+formatString], rax; formatString
0x180006b62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006b67  mov     this, [rbp+57h+lookupValue._pI]
0x180006b6b  test    this, this
0x180006b6e  jnz     short loc_180006B75
0x180006b70  mov     eax, r14d
0x180006b73  jmp     short loc_180006AF7
0x180006b75  mov     eax, [rbp+57h+lookupValue._hrState]
0x180006b78  add     eax, 0FFFFFFFDh
0x180006b7b  test    eax, 0FFFFFFFBh
0x180006b80  jnz     short loc_180006B70
0x180006b82  mov     rax, [this]
0x180006b85  mov     rax, [rax+10h]
0x180006b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b8e  jmp     short loc_180006B70
0x180006b90  mov     this, [rbp+5Fh]; callerReturnAddress
0x180006b94  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180006b9b  mov     ebx, 80070057h
0x180006ba0  mov     edx, 2F8h; lineNumber
0x180006ba5  mov     r9d, ebx; hr
0x180006ba8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bad  jmp     short loc_180006BD3
0x180006baf  mov     this, [rbp+5Fh]; callerReturnAddress
0x180006bb3  lea     rax, aGetHascurrent; "get_HasCurrent"
0x180006bba  mov     r9d, ebx; hr
0x180006bbd  mov     [rsp+0A0h+formatString], rax; formatString
0x180006bc2  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180006bc9  mov     edx, 302h; lineNumber
0x180006bce  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006bd3  mov     eax, ebx
0x180006bd5  jmp     loc_180006AF7
0x180006bda  mov     this, rbx; this
0x180006bdd  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef(void)
0x180006be2  mov     rax, [rbx]
0x180006be5  mov     [rsi], rax
0x180006be8  jmp     loc_180006AF5
0x180006bed  mov     this, [rdi+38h]
0x180006bf1  lea     rax, aMakeWs; "Make %ws"
0x180006bf8  mov     current, [this+8]
0x180006bfc  mov     [rsp+0A0h+var_78], current
0x180006c01  mov     edx, 316h
0x180006c06  jmp     short loc_180006C21
0x180006c08  mov     this, [rdi+38h]
0x180006c0c  lea     rax, aAsWs; "As %ws"
0x180006c13  mov     current, [this+8]
0x180006c17  mov     [rsp+0A0h+var_78], current
0x180006c1c  mov     edx, 319h; lineNumber
0x180006c21  mov     this, [rbp+5Fh]; callerReturnAddress
0x180006c25  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180006c2c  mov     r9d, r14d; hr
0x180006c2f  mov     [rsp+0A0h+formatString], rax; formatString
0x180006c34  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006c39  lea     this, [rbp+57h+newKeyValuePairInstance]; this
0x180006c3d  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x180006c42  lea     this, [rbp+57h+lookupValue]; this
0x180006c46  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180006c4b  jmp     loc_180006B70
```
