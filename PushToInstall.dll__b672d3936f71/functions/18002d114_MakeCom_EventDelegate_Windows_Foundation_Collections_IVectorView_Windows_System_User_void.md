# MakeCom<EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,>(void)

- ea: `0x18002d114`
- end: `0x18002d229`
- name: `??$MakeCom@V?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@$$V@@YA?AV?$ComPtr@V?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@@WRL@Microsoft@@XZ`
- size: `277`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d380`

## callees

- `0x18000d7a0`
- `0x18000dc43`
- `0x180021958`
- `0x18002d114`
- `0x18002de7c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d1c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d1c0`

## pseudocode

```c
_QWORD *__fastcall MakeCom<EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,>(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable';
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v2 + 2);
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'};
    *((_QWORD *)v2 + 1) = &EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'};
    *((_QWORD *)v2 + 1) = &EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_QWORD *)v2 + 7) = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v2 + 6) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v2;
  }
  if ( !*a1 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18002d114  mov     rax, rsp
0x18002d117  mov     [rax+10h], rbx
0x18002d11b  mov     [rax+18h], rsi
0x18002d11f  mov     [rax+8], rcx
0x18002d123  push    rdi
0x18002d124  sub     rsp, 40h
0x18002d128  mov     rdi, rcx
0x18002d12b  mov     dword ptr [rax-28h], 0
0x18002d132  mov     qword ptr [rcx], 0
0x18002d139  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d140  mov     ecx, 40h ; '@'; unsigned __int64
0x18002d145  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d14a  mov     rbx, rax
0x18002d14d  test    rax, rax
0x18002d150  jz      loc_18002D1EC
0x18002d156  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>::`vftable'
0x18002d15d  mov     [rbx], rax
0x18002d160  lea     rsi, [rbx+8]
0x18002d164  mov     rcx, rsi
0x18002d167  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x18002d16c  mov     dword ptr [rbx+2Ch], 1
0x18002d173  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x18002d17a  mov     [rbx], rax
0x18002d17d  lea     rax, ??_7?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002d184  mov     [rsi], rax
0x18002d187  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002d18e  test    rcx, rcx
0x18002d191  jz      short loc_18002D1A0
0x18002d193  mov     rax, [rcx]
0x18002d196  mov     rax, [rax+8]
0x18002d19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d19f  nop
0x18002d1a0  lea     rax, ??_7?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x18002d1a7  mov     [rbx], rax
0x18002d1aa  lea     rax, ??_7?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002d1b1  mov     [rsi], rax
0x18002d1b4  xor     r9d, r9d; lpName
0x18002d1b7  xor     r8d, r8d; bInitialState
0x18002d1ba  lea     edx, [r9+1]; bManualReset
0x18002d1be  xor     ecx, ecx; lpEventAttributes
0x18002d1c0  call    cs:__imp_CreateEventW
0x18002d1c6  mov     [rbx+38h], rax
0x18002d1ca  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002d1d1  mov     [rbx+30h], rax
0x18002d1d5  mov     rcx, [rdi]
0x18002d1d8  test    rcx, rcx
0x18002d1db  jz      short loc_18002D1E9
0x18002d1dd  mov     rax, [rcx]
0x18002d1e0  mov     rax, [rax+10h]
0x18002d1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1e9  mov     [rdi], rbx
0x18002d1ec  mov     [rsp+48h+var_28], 1
0x18002d1f4  cmp     qword ptr [rdi], 0
0x18002d1f8  jz      short loc_18002D20D
0x18002d1fa  mov     rax, rdi
0x18002d1fd  mov     rbx, [rsp+48h+arg_8]
0x18002d202  mov     rsi, [rsp+48h+arg_10]
0x18002d207  add     rsp, 40h
0x18002d20b  pop     rdi
0x18002d20c  retn
0x18002d20d  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002d212  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18002d217  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002d21e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002d223  call    _CxxThrowException_0
```
