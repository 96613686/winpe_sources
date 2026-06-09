# Microsoft::WRL::Details::Make<MediaFramePropertySetImpl,Microsoft::WRL::ComPtr<IMFSample> const &,bool &>(Microsoft::WRL::ComPtr<IMFSample> const &,bool &)

- ea: `0x18000ac60`
- end: `0x18000b07d`
- name: `??$Make@VMediaFramePropertySetImpl@@AEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@AEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMediaFramePropertySetImpl@@@12@AEBV?$ComPtr@UIMFSample@@@12@AEA_N@Z`
- size: `1053`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180009090`
- `0x1800093d4`

## callees

- `0x1800095c0`
- `0x18000a820`
- `0x18000a8ac`
- `0x18000a930`
- `0x18000a9b0`
- `0x18000ab50`
- `0x18000ab80`
- `0x18000ac30`
- `0x18000ac60`
- `0x18000b090`
- `0x180026920`
- `0x180026e0c`
- `0x180026e30`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b015`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b015`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000add5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ade2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000adf0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000aeb1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000add5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ade2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000adf0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000aeb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000af36`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000af74`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000af74`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
RTL_SRWLOCK **__fastcall Microsoft::WRL::Details::Make<MediaFramePropertySetImpl,Microsoft::WRL::ComPtr<IMFSample> const &,bool &>(
        RTL_SRWLOCK **a1,
        PVOID *a2,
        char *a3)
{
  RTL_SRWLOCK *v6; // rax
  RTL_SRWLOCK *v7; // rbx
  char v8; // bp
  __int64 v9; // rcx
  __int64 v10; // rcx
  PVOID v11; // rcx
  RTL_SRWLOCK *v12; // rax
  RTL_SRWLOCK *v13; // rdi
  _DWORD *v14; // rax
  int v15; // ebp
  HRESULT StringReference; // eax
  __int64 v17; // rdi
  PVOID Ptr; // rcx
  int ActivationFactory; // eax
  void **pExceptionObject; // [rsp+48h] [rbp-70h] BYREF
  int v22; // [rsp+50h] [rbp-68h]
  __int128 v23; // [rsp+58h] [rbp-60h]
  void **hstringHeader; // [rsp+68h] [rbp-50h] BYREF
  int hstringHeader_8; // [rsp+70h] [rbp-48h]
  __int128 hstringHeader_16; // [rsp+78h] [rbp-40h] BYREF

  *a1 = 0;
  v6 = (RTL_SRWLOCK *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
    goto LABEL_20;
  v8 = *a3;
  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(v6);
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(v9 + 16);
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>(&v7[3]);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v10 + 16));
  v7[10].Ptr = (PVOID)1;
  v7->Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v7[1].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v7[2].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v7[3].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v7[4].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  v7[5].Ptr = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  v7->Ptr = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v7[1].Ptr = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v7[2].Ptr = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v7[3].Ptr = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  v7[4].Ptr = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  v7[5].Ptr = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  LOBYTE(v7[11].Ptr) = v8;
  BYTE1(v7[11].Ptr) = 0;
  v11 = *a2;
  v7[12].Ptr = *a2;
  if ( v11 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v11 + 8LL))(v11);
  v7[13].Ptr = 0;
  v7[14].Ptr = 0;
  v7[15].Ptr = 0;
  InitializeSRWLock(v7 + 16);
  InitializeSRWLock(v7 + 17);
  InitializeSRWLock(v7 + 18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(&v7[13]);
  v7[13].Ptr = 0;
  v12 = (RTL_SRWLOCK *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( !v12 )
  {
    v15 = -2147024882;
    goto LABEL_9;
  }
  Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>(v12);
  v13->Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v13[1].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>'};
  v13[2].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v13[3].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v13[9].Ptr = v13;
  v13[10].Ptr = 0;
  v13[11].Ptr = 0;
  LODWORD(v13[12].Ptr) = 17;
  v13[14].Ptr = (PVOID)0xFFFFFFFFLL;
  v13[15].Ptr = 0;
  LODWORD(v13[16].Ptr) = 0;
  HIDWORD(v13[16].Ptr) = 10;
  v13[17].Ptr = 0;
  v13[18].Ptr = 0;
  HIDWORD(v13[12].Ptr) = 1061158912;
  LODWORD(v13[13].Ptr) = 1048576000;
  HIDWORD(v13[13].Ptr) = 1074790400;
  XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(&v13[9]);
  LODWORD(v13[20].Ptr) = 0;
  InitializeSRWLock(v13 + 21);
  v13[22].Ptr = 0;
  LOBYTE(v13[23].Ptr) = 0;
  HIDWORD(v13[23].Ptr) = 0;
  v14 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 )
  {
    *v14 = 1;
    v13[22].Ptr = v14;
    LOBYTE(v13[23].Ptr) = 1;
    v7[13].Ptr = v13;
    v15 = 0;
LABEL_9:
    v13 = 0;
    goto LABEL_10;
  }
  v13[22].Ptr = 0;
  v15 = -2147024882;
LABEL_10:
  if ( v13 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v13->Ptr + 2))(v13);
  if ( v15 < 0 )
  {
LABEL_26:
    hstringHeader = &_com_error::`vftable';
    hstringHeader_8 = v15;
    hstringHeader_16 = 0;
    throw (_com_error *)&hstringHeader;
  }
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Foundation.PropertyValue",
                      0x20u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    goto LABEL_26;
  }
  v17 = *((_QWORD *)&hstringHeader_16 + 1);
  Ptr = v7[14].Ptr;
  if ( Ptr )
  {
    v7[14].Ptr = 0;
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 16LL))(Ptr);
  }
  ActivationFactory = RoGetActivationFactory(v17, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v7[14]);
  if ( ActivationFactory < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v22 = ActivationFactory;
    v23 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  MediaFramePropertySetImpl::ReadMfSample((MediaFramePropertySetImpl *)v7);
  if ( *a1 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(*a1);
  *a1 = v7;
  v7 = 0;
LABEL_20:
  if ( v7 )
    operator delete(v7);
  return a1;
}

```

## disassembly

```asm
0x18000ac60  mov     [rsp+arg_8], rbx
0x18000ac65  mov     [rsp+arg_10], rbp
0x18000ac6a  push    rsi
0x18000ac6b  push    rdi
0x18000ac6c  push    r12
0x18000ac6e  push    r14
0x18000ac70  push    r15
0x18000ac72  sub     rsp, 90h
0x18000ac79  mov     rax, cs:__security_cookie
0x18000ac80  xor     rax, rsp
0x18000ac83  mov     [rsp+0B8h+var_30], rax
0x18000ac8b  mov     rdi, r8
0x18000ac8e  mov     r14, rdx
0x18000ac91  mov     rsi, rcx
0x18000ac94  mov     [rsp+0B8h+var_90], rcx
0x18000ac99  xor     r12d, r12d
0x18000ac9c  mov     [rsp+0B8h+var_98], r12d
0x18000aca1  mov     [rcx], r12
0x18000aca4  mov     [rsp+0B8h+var_98], 1
0x18000acac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000acb3  mov     ecx, 98h; unsigned __int64
0x18000acb8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000acbd  mov     rbx, rax
0x18000acc0  mov     [rsp+0B8h+var_88], rax
0x18000acc5  mov     [rsp+0B8h+var_80], rax
0x18000acca  test    rax, rax
0x18000accd  jz      loc_18000AF9D
0x18000acd3  mov     [rsp+0B8h+var_78], rax
0x18000acd8  movzx   ebp, byte ptr [rdi]
0x18000acdb  mov     rcx, rax
0x18000acde  call    ??0?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(void)
0x18000ace3  lea     rcx, [rcx+10h]
0x18000ace7  call    ??0?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(void)
0x18000acec  lea     rcx, [rbx+18h]
0x18000acf0  call    ??0?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>(void)
0x18000acf5  add     rcx, 10h; this
0x18000acf9  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000acfe  mov     qword ptr [rbx+50h], 1
0x18000ad06  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x18000ad0d  mov     [rbx], rax
0x18000ad10  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x18000ad17  mov     [rbx+8], rax
0x18000ad1b  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x18000ad22  mov     [rbx+10h], rax
0x18000ad26  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x18000ad2d  mov     [rbx+18h], rax
0x18000ad31  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIPropertySet@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x18000ad38  mov     [rbx+20h], rax
0x18000ad3c  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ad43  mov     [rbx+28h], rax
0x18000ad47  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ad4e  test    rcx, rcx
0x18000ad51  jz      short loc_18000AD60
0x18000ad53  mov     rax, [rcx]
0x18000ad56  mov     rax, [rax+8]
0x18000ad5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5f  nop
0x18000ad60  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x18000ad67  mov     [rbx], rax
0x18000ad6a  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x18000ad71  mov     [rbx+8], rax
0x18000ad75  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x18000ad7c  mov     [rbx+10h], rax
0x18000ad80  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x18000ad87  mov     [rbx+18h], rax
0x18000ad8b  lea     rax, ??_7MediaFramePropertySetImpl@@6BIPropertySet@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x18000ad92  mov     [rbx+20h], rax
0x18000ad96  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ad9d  mov     [rbx+28h], rax
0x18000ada1  mov     [rbx+58h], bpl
0x18000ada5  mov     byte ptr [rbx+59h], 0
0x18000ada9  mov     rcx, [r14]
0x18000adac  mov     [rbx+60h], rcx
0x18000adb0  test    rcx, rcx
0x18000adb3  jz      short loc_18000ADC2
0x18000adb5  mov     rax, [rcx]
0x18000adb8  mov     rax, [rax+8]
0x18000adbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc1  nop
0x18000adc2  mov     [rbx+68h], r12
0x18000adc6  mov     [rbx+70h], r12
0x18000adca  mov     [rbx+78h], r12
0x18000adce  lea     rcx, [rbx+80h]; SRWLock
0x18000add5  call    cs:__imp_InitializeSRWLock
0x18000addb  lea     rcx, [rbx+88h]; SRWLock
0x18000ade2  call    cs:__imp_InitializeSRWLock
0x18000ade8  nop
0x18000ade9  lea     rcx, [rbx+90h]; SRWLock
0x18000adf0  call    cs:__imp_InitializeSRWLock
0x18000adf6  lea     rcx, [rbx+68h]
0x18000adfa  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x18000adff  mov     [rbx+68h], r12
0x18000ae03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ae0a  mov     ecx, 0C0h; unsigned __int64
0x18000ae0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ae14  mov     rdi, rax
0x18000ae17  test    rax, rax
0x18000ae1a  jz      loc_18000AFEA
0x18000ae20  mov     rcx, rax
0x18000ae23  call    ??0?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>(void)
0x18000ae28  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@234@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x18000ae2f  mov     [rdi], rax
0x18000ae32  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>'}
0x18000ae39  mov     [rdi+8], rax
0x18000ae3d  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x18000ae44  mov     [rdi+10h], rax
0x18000ae48  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ae4f  mov     [rdi+18h], rax
0x18000ae53  lea     rcx, [rdi+48h]
0x18000ae57  mov     [rcx], rdi
0x18000ae5a  mov     [rcx+8], r12
0x18000ae5e  mov     [rcx+10h], r12
0x18000ae62  mov     dword ptr [rcx+18h], 11h
0x18000ae69  mov     eax, 0FFFFFFFFh
0x18000ae6e  mov     [rcx+28h], rax
0x18000ae72  mov     [rcx+30h], r12
0x18000ae76  mov     [rcx+38h], r12d
0x18000ae7a  mov     dword ptr [rcx+3Ch], 0Ah
0x18000ae81  mov     [rcx+40h], r12
0x18000ae85  mov     [rcx+48h], r12
0x18000ae89  mov     dword ptr [rcx+1Ch], 3F400000h
0x18000ae90  mov     dword ptr [rcx+20h], 3E800000h
0x18000ae97  mov     dword ptr [rcx+24h], 40100000h
0x18000ae9e  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(void)
0x18000aea3  mov     [rdi+0A0h], r12d
0x18000aeaa  lea     rcx, [rdi+0A8h]; SRWLock
0x18000aeb1  call    cs:__imp_InitializeSRWLock
0x18000aeb7  mov     [rdi+0B0h], r12
0x18000aebe  mov     byte ptr [rdi+0B8h], 0
0x18000aec5  mov     [rdi+0BCh], r12d
0x18000aecc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aed3  mov     ecx, 4; unsigned __int64
0x18000aed8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aedd  test    rax, rax
0x18000aee0  jz      loc_18000AFD9
0x18000aee6  mov     dword ptr [rax], 1
0x18000aeec  mov     [rdi+0B0h], rax
0x18000aef3  mov     byte ptr [rdi+0B8h], 1
0x18000aefa  mov     [rbx+68h], rdi
0x18000aefe  mov     ebp, r12d
0x18000af01  mov     rdi, r12
0x18000af04  test    rdi, rdi
0x18000af07  jnz     loc_18000AFF4
0x18000af0d  test    ebp, ebp
0x18000af0f  js      loc_18000B01C
0x18000af15  mov     [rsp+0B8h+string], r12
0x18000af1d  lea     r9, [rsp+0B8h+string]; string
0x18000af25  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x18000af2a  mov     edx, 20h ; ' '; length
0x18000af2f  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18000af36  call    cs:__imp_WindowsCreateStringReference
0x18000af3c  test    eax, eax
0x18000af3e  js      loc_18000B008
0x18000af44  mov     rdi, [rsp+0B8h+string]
0x18000af4c  mov     rcx, [rbx+70h]
0x18000af50  test    rcx, rcx
0x18000af53  jz      short loc_18000AF66
0x18000af55  mov     [rbx+70h], r12
0x18000af59  mov     rax, [rcx]
0x18000af5c  mov     rax, [rax+10h]
0x18000af60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af65  nop
0x18000af66  lea     r8, [rbx+70h]
0x18000af6a  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18000af71  mov     rcx, rdi
0x18000af74  call    cs:__imp_RoGetActivationFactory
0x18000af7a  test    eax, eax
0x18000af7c  js      loc_18000B047
0x18000af82  mov     rcx, rbx; this
0x18000af85  call    ?ReadMfSample@MediaFramePropertySetImpl@@AEAAXXZ; MediaFramePropertySetImpl::ReadMfSample(void)
0x18000af8a  nop
0x18000af8b  mov     rcx, [rsi]
0x18000af8e  test    rcx, rcx
0x18000af91  jnz     loc_18000B072
0x18000af97  mov     [rsi], rbx
0x18000af9a  mov     rbx, r12
0x18000af9d  test    rbx, rbx
0x18000afa0  jz      short loc_18000AFAA
0x18000afa2  mov     rcx, rbx; Block
0x18000afa5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000afaa  mov     rax, rsi
0x18000afad  mov     rcx, [rsp+0B8h+var_30]
0x18000afb5  xor     rcx, rsp; StackCookie
0x18000afb8  call    __security_check_cookie
0x18000afbd  lea     r11, [rsp+0B8h+var_28]
0x18000afc5  mov     rbx, [r11+38h]
0x18000afc9  mov     rbp, [r11+40h]
0x18000afcd  mov     rsp, r11
0x18000afd0  pop     r15
0x18000afd2  pop     r14
0x18000afd4  pop     r12
0x18000afd6  pop     rdi
0x18000afd7  pop     rsi
0x18000afd8  retn
0x18000afd9  mov     [rdi+0B0h], r12
0x18000afe0  mov     ebp, 8007000Eh
0x18000afe5  jmp     loc_18000AF04
0x18000afea  mov     ebp, 8007000Eh
0x18000afef  jmp     loc_18000AF01
0x18000aff4  mov     rax, [rdi]
0x18000aff7  mov     rcx, rdi
0x18000affa  mov     rax, [rax+10h]
0x18000affe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b003  jmp     loc_18000AF0D
0x18000b008  xor     r9d, r9d; lpArguments
0x18000b00b  xor     r8d, r8d; nNumberOfArguments
0x18000b00e  mov     edx, 1; dwExceptionFlags
0x18000b013  mov     ecx, eax; dwExceptionCode
0x18000b015  call    cs:__imp_RaiseException
0x18000b01b  nop
0x18000b01c  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000b023  mov     qword ptr [rsp+0B8h+hstringHeader.Reserved], rcx
0x18000b028  mov     dword ptr [rsp+0B8h+hstringHeader.Reserved+8], ebp
0x18000b02c  xorps   xmm0, xmm0
0x18000b02f  movdqu  xmmword ptr [rsp+0B8h+hstringHeader.Reserved+10h], xmm0
0x18000b035  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000b03c  lea     rcx, [rsp+0B8h+hstringHeader]; pExceptionObject
0x18000b041  call    _CxxThrowException_0
0x18000b047  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000b04e  mov     [rsp+0B8h+pExceptionObject], rcx
0x18000b053  mov     [rsp+0B8h+var_68], eax
0x18000b057  xorps   xmm0, xmm0
0x18000b05a  movdqu  [rsp+0B8h+var_60], xmm0
0x18000b060  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18000b067  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18000b06c  call    _CxxThrowException_0
0x18000b072  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@567@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@567@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::Release(void)
0x18000b077  jmp     loc_18000AF97
```
