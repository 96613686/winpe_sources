# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Iterator::get_Current(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> * *)

- ea: `0x1800064c0`
- end: `0x1800066c9`
- name: `?get_Current@Iterator@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$00$0A@$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@456@@Z`
- size: `521`
- prototype: `HRESULT __fastcall(Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::Iterator *this, Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> **current)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800064c0`
- `0x180006804`
- `0x180006830`
- `0x1800254e8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006501`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006501`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000664d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000664d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800065aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800065aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800066b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180006605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800066b6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006669`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800066a3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006669`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800066a3`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0>>::Iterator::get_Current(
        Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> >::Iterator *this,
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > **current)
{
  Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,1,0,0> > *ptr; // rdi
  _RTL_SRWLOCK *v5; // rsi
  XWinRT::TXPOSITION *volatile position; // r15
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *v7; // rax
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *v8; // rbx
  Microsoft::WRL::Details::ModuleBase *v9; // rcx
  HRESULT v10; // ebp
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *v11; // r15
  HSTRING v12; // rcx
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *v13; // rdx
  HSTRING newString; // [rsp+50h] [rbp+8h] BYREF

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
      v7 = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *)operator new(0x30u, &std::nothrow);
      v8 = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> > *)v7;
      if ( v7 )
      {
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(v7);
        v8->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'};
        v9 = Microsoft::WRL::Details::ModuleBase::module_;
        v8->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
        if ( v9 )
          v9->IncrementObjectCount(v9);
        v8->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'};
        v8->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
        v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = 0;
        v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = 0;
        v10 = WindowsDuplicateString(*(HSTRING *)position, &newString);
        if ( v10 < 0 )
        {
          newString = 0;
          WindowsDeleteString(0);
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(v8);
        }
        else
        {
          v11 = *(Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl **)&position[8];
          if ( v11 )
            (*((void (__fastcall **)(Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *))v11->QueryInterface
             + 1))(v11);
          v12 = (HSTRING)v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable;
          v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >_vtbl *)newString;
          v13 = v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable;
          newString = v12;
          v8[1].Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = v11;
          if ( v13 )
          {
            (*((void (__fastcall **)(Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *))v13->QueryInterface
             + 2))(v13);
            v12 = newString;
          }
          WindowsDeleteString(v12);
          v10 = 0;
          v8->AddRef(v8);
          *current = v8;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(v8);
        }
      }
      else
      {
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
0x1800064c0  push    rsi
0x1800064c2  sub     rsp, 40h
0x1800064c6  mov     [rsp+48h+arg_8], rbx
0x1800064cb  mov     rbx, this
0x1800064ce  mov     [rsp+48h+var_10], rdi
0x1800064d3  mov     [rsp+48h+var_18], r12
0x1800064d8  xor     r12d, r12d
0x1800064db  mov     [current], r12
0x1800064de  mov     rdi, [this+20h]
0x1800064e2  mov     [rsp+48h+var_20], r14
0x1800064e7  mov     r14, current
0x1800064ea  cmp     dword ptr [rdi+88h], 1
0x1800064f1  lea     rsi, [rdi+90h]
0x1800064f8  jz      loc_180006680
0x1800064fe  mov     this, rsi; SRWLock
0x180006501  call    cs:__imp_AcquireSRWLockShared
0x180006507  mov     this, [rbx+20h]
0x18000650b  mov     rax, [rbx+30h]
0x18000650f  mov     [rsp+48h+arg_10], rbp
0x180006514  cmp     [this+98h], rax
0x18000651b  jnz     loc_180006660
0x180006521  mov     [rsp+48h+var_28], r15
0x180006526  mov     r15, [rbx+28h]
0x18000652a  test    r15, r15
0x18000652d  jz      loc_18000669A
0x180006533  lea     current, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x18000653a  mov     ecx, 30h ; '0'; count
0x18000653f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006544  mov     rbx, rax
0x180006547  test    rax, rax
0x18000654a  jz      loc_180006693
0x180006550  mov     this, rax; this
0x180006553  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(void)
0x180006558  lea     this, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'}
0x18000655f  mov     [rbx], this
0x180006562  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x180006569  mov     this, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006570  mov     [rbx+8], rax
0x180006574  test    this, this
0x180006577  jz      short loc_180006585
0x180006579  mov     rax, [this]
0x18000657c  mov     rax, [rax+8]
0x180006580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006585  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@234@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'}
0x18000658c  mov     [rbx], rax
0x18000658f  lea     current, [rsp+48h+newString]; newString
0x180006594  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000659b  mov     [rbx+8], rax
0x18000659f  mov     [rbx+20h], r12
0x1800065a3  mov     [rbx+28h], r12
0x1800065a7  mov     this, [r15]; string
0x1800065aa  call    cs:__imp_WindowsDuplicateString
0x1800065b0  mov     ebp, eax
0x1800065b2  test    eax, eax
0x1800065b4  js      loc_1800066AE
0x1800065ba  mov     r15, [r15+8]
0x1800065be  test    r15, r15
0x1800065c1  jz      short loc_1800065D2
0x1800065c3  mov     rax, [r15]
0x1800065c6  mov     this, r15
0x1800065c9  mov     rax, [rax+8]
0x1800065cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d2  mov     this, [rbx+20h]
0x1800065d6  mov     rax, [rsp+48h+newString]
0x1800065db  mov     [rbx+20h], rax
0x1800065df  mov     current, [rbx+28h]
0x1800065e3  mov     [rsp+48h+newString], this
0x1800065e8  mov     [rbx+28h], r15
0x1800065ec  test    current, current
0x1800065ef  jz      short loc_180006605
0x1800065f1  mov     rax, [current]
0x1800065f4  mov     this, current
0x1800065f7  mov     rax, [rax+10h]
0x1800065fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006600  mov     this, [rsp+48h+newString]; string
0x180006605  call    cs:__imp_WindowsDeleteString
0x18000660b  mov     rax, [rbx]
0x18000660e  mov     this, rbx
0x180006611  mov     ebp, r12d
0x180006614  mov     rax, [rax+8]
0x180006618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661d  mov     this, rbx; this
0x180006620  mov     [r14], rbx
0x180006623  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(void)
0x180006628  mov     r15, [rsp+48h+var_28]
0x18000662d  cmp     dword ptr [rdi+88h], 1
0x180006634  mov     rdi, [rsp+48h+var_10]
0x180006639  mov     r14, [rsp+48h+var_20]
0x18000663e  mov     r12, [rsp+48h+var_18]
0x180006643  mov     rbx, [rsp+48h+arg_8]
0x180006648  jz      short loc_180006671
0x18000664a  mov     this, rsi; SRWLock
0x18000664d  call    cs:__imp_ReleaseSRWLockShared
0x180006653  mov     eax, ebp
0x180006655  mov     rbp, [rsp+48h+arg_10]
0x18000665a  add     rsp, 40h
0x18000665e  pop     rsi
0x18000665f  retn
0x180006660  mov     ebp, 8000000Ch
0x180006665  xor     edx, edx
0x180006667  mov     ecx, ebp
0x180006669  call    cs:__imp_RoOriginateError
0x18000666f  jmp     short loc_18000662D
0x180006671  dec     dword ptr [rsi]
0x180006673  mov     eax, ebp
0x180006675  mov     rbp, [rsp+48h+arg_10]
0x18000667a  add     rsp, 40h
0x18000667e  pop     rsi
0x18000667f  retn
0x180006680  mov     eax, [rsi]
0x180006682  test    eax, eax
0x180006684  js      loc_180006507
0x18000668a  inc     eax
0x18000668c  mov     [rsi], eax
0x18000668e  jmp     loc_180006507
0x180006693  mov     ebp, 8007000Eh
0x180006698  jmp     short loc_180006628
0x18000669a  mov     ebp, 8000000Bh
0x18000669f  xor     edx, edx
0x1800066a1  mov     ecx, ebp
0x1800066a3  call    cs:__imp_RoOriginateError
0x1800066a9  jmp     loc_180006628
0x1800066ae  mov     this, r12; string
0x1800066b1  mov     [rsp+48h+newString], this
0x1800066b6  call    cs:__imp_WindowsDeleteString
0x1800066bc  mov     this, rbx; this
0x1800066bf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(void)
0x1800066c4  jmp     loc_180006628
```
