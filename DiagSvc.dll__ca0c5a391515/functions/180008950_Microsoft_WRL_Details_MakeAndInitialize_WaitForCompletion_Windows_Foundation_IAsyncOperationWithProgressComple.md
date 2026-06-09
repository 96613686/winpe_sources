# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180008950`
- end: `0x180008a88`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800092c4`

## callees

- `0x18000446c`
- `0x18000517c`
- `0x180006574`
- `0x180008950`
- `0x180009708`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008a19`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a28`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__U__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__23___YAJPEAU__IAsyncOperationWithProgress_PEAVHttpResponseMessage_Http_Web_Windows__UHttpProgress_234__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008950  mov     [rsp+arg_10], rbx
0x180008955  mov     [rsp+arg_18], rsi
0x18000895a  push    rdi
0x18000895b  sub     rsp, 20h
0x18000895f  mov     rsi, rcx
0x180008962  mov     qword ptr [rcx], 0
0x180008969  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008970  mov     ecx, 40h ; '@'; unsigned __int64
0x180008975  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000897a  mov     rbx, rax
0x18000897d  mov     [rsp+28h+arg_8], rax
0x180008982  test    rax, rax
0x180008985  jnz     short loc_180008991
0x180008987  mov     edi, 8007000Eh
0x18000898c  jmp     loc_180008A6C
0x180008991  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable'
0x180008998  mov     [rbx], rax
0x18000899b  lea     rdi, [rbx+8]
0x18000899f  mov     rcx, rdi; this
0x1800089a2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800089a7  mov     dword ptr [rbx+2Ch], 1
0x1800089ae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x1800089b5  mov     [rbx], rax
0x1800089b8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800089bf  mov     [rdi], rax
0x1800089c2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800089c9  test    rcx, rcx
0x1800089cc  jz      short loc_1800089DB
0x1800089ce  mov     rax, [rcx]
0x1800089d1  mov     rax, [rax+8]
0x1800089d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089da  nop
0x1800089db  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>'}
0x1800089e2  mov     [rbx], rax
0x1800089e5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800089ec  mov     [rdi], rax
0x1800089ef  mov     dword ptr [rbx+30h], 0
0x1800089f6  mov     qword ptr [rbx+38h], 0
0x1800089fe  mov     [rsp+28h+arg_0], rbx
0x180008a03  mov     [rsp+28h+arg_8], 0
0x180008a0c  mov     r9d, 1F0003h; dwDesiredAccess
0x180008a12  xor     r8d, r8d; dwFlags
0x180008a15  xor     edx, edx; lpName
0x180008a17  xor     ecx, ecx; lpEventAttributes
0x180008a19  call    cs:__imp_CreateEventExW
0x180008a1f  mov     [rbx+38h], rax
0x180008a23  test    rax, rax
0x180008a26  jnz     short loc_180008A4D
0x180008a28  call    cs:__imp_GetLastError
0x180008a2e  mov     edi, eax
0x180008a30  test    eax, eax
0x180008a32  jle     short loc_180008A3D
0x180008a34  movzx   edi, ax
0x180008a37  or      edi, 80070000h
0x180008a3d  test    edi, edi
0x180008a3f  jns     short loc_180008A4D
0x180008a41  lea     rcx, [rsp+28h+arg_0]
0x180008a46  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180008a4b  jmp     short loc_180008A6C
0x180008a4d  mov     rax, [rbx]
0x180008a50  mov     rcx, rbx
0x180008a53  mov     rax, [rax+8]
0x180008a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a5c  nop
0x180008a5d  mov     [rsi], rbx
0x180008a60  lea     rcx, [rsp+28h+arg_0]
0x180008a65  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180008a6a  xor     edi, edi
0x180008a6c  lea     rcx, [rsp+28h+arg_8]
0x180008a71  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180008a76  mov     eax, edi
0x180008a78  mov     rbx, [rsp+28h+arg_10]
0x180008a7d  mov     rsi, [rsp+28h+arg_18]
0x180008a82  add     rsp, 20h
0x180008a86  pop     rdi
0x180008a87  retn
```
