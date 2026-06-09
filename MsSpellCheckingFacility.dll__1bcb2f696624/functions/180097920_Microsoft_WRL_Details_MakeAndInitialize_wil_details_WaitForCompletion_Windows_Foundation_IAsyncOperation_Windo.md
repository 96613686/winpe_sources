# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180097920`
- end: `0x180097a6f`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180097e90`

## callees

- `0x180044fbc`
- `0x18004a920`
- `0x18004a954`
- `0x18004aa2c`
- `0x18004d0b4`
- `0x18006183c`
- `0x180073ad4`
- `0x180097920`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800979f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800979e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800979e6`

## string_xrefs

- `0x180097a52`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v10; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v10 = v2;
    v11 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
      v3 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(&v11);
  return v3;
}

```

## disassembly

```asm
0x180097920  mov     [rsp+arg_10], rbx
0x180097925  push    rbp
0x180097926  push    rsi
0x180097927  push    rdi; int
0x180097928  sub     rsp, 20h
0x18009792c  mov     rsi, rcx
0x18009792f  mov     qword ptr [rcx], 0
0x180097936  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009793d  mov     ecx, 40h ; '@'; unsigned __int64
0x180097942  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180097947  mov     rbx, rax
0x18009794a  mov     [rsp+38h+arg_8], rax
0x18009794f  test    rax, rax
0x180097952  jnz     short loc_18009795E
0x180097954  mov     edi, 8007000Eh
0x180097959  jmp     loc_180097A26
0x18009795e  lea     rax, ??_7?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable'
0x180097965  mov     [rbx], rax
0x180097968  lea     rdi, [rbx+8]
0x18009796c  mov     rcx, rdi; this
0x18009796f  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180097974  mov     dword ptr [rbx+2Ch], 1
0x18009797b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x180097982  mov     [rbx], rax
0x180097985  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18009798c  mov     [rdi], rax
0x18009798f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180097996  test    rcx, rcx
0x180097999  jz      short loc_1800979A8
0x18009799b  mov     rax, [rcx]
0x18009799e  mov     rax, [rax+8]
0x1800979a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800979a7  nop
0x1800979a8  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x1800979af  mov     [rbx], rax
0x1800979b2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800979b9  mov     [rdi], rax
0x1800979bc  mov     dword ptr [rbx+30h], 0
0x1800979c3  mov     qword ptr [rbx+38h], 0
0x1800979cb  mov     [rsp+38h+arg_0], rbx
0x1800979d0  mov     [rsp+38h+arg_8], 0
0x1800979d9  mov     r9d, 1F0003h; dwDesiredAccess
0x1800979df  xor     r8d, r8d; dwFlags
0x1800979e2  xor     edx, edx; lpName
0x1800979e4  xor     ecx, ecx; lpEventAttributes
0x1800979e6  call    cs:__imp_CreateEventExW
0x1800979ec  mov     rbp, rax
0x1800979ef  test    rax, rax
0x1800979f2  jz      short loc_180097A3F
0x1800979f4  call    cs:__imp_GetLastError
0x1800979fa  mov     rdx, rbp
0x1800979fd  lea     rcx, [rbx+38h]
0x180097a01  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180097a06  nop
0x180097a07  mov     rax, [rbx]
0x180097a0a  mov     rcx, rbx
0x180097a0d  mov     rax, [rax+8]
0x180097a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a16  nop
0x180097a17  mov     [rsi], rbx
0x180097a1a  lea     rcx, [rsp+38h+arg_0]
0x180097a1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097a24  xor     edi, edi
0x180097a26  lea     rcx, [rsp+38h+arg_8]
0x180097a2b  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_88f340da8e3d9318e274dc95da2b1a9f_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(void)
0x180097a30  mov     eax, edi
0x180097a32  mov     rbx, [rsp+38h+arg_10]
0x180097a37  add     rsp, 20h
0x180097a3b  pop     rdi
0x180097a3c  pop     rsi
0x180097a3d  pop     rbp
0x180097a3e  retn
0x180097a3f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180097a44  mov     edi, eax
0x180097a46  test    eax, eax
0x180097a48  jns     short loc_180097A07
0x180097a4a  mov     rcx, [rsp+38h]; this
0x180097a4f  mov     r9d, eax; char *
0x180097a52  lea     r8, aOnecoreInterna_10; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180097a59  mov     edx, 62Bh; void *
0x180097a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097a63  lea     rcx, [rsp+38h+arg_0]
0x180097a68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097a6d  jmp     short loc_180097A26
```
