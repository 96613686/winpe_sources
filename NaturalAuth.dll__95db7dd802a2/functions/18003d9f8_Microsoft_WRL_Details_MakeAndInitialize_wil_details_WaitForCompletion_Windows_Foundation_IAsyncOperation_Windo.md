# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x18003d9f8`
- end: `0x18003db3b`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `323`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dcec`

## callees

- `0x180004960`
- `0x180007d38`
- `0x180009114`
- `0x18000a494`
- `0x180014e7c`
- `0x18002967c`
- `0x18003d9f8`
- `0x18003e080`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003dab2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003dab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac0`

## string_xrefs

- `0x18003db1e`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVGeoposition_Geolocation_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  unsigned int v4; // edi
  wil::details *v5; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v11; // [rsp+40h] [rbp+8h] BYREF
  void *v12; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v12 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(v2);
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>'};
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v3[12] = 0;
    *((_QWORD *)v3 + 7) = 0;
    v11 = v3;
    v12 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v3 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
      v4 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v9);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<GeolocSignal::GeopositionHandler>::~MakeAllocator<GeolocSignal::GeopositionHandler>(&v12);
  return v4;
}

```

## disassembly

```asm
0x18003d9f8  mov     [rsp+arg_10], rbx
0x18003d9fd  push    rbp
0x18003d9fe  push    rsi
0x18003d9ff  push    rdi; int
0x18003da00  sub     rsp, 20h
0x18003da04  mov     rsi, rcx
0x18003da07  mov     qword ptr [rcx], 0
0x18003da0e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003da15  mov     ecx, 40h ; '@'; unsigned __int64
0x18003da1a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003da1f  mov     rbx, rax
0x18003da22  mov     [rsp+38h+arg_8], rax
0x18003da27  test    rax, rax
0x18003da2a  jnz     short loc_18003DA36
0x18003da2c  mov     edi, 8007000Eh
0x18003da31  jmp     loc_18003DAF2
0x18003da36  mov     rcx, rbx
0x18003da39  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(void)
0x18003da3e  mov     dword ptr [rbx+2Ch], 1
0x18003da45  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>'}
0x18003da4c  mov     [rbx], rax
0x18003da4f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003da56  mov     [rbx+8], rax
0x18003da5a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003da61  test    rcx, rcx
0x18003da64  jz      short loc_18003DA73
0x18003da66  mov     rax, [rcx]
0x18003da69  mov     rax, [rax+8]
0x18003da6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da72  nop
0x18003da73  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>'}
0x18003da7a  mov     [rbx], rax
0x18003da7d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003da84  mov     [rbx+8], rax
0x18003da88  mov     dword ptr [rbx+30h], 0
0x18003da8f  mov     qword ptr [rbx+38h], 0
0x18003da97  mov     [rsp+38h+arg_0], rbx
0x18003da9c  mov     [rsp+38h+arg_8], 0
0x18003daa5  mov     r9d, 1F0003h; dwDesiredAccess
0x18003daab  xor     r8d, r8d; dwFlags
0x18003daae  xor     edx, edx; lpName
0x18003dab0  xor     ecx, ecx; lpEventAttributes
0x18003dab2  call    cs:__imp_CreateEventExW
0x18003dab8  mov     rbp, rax
0x18003dabb  test    rax, rax
0x18003dabe  jz      short loc_18003DB0B
0x18003dac0  call    cs:__imp_GetLastError
0x18003dac6  mov     rdx, rbp
0x18003dac9  lea     rcx, [rbx+38h]
0x18003dacd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003dad2  nop
0x18003dad3  mov     rax, [rbx]
0x18003dad6  mov     rcx, rbx
0x18003dad9  mov     rax, [rax+8]
0x18003dadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dae2  nop
0x18003dae3  mov     [rsi], rbx
0x18003dae6  lea     rcx, [rsp+38h+arg_0]
0x18003daeb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003daf0  xor     edi, edi
0x18003daf2  lea     rcx, [rsp+38h+arg_8]
0x18003daf7  call    ??1?$MakeAllocator@VGeopositionHandler@GeolocSignal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<GeolocSignal::GeopositionHandler>::~MakeAllocator<GeolocSignal::GeopositionHandler>(void)
0x18003dafc  mov     eax, edi
0x18003dafe  mov     rbx, [rsp+38h+arg_10]
0x18003db03  add     rsp, 20h
0x18003db07  pop     rdi
0x18003db08  pop     rsi
0x18003db09  pop     rbp
0x18003db0a  retn
0x18003db0b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003db10  mov     edi, eax
0x18003db12  test    eax, eax
0x18003db14  jns     short loc_18003DAD3
0x18003db16  mov     rcx, [rsp+38h]; this
0x18003db1b  mov     r9d, eax; char *
0x18003db1e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003db25  mov     edx, 62Bh; void *
0x18003db2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003db2f  lea     rcx, [rsp+38h+arg_0]
0x18003db34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db39  jmp     short loc_18003DAF2
```
