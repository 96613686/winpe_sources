# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::Make(HSTRING__ * const &,IInspectable * const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> * *)

- ea: `0x1800066d0`
- end: `0x1800067fc`
- name: `?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBQEAUIInspectable@@PEAPEAV12345@@Z`
- size: `300`
- prototype: `HRESULT __fastcall(HSTRING__ *const *key, IInspectable *const *value, Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> **ppPair)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006990`
- `0x18002b830`

## callees

- `0x1800066d0`
- `0x180006804`
- `0x180006830`
- `0x1800254e8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180006767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180006767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800067ea`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::Make(
        HSTRING *key,
        IInspectable **value,
        Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> **ppPair)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *v6; // rax
  Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> *v7; // rbx
  Microsoft::WRL::Details::ModuleBase *v8; // rcx
  HRESULT v9; // esi
  IInspectable *v10; // rsi
  HSTRING v11; // rcx
  IInspectable *v12; // rdx
  __int64 result; // rax
  HSTRING newString; // [rsp+50h] [rbp+18h] BYREF

  *ppPair = 0;
  v6 = (Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *> > *)operator new(0x30u, &std::nothrow);
  v7 = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> *)v6;
  if ( !v6 )
    return 2147942414LL;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(v6);
  v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'};
  v8 = Microsoft::WRL::Details::ModuleBase::module_;
  v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  if ( v8 )
    v8->IncrementObjectCount(v8);
  v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>::Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,IInspectable *>::IInspectable::IUnknown::__vftable = (Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'};
  v7->Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,IWeakReferenceSource>::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>::IWeakReferenceSource::IUnknown::__vftable = (Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>_vtbl *)Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  v7->_sKey._value = 0;
  v7->_sValue._value = 0;
  v9 = WindowsDuplicateString(*key, &newString);
  if ( v9 < 0 )
  {
    newString = 0;
    WindowsDeleteString(0);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(v7);
    return (unsigned int)v9;
  }
  else
  {
    v10 = *value;
    if ( *value )
      v10->AddRef(*value);
    v11 = v7->_sKey._value;
    v7->_sKey._value = newString;
    v12 = v7->_sValue._value;
    newString = v11;
    v7->_sValue._value = v10;
    if ( v12 )
    {
      v12->Release(v12);
      v11 = newString;
    }
    WindowsDeleteString(v11);
    result = 0;
    *ppPair = v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800066d0  mov     [rsp+arg_0], rbx
0x1800066d5  mov     [rsp+arg_8], rbp
0x1800066da  push    rsi
0x1800066db  push    rdi
0x1800066dc  push    r14
0x1800066de  sub     rsp, 20h
0x1800066e2  mov     r14, value
0x1800066e5  mov     rsi, key
0x1800066e8  xor     ebp, ebp
0x1800066ea  lea     value, ?nothrow@std@@3Unothrow_t@1@B; __formal
0x1800066f1  mov     ecx, 30h ; '0'; count
0x1800066f6  mov     [ppPair], rbp
0x1800066f9  mov     rdi, ppPair
0x1800066fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006701  mov     rbx, rax
0x180006704  test    rax, rax
0x180006707  jz      loc_1800067DB
0x18000670d  mov     key, rax; this
0x180006710  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>(void)
0x180006715  lea     key, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'}
0x18000671c  mov     [rbx], key
0x18000671f  lea     rax, ??_7?$RuntimeClass@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x180006726  mov     key, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000672d  mov     [rbx+8], rax
0x180006731  test    key, key
0x180006734  jz      short loc_180006742
0x180006736  mov     rax, [key]
0x180006739  mov     rax, [rax+8]
0x18000673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006742  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@6B?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@234@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>'}
0x180006749  mov     [rbx], rax
0x18000674c  lea     value, [rsp+38h+newString]; newString
0x180006751  lea     rax, ??_7?$SimpleKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@$0A@@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x180006758  mov     [rbx+8], rax
0x18000675c  mov     [rbx+20h], rbp
0x180006760  mov     [rbx+28h], rbp
0x180006764  mov     key, [rsi]; string
0x180006767  call    cs:__imp_WindowsDuplicateString
0x18000676d  mov     esi, eax
0x18000676f  test    eax, eax
0x180006771  js      short loc_1800067E2
0x180006773  mov     rsi, [r14]
0x180006776  test    rsi, rsi
0x180006779  jz      short loc_18000678A
0x18000677b  mov     rax, [rsi]
0x18000677e  mov     key, rsi
0x180006781  mov     rax, [rax+8]
0x180006785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678a  mov     key, [rbx+20h]
0x18000678e  mov     rax, [rsp+38h+newString]
0x180006793  mov     [rbx+20h], rax
0x180006797  mov     value, [rbx+28h]
0x18000679b  mov     [rsp+38h+newString], key
0x1800067a0  mov     [rbx+28h], rsi
0x1800067a4  test    value, value
0x1800067a7  jz      short loc_1800067BD
0x1800067a9  mov     rax, [value]
0x1800067ac  mov     key, value
0x1800067af  mov     rax, [rax+10h]
0x1800067b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b8  mov     key, [rsp+38h+newString]; string
0x1800067bd  call    cs:__imp_WindowsDeleteString
0x1800067c3  mov     eax, ebp
0x1800067c5  mov     [rdi], rbx
0x1800067c8  mov     rbx, [rsp+38h+arg_0]
0x1800067cd  mov     rbp, [rsp+38h+arg_8]
0x1800067d2  add     rsp, 20h
0x1800067d6  pop     r14
0x1800067d8  pop     rdi
0x1800067d9  pop     rsi
0x1800067da  retn
0x1800067db  mov     eax, 8007000Eh
0x1800067e0  jmp     short loc_1800067C8
0x1800067e2  mov     key, rbp; string
0x1800067e5  mov     [rsp+38h+newString], key
0x1800067ea  call    cs:__imp_WindowsDeleteString
0x1800067f0  mov     key, rbx; this
0x1800067f3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>>::Release(void)
0x1800067f8  mov     eax, esi
0x1800067fa  jmp     short loc_1800067C8
```
