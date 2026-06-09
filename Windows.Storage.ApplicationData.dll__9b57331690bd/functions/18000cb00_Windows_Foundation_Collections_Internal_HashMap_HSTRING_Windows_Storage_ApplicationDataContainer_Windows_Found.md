# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Iterator::get_Current(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> * *)

- ea: `0x18000cb00`
- end: `0x18000cd4c`
- name: `?get_Current@Iterator@?$HashMap@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@6784@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@@6784@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@456@@Z`
- size: `588`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::Iterator *this, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> **current)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006804`
- `0x18000cb00`
- `0x18000ce40`
- `0x18000cee0`
- `0x1800254e8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cb41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000cb41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ccc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ccc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cc08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cd37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cc63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cd37`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cce0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cd24`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cce0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000cd24`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Iterator::get_Current(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > >::Iterator *this,
        Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> **current)
{
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *> > > *ptr; // rbx
  _RTL_SRWLOCK *v5; // rsi
  XWinRT::TXPOSITION *volatile position; // r15
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *v7; // rax
  Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> *v8; // rdi
  Microsoft::WRL::Details::ModuleBase *v9; // rcx
  HRESULT v10; // ebp
  Windows::Storage::IApplicationDataContainer *v11; // r15
  HSTRING value; // rcx
  Windows::Storage::IApplicationDataContainer *v13; // rdx
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> > spPair; // [rsp+50h] [rbp+8h] BYREF
  HSTRING newString; // [rsp+58h] [rbp+10h] BYREF

  *current = 0;
  ptr = this->_spHashMap.ptr_;
  v5 = (_RTL_SRWLOCK *)&ptr->_comLock.8;
  if ( ptr->_comLock.kind == Kind_StaReentrancy )
  {
    if ( *(_DWORD *)&v5->0 >= 0 )
      ++*(_DWORD *)&v5->0;
  }
  else
  {
    AcquireSRWLockShared((PSRWLOCK)&ptr->_comLock.8);
  }
  if ( this->_spHashMap.ptr_->_versionManager._pTag == this->_expectedVersion._pVersion )
  {
    position = this->_position;
    if ( position )
    {
      spPair.ptr_ = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(&spPair);
      spPair.ptr_ = 0;
      v7 = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *)operator new(0x30u, &std::nothrow);
      v8 = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> *)v7;
      if ( v7 )
      {
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(v7);
        v8->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Foundation::Internal::AggregateType<Windows::Storage::ApplicationDataContainer *,Windows::Storage::IApplicationDataContainer *> >::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'};
        v9 = Microsoft::WRL::Details::ModuleBase::module_;
        v8->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
        if ( v9 )
          v9->IncrementObjectCount(v9);
        spPair.ptr_ = v8;
        v8->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Foundation::Internal::AggregateType<Windows::Storage::ApplicationDataContainer *,Windows::Storage::IApplicationDataContainer *> >::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'};
        v8->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
        v8->_sKey._value = 0;
        v8->_sValue._value = 0;
        v10 = WindowsDuplicateString(*(HSTRING *)position, &newString);
        if ( v10 < 0 )
        {
          newString = 0;
          WindowsDeleteString(0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(&spPair);
        }
        else
        {
          v11 = *(Windows::Storage::IApplicationDataContainer **)&position[8];
          if ( v11 )
            v11->AddRef(v11);
          value = v8->_sKey._value;
          v8->_sKey._value = newString;
          v13 = v8->_sValue._value;
          newString = value;
          v8->_sValue._value = v11;
          if ( v13 )
          {
            v13->Release(v13);
            value = newString;
          }
          WindowsDeleteString(value);
          spPair.ptr_ = 0;
          v10 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(&spPair);
          if ( v8 )
            v8->AddRef(v8);
          *current = v8;
          if ( v8 )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::Release(v8);
        }
      }
      else
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(&spPair);
        v10 = -2147024882;
      }
    }
    else
    {
      v10 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
  }
  else
  {
    v10 = -2147483636;
    RoOriginateError(2147483660LL, 0);
  }
  if ( ptr->_comLock.kind == Kind_StaReentrancy )
    --*(_DWORD *)&v5->0;
  else
    ReleaseSRWLockShared(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000cb00  push    rsi
0x18000cb02  sub     rsp, 40h
0x18000cb06  mov     [rsp+48h+arg_10], rbx
0x18000cb0b  mov     [rsp+48h+var_10], rdi
0x18000cb10  mov     rdi, this
0x18000cb13  mov     [rsp+48h+var_18], r12
0x18000cb18  xor     r12d, r12d
0x18000cb1b  mov     [current], r12
0x18000cb1e  mov     rbx, [this+20h]
0x18000cb22  mov     [rsp+48h+var_20], r14
0x18000cb27  mov     r14, current
0x18000cb2a  cmp     dword ptr [rbx+80h], 1
0x18000cb31  lea     rsi, [rbx+88h]
0x18000cb38  jz      loc_18000CCF7
0x18000cb3e  mov     this, rsi; SRWLock
0x18000cb41  call    cs:__imp_AcquireSRWLockShared
0x18000cb47  mov     this, [rdi+20h]
0x18000cb4b  mov     rax, [rdi+30h]
0x18000cb4f  mov     [rsp+48h+arg_18], rbp
0x18000cb54  cmp     [this+90h], rax
0x18000cb5b  jnz     loc_18000CCD7
0x18000cb61  mov     [rsp+48h+var_28], r15
0x18000cb66  mov     r15, [rdi+28h]
0x18000cb6a  test    r15, r15
0x18000cb6d  jz      loc_18000CD1B
0x18000cb73  lea     this, [rsp+48h+spPair]; this
0x18000cb78  mov     [rsp+48h+spPair.ptr_], r12
0x18000cb7d  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(void)
0x18000cb82  lea     current, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x18000cb89  mov     [rsp+48h+spPair.ptr_], r12
0x18000cb8e  mov     ecx, 30h ; '0'; count
0x18000cb93  mov     [rsp+48h+spPair.ptr_], r12
0x18000cb98  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cb9d  mov     rdi, rax
0x18000cba0  test    rax, rax
0x18000cba3  jz      loc_18000CD0A
0x18000cba9  mov     this, rax; this
0x18000cbac  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(void)
0x18000cbb1  lea     this, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'}
0x18000cbb8  mov     [rdi], this
0x18000cbbb  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000cbc2  mov     this, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000cbc9  mov     [rdi+8], rax
0x18000cbcd  test    this, this
0x18000cbd0  jz      short loc_18000CBDE
0x18000cbd2  mov     rax, [this]
0x18000cbd5  mov     rax, [rax+8]
0x18000cbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbde  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@234@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'}
0x18000cbe5  mov     [rsp+48h+spPair.ptr_], rdi
0x18000cbea  mov     [rdi], rax
0x18000cbed  lea     current, [rsp+48h+newString]; newString
0x18000cbf2  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000cbf9  mov     [rdi+8], rax
0x18000cbfd  mov     [rdi+20h], r12
0x18000cc01  mov     [rdi+28h], r12
0x18000cc05  mov     this, [r15]; string
0x18000cc08  call    cs:__imp_WindowsDuplicateString
0x18000cc0e  mov     ebp, eax
0x18000cc10  test    eax, eax
0x18000cc12  js      loc_18000CD2F
0x18000cc18  mov     r15, [r15+8]
0x18000cc1c  test    r15, r15
0x18000cc1f  jz      short loc_18000CC30
0x18000cc21  mov     rax, [r15]
0x18000cc24  mov     this, r15
0x18000cc27  mov     rax, [rax+8]
0x18000cc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc30  mov     this, [rdi+20h]
0x18000cc34  mov     rax, [rsp+48h+newString]
0x18000cc39  mov     [rdi+20h], rax
0x18000cc3d  mov     current, [rdi+28h]
0x18000cc41  mov     [rsp+48h+newString], this
0x18000cc46  mov     [rdi+28h], r15
0x18000cc4a  test    current, current
0x18000cc4d  jz      short loc_18000CC63
0x18000cc4f  mov     rax, [current]
0x18000cc52  mov     this, current
0x18000cc55  mov     rax, [rax+10h]
0x18000cc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc5e  mov     this, [rsp+48h+newString]; string
0x18000cc63  call    cs:__imp_WindowsDeleteString
0x18000cc69  lea     this, [rsp+48h+spPair]; this
0x18000cc6e  mov     [rsp+48h+spPair.ptr_], r12
0x18000cc73  mov     ebp, r12d
0x18000cc76  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(void)
0x18000cc7b  test    rdi, rdi
0x18000cc7e  jz      short loc_18000CC8F
0x18000cc80  mov     rax, [rdi]
0x18000cc83  mov     this, rdi
0x18000cc86  mov     rax, [rax+8]
0x18000cc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc8f  mov     [r14], rdi
0x18000cc92  test    rdi, rdi
0x18000cc95  jz      short loc_18000CC9F
0x18000cc97  mov     this, rdi; this
0x18000cc9a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::Release(void)
0x18000cc9f  mov     r15, [rsp+48h+var_28]
0x18000cca4  cmp     dword ptr [rbx+80h], 1
0x18000ccab  mov     rbx, [rsp+48h+arg_10]
0x18000ccb0  mov     r14, [rsp+48h+var_20]
0x18000ccb5  mov     r12, [rsp+48h+var_18]
0x18000ccba  mov     rdi, [rsp+48h+var_10]
0x18000ccbf  jz      short loc_18000CCE8
0x18000ccc1  mov     this, rsi; SRWLock
0x18000ccc4  call    cs:__imp_ReleaseSRWLockShared
0x18000ccca  mov     eax, ebp
0x18000cccc  mov     rbp, [rsp+48h+arg_18]
0x18000ccd1  add     rsp, 40h
0x18000ccd5  pop     rsi
0x18000ccd6  retn
0x18000ccd7  mov     ebp, 8000000Ch
0x18000ccdc  xor     edx, edx
0x18000ccde  mov     ecx, ebp
0x18000cce0  call    cs:__imp_RoOriginateError
0x18000cce6  jmp     short loc_18000CCA4
0x18000cce8  dec     dword ptr [rsi]
0x18000ccea  mov     eax, ebp
0x18000ccec  mov     rbp, [rsp+48h+arg_18]
0x18000ccf1  add     rsp, 40h
0x18000ccf5  pop     rsi
0x18000ccf6  retn
0x18000ccf7  mov     eax, [rsi]
0x18000ccf9  test    eax, eax
0x18000ccfb  js      loc_18000CB47
0x18000cd01  inc     eax
0x18000cd03  mov     [rsi], eax
0x18000cd05  jmp     loc_18000CB47
0x18000cd0a  lea     this, [rsp+48h+spPair]; this
0x18000cd0f  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(void)
0x18000cd14  mov     ebp, 8007000Eh
0x18000cd19  jmp     short loc_18000CC9F
0x18000cd1b  mov     ebp, 8000000Bh
0x18000cd20  xor     edx, edx
0x18000cd22  mov     ecx, ebp
0x18000cd24  call    cs:__imp_RoOriginateError
0x18000cd2a  jmp     loc_18000CC9F
0x18000cd2f  mov     this, r12; string
0x18000cd32  mov     [rsp+48h+newString], this
0x18000cd37  call    cs:__imp_WindowsDeleteString
0x18000cd3d  lea     this, [rsp+48h+spPair]; this
0x18000cd42  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(void)
0x18000cd47  jmp     loc_18000CC9F
```
