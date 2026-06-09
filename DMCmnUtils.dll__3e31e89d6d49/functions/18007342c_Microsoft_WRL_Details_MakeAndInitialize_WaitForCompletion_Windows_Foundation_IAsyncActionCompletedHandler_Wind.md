# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18007342c`
- end: `0x180073567`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180073a34`

## callees

- `0x1800520f0`
- `0x18006394c`
- `0x180063a1c`
- `0x180064a44`
- `0x18007342c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800734eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800734eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073500`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        char **a1)
{
  char *v2; // rax
  char *v3; // rbx
  signed int v4; // edi
  _QWORD *v5; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  char *v9; // [rsp+30h] [rbp+8h] BYREF
  char *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    v5 = v2 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 7) = 0;
    v9 = v3;
    v10 = 0;
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
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007342c  mov     [rsp+arg_10], rbx
0x180073431  mov     [rsp+arg_18], rsi
0x180073436  push    rdi
0x180073437  sub     rsp, 20h
0x18007343b  mov     rsi, rcx
0x18007343e  mov     qword ptr [rcx], 0
0x180073445  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007344c  mov     ecx, 40h ; '@'; unsigned __int64
0x180073451  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180073456  mov     rbx, rax
0x180073459  mov     [rsp+28h+arg_8], rax
0x18007345e  test    rax, rax
0x180073461  jnz     short loc_18007346D
0x180073463  mov     edi, 8007000Eh
0x180073468  jmp     loc_18007354A
0x18007346d  lea     rdi, [rax+8]
0x180073471  mov     rcx, rdi; this
0x180073474  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180073479  mov     dword ptr [rbx+2Ch], 1
0x180073480  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x180073487  mov     [rbx], rax
0x18007348a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180073491  mov     [rdi], rax
0x180073494  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18007349b  test    rcx, rcx
0x18007349e  jz      short loc_1800734AD
0x1800734a0  mov     rax, [rcx]
0x1800734a3  mov     rax, [rax+8]
0x1800734a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734ac  nop
0x1800734ad  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x1800734b4  mov     [rbx], rax
0x1800734b7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800734be  mov     [rdi], rax
0x1800734c1  mov     dword ptr [rbx+30h], 0
0x1800734c8  mov     qword ptr [rbx+38h], 0
0x1800734d0  mov     [rsp+28h+arg_0], rbx
0x1800734d5  mov     [rsp+28h+arg_8], 0
0x1800734de  mov     r9d, 1F0003h; dwDesiredAccess
0x1800734e4  xor     r8d, r8d; dwFlags
0x1800734e7  xor     edx, edx; lpName
0x1800734e9  xor     ecx, ecx; lpEventAttributes
0x1800734eb  call    cs:__imp_CreateEventExW
0x1800734f2  nop     dword ptr [rax+rax+00h]
0x1800734f7  mov     [rbx+38h], rax
0x1800734fb  test    rax, rax
0x1800734fe  jnz     short loc_18007352B
0x180073500  call    cs:__imp_GetLastError
0x180073507  nop     dword ptr [rax+rax+00h]
0x18007350c  mov     edi, eax
0x18007350e  test    eax, eax
0x180073510  jle     short loc_18007351B
0x180073512  movzx   edi, ax
0x180073515  or      edi, 80070000h
0x18007351b  test    edi, edi
0x18007351d  jns     short loc_18007352B
0x18007351f  lea     rcx, [rsp+28h+arg_0]
0x180073524  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073529  jmp     short loc_18007354A
0x18007352b  mov     rax, [rbx]
0x18007352e  mov     rcx, rbx
0x180073531  mov     rax, [rax+8]
0x180073535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007353a  nop
0x18007353b  mov     [rsi], rbx
0x18007353e  lea     rcx, [rsp+28h+arg_0]
0x180073543  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073548  xor     edi, edi
0x18007354a  lea     rcx, [rsp+28h+arg_8]
0x18007354f  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x180073554  mov     eax, edi
0x180073556  mov     rbx, [rsp+28h+arg_10]
0x18007355b  mov     rsi, [rsp+28h+arg_18]
0x180073560  add     rsp, 20h
0x180073564  pop     rdi
0x180073565  retn
```
