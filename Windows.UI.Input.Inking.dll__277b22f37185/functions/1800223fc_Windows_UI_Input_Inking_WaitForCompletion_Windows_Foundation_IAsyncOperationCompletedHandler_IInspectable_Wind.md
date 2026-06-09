# Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *> *>(Windows::Foundation::IAsyncOperation<IInspectable *> *)

- ea: `0x1800223fc`
- end: `0x1800225ea`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@PEAU?$IAsyncOperation@PEAUIInspectable@@@23@@Inking@Input@UI@Windows@@YAJPEAU?$IAsyncOperation@PEAUIInspectable@@@Foundation@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030750`

## callees

- `0x18001332c`
- `0x180021010`
- `0x1800223fc`
- `0x18002dfe0`
- `0x1800328b0`
- `0x180033b04`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022502`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022502`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002241b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002241b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800224ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022578`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800225d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800224ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022578`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800225d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002255a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002255a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Windows::Foundation::IAsyncOperation<IInspectable *> *>(
        __int64 a1)
{
  void ****v2; // rax
  void ***v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  int LastError; // eax
  DWORD v8; // eax
  int v9; // eax
  int v10; // eax
  void **v11; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  __int64 v14; // [rsp+40h] [rbp+10h] BYREF
  void ***v15; // [rsp+48h] [rbp+18h] BYREF

  hHandle = CreateEventW(0, 0, 0, 0);
  v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  v15 = &v11;
  v2 = (void ****)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<IInspectable *>::*)(Windows::Foundation::IAsyncOperation<IInspectable *> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_e13d97e02be779787e714196168a6fb2_,-1,Windows::Foundation::IAsyncOperation<IInspectable *> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_e13d97e02be779787e714196168a6fb2_>(
                    &v14,
                    &v15);
  v3 = *v2;
  v15 = *v2;
  *v2 = 0;
  if ( v14 )
  {
    v14 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
  }
  v4 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)a1 + 48LL))(a1, v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)(unsigned int)v4,
      (int)v11);
    if ( v3 )
      ((void (__fastcall *)(void ***))(*v3)[2])(v3);
    v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( hHandle
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RaiseException(LastError, 1u, 0, 0);
      __debugbreak();
    }
    return v5;
  }
  v8 = WaitForSingleObject(hHandle, 0xFFFFFFFF);
  if ( v8 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x48,
           (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
           (const char *)v8,
           (unsigned int)v11);
    if ( v3 )
      ((void (__fastcall *)(void ***))(*v3)[2])(v3);
    v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !hHandle
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
    {
      return v5;
    }
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    RaiseException(v9, 1u, 0, 0);
  }
  if ( v3 )
    ((void (__fastcall *)(void ***))(*v3)[2])(v3);
  v11 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v11) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800223fc  mov     [rsp-8+arg_10], rbx
0x180022401  mov     [rsp-8+arg_18], rdi
0x180022406  push    rbp
0x180022407  mov     rbp, rsp
0x18002240a  sub     rsp, 30h
0x18002240e  mov     rdi, rcx
0x180022411  xor     r9d, r9d; lpName
0x180022414  xor     r8d, r8d; bInitialState
0x180022417  xor     edx, edx; bManualReset
0x180022419  xor     ecx, ecx; lpEventAttributes
0x18002241b  call    cs:__imp_CreateEventW
0x180022421  mov     [rbp+hHandle], rax
0x180022425  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18002242c  mov     [rbp+var_10], rax
0x180022430  lea     rax, [rbp+var_10]
0x180022434  mov     [rbp+arg_8], rax
0x180022438  lea     rdx, [rbp+arg_8]
0x18002243c  lea     rcx, [rbp+arg_0]
0x180022440  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_e13d97e02be779787e714196168a6fb2_@@$0?0PEAU?$IAsyncOperation@PEAUIInspectable@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAUIInspectable@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_e13d97e02be779787e714196168a6fb2_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_e13d97e02be779787e714196168a6fb2_@@$0?0PEAU?$IAsyncOperation@PEAUIInspectable@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@PEAUIInspectable@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAUIInspectable@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_e13d97e02be779787e714196168a6fb2_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<IInspectable *>::*)(Windows::Foundation::IAsyncOperation<IInspectable *> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<IInspectable *>,Microsoft::WRL::FtmBase>,_lambda_e13d97e02be779787e714196168a6fb2_,-1,Windows::Foundation::IAsyncOperation<IInspectable *> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_e13d97e02be779787e714196168a6fb2_>(_lambda_e13d97e02be779787e714196168a6fb2_ &&)
0x180022445  mov     rbx, [rax]
0x180022448  mov     [rbp+arg_8], rbx
0x18002244c  mov     qword ptr [rax], 0
0x180022453  mov     rcx, [rbp+arg_0]
0x180022457  test    rcx, rcx
0x18002245a  jz      short loc_18002246A
0x18002245c  mov     [rbp+arg_0], 0
0x180022464  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180022469  nop
0x18002246a  mov     rax, [rdi]
0x18002246d  mov     rdx, rbx
0x180022470  mov     rcx, rdi
0x180022473  mov     rax, [rax+30h]
0x180022477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002247c  mov     edi, eax
0x18002247e  test    eax, eax
0x180022480  jns     short loc_1800224FB
0x180022482  mov     rcx, [rbp+8]; this
0x180022486  mov     r9d, eax; char *
0x180022489  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022490  mov     edx, 47h ; 'G'; void *
0x180022495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002249a  nop
0x18002249b  test    rbx, rbx
0x18002249e  jz      short loc_1800224B0
0x1800224a0  mov     rax, [rbx]
0x1800224a3  mov     rcx, rbx
0x1800224a6  mov     rax, [rax+10h]
0x1800224aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224af  nop
0x1800224b0  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800224b7  mov     [rbp+var_10], rax
0x1800224bb  cmp     [rbp+hHandle], 0
0x1800224c0  jz      short loc_1800224F4
0x1800224c2  lea     rcx, [rbp+var_10]
0x1800224c6  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800224cb  test    al, al
0x1800224cd  jnz     short loc_1800224F4
0x1800224cf  call    cs:__imp_GetLastError
0x1800224d5  test    eax, eax
0x1800224d7  jle     short loc_1800224E1
0x1800224d9  movzx   eax, ax
0x1800224dc  or      eax, 80070000h
0x1800224e1  xor     r9d, r9d; lpArguments
0x1800224e4  xor     r8d, r8d; nNumberOfArguments
0x1800224e7  lea     edx, [r9+1]; dwExceptionFlags
0x1800224eb  mov     ecx, eax; dwExceptionCode
0x1800224ed  call    cs:__imp_RaiseException
0x1800224f3  int     3; Trap to Debugger
0x1800224f4  mov     eax, edi
0x1800224f6  jmp     loc_1800225DA
0x1800224fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800224fe  mov     rcx, [rbp+hHandle]; hHandle
0x180022502  call    cs:__imp_WaitForSingleObject
0x180022508  test    eax, eax
0x18002250a  jz      short loc_18002257F
0x18002250c  mov     rcx, [rbp+8]; this
0x180022510  mov     r9d, eax; char *
0x180022513  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x18002251a  mov     edx, 48h ; 'H'; void *
0x18002251f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022524  mov     edi, eax
0x180022526  test    rbx, rbx
0x180022529  jz      short loc_18002253B
0x18002252b  mov     rcx, [rbx]
0x18002252e  mov     rax, [rcx+10h]
0x180022532  mov     rcx, rbx
0x180022535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002253a  nop
0x18002253b  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022542  mov     [rbp+var_10], rax
0x180022546  cmp     [rbp+hHandle], 0
0x18002254b  jz      short loc_1800224F4
0x18002254d  lea     rcx, [rbp+var_10]
0x180022551  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180022556  test    al, al
0x180022558  jnz     short loc_1800224F4
0x18002255a  call    cs:__imp_GetLastError
0x180022560  test    eax, eax
0x180022562  jle     short loc_18002256C
0x180022564  movzx   eax, ax
0x180022567  or      eax, 80070000h
0x18002256c  xor     r9d, r9d; lpArguments
0x18002256f  xor     r8d, r8d; nNumberOfArguments
0x180022572  lea     edx, [r9+1]; dwExceptionFlags
0x180022576  mov     ecx, eax; dwExceptionCode
0x180022578  call    cs:__imp_RaiseException
0x18002257e  nop
0x18002257f  test    rbx, rbx
0x180022582  jz      short loc_180022594
0x180022584  mov     rax, [rbx]
0x180022587  mov     rcx, rbx
0x18002258a  mov     rax, [rax+10h]
0x18002258e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022593  nop
0x180022594  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18002259b  mov     [rbp+var_10], rax
0x18002259f  cmp     [rbp+hHandle], 0
0x1800225a4  jz      short loc_1800225D8
0x1800225a6  lea     rcx, [rbp+var_10]
0x1800225aa  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800225af  test    al, al
0x1800225b1  jnz     short loc_1800225D8
0x1800225b3  call    cs:__imp_GetLastError
0x1800225b9  test    eax, eax
0x1800225bb  jle     short loc_1800225C5
0x1800225bd  movzx   eax, ax
0x1800225c0  or      eax, 80070000h
0x1800225c5  xor     r9d, r9d; lpArguments
0x1800225c8  xor     r8d, r8d; nNumberOfArguments
0x1800225cb  lea     edx, [r9+1]; dwExceptionFlags
0x1800225cf  mov     ecx, eax; dwExceptionCode
0x1800225d1  call    cs:__imp_RaiseException
0x1800225d7  int     3; Trap to Debugger
0x1800225d8  xor     eax, eax
0x1800225da  mov     rbx, [rsp+30h+arg_10]
0x1800225df  mov     rdi, [rsp+30h+arg_18]
0x1800225e4  add     rsp, 30h
0x1800225e8  pop     rbp
0x1800225e9  retn
```
