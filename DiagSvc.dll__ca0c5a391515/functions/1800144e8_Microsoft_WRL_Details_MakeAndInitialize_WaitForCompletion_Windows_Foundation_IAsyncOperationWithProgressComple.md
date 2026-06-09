# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800144e8`
- end: `0x180014620`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014bcc`

## callees

- `0x18000446c`
- `0x18000517c`
- `0x180006574`
- `0x180009708`
- `0x1800144e8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800145b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800145b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c0`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_23___YAJPEAU__IAsyncOperationWithProgress_PEAUIBuffer_Streams_Storage_Windows__I_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x1800144e8  mov     [rsp+arg_10], rbx
0x1800144ed  mov     [rsp+arg_18], rsi
0x1800144f2  push    rdi
0x1800144f3  sub     rsp, 20h
0x1800144f7  mov     rsi, rcx
0x1800144fa  mov     qword ptr [rcx], 0
0x180014501  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014508  mov     ecx, 40h ; '@'; unsigned __int64
0x18001450d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014512  mov     rbx, rax
0x180014515  mov     [rsp+28h+arg_8], rax
0x18001451a  test    rax, rax
0x18001451d  jnz     short loc_180014529
0x18001451f  mov     edi, 8007000Eh
0x180014524  jmp     loc_180014604
0x180014529  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable'
0x180014530  mov     [rbx], rax
0x180014533  lea     rdi, [rbx+8]
0x180014537  mov     rcx, rdi; this
0x18001453a  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001453f  mov     dword ptr [rbx+2Ch], 1
0x180014546  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>'}
0x18001454d  mov     [rbx], rax
0x180014550  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014557  mov     [rdi], rax
0x18001455a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014561  test    rcx, rcx
0x180014564  jz      short loc_180014573
0x180014566  mov     rax, [rcx]
0x180014569  mov     rax, [rax+8]
0x18001456d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014572  nop
0x180014573  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>'}
0x18001457a  mov     [rbx], rax
0x18001457d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014584  mov     [rdi], rax
0x180014587  mov     dword ptr [rbx+30h], 0
0x18001458e  mov     qword ptr [rbx+38h], 0
0x180014596  mov     [rsp+28h+arg_0], rbx
0x18001459b  mov     [rsp+28h+arg_8], 0
0x1800145a4  mov     r9d, 1F0003h; dwDesiredAccess
0x1800145aa  xor     r8d, r8d; dwFlags
0x1800145ad  xor     edx, edx; lpName
0x1800145af  xor     ecx, ecx; lpEventAttributes
0x1800145b1  call    cs:__imp_CreateEventExW
0x1800145b7  mov     [rbx+38h], rax
0x1800145bb  test    rax, rax
0x1800145be  jnz     short loc_1800145E5
0x1800145c0  call    cs:__imp_GetLastError
0x1800145c6  mov     edi, eax
0x1800145c8  test    eax, eax
0x1800145ca  jle     short loc_1800145D5
0x1800145cc  movzx   edi, ax
0x1800145cf  or      edi, 80070000h
0x1800145d5  test    edi, edi
0x1800145d7  jns     short loc_1800145E5
0x1800145d9  lea     rcx, [rsp+28h+arg_0]
0x1800145de  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800145e3  jmp     short loc_180014604
0x1800145e5  mov     rax, [rbx]
0x1800145e8  mov     rcx, rbx
0x1800145eb  mov     rax, [rax+8]
0x1800145ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145f4  nop
0x1800145f5  mov     [rsi], rbx
0x1800145f8  lea     rcx, [rsp+28h+arg_0]
0x1800145fd  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180014602  xor     edi, edi
0x180014604  lea     rcx, [rsp+28h+arg_8]
0x180014609  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001460e  mov     eax, edi
0x180014610  mov     rbx, [rsp+28h+arg_10]
0x180014615  mov     rsi, [rsp+28h+arg_18]
0x18001461a  add     rsp, 20h
0x18001461e  pop     rdi
0x18001461f  retn
```
