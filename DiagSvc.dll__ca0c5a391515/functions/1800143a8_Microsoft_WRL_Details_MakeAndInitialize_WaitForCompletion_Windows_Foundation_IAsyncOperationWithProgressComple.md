# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800143a8`
- end: `0x1800144e0`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014a3c`

## callees

- `0x18000446c`
- `0x18000517c`
- `0x180006574`
- `0x180009708`
- `0x1800143a8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180014471`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180014471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014480`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationWithProgressCompletedHandler_PEAUHSTRING_____K_Foundation_Windows__U__IAsyncOperationWithProgress_PEAUHSTRING_____K_23___YAJPEAU__IAsyncOperationWithProgress_PEAUHSTRING_____K_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>'::`2'::FTMEventDelegate::`vftable';
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
0x1800143a8  mov     [rsp+arg_10], rbx
0x1800143ad  mov     [rsp+arg_18], rsi
0x1800143b2  push    rdi
0x1800143b3  sub     rsp, 20h
0x1800143b7  mov     rsi, rcx
0x1800143ba  mov     qword ptr [rcx], 0
0x1800143c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800143c8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800143cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800143d2  mov     rbx, rax
0x1800143d5  mov     [rsp+28h+arg_8], rax
0x1800143da  test    rax, rax
0x1800143dd  jnz     short loc_1800143E9
0x1800143df  mov     edi, 8007000Eh
0x1800143e4  jmp     loc_1800144C4
0x1800143e9  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>::`vftable'
0x1800143f0  mov     [rbx], rax
0x1800143f3  lea     rdi, [rbx+8]
0x1800143f7  mov     rcx, rdi; this
0x1800143fa  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800143ff  mov     dword ptr [rbx+2Ch], 1
0x180014406  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>'}
0x18001440d  mov     [rbx], rax
0x180014410  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014417  mov     [rdi], rax
0x18001441a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180014421  test    rcx, rcx
0x180014424  jz      short loc_180014433
0x180014426  mov     rax, [rcx]
0x180014429  mov     rax, [rax+8]
0x18001442d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014432  nop
0x180014433  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>'}
0x18001443a  mov     [rbx], rax
0x18001443d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUHSTRING__@@_K@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64>>(Windows::Foundation::IAsyncOperationWithProgress<HSTRING__ *,unsigned __int64> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180014444  mov     [rdi], rax
0x180014447  mov     dword ptr [rbx+30h], 0
0x18001444e  mov     qword ptr [rbx+38h], 0
0x180014456  mov     [rsp+28h+arg_0], rbx
0x18001445b  mov     [rsp+28h+arg_8], 0
0x180014464  mov     r9d, 1F0003h; dwDesiredAccess
0x18001446a  xor     r8d, r8d; dwFlags
0x18001446d  xor     edx, edx; lpName
0x18001446f  xor     ecx, ecx; lpEventAttributes
0x180014471  call    cs:__imp_CreateEventExW
0x180014477  mov     [rbx+38h], rax
0x18001447b  test    rax, rax
0x18001447e  jnz     short loc_1800144A5
0x180014480  call    cs:__imp_GetLastError
0x180014486  mov     edi, eax
0x180014488  test    eax, eax
0x18001448a  jle     short loc_180014495
0x18001448c  movzx   edi, ax
0x18001448f  or      edi, 80070000h
0x180014495  test    edi, edi
0x180014497  jns     short loc_1800144A5
0x180014499  lea     rcx, [rsp+28h+arg_0]
0x18001449e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800144a3  jmp     short loc_1800144C4
0x1800144a5  mov     rax, [rbx]
0x1800144a8  mov     rcx, rbx
0x1800144ab  mov     rax, [rax+8]
0x1800144af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b4  nop
0x1800144b5  mov     [rsi], rbx
0x1800144b8  lea     rcx, [rsp+28h+arg_0]
0x1800144bd  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800144c2  xor     edi, edi
0x1800144c4  lea     rcx, [rsp+28h+arg_8]
0x1800144c9  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800144ce  mov     eax, edi
0x1800144d0  mov     rbx, [rsp+28h+arg_10]
0x1800144d5  mov     rsi, [rsp+28h+arg_18]
0x1800144da  add     rsp, 20h
0x1800144de  pop     rdi
0x1800144df  retn
```
