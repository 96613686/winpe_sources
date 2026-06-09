# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180014628`
- end: `0x180014760`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014d5c`

## callees

- `0x18000446c`
- `0x18000517c`
- `0x180006574`
- `0x180009708`
- `0x180014628`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800146f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800146f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014700`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJPEAU__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__23___YAJPEAU__IAsyncOperationWithProgress_PEAUIInputStream_Streams_Storage_Windows__UHttpProgress_Http_Web_4__Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>'::`2'::FTMEventDelegate::`vftable';
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
0x180014628  mov     [rsp+arg_10], rbx
0x18001462d  mov     [rsp+arg_18], rsi
0x180014632  push    rdi
0x180014633  sub     rsp, 20h
0x180014637  mov     rsi, rcx
0x18001463a  mov     qword ptr [rcx], 0
0x180014641  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014648  mov     ecx, 40h ; '@'; unsigned __int64
0x18001464d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014652  mov     rbx, rax
0x180014655  mov     [rsp+28h+arg_8], rax
0x18001465a  test    rax, rax
0x18001465d  jnz     short loc_180014669
0x18001465f  mov     edi, 8007000Eh
0x180014664  jmp     loc_180014744
0x180014669  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable'
0x180014670  mov     [rbx], rax
0x180014673  lea     rdi, [rbx+8]
0x180014677  mov     rcx, rdi; this
0x18001467a  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001467f  mov     dword ptr [rbx+2Ch], 1
0x180014686  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>'}
0x18001468d  mov     [rbx], rax
0x180014690  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014697  mov     [rdi], rax
0x18001469a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800146a1  test    rcx, rcx
0x1800146a4  jz      short loc_1800146B3
0x1800146a6  mov     rax, [rcx]
0x1800146a9  mov     rax, [rax+8]
0x1800146ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146b2  nop
0x1800146b3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>'}
0x1800146ba  mov     [rbx], rax
0x1800146bd  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800146c4  mov     [rdi], rax
0x1800146c7  mov     dword ptr [rbx+30h], 0
0x1800146ce  mov     qword ptr [rbx+38h], 0
0x1800146d6  mov     [rsp+28h+arg_0], rbx
0x1800146db  mov     [rsp+28h+arg_8], 0
0x1800146e4  mov     r9d, 1F0003h; dwDesiredAccess
0x1800146ea  xor     r8d, r8d; dwFlags
0x1800146ed  xor     edx, edx; lpName
0x1800146ef  xor     ecx, ecx; lpEventAttributes
0x1800146f1  call    cs:__imp_CreateEventExW
0x1800146f7  mov     [rbx+38h], rax
0x1800146fb  test    rax, rax
0x1800146fe  jnz     short loc_180014725
0x180014700  call    cs:__imp_GetLastError
0x180014706  mov     edi, eax
0x180014708  test    eax, eax
0x18001470a  jle     short loc_180014715
0x18001470c  movzx   edi, ax
0x18001470f  or      edi, 80070000h
0x180014715  test    edi, edi
0x180014717  jns     short loc_180014725
0x180014719  lea     rcx, [rsp+28h+arg_0]
0x18001471e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014723  jmp     short loc_180014744
0x180014725  mov     rax, [rbx]
0x180014728  mov     rcx, rbx
0x18001472b  mov     rax, [rax+8]
0x18001472f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014734  nop
0x180014735  mov     [rsi], rbx
0x180014738  lea     rcx, [rsp+28h+arg_0]
0x18001473d  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014742  xor     edi, edi
0x180014744  lea     rcx, [rsp+28h+arg_8]
0x180014749  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001474e  mov     eax, edi
0x180014750  mov     rbx, [rsp+28h+arg_10]
0x180014755  mov     rsi, [rsp+28h+arg_18]
0x18001475a  add     rsp, 20h
0x18001475e  pop     rdi
0x18001475f  retn
```
