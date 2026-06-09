# `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::~FTMEventDelegate(void)

- ea: `0x14000a330`
- end: `0x14000a36d`
- name: `??1FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAA@XZ`
- size: `61`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a810`

## callees

- `0x14000d49c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a352`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a352`

## pseudocode

```c
__int64 __fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::~FTMEventDelegate(
        __int64 a1)
{
  *(_QWORD *)a1 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CloseHandle(*(HANDLE *)(a1 + 56));
  *(_DWORD *)(a1 + 44) = -1073741823;
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(a1 + 32);
}

```

## disassembly

```asm
0x14000a330  push    rbx
0x14000a332  sub     rsp, 20h
0x14000a336  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x14000a33d  mov     rbx, rcx
0x14000a340  mov     [rcx], rax
0x14000a343  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x14000a34a  mov     [rcx+8], rax
0x14000a34e  mov     rcx, [rcx+38h]; hObject
0x14000a352  call    cs:__imp_CloseHandle
0x14000a358  lea     rcx, [rbx+20h]
0x14000a35c  mov     dword ptr [rbx+2Ch], 0C0000001h
0x14000a363  add     rsp, 20h
0x14000a367  pop     rbx
0x14000a368  jmp     ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
```
