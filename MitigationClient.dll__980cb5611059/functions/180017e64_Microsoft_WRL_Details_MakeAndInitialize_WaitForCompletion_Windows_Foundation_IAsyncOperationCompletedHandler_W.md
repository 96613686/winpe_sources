# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180017e64`
- end: `0x180017f9c`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180018688`

## callees

- `0x18000ac20`
- `0x18001055c`
- `0x180014e9c`
- `0x180017e64`
- `0x180019918`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017f2d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180017f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f3c`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVUser_System_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>'::`2'::FTMEventDelegate::`vftable';
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
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<ServiceDrivenActionJsonDescriptor>::~MakeAllocator<ServiceDrivenActionJsonDescriptor>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017e64  mov     [rsp+arg_10], rbx
0x180017e69  mov     [rsp+arg_18], rsi
0x180017e6e  push    rdi
0x180017e6f  sub     rsp, 20h
0x180017e73  mov     rsi, rcx
0x180017e76  mov     qword ptr [rcx], 0
0x180017e7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017e84  mov     ecx, 40h ; '@'; unsigned __int64
0x180017e89  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017e8e  mov     rbx, rax
0x180017e91  mov     [rsp+28h+arg_8], rax
0x180017e96  test    rax, rax
0x180017e99  jnz     short loc_180017EA5
0x180017e9b  mov     edi, 8007000Eh
0x180017ea0  jmp     loc_180017F80
0x180017ea5  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'
0x180017eac  mov     [rbx], rax
0x180017eaf  lea     rdi, [rbx+8]
0x180017eb3  mov     rcx, rdi; this
0x180017eb6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180017ebb  mov     dword ptr [rbx+2Ch], 1
0x180017ec2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x180017ec9  mov     [rbx], rax
0x180017ecc  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180017ed3  mov     [rdi], rax
0x180017ed6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180017edd  test    rcx, rcx
0x180017ee0  jz      short loc_180017EEF
0x180017ee2  mov     rax, [rcx]
0x180017ee5  mov     rax, [rax+8]
0x180017ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eee  nop
0x180017eef  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>'}
0x180017ef6  mov     [rbx], rax
0x180017ef9  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180017f00  mov     [rdi], rax
0x180017f03  mov     dword ptr [rbx+30h], 0
0x180017f0a  mov     qword ptr [rbx+38h], 0
0x180017f12  mov     [rsp+28h+arg_0], rbx
0x180017f17  mov     [rsp+28h+arg_8], 0
0x180017f20  mov     r9d, 1F0003h; dwDesiredAccess
0x180017f26  xor     r8d, r8d; dwFlags
0x180017f29  xor     edx, edx; lpName
0x180017f2b  xor     ecx, ecx; lpEventAttributes
0x180017f2d  call    cs:__imp_CreateEventExW
0x180017f33  mov     [rbx+38h], rax
0x180017f37  test    rax, rax
0x180017f3a  jnz     short loc_180017F61
0x180017f3c  call    cs:__imp_GetLastError
0x180017f42  mov     edi, eax
0x180017f44  test    eax, eax
0x180017f46  jle     short loc_180017F51
0x180017f48  movzx   edi, ax
0x180017f4b  or      edi, 80070000h
0x180017f51  test    edi, edi
0x180017f53  jns     short loc_180017F61
0x180017f55  lea     rcx, [rsp+28h+arg_0]
0x180017f5a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017f5f  jmp     short loc_180017F80
0x180017f61  mov     rax, [rbx]
0x180017f64  mov     rcx, rbx
0x180017f67  mov     rax, [rax+8]
0x180017f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f70  nop
0x180017f71  mov     [rsi], rbx
0x180017f74  lea     rcx, [rsp+28h+arg_0]
0x180017f79  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017f7e  xor     edi, edi
0x180017f80  lea     rcx, [rsp+28h+arg_8]
0x180017f85  call    ??1?$MakeAllocator@VServiceDrivenActionJsonDescriptor@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<ServiceDrivenActionJsonDescriptor>::~MakeAllocator<ServiceDrivenActionJsonDescriptor>(void)
0x180017f8a  mov     eax, edi
0x180017f8c  mov     rbx, [rsp+28h+arg_10]
0x180017f91  mov     rsi, [rsp+28h+arg_18]
0x180017f96  add     rsp, 20h
0x180017f9a  pop     rdi
0x180017f9b  retn
```
