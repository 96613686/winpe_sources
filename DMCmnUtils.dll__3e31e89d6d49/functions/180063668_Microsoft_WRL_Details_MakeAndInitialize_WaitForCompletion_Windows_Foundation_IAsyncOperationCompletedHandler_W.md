# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180063668`
- end: `0x1800637ad`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800637b4`

## callees

- `0x1800520f0`
- `0x180063668`
- `0x18006394c`
- `0x180063a1c`
- `0x180064a44`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180063731`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180063731`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063746`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVDeviceInformationCollection_Enumeration_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180063668  mov     [rsp+arg_10], rbx
0x18006366d  mov     [rsp+arg_18], rsi
0x180063672  push    rdi
0x180063673  sub     rsp, 20h
0x180063677  mov     rsi, rcx
0x18006367a  mov     qword ptr [rcx], 0
0x180063681  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180063688  mov     ecx, 40h ; '@'; unsigned __int64
0x18006368d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180063692  mov     rbx, rax
0x180063695  mov     [rsp+28h+arg_8], rax
0x18006369a  test    rax, rax
0x18006369d  jnz     short loc_1800636A9
0x18006369f  mov     edi, 8007000Eh
0x1800636a4  jmp     loc_180063790
0x1800636a9  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x1800636b0  mov     [rbx], rax
0x1800636b3  lea     rdi, [rbx+8]
0x1800636b7  mov     rcx, rdi; this
0x1800636ba  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800636bf  mov     dword ptr [rbx+2Ch], 1
0x1800636c6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x1800636cd  mov     [rbx], rax
0x1800636d0  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800636d7  mov     [rdi], rax
0x1800636da  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800636e1  test    rcx, rcx
0x1800636e4  jz      short loc_1800636F3
0x1800636e6  mov     rax, [rcx]
0x1800636e9  mov     rax, [rax+8]
0x1800636ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800636f2  nop
0x1800636f3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>'}
0x1800636fa  mov     [rbx], rax
0x1800636fd  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180063704  mov     [rdi], rax
0x180063707  mov     dword ptr [rbx+30h], 0
0x18006370e  mov     qword ptr [rbx+38h], 0
0x180063716  mov     [rsp+28h+arg_0], rbx
0x18006371b  mov     [rsp+28h+arg_8], 0
0x180063724  mov     r9d, 1F0003h; dwDesiredAccess
0x18006372a  xor     r8d, r8d; dwFlags
0x18006372d  xor     edx, edx; lpName
0x18006372f  xor     ecx, ecx; lpEventAttributes
0x180063731  call    cs:__imp_CreateEventExW
0x180063738  nop     dword ptr [rax+rax+00h]
0x18006373d  mov     [rbx+38h], rax
0x180063741  test    rax, rax
0x180063744  jnz     short loc_180063771
0x180063746  call    cs:__imp_GetLastError
0x18006374d  nop     dword ptr [rax+rax+00h]
0x180063752  mov     edi, eax
0x180063754  test    eax, eax
0x180063756  jle     short loc_180063761
0x180063758  movzx   edi, ax
0x18006375b  or      edi, 80070000h
0x180063761  test    edi, edi
0x180063763  jns     short loc_180063771
0x180063765  lea     rcx, [rsp+28h+arg_0]
0x18006376a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006376f  jmp     short loc_180063790
0x180063771  mov     rax, [rbx]
0x180063774  mov     rcx, rbx
0x180063777  mov     rax, [rax+8]
0x18006377b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063780  nop
0x180063781  mov     [rsi], rbx
0x180063784  lea     rcx, [rsp+28h+arg_0]
0x180063789  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006378e  xor     edi, edi
0x180063790  lea     rcx, [rsp+28h+arg_8]
0x180063795  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x18006379a  mov     eax, edi
0x18006379c  mov     rbx, [rsp+28h+arg_10]
0x1800637a1  mov     rsi, [rsp+28h+arg_18]
0x1800637a6  add     rsp, 20h
0x1800637aa  pop     rdi
0x1800637ab  retn
```
