# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800264a8`
- end: `0x1800265df`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026748`

## callees

- `0x18001bc74`
- `0x1800264a8`
- `0x180026e10`
- `0x180027094`
- `0x180034150`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180026564`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180026564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026579`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rdi
  signed int v3; // ebx
  _QWORD *v4; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v9; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v10 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v10;
  if ( v10 )
  {
    v4 = v10 + 1;
    *v10 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 1));
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>'};
    v2[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v2 + 11) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_DWORD *)v2 + 12) = 0;
    v2[7] = 0;
    v10 = 0;
    *v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>'::`2'::FTMEventDelegate::`vftable';
    v9 = v2;
    *v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>'::`2'::FTMEventDelegate::`vftable';
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v2[7] = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_QWORD *))(*v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserSelectionResult_UserSelection_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800264a8  mov     [rsp+arg_10], rbx
0x1800264ad  mov     [rsp+arg_18], rsi
0x1800264b2  push    rdi
0x1800264b3  sub     rsp, 20h
0x1800264b7  and     qword ptr [rcx], 0
0x1800264bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800264c2  mov     rsi, rcx
0x1800264c5  mov     ecx, 40h ; '@'; unsigned __int64
0x1800264ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800264cf  mov     [rsp+28h+arg_8], rax
0x1800264d4  mov     rdi, rax
0x1800264d7  test    rax, rax
0x1800264da  jnz     short loc_1800264E6
0x1800264dc  mov     ebx, 8007000Eh
0x1800264e1  jmp     loc_1800265C2
0x1800264e6  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>::`vftable'
0x1800264ed  lea     rbx, [rdi+8]
0x1800264f1  mov     [rdi], rax
0x1800264f4  mov     rcx, rbx; this
0x1800264f7  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800264fc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180026503  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>'}
0x18002650a  mov     [rdi], rax
0x18002650d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180026514  mov     [rbx], rax
0x180026517  mov     dword ptr [rdi+2Ch], 1
0x18002651e  test    rcx, rcx
0x180026521  jz      short loc_18002652F
0x180026523  mov     rax, [rcx]
0x180026526  mov     rax, [rax+8]
0x18002652a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002652f  and     dword ptr [rdi+30h], 0
0x180026533  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>'}
0x18002653a  and     qword ptr [rdi+38h], 0
0x18002653f  mov     r9d, 1F0003h; dwDesiredAccess
0x180026545  and     [rsp+28h+arg_8], 0
0x18002654b  xor     r8d, r8d; dwFlags
0x18002654e  mov     [rdi], rax
0x180026551  xor     edx, edx; lpName
0x180026553  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002655a  mov     [rsp+28h+arg_0], rdi
0x18002655f  xor     ecx, ecx; lpEventAttributes
0x180026561  mov     [rbx], rax
0x180026564  call    cs:__imp_CreateEventExW
0x18002656b  nop     dword ptr [rax+rax+00h]
0x180026570  mov     [rdi+38h], rax
0x180026574  test    rax, rax
0x180026577  jnz     short loc_1800265A4
0x180026579  call    cs:__imp_GetLastError
0x180026580  nop     dword ptr [rax+rax+00h]
0x180026585  mov     ebx, eax
0x180026587  test    eax, eax
0x180026589  jle     short loc_180026594
0x18002658b  movzx   ebx, ax
0x18002658e  or      ebx, 80070000h
0x180026594  test    ebx, ebx
0x180026596  jns     short loc_1800265A4
0x180026598  lea     rcx, [rsp+28h+arg_0]
0x18002659d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800265a2  jmp     short loc_1800265C2
0x1800265a4  mov     rax, [rdi]
0x1800265a7  mov     rcx, rdi
0x1800265aa  mov     rax, [rax+8]
0x1800265ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265b3  lea     rcx, [rsp+28h+arg_0]
0x1800265b8  mov     [rsi], rdi
0x1800265bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800265c0  xor     ebx, ebx
0x1800265c2  lea     rcx, [rsp+28h+arg_8]
0x1800265c7  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x1800265cc  mov     rsi, [rsp+28h+arg_18]
0x1800265d1  mov     eax, ebx
0x1800265d3  mov     rbx, [rsp+28h+arg_10]
0x1800265d8  add     rsp, 20h
0x1800265dc  pop     rdi
0x1800265dd  retn
```
