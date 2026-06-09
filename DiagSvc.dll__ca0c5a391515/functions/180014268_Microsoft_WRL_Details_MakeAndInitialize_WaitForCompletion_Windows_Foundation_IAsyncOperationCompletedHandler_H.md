# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180014268`
- end: `0x1800143a0`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800148ac`

## callees

- `0x18000446c`
- `0x18000517c`
- `0x180006574`
- `0x180009708`
- `0x180014268`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180014331`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180014331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014340`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUHSTRING_____Foundation_Windows__U__IAsyncOperation_PEAUHSTRING_____23___YAJPEAU__IAsyncOperation_PEAUHSTRING_____Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>'::`2'::FTMEventDelegate::`vftable';
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
0x180014268  mov     [rsp+arg_10], rbx
0x18001426d  mov     [rsp+arg_18], rsi
0x180014272  push    rdi
0x180014273  sub     rsp, 20h
0x180014277  mov     rsi, rcx
0x18001427a  mov     qword ptr [rcx], 0
0x180014281  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014288  mov     ecx, 40h ; '@'; unsigned __int64
0x18001428d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014292  mov     rbx, rax
0x180014295  mov     [rsp+28h+arg_8], rax
0x18001429a  test    rax, rax
0x18001429d  jnz     short loc_1800142A9
0x18001429f  mov     edi, 8007000Eh
0x1800142a4  jmp     loc_180014384
0x1800142a9  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable'
0x1800142b0  mov     [rbx], rax
0x1800142b3  lea     rdi, [rbx+8]
0x1800142b7  mov     rcx, rdi; this
0x1800142ba  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800142bf  mov     dword ptr [rbx+2Ch], 1
0x1800142c6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x1800142cd  mov     [rbx], rax
0x1800142d0  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800142d7  mov     [rdi], rax
0x1800142da  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800142e1  test    rcx, rcx
0x1800142e4  jz      short loc_1800142F3
0x1800142e6  mov     rax, [rcx]
0x1800142e9  mov     rax, [rax+8]
0x1800142ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142f2  nop
0x1800142f3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>'}
0x1800142fa  mov     [rbx], rax
0x1800142fd  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014304  mov     [rdi], rax
0x180014307  mov     dword ptr [rbx+30h], 0
0x18001430e  mov     qword ptr [rbx+38h], 0
0x180014316  mov     [rsp+28h+arg_0], rbx
0x18001431b  mov     [rsp+28h+arg_8], 0
0x180014324  mov     r9d, 1F0003h; dwDesiredAccess
0x18001432a  xor     r8d, r8d; dwFlags
0x18001432d  xor     edx, edx; lpName
0x18001432f  xor     ecx, ecx; lpEventAttributes
0x180014331  call    cs:__imp_CreateEventExW
0x180014337  mov     [rbx+38h], rax
0x18001433b  test    rax, rax
0x18001433e  jnz     short loc_180014365
0x180014340  call    cs:__imp_GetLastError
0x180014346  mov     edi, eax
0x180014348  test    eax, eax
0x18001434a  jle     short loc_180014355
0x18001434c  movzx   edi, ax
0x18001434f  or      edi, 80070000h
0x180014355  test    edi, edi
0x180014357  jns     short loc_180014365
0x180014359  lea     rcx, [rsp+28h+arg_0]
0x18001435e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014363  jmp     short loc_180014384
0x180014365  mov     rax, [rbx]
0x180014368  mov     rcx, rbx
0x18001436b  mov     rax, [rax+8]
0x18001436f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014374  nop
0x180014375  mov     [rsi], rbx
0x180014378  lea     rcx, [rsp+28h+arg_0]
0x18001437d  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014382  xor     edi, edi
0x180014384  lea     rcx, [rsp+28h+arg_8]
0x180014389  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001438e  mov     eax, edi
0x180014390  mov     rbx, [rsp+28h+arg_10]
0x180014395  mov     rsi, [rsp+28h+arg_18]
0x18001439a  add     rsp, 20h
0x18001439e  pop     rdi
0x18001439f  retn
```
