# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180073048`
- end: `0x18007318d`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073570`

## callees

- `0x1800520f0`
- `0x18006394c`
- `0x180063a1c`
- `0x180064a44`
- `0x180073048`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180073111`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180073111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073126`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccount_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180073048  mov     [rsp+arg_10], rbx
0x18007304d  mov     [rsp+arg_18], rsi
0x180073052  push    rdi
0x180073053  sub     rsp, 20h
0x180073057  mov     rsi, rcx
0x18007305a  mov     qword ptr [rcx], 0
0x180073061  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180073068  mov     ecx, 40h ; '@'; unsigned __int64
0x18007306d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180073072  mov     rbx, rax
0x180073075  mov     [rsp+28h+arg_8], rax
0x18007307a  test    rax, rax
0x18007307d  jnz     short loc_180073089
0x18007307f  mov     edi, 8007000Eh
0x180073084  jmp     loc_180073170
0x180073089  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x180073090  mov     [rbx], rax
0x180073093  lea     rdi, [rbx+8]
0x180073097  mov     rcx, rdi; this
0x18007309a  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18007309f  mov     dword ptr [rbx+2Ch], 1
0x1800730a6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x1800730ad  mov     [rbx], rax
0x1800730b0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800730b7  mov     [rdi], rax
0x1800730ba  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800730c1  test    rcx, rcx
0x1800730c4  jz      short loc_1800730D3
0x1800730c6  mov     rax, [rcx]
0x1800730c9  mov     rax, [rax+8]
0x1800730cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800730d2  nop
0x1800730d3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>'}
0x1800730da  mov     [rbx], rax
0x1800730dd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccount@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800730e4  mov     [rdi], rax
0x1800730e7  mov     dword ptr [rbx+30h], 0
0x1800730ee  mov     qword ptr [rbx+38h], 0
0x1800730f6  mov     [rsp+28h+arg_0], rbx
0x1800730fb  mov     [rsp+28h+arg_8], 0
0x180073104  mov     r9d, 1F0003h; dwDesiredAccess
0x18007310a  xor     r8d, r8d; dwFlags
0x18007310d  xor     edx, edx; lpName
0x18007310f  xor     ecx, ecx; lpEventAttributes
0x180073111  call    cs:__imp_CreateEventExW
0x180073118  nop     dword ptr [rax+rax+00h]
0x18007311d  mov     [rbx+38h], rax
0x180073121  test    rax, rax
0x180073124  jnz     short loc_180073151
0x180073126  call    cs:__imp_GetLastError
0x18007312d  nop     dword ptr [rax+rax+00h]
0x180073132  mov     edi, eax
0x180073134  test    eax, eax
0x180073136  jle     short loc_180073141
0x180073138  movzx   edi, ax
0x18007313b  or      edi, 80070000h
0x180073141  test    edi, edi
0x180073143  jns     short loc_180073151
0x180073145  lea     rcx, [rsp+28h+arg_0]
0x18007314a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007314f  jmp     short loc_180073170
0x180073151  mov     rax, [rbx]
0x180073154  mov     rcx, rbx
0x180073157  mov     rax, [rax+8]
0x18007315b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073160  nop
0x180073161  mov     [rsi], rbx
0x180073164  lea     rcx, [rsp+28h+arg_0]
0x180073169  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007316e  xor     edi, edi
0x180073170  lea     rcx, [rsp+28h+arg_8]
0x180073175  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x18007317a  mov     eax, edi
0x18007317c  mov     rbx, [rsp+28h+arg_10]
0x180073181  mov     rsi, [rsp+28h+arg_18]
0x180073186  add     rsp, 20h
0x18007318a  pop     rdi
0x18007318b  retn
```
