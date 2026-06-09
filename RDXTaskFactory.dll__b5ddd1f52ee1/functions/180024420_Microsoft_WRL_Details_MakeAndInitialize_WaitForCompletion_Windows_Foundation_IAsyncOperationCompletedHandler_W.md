# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180024420`
- end: `0x180024558`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024710`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e108`
- `0x18000e264`
- `0x180024420`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800244e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800244e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800244f8`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVGetDefaultSignInAccountResult_Web_Authentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  _DWORD *v11; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v12; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v11 = v2;
    v12 = 0;
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11, v8, v9);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11, v6, v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180024420  mov     [rsp+arg_10], rbx
0x180024425  mov     [rsp+arg_18], rsi
0x18002442a  push    rdi
0x18002442b  sub     rsp, 20h
0x18002442f  mov     rsi, rcx
0x180024432  mov     qword ptr [rcx], 0
0x180024439  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024440  mov     ecx, 40h ; '@'; unsigned __int64
0x180024445  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002444a  mov     rbx, rax
0x18002444d  mov     [rsp+28h+arg_8], rax
0x180024452  test    rax, rax
0x180024455  jnz     short loc_180024461
0x180024457  mov     edi, 8007000Eh
0x18002445c  jmp     loc_18002453C
0x180024461  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x180024468  mov     [rbx], rax
0x18002446b  lea     rdi, [rbx+8]
0x18002446f  mov     rcx, rdi; this
0x180024472  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180024477  mov     dword ptr [rbx+2Ch], 1
0x18002447e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x180024485  mov     [rbx], rax
0x180024488  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002448f  mov     [rdi], rax
0x180024492  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180024499  test    rcx, rcx
0x18002449c  jz      short loc_1800244AB
0x18002449e  mov     rax, [rcx]
0x1800244a1  mov     rax, [rax+8]
0x1800244a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244aa  nop
0x1800244ab  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>'}
0x1800244b2  mov     [rbx], rax
0x1800244b5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800244bc  mov     [rdi], rax
0x1800244bf  mov     dword ptr [rbx+30h], 0
0x1800244c6  mov     qword ptr [rbx+38h], 0
0x1800244ce  mov     [rsp+28h+arg_0], rbx
0x1800244d3  mov     [rsp+28h+arg_8], 0
0x1800244dc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800244e2  xor     r8d, r8d; dwFlags
0x1800244e5  xor     edx, edx; lpName
0x1800244e7  xor     ecx, ecx; lpEventAttributes
0x1800244e9  call    cs:__imp_CreateEventExW
0x1800244ef  mov     [rbx+38h], rax
0x1800244f3  test    rax, rax
0x1800244f6  jnz     short loc_18002451D
0x1800244f8  call    cs:__imp_GetLastError
0x1800244fe  mov     edi, eax
0x180024500  test    eax, eax
0x180024502  jle     short loc_18002450D
0x180024504  movzx   edi, ax
0x180024507  or      edi, 80070000h
0x18002450d  test    edi, edi
0x18002450f  jns     short loc_18002451D
0x180024511  lea     rcx, [rsp+28h+arg_0]
0x180024516  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002451b  jmp     short loc_18002453C
0x18002451d  mov     rax, [rbx]
0x180024520  mov     rcx, rbx
0x180024523  mov     rax, [rax+8]
0x180024527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002452c  nop
0x18002452d  mov     [rsi], rbx
0x180024530  lea     rcx, [rsp+28h+arg_0]
0x180024535  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002453a  xor     edi, edi
0x18002453c  lea     rcx, [rsp+28h+arg_8]
0x180024541  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x180024546  mov     eax, edi
0x180024548  mov     rbx, [rsp+28h+arg_10]
0x18002454d  mov     rsi, [rsp+28h+arg_18]
0x180024552  add     rsp, 20h
0x180024556  pop     rdi
0x180024557  retn
```
