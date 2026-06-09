# MediaFramePropertySetImpl::MediaFramePropertySetImpl(Microsoft::WRL::ComPtr<IMFSample> const &,bool)

- ea: `0x180009760`
- end: `0x180009ae8`
- name: `??0MediaFramePropertySetImpl@@QEAA@AEBV?$ComPtr@UIMFSample@@@WRL@Microsoft@@_N@Z`
- size: `904`
- prototype: `__int64 __fastcall(MediaFramePropertySetImpl *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006620`

## callees

- `0x180009760`
- `0x18000a820`
- `0x18000a8ac`
- `0x18000a930`
- `0x18000a9b0`
- `0x18000ab50`
- `0x18000ab80`
- `0x18000ac30`
- `0x18000b090`
- `0x180026920`
- `0x180026e0c`
- `0x18002749c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009a8b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009a8b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009885`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009892`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800098a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009961`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009885`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009892`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800098a0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800099e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800099e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009a1b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009a1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
MediaFramePropertySetImpl *__fastcall MediaFramePropertySetImpl::MediaFramePropertySetImpl(
        MediaFramePropertySetImpl *this,
        __int64 *a2,
        char a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  RTL_SRWLOCK *v9; // rax
  RTL_SRWLOCK *v10; // rdi
  _DWORD *v11; // rax
  int v12; // ebp
  HRESULT StringReference; // eax
  __int64 v14; // rdi
  __int64 v15; // rcx
  int ActivationFactory; // eax
  void **pExceptionObject; // [rsp+28h] [rbp-80h] BYREF
  int v19; // [rsp+30h] [rbp-78h]
  __int128 v20; // [rsp+38h] [rbp-70h]
  void **hstringHeader; // [rsp+48h] [rbp-60h] BYREF
  int hstringHeader_8; // [rsp+50h] [rbp-58h]
  __int128 hstringHeader_16; // [rsp+58h] [rbp-50h] BYREF

  Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(this);
  Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(v6 + 16);
  Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>((char *)this + 24);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 16));
  *((_QWORD *)this + 10) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  *((_QWORD *)this + 1) = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  *((_QWORD *)this + 3) = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IPropertySet'};
  *((_QWORD *)this + 5) = &MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_BYTE *)this + 88) = a3;
  *((_BYTE *)this + 89) = 0;
  v8 = *a2;
  *((_QWORD *)this + 12) = *a2;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  InitializeSRWLock((PSRWLOCK)this + 16);
  InitializeSRWLock((PSRWLOCK)this + 17);
  InitializeSRWLock((PSRWLOCK)this + 18);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease((char *)this + 104);
  *((_QWORD *)this + 13) = 0;
  v9 = (RTL_SRWLOCK *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    v12 = -2147024882;
    goto LABEL_8;
  }
  Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>(v9);
  v10->Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'};
  v10[1].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>'};
  v10[2].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'};
  v10[3].Ptr = &Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v10[9].Ptr = v10;
  v10[10].Ptr = 0;
  v10[11].Ptr = 0;
  LODWORD(v10[12].Ptr) = 17;
  v10[14].Ptr = (PVOID)0xFFFFFFFFLL;
  v10[15].Ptr = 0;
  LODWORD(v10[16].Ptr) = 0;
  HIDWORD(v10[16].Ptr) = 10;
  v10[17].Ptr = 0;
  v10[18].Ptr = 0;
  HIDWORD(v10[12].Ptr) = 1061158912;
  LODWORD(v10[13].Ptr) = 1048576000;
  HIDWORD(v10[13].Ptr) = 1074790400;
  XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(&v10[9]);
  LODWORD(v10[20].Ptr) = 0;
  InitializeSRWLock(v10 + 21);
  v10[22].Ptr = 0;
  LOBYTE(v10[23].Ptr) = 0;
  HIDWORD(v10[23].Ptr) = 0;
  v11 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v11 )
  {
    *v11 = 1;
    v10[22].Ptr = v11;
    LOBYTE(v10[23].Ptr) = 1;
    *((_QWORD *)this + 13) = v10;
    v12 = 0;
LABEL_8:
    v10 = 0;
    goto LABEL_9;
  }
  v10[22].Ptr = 0;
  v12 = -2147024882;
LABEL_9:
  if ( v10 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v10->Ptr + 2))(v10);
  if ( v12 < 0 )
  {
LABEL_20:
    hstringHeader = &_com_error::`vftable';
    hstringHeader_8 = v12;
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
    goto LABEL_20;
  }
  v14 = *((_QWORD *)&hstringHeader_16 + 1);
  v15 = *((_QWORD *)this + 14);
  if ( v15 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  ActivationFactory = RoGetActivationFactory(v14, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, (char *)this + 112);
  if ( ActivationFactory < 0 )
  {
    pExceptionObject = &_com_error::`vftable';
    v19 = ActivationFactory;
    v20 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  MediaFramePropertySetImpl::ReadMfSample(this);
  return this;
}

```

## disassembly

```asm
0x180009760  push    rbx
0x180009762  push    rbp
0x180009763  push    rsi
0x180009764  push    rdi
0x180009765  push    r14
0x180009767  push    r15
0x180009769  sub     rsp, 78h
0x18000976d  mov     rax, cs:__security_cookie
0x180009774  xor     rax, rsp
0x180009777  mov     [rsp+0A8h+var_40], rax
0x18000977c  movzx   esi, r8b
0x180009780  mov     r14, rdx
0x180009783  mov     rbx, rcx
0x180009786  mov     [rsp+0A8h+var_88], rcx
0x18000978b  call    ??0?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>::IMap<HSTRING__ *,IInspectable *>(void)
0x180009790  add     rcx, 10h
0x180009794  call    ??0?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>(void)
0x180009799  lea     rcx, [rbx+18h]
0x18000979d  call    ??0?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@QEAA@XZ; Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::IKeyValuePair<HSTRING__ *,IInspectable *>(void)
0x1800097a2  add     rcx, 10h; this
0x1800097a6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800097ab  mov     qword ptr [rbx+50h], 1
0x1800097b3  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x1800097ba  mov     [rbx], rax
0x1800097bd  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x1800097c4  mov     [rbx+8], rax
0x1800097c8  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x1800097cf  mov     [rbx+10h], rax
0x1800097d3  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x1800097da  mov     [rbx+18h], rax
0x1800097de  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6BIPropertySet@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x1800097e5  mov     [rbx+20h], rax
0x1800097e9  lea     rax, ??_7?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@234@UIPropertySet@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800097f0  mov     [rbx+28h], rax
0x1800097f4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800097fb  test    rcx, rcx
0x1800097fe  jz      short loc_18000980D
0x180009800  mov     rax, [rcx]
0x180009803  mov     rax, [rax+8]
0x180009807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000980c  nop
0x18000980d  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x180009814  mov     [rbx], rax
0x180009817  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@678@UIPropertySet@678@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x18000981e  mov     [rbx+8], rax
0x180009822  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x180009829  mov     [rbx+10h], rax
0x18000982d  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@UIPropertySet@567@VFtmBase@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Microsoft::WRL::FtmBase>'}
0x180009834  mov     [rbx+18h], rax
0x180009838  lea     rax, ??_7MediaFramePropertySetImpl@@6BIPropertySet@Collections@Foundation@Windows@@@; const MediaFramePropertySetImpl::`vftable'{for `Windows::Foundation::Collections::IPropertySet'}
0x18000983f  mov     [rbx+20h], rax
0x180009843  lea     rax, ??_7MediaFramePropertySetImpl@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const MediaFramePropertySetImpl::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000984a  mov     [rbx+28h], rax
0x18000984e  mov     [rbx+58h], sil
0x180009852  mov     byte ptr [rbx+59h], 0
0x180009856  mov     rcx, [r14]
0x180009859  mov     [rbx+60h], rcx
0x18000985d  test    rcx, rcx
0x180009860  jz      short loc_18000986F
0x180009862  mov     rax, [rcx]
0x180009865  mov     rax, [rax+8]
0x180009869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000986e  nop
0x18000986f  xor     r15d, r15d
0x180009872  mov     [rbx+68h], r15
0x180009876  mov     [rbx+70h], r15
0x18000987a  mov     [rbx+78h], r15
0x18000987e  lea     rcx, [rbx+80h]; SRWLock
0x180009885  call    cs:__imp_InitializeSRWLock
0x18000988b  lea     rcx, [rbx+88h]; SRWLock
0x180009892  call    cs:__imp_InitializeSRWLock
0x180009898  nop
0x180009899  lea     rcx, [rbx+90h]; SRWLock
0x1800098a0  call    cs:__imp_InitializeSRWLock
0x1800098a6  lea     rcx, [rbx+68h]
0x1800098aa  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>::InternalRelease(void)
0x1800098af  mov     [rbx+68h], r15
0x1800098b3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800098ba  mov     ecx, 0C0h; unsigned __int64
0x1800098bf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800098c4  mov     rdi, rax
0x1800098c7  test    rax, rax
0x1800098ca  jz      loc_180009A60
0x1800098d0  mov     rcx, rax
0x1800098d3  call    ??0?$RuntimeClass@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>::RuntimeClass<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>(void)
0x1800098d8  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@234@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>'}
0x1800098df  mov     [rdi], rax
0x1800098e2  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Microsoft::WRL::FtmBase>'}
0x1800098e9  mov     [rdi+8], rax
0x1800098ed  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@234@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>'}
0x1800098f4  mov     [rdi+10h], rax
0x1800098f8  lea     rax, ??_7?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800098ff  mov     [rdi+18h], rax
0x180009903  lea     rcx, [rdi+48h]
0x180009907  mov     [rcx], rdi
0x18000990a  mov     [rcx+8], r15
0x18000990e  mov     [rcx+10h], r15
0x180009912  mov     dword ptr [rcx+18h], 11h
0x180009919  mov     eax, 0FFFFFFFFh
0x18000991e  mov     [rcx+28h], rax
0x180009922  mov     [rcx+30h], r15
0x180009926  mov     [rcx+38h], r15d
0x18000992a  mov     dword ptr [rcx+3Ch], 0Ah
0x180009931  mov     [rcx+40h], r15
0x180009935  mov     [rcx+48h], r15
0x180009939  mov     dword ptr [rcx+1Ch], 3F400000h
0x180009940  mov     dword ptr [rcx+20h], 3E800000h
0x180009947  mov     dword ptr [rcx+24h], 40100000h
0x18000994e  call    ?UpdateRehashThresholds@?$XHashMap@PEAUHSTRING__@@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@V?$GitStorageType@UIInspectable@@@detail@XWinRT@@@4@@XWinRT@@AEAAXXZ; XWinRT::XHashMap<HSTRING__ *,XWinRT::detail::GitStorageType<IInspectable>,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::KeyTraits,XWinRT::CElementTraits<XWinRT::detail::GitStorageType<IInspectable>>>::UpdateRehashThresholds(void)
0x180009953  mov     [rdi+0A0h], r15d
0x18000995a  lea     rcx, [rdi+0A8h]; SRWLock
0x180009961  call    cs:__imp_InitializeSRWLock
0x180009967  mov     [rdi+0B0h], r15
0x18000996e  mov     [rdi+0B8h], r15b
0x180009975  mov     [rdi+0BCh], r15d
0x18000997c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009983  mov     ecx, 4; unsigned __int64
0x180009988  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000998d  test    rax, rax
0x180009990  jz      loc_180009A4F
0x180009996  mov     dword ptr [rax], 1
0x18000999c  mov     [rdi+0B0h], rax
0x1800099a3  mov     byte ptr [rdi+0B8h], 1
0x1800099aa  mov     [rbx+68h], rdi
0x1800099ae  mov     ebp, r15d
0x1800099b1  mov     rdi, r15
0x1800099b4  test    rdi, rdi
0x1800099b7  jnz     loc_180009A6A
0x1800099bd  test    ebp, ebp
0x1800099bf  js      loc_180009A92
0x1800099c5  mov     [rsp+0A8h+string], r15
0x1800099ca  lea     r9, [rsp+0A8h+string]; string
0x1800099cf  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x1800099d4  mov     edx, 20h ; ' '; length
0x1800099d9  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1800099e0  call    cs:__imp_WindowsCreateStringReference
0x1800099e6  test    eax, eax
0x1800099e8  js      loc_180009A7E
0x1800099ee  mov     rdi, [rsp+0A8h+string]
0x1800099f3  mov     rcx, [rbx+70h]
0x1800099f7  test    rcx, rcx
0x1800099fa  jz      short loc_180009A0D
0x1800099fc  mov     [rbx+70h], r15
0x180009a00  mov     rax, [rcx]
0x180009a03  mov     rax, [rax+10h]
0x180009a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a0c  nop
0x180009a0d  lea     r8, [rbx+70h]
0x180009a11  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x180009a18  mov     rcx, rdi
0x180009a1b  call    cs:__imp_RoGetActivationFactory
0x180009a21  test    eax, eax
0x180009a23  js      loc_180009ABD
0x180009a29  mov     rcx, rbx; this
0x180009a2c  call    ?ReadMfSample@MediaFramePropertySetImpl@@AEAAXXZ; MediaFramePropertySetImpl::ReadMfSample(void)
0x180009a31  nop
0x180009a32  mov     rax, rbx
0x180009a35  mov     rcx, [rsp+0A8h+var_40]
0x180009a3a  xor     rcx, rsp; StackCookie
0x180009a3d  call    __security_check_cookie
0x180009a42  add     rsp, 78h
0x180009a46  pop     r15
0x180009a48  pop     r14
0x180009a4a  pop     rdi
0x180009a4b  pop     rsi
0x180009a4c  pop     rbp
0x180009a4d  pop     rbx
0x180009a4e  retn
0x180009a4f  mov     [rdi+0B0h], r15
0x180009a56  mov     ebp, 8007000Eh
0x180009a5b  jmp     loc_1800099B4
0x180009a60  mov     ebp, 8007000Eh
0x180009a65  jmp     loc_1800099B1
0x180009a6a  mov     rax, [rdi]
0x180009a6d  mov     rcx, rdi
0x180009a70  mov     rax, [rax+10h]
0x180009a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a79  jmp     loc_1800099BD
0x180009a7e  xor     r9d, r9d; lpArguments
0x180009a81  xor     r8d, r8d; nNumberOfArguments
0x180009a84  mov     edx, 1; dwExceptionFlags
0x180009a89  mov     ecx, eax; dwExceptionCode
0x180009a8b  call    cs:__imp_RaiseException
0x180009a91  nop
0x180009a92  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180009a99  mov     qword ptr [rsp+0A8h+hstringHeader.Reserved], rcx
0x180009a9e  mov     dword ptr [rsp+0A8h+hstringHeader.Reserved+8], ebp
0x180009aa2  xorps   xmm0, xmm0
0x180009aa5  movdqu  xmmword ptr [rsp+0A8h+hstringHeader.Reserved+10h], xmm0
0x180009aab  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180009ab2  lea     rcx, [rsp+0A8h+hstringHeader]; pExceptionObject
0x180009ab7  call    _CxxThrowException_0
0x180009abd  lea     rcx, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180009ac4  mov     [rsp+0A8h+pExceptionObject], rcx
0x180009ac9  mov     [rsp+0A8h+var_78], eax
0x180009acd  xorps   xmm0, xmm0
0x180009ad0  movdqu  [rsp+0A8h+var_70], xmm0
0x180009ad6  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180009add  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180009ae2  call    _CxxThrowException_0
```
