# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::Make(HSTRING__ * const &,Windows::Storage::IApplicationDataContainer * const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> * *)

- ea: `0x18000c8bc`
- end: `0x18000ca02`
- name: `?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBQEAUIApplicationDataContainer@Storage@5@PEAPEAV12345@@Z`
- size: `326`
- prototype: `HRESULT __fastcall(HSTRING__ *const *key, Windows::Storage::IApplicationDataContainer *const *value, Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> **ppPair)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030f30`

## callees

- `0x180006804`
- `0x18000c8bc`
- `0x18000ce40`
- `0x1800254e8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000c966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000c966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c9c2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::Make(
        HSTRING *key,
        Windows::Storage::IApplicationDataContainer **value,
        Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> **ppPair)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *v6; // rax
  Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> *v7; // rbx
  Microsoft::WRL::Details::ModuleBase *v8; // rcx
  HRESULT v9; // edi
  Windows::Storage::IApplicationDataContainer *v10; // rsi
  HSTRING v11; // rcx
  Windows::Storage::IApplicationDataContainer *v12; // rdx
  HSTRING newString; // [rsp+50h] [rbp+18h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> > v15; // [rsp+58h] [rbp+20h] BYREF

  *ppPair = 0;
  v15.ptr_ = 0;
  v6 = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *)operator new(0x30u, &std::nothrow);
  v7 = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0> *)v6;
  if ( v6 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(v6);
    v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Foundation::Internal::AggregateType<Windows::Storage::ApplicationDataContainer *,Windows::Storage::IApplicationDataContainer *> >::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'};
    v8 = Microsoft::WRL::Details::ModuleBase::module_;
    v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
    if ( v8 )
      v8->IncrementObjectCount(v8);
    v15.ptr_ = v7;
    v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Foundation::Internal::AggregateType<Windows::Storage::ApplicationDataContainer *,Windows::Storage::IApplicationDataContainer *> >::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'};
    v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
    v7->_sKey._value = 0;
    v7->_sValue._value = 0;
    v9 = WindowsDuplicateString(*key, &newString);
    if ( v9 < 0 )
    {
      v11 = 0;
      newString = 0;
    }
    else
    {
      v10 = *value;
      if ( v10 )
        v10->AddRef(v10);
      v11 = v7->_sKey._value;
      v9 = 0;
      v7->_sKey._value = newString;
      v12 = v7->_sValue._value;
      newString = v11;
      v7->_sValue._value = v10;
      if ( v12 )
      {
        v12->Release(v12);
        v11 = newString;
      }
    }
    WindowsDeleteString(v11);
    if ( v9 >= 0 )
    {
      v15.ptr_ = 0;
      *ppPair = v7;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c8bc  mov     [rsp+arg_0], rbx
0x18000c8c1  push    rsi
0x18000c8c2  push    rdi
0x18000c8c3  push    r14
0x18000c8c5  sub     rsp, 20h
0x18000c8c9  mov     rsi, value
0x18000c8cc  mov     qword ptr [ppPair], 0
0x18000c8d3  mov     rdi, key
0x18000c8d6  mov     [rsp+38h+arg_18.ptr_], 0
0x18000c8df  lea     value, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x18000c8e6  mov     ecx, 30h ; '0'; count
0x18000c8eb  mov     r14, ppPair
0x18000c8ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c8f3  mov     rbx, rax
0x18000c8f6  test    rax, rax
0x18000c8f9  jz      loc_18000C9F2
0x18000c8ff  mov     key, rax; this
0x18000c902  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(void)
0x18000c907  lea     key, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'}
0x18000c90e  mov     [rbx], key
0x18000c911  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000c918  mov     key, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c91f  mov     [rbx+8], rax
0x18000c923  test    key, key
0x18000c926  jz      short loc_18000C934
0x18000c928  mov     rax, [key]
0x18000c92b  mov     rax, [rax+8]
0x18000c92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c934  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@234@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>'}
0x18000c93b  mov     [rsp+38h+arg_18.ptr_], rbx
0x18000c940  mov     [rbx], rax
0x18000c943  lea     value, [rsp+38h+newString]; newString
0x18000c948  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000c94f  mov     [rbx+8], rax
0x18000c953  mov     qword ptr [rbx+20h], 0
0x18000c95b  mov     qword ptr [rbx+28h], 0
0x18000c963  mov     key, [rdi]; string
0x18000c966  call    cs:__imp_WindowsDuplicateString
0x18000c96c  mov     edi, eax
0x18000c96e  test    eax, eax
0x18000c970  js      loc_18000C9F9
0x18000c976  mov     rsi, [rsi]
0x18000c979  test    rsi, rsi
0x18000c97c  jz      short loc_18000C98D
0x18000c97e  mov     rax, [rsi]
0x18000c981  mov     key, rsi
0x18000c984  mov     rax, [rax+8]
0x18000c988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c98d  mov     key, [rbx+20h]
0x18000c991  xor     edi, edi
0x18000c993  mov     rax, [rsp+38h+newString]
0x18000c998  mov     [rbx+20h], rax
0x18000c99c  mov     value, [rbx+28h]
0x18000c9a0  mov     [rsp+38h+newString], key
0x18000c9a5  mov     [rbx+28h], rsi
0x18000c9a9  test    value, value
0x18000c9ac  jz      short loc_18000C9C2
0x18000c9ae  mov     rax, [value]
0x18000c9b1  mov     key, value
0x18000c9b4  mov     rax, [rax+10h]
0x18000c9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9bd  mov     key, [rsp+38h+newString]; string
0x18000c9c2  call    cs:__imp_WindowsDeleteString
0x18000c9c8  test    edi, edi
0x18000c9ca  js      short loc_18000C9D8
0x18000c9cc  mov     [rsp+38h+arg_18.ptr_], 0
0x18000c9d5  mov     [r14], rbx
0x18000c9d8  lea     key, [rsp+38h+arg_18]; this
0x18000c9dd  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplicationDataContainer@Storage@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::ApplicationDataContainer *>,0>>::InternalRelease(void)
0x18000c9e2  mov     rbx, [rsp+38h+arg_0]
0x18000c9e7  mov     eax, edi
0x18000c9e9  add     rsp, 20h
0x18000c9ed  pop     r14
0x18000c9ef  pop     rdi
0x18000c9f0  pop     rsi
0x18000c9f1  retn
0x18000c9f2  mov     edi, 8007000Eh
0x18000c9f7  jmp     short loc_18000C9D8
0x18000c9f9  xor     ecx, ecx
0x18000c9fb  mov     [rsp+38h+newString], key
0x18000ca00  jmp     short loc_18000C9C2
```
