# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18004e114`
- end: `0x18004e24c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004e460`

## callees

- `0x180003918`
- `0x18000b618`
- `0x18000be78`
- `0x180011ffc`
- `0x18004e114`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004e1dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004e1dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1ec`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserDataAccountStore_UserDataAccounts_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>'::`2'::FTMEventDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004e114  mov     [rsp+arg_10], rbx
0x18004e119  mov     [rsp+arg_18], rsi
0x18004e11e  push    rdi
0x18004e11f  sub     rsp, 20h
0x18004e123  mov     rsi, rcx
0x18004e126  mov     qword ptr [rcx], 0
0x18004e12d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004e134  mov     ecx, 40h ; '@'; unsigned __int64
0x18004e139  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004e13e  mov     rbx, rax
0x18004e141  mov     [rsp+28h+arg_8], rax
0x18004e146  test    rax, rax
0x18004e149  jnz     short loc_18004E155
0x18004e14b  mov     edi, 8007000Eh
0x18004e150  jmp     loc_18004E230
0x18004e155  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>::`vftable'
0x18004e15c  mov     [rbx], rax
0x18004e15f  lea     rdi, [rbx+8]
0x18004e163  mov     rcx, rdi; this
0x18004e166  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18004e16b  mov     dword ptr [rbx+2Ch], 1
0x18004e172  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>'}
0x18004e179  mov     [rbx], rax
0x18004e17c  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004e183  mov     [rdi], rax
0x18004e186  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004e18d  test    rcx, rcx
0x18004e190  jz      short loc_18004E19F
0x18004e192  mov     rax, [rcx]
0x18004e195  mov     rax, [rax+8]
0x18004e199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e19e  nop
0x18004e19f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>'}
0x18004e1a6  mov     [rbx], rax
0x18004e1a9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004e1b0  mov     [rdi], rax
0x18004e1b3  mov     dword ptr [rbx+30h], 0
0x18004e1ba  mov     qword ptr [rbx+38h], 0
0x18004e1c2  mov     [rsp+28h+arg_0], rbx
0x18004e1c7  mov     [rsp+28h+arg_8], 0
0x18004e1d0  mov     r9d, 1F0003h; dwDesiredAccess
0x18004e1d6  xor     r8d, r8d; dwFlags
0x18004e1d9  xor     edx, edx; lpName
0x18004e1db  xor     ecx, ecx; lpEventAttributes
0x18004e1dd  call    cs:__imp_CreateEventExW
0x18004e1e3  mov     [rbx+38h], rax
0x18004e1e7  test    rax, rax
0x18004e1ea  jnz     short loc_18004E211
0x18004e1ec  call    cs:__imp_GetLastError
0x18004e1f2  mov     edi, eax
0x18004e1f4  test    eax, eax
0x18004e1f6  jle     short loc_18004E201
0x18004e1f8  movzx   edi, ax
0x18004e1fb  or      edi, 80070000h
0x18004e201  test    edi, edi
0x18004e203  jns     short loc_18004E211
0x18004e205  lea     rcx, [rsp+28h+arg_0]
0x18004e20a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e20f  jmp     short loc_18004E230
0x18004e211  mov     rax, [rbx]
0x18004e214  mov     rcx, rbx
0x18004e217  mov     rax, [rax+8]
0x18004e21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e220  nop
0x18004e221  mov     [rsi], rbx
0x18004e224  lea     rcx, [rsp+28h+arg_0]
0x18004e229  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e22e  xor     edi, edi
0x18004e230  lea     rcx, [rsp+28h+arg_8]
0x18004e235  call    ??1?$MakeAllocator@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>(void)
0x18004e23a  mov     eax, edi
0x18004e23c  mov     rbx, [rsp+28h+arg_10]
0x18004e241  mov     rsi, [rsp+28h+arg_18]
0x18004e246  add     rsp, 20h
0x18004e24a  pop     rdi
0x18004e24b  retn
```
