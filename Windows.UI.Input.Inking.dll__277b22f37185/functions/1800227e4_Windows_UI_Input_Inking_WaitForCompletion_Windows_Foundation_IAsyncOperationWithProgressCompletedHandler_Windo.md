# Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *)

- ea: `0x1800227e4`
- end: `0x1800229d2`
- name: `??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@PEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@@Inking@Input@UI@Windows@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@3@@Z`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030750`

## callees

- `0x18001332c`
- `0x1800211b0`
- `0x1800227e4`
- `0x18002dfe0`
- `0x1800328b0`
- `0x180033b04`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800228ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800228ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022803`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022803`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800228d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022960`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800229b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800228d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180022960`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800229b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002299b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800228b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022942`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002299b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int> *>(
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
  v2 = (void ****)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Storage::Streams::IBuffer *,unsigned int>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,unsigned int>,Microsoft::WRL::FtmBase>,_lambda_f8d5a5afd245ca936e0fe7e3848ed351_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,unsigned int> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_f8d5a5afd245ca936e0fe7e3848ed351_>(
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
  v4 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)a1 + 64LL))(a1, v3);
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
0x1800227e4  mov     [rsp-8+arg_10], rbx
0x1800227e9  mov     [rsp-8+arg_18], rdi
0x1800227ee  push    rbp
0x1800227ef  mov     rbp, rsp
0x1800227f2  sub     rsp, 30h
0x1800227f6  mov     rdi, rcx
0x1800227f9  xor     r9d, r9d; lpName
0x1800227fc  xor     r8d, r8d; bInitialState
0x1800227ff  xor     edx, edx; bManualReset
0x180022801  xor     ecx, ecx; lpEventAttributes
0x180022803  call    cs:__imp_CreateEventW
0x180022809  mov     [rbp+hHandle], rax
0x18002280d  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022814  mov     [rbp+var_10], rax
0x180022818  lea     rax, [rbp+var_10]
0x18002281c  mov     [rbp+arg_8], rax
0x180022820  lea     rdx, [rbp+arg_8]
0x180022824  lea     rcx, [rbp+arg_0]
0x180022828  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_f8d5a5afd245ca936e0fe7e3848ed351_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_f8d5a5afd245ca936e0fe7e3848ed351_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_f8d5a5afd245ca936e0fe7e3848ed351_@@$0?0PEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationWithProgressCompletedHandler_impl@PEAUIBuffer@Streams@Storage@Windows@@I@Foundation@Windows@@EAAJPEAU?$IAsyncOperationWithProgress@PEAUIBuffer@Streams@Storage@Windows@@I@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_f8d5a5afd245ca936e0fe7e3848ed351_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationWithProgressCompletedHandler_impl<Windows::Storage::Streams::IBuffer *,uint>::*)(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IBuffer *,uint>,Microsoft::WRL::FtmBase>,_lambda_f8d5a5afd245ca936e0fe7e3848ed351_,-1,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IBuffer *,uint> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_f8d5a5afd245ca936e0fe7e3848ed351_>(_lambda_f8d5a5afd245ca936e0fe7e3848ed351_ &&)
0x18002282d  mov     rbx, [rax]
0x180022830  mov     [rbp+arg_8], rbx
0x180022834  mov     qword ptr [rax], 0
0x18002283b  mov     rcx, [rbp+arg_0]
0x18002283f  test    rcx, rcx
0x180022842  jz      short loc_180022852
0x180022844  mov     [rbp+arg_0], 0
0x18002284c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x180022851  nop
0x180022852  mov     rax, [rdi]
0x180022855  mov     rdx, rbx
0x180022858  mov     rcx, rdi
0x18002285b  mov     rax, [rax+40h]
0x18002285f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022864  mov     edi, eax
0x180022866  test    eax, eax
0x180022868  jns     short loc_1800228E3
0x18002286a  mov     rcx, [rbp+8]; this
0x18002286e  mov     r9d, eax; char *
0x180022871  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022878  mov     edx, 47h ; 'G'; void *
0x18002287d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022882  nop
0x180022883  test    rbx, rbx
0x180022886  jz      short loc_180022898
0x180022888  mov     rax, [rbx]
0x18002288b  mov     rcx, rbx
0x18002288e  mov     rax, [rax+10h]
0x180022892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022897  nop
0x180022898  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18002289f  mov     [rbp+var_10], rax
0x1800228a3  cmp     [rbp+hHandle], 0
0x1800228a8  jz      short loc_1800228DC
0x1800228aa  lea     rcx, [rbp+var_10]
0x1800228ae  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800228b3  test    al, al
0x1800228b5  jnz     short loc_1800228DC
0x1800228b7  call    cs:__imp_GetLastError
0x1800228bd  test    eax, eax
0x1800228bf  jle     short loc_1800228C9
0x1800228c1  movzx   eax, ax
0x1800228c4  or      eax, 80070000h
0x1800228c9  xor     r9d, r9d; lpArguments
0x1800228cc  xor     r8d, r8d; nNumberOfArguments
0x1800228cf  lea     edx, [r9+1]; dwExceptionFlags
0x1800228d3  mov     ecx, eax; dwExceptionCode
0x1800228d5  call    cs:__imp_RaiseException
0x1800228db  int     3; Trap to Debugger
0x1800228dc  mov     eax, edi
0x1800228de  jmp     loc_1800229C2
0x1800228e3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800228e6  mov     rcx, [rbp+hHandle]; hHandle
0x1800228ea  call    cs:__imp_WaitForSingleObject
0x1800228f0  test    eax, eax
0x1800228f2  jz      short loc_180022967
0x1800228f4  mov     rcx, [rbp+8]; this
0x1800228f8  mov     r9d, eax; char *
0x1800228fb  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180022902  mov     edx, 48h ; 'H'; void *
0x180022907  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002290c  mov     edi, eax
0x18002290e  test    rbx, rbx
0x180022911  jz      short loc_180022923
0x180022913  mov     rcx, [rbx]
0x180022916  mov     rax, [rcx+10h]
0x18002291a  mov     rcx, rbx
0x18002291d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022922  nop
0x180022923  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18002292a  mov     [rbp+var_10], rax
0x18002292e  cmp     [rbp+hHandle], 0
0x180022933  jz      short loc_1800228DC
0x180022935  lea     rcx, [rbp+var_10]
0x180022939  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x18002293e  test    al, al
0x180022940  jnz     short loc_1800228DC
0x180022942  call    cs:__imp_GetLastError
0x180022948  test    eax, eax
0x18002294a  jle     short loc_180022954
0x18002294c  movzx   eax, ax
0x18002294f  or      eax, 80070000h
0x180022954  xor     r9d, r9d; lpArguments
0x180022957  xor     r8d, r8d; nNumberOfArguments
0x18002295a  lea     edx, [r9+1]; dwExceptionFlags
0x18002295e  mov     ecx, eax; dwExceptionCode
0x180022960  call    cs:__imp_RaiseException
0x180022966  nop
0x180022967  test    rbx, rbx
0x18002296a  jz      short loc_18002297C
0x18002296c  mov     rax, [rbx]
0x18002296f  mov     rcx, rbx
0x180022972  mov     rax, [rax+10h]
0x180022976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002297b  nop
0x18002297c  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180022983  mov     [rbp+var_10], rax
0x180022987  cmp     [rbp+hHandle], 0
0x18002298c  jz      short loc_1800229C0
0x18002298e  lea     rcx, [rbp+var_10]
0x180022992  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180022997  test    al, al
0x180022999  jnz     short loc_1800229C0
0x18002299b  call    cs:__imp_GetLastError
0x1800229a1  test    eax, eax
0x1800229a3  jle     short loc_1800229AD
0x1800229a5  movzx   eax, ax
0x1800229a8  or      eax, 80070000h
0x1800229ad  xor     r9d, r9d; lpArguments
0x1800229b0  xor     r8d, r8d; nNumberOfArguments
0x1800229b3  lea     edx, [r9+1]; dwExceptionFlags
0x1800229b7  mov     ecx, eax; dwExceptionCode
0x1800229b9  call    cs:__imp_RaiseException
0x1800229bf  int     3; Trap to Debugger
0x1800229c0  xor     eax, eax
0x1800229c2  mov     rbx, [rsp+30h+arg_10]
0x1800229c7  mov     rdi, [rsp+30h+arg_18]
0x1800229cc  add     rsp, 30h
0x1800229d0  pop     rbp
0x1800229d1  retn
```
