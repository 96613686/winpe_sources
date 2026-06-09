# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180024560`
- end: `0x180024698`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800248ac`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e108`
- `0x18000e264`
- `0x180024560`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024629`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180024629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024638`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180024560  mov     [rsp+arg_10], rbx
0x180024565  mov     [rsp+arg_18], rsi
0x18002456a  push    rdi
0x18002456b  sub     rsp, 20h
0x18002456f  mov     rsi, rcx
0x180024572  mov     qword ptr [rcx], 0
0x180024579  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024580  mov     ecx, 40h ; '@'; unsigned __int64
0x180024585  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002458a  mov     rbx, rax
0x18002458d  mov     [rsp+28h+arg_8], rax
0x180024592  test    rax, rax
0x180024595  jnz     short loc_1800245A1
0x180024597  mov     edi, 8007000Eh
0x18002459c  jmp     loc_18002467C
0x1800245a1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x1800245a8  mov     [rbx], rax
0x1800245ab  lea     rdi, [rbx+8]
0x1800245af  mov     rcx, rdi; this
0x1800245b2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800245b7  mov     dword ptr [rbx+2Ch], 1
0x1800245be  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x1800245c5  mov     [rbx], rax
0x1800245c8  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800245cf  mov     [rdi], rax
0x1800245d2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800245d9  test    rcx, rcx
0x1800245dc  jz      short loc_1800245EB
0x1800245de  mov     rax, [rcx]
0x1800245e1  mov     rax, [rax+8]
0x1800245e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245ea  nop
0x1800245eb  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x1800245f2  mov     [rbx], rax
0x1800245f5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800245fc  mov     [rdi], rax
0x1800245ff  mov     dword ptr [rbx+30h], 0
0x180024606  mov     qword ptr [rbx+38h], 0
0x18002460e  mov     [rsp+28h+arg_0], rbx
0x180024613  mov     [rsp+28h+arg_8], 0
0x18002461c  mov     r9d, 1F0003h; dwDesiredAccess
0x180024622  xor     r8d, r8d; dwFlags
0x180024625  xor     edx, edx; lpName
0x180024627  xor     ecx, ecx; lpEventAttributes
0x180024629  call    cs:__imp_CreateEventExW
0x18002462f  mov     [rbx+38h], rax
0x180024633  test    rax, rax
0x180024636  jnz     short loc_18002465D
0x180024638  call    cs:__imp_GetLastError
0x18002463e  mov     edi, eax
0x180024640  test    eax, eax
0x180024642  jle     short loc_18002464D
0x180024644  movzx   edi, ax
0x180024647  or      edi, 80070000h
0x18002464d  test    edi, edi
0x18002464f  jns     short loc_18002465D
0x180024651  lea     rcx, [rsp+28h+arg_0]
0x180024656  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002465b  jmp     short loc_18002467C
0x18002465d  mov     rax, [rbx]
0x180024660  mov     rcx, rbx
0x180024663  mov     rax, [rax+8]
0x180024667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466c  nop
0x18002466d  mov     [rsi], rbx
0x180024670  lea     rcx, [rsp+28h+arg_0]
0x180024675  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002467a  xor     edi, edi
0x18002467c  lea     rcx, [rsp+28h+arg_8]
0x180024681  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x180024686  mov     eax, edi
0x180024688  mov     rbx, [rsp+28h+arg_10]
0x18002468d  mov     rsi, [rsp+28h+arg_18]
0x180024692  add     rsp, 20h
0x180024696  pop     rdi
0x180024697  retn
```
