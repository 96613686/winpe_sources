# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180027a18`
- end: `0x180027b4f`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027cb8`

## callees

- `0x18001b8a4`
- `0x180027a18`
- `0x180028380`
- `0x180028604`
- `0x180033de0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027ad4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180027ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ae9`

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
0x180027a18  mov     [rsp+arg_10], rbx
0x180027a1d  mov     [rsp+arg_18], rsi
0x180027a22  push    rdi
0x180027a23  sub     rsp, 20h
0x180027a27  and     qword ptr [rcx], 0
0x180027a2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027a32  mov     rsi, rcx
0x180027a35  mov     ecx, 40h ; '@'; unsigned __int64
0x180027a3a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027a3f  mov     [rsp+28h+arg_8], rax
0x180027a44  mov     rdi, rax
0x180027a47  test    rax, rax
0x180027a4a  jnz     short loc_180027A56
0x180027a4c  mov     ebx, 8007000Eh
0x180027a51  jmp     loc_180027B32
0x180027a56  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>::`vftable'
0x180027a5d  lea     rbx, [rdi+8]
0x180027a61  mov     [rdi], rax
0x180027a64  mov     rcx, rbx; this
0x180027a67  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180027a6c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180027a73  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>'}
0x180027a7a  mov     [rdi], rax
0x180027a7d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180027a84  mov     [rbx], rax
0x180027a87  mov     dword ptr [rdi+2Ch], 1
0x180027a8e  test    rcx, rcx
0x180027a91  jz      short loc_180027A9F
0x180027a93  mov     rax, [rcx]
0x180027a96  mov     rax, [rax+8]
0x180027a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a9f  and     dword ptr [rdi+30h], 0
0x180027aa3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>'}
0x180027aaa  and     qword ptr [rdi+38h], 0
0x180027aaf  mov     r9d, 1F0003h; dwDesiredAccess
0x180027ab5  and     [rsp+28h+arg_8], 0
0x180027abb  xor     r8d, r8d; dwFlags
0x180027abe  mov     [rdi], rax
0x180027ac1  xor     edx, edx; lpName
0x180027ac3  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180027aca  mov     [rsp+28h+arg_0], rdi
0x180027acf  xor     ecx, ecx; lpEventAttributes
0x180027ad1  mov     [rbx], rax
0x180027ad4  call    cs:__imp_CreateEventExW
0x180027adb  nop     dword ptr [rax+rax+00h]
0x180027ae0  mov     [rdi+38h], rax
0x180027ae4  test    rax, rax
0x180027ae7  jnz     short loc_180027B14
0x180027ae9  call    cs:__imp_GetLastError
0x180027af0  nop     dword ptr [rax+rax+00h]
0x180027af5  mov     ebx, eax
0x180027af7  test    eax, eax
0x180027af9  jle     short loc_180027B04
0x180027afb  movzx   ebx, ax
0x180027afe  or      ebx, 80070000h
0x180027b04  test    ebx, ebx
0x180027b06  jns     short loc_180027B14
0x180027b08  lea     rcx, [rsp+28h+arg_0]
0x180027b0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027b12  jmp     short loc_180027B32
0x180027b14  mov     rax, [rdi]
0x180027b17  mov     rcx, rdi
0x180027b1a  mov     rax, [rax+8]
0x180027b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b23  lea     rcx, [rsp+28h+arg_0]
0x180027b28  mov     [rsi], rdi
0x180027b2b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027b30  xor     ebx, ebx
0x180027b32  lea     rcx, [rsp+28h+arg_8]
0x180027b37  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x180027b3c  mov     rsi, [rsp+28h+arg_18]
0x180027b41  mov     eax, ebx
0x180027b43  mov     rbx, [rsp+28h+arg_10]
0x180027b48  add     rsp, 20h
0x180027b4c  pop     rdi
0x180027b4d  retn
```
