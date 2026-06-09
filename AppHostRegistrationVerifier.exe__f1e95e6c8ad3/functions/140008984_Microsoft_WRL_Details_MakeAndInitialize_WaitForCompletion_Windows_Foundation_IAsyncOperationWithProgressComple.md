# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x140008984`
- end: `0x140008ab0`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400090ac`

## callees

- `0x140003038`
- `0x140008984`
- `0x140009a84`
- `0x140009e54`
- `0x14000d49c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140008a41`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140008a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008a50`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  signed int v4; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v9 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>(v2);
    v3[11] = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'};
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v3 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v3[12] = 0;
    *((_QWORD *)v3 + 7) = 0;
    v8 = v3;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v3 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140008984  mov     [rsp+arg_10], rbx
0x140008989  mov     [rsp+arg_18], rsi
0x14000898e  push    rdi
0x14000898f  sub     rsp, 20h
0x140008993  mov     rsi, rcx
0x140008996  mov     qword ptr [rcx], 0
0x14000899d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400089a4  mov     ecx, 40h ; '@'; unsigned __int64
0x1400089a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400089ae  mov     rbx, rax
0x1400089b1  mov     [rsp+28h+arg_8], rax
0x1400089b6  test    rax, rax
0x1400089b9  jnz     short loc_1400089C5
0x1400089bb  mov     edi, 8007000Eh
0x1400089c0  jmp     loc_140008A94
0x1400089c5  mov     rcx, rbx
0x1400089c8  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>(void)
0x1400089cd  mov     dword ptr [rbx+2Ch], 1
0x1400089d4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x1400089db  mov     [rbx], rax
0x1400089de  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400089e5  mov     [rbx+8], rax
0x1400089e9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400089f0  test    rcx, rcx
0x1400089f3  jz      short loc_140008A02
0x1400089f5  mov     rax, [rcx]
0x1400089f8  mov     rax, [rax+8]
0x1400089fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a01  nop
0x140008a02  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x140008a09  mov     [rbx], rax
0x140008a0c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140008a13  mov     [rbx+8], rax
0x140008a17  mov     dword ptr [rbx+30h], 0
0x140008a1e  mov     qword ptr [rbx+38h], 0
0x140008a26  mov     [rsp+28h+arg_0], rbx
0x140008a2b  mov     [rsp+28h+arg_8], 0
0x140008a34  mov     r9d, 1F0003h; dwDesiredAccess
0x140008a3a  xor     r8d, r8d; dwFlags
0x140008a3d  xor     edx, edx; lpName
0x140008a3f  xor     ecx, ecx; lpEventAttributes
0x140008a41  call    cs:__imp_CreateEventExW
0x140008a47  mov     [rbx+38h], rax
0x140008a4b  test    rax, rax
0x140008a4e  jnz     short loc_140008A75
0x140008a50  call    cs:__imp_GetLastError
0x140008a56  mov     edi, eax
0x140008a58  test    eax, eax
0x140008a5a  jle     short loc_140008A65
0x140008a5c  movzx   edi, ax
0x140008a5f  or      edi, 80070000h
0x140008a65  test    edi, edi
0x140008a67  jns     short loc_140008A75
0x140008a69  lea     rcx, [rsp+28h+arg_0]
0x140008a6e  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140008a73  jmp     short loc_140008A94
0x140008a75  mov     rax, [rbx]
0x140008a78  mov     rcx, rbx
0x140008a7b  mov     rax, [rax+8]
0x140008a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a84  nop
0x140008a85  mov     [rsi], rbx
0x140008a88  lea     rcx, [rsp+28h+arg_0]
0x140008a8d  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140008a92  xor     edi, edi
0x140008a94  lea     rcx, [rsp+28h+arg_8]
0x140008a99  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x140008a9e  mov     eax, edi
0x140008aa0  mov     rbx, [rsp+28h+arg_10]
0x140008aa5  mov     rsi, [rsp+28h+arg_18]
0x140008aaa  add     rsp, 20h
0x140008aae  pop     rdi
0x140008aaf  retn
```
