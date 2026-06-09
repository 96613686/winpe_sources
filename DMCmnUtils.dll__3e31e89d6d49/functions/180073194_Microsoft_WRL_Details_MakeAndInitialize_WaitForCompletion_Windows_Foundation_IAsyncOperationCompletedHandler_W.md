# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180073194`
- end: `0x1800732d9`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073704`

## callees

- `0x1800520f0`
- `0x18006394c`
- `0x180063a1c`
- `0x180064a44`
- `0x180073194`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007325d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18007325d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073272`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180073194  mov     [rsp+arg_10], rbx
0x180073199  mov     [rsp+arg_18], rsi
0x18007319e  push    rdi
0x18007319f  sub     rsp, 20h
0x1800731a3  mov     rsi, rcx
0x1800731a6  mov     qword ptr [rcx], 0
0x1800731ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800731b4  mov     ecx, 40h ; '@'; unsigned __int64
0x1800731b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800731be  mov     rbx, rax
0x1800731c1  mov     [rsp+28h+arg_8], rax
0x1800731c6  test    rax, rax
0x1800731c9  jnz     short loc_1800731D5
0x1800731cb  mov     edi, 8007000Eh
0x1800731d0  jmp     loc_1800732BC
0x1800731d5  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x1800731dc  mov     [rbx], rax
0x1800731df  lea     rdi, [rbx+8]
0x1800731e3  mov     rcx, rdi; this
0x1800731e6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800731eb  mov     dword ptr [rbx+2Ch], 1
0x1800731f2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x1800731f9  mov     [rbx], rax
0x1800731fc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180073203  mov     [rdi], rax
0x180073206  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18007320d  test    rcx, rcx
0x180073210  jz      short loc_18007321F
0x180073212  mov     rax, [rcx]
0x180073215  mov     rax, [rax+8]
0x180073219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007321e  nop
0x18007321f  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x180073226  mov     [rbx], rax
0x180073229  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180073230  mov     [rdi], rax
0x180073233  mov     dword ptr [rbx+30h], 0
0x18007323a  mov     qword ptr [rbx+38h], 0
0x180073242  mov     [rsp+28h+arg_0], rbx
0x180073247  mov     [rsp+28h+arg_8], 0
0x180073250  mov     r9d, 1F0003h; dwDesiredAccess
0x180073256  xor     r8d, r8d; dwFlags
0x180073259  xor     edx, edx; lpName
0x18007325b  xor     ecx, ecx; lpEventAttributes
0x18007325d  call    cs:__imp_CreateEventExW
0x180073264  nop     dword ptr [rax+rax+00h]
0x180073269  mov     [rbx+38h], rax
0x18007326d  test    rax, rax
0x180073270  jnz     short loc_18007329D
0x180073272  call    cs:__imp_GetLastError
0x180073279  nop     dword ptr [rax+rax+00h]
0x18007327e  mov     edi, eax
0x180073280  test    eax, eax
0x180073282  jle     short loc_18007328D
0x180073284  movzx   edi, ax
0x180073287  or      edi, 80070000h
0x18007328d  test    edi, edi
0x18007328f  jns     short loc_18007329D
0x180073291  lea     rcx, [rsp+28h+arg_0]
0x180073296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007329b  jmp     short loc_1800732BC
0x18007329d  mov     rax, [rbx]
0x1800732a0  mov     rcx, rbx
0x1800732a3  mov     rax, [rax+8]
0x1800732a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800732ac  nop
0x1800732ad  mov     [rsi], rbx
0x1800732b0  lea     rcx, [rsp+28h+arg_0]
0x1800732b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800732ba  xor     edi, edi
0x1800732bc  lea     rcx, [rsp+28h+arg_8]
0x1800732c1  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x1800732c6  mov     eax, edi
0x1800732c8  mov     rbx, [rsp+28h+arg_10]
0x1800732cd  mov     rsi, [rsp+28h+arg_18]
0x1800732d2  add     rsp, 20h
0x1800732d6  pop     rdi
0x1800732d7  retn
```
