# ConnectedStorage::WaitForAsync<Windows::Foundation::Collections::IPropertySet,Windows::Foundation::Collections::IPropertySet>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180028878`
- end: `0x180028aa8`
- name: `??$WaitForAsync@UIPropertySet@Collections@Foundation@Windows@@U1234@@ConnectedStorage@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@PEAPEAUIPropertySet@Collections@23@@Z`
- size: `560`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c408`

## callees

- `0x18002860c`
- `0x180028878`
- `0x18002c9f0`
- `0x18002d810`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028907`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028a34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028a8c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028907`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800289c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028a34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028a8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002889d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002889d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800289d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800289d2`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::WaitForAsync<Windows::Foundation::Collections::IPropertySet,Windows::Foundation::Collections::IPropertySet>(
        __int64 a1,
        __int64 a2)
{
  signed int LastError; // eax
  unsigned int v5; // edi
  __int64 (__fastcall *v7)(__int64, void ***); // rbx
  void ****v8; // rax
  void ***v9; // rdi
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // eax
  signed int v13; // eax
  int v14; // eax
  int v15; // eax
  void **v16; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-8h]
  __int64 v18; // [rsp+60h] [rbp+30h] BYREF
  void ***v19; // [rsp+68h] [rbp+38h] BYREF

  hHandle = CreateEventW(0, 0, 0, 0);
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !hHandle )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    return v5;
  }
  v7 = *(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)a1 + 48LL);
  v19 = &v16;
  v8 = (void ****)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Collections::IPropertySet *>::*)(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,enum ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>,_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_,-1,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,enum ABI::Windows::Foundation::AsyncStatus>,_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_>(
                    &v18,
                    &v19);
  v9 = *v8;
  v19 = *v8;
  *v8 = 0;
  v10 = v18;
  if ( v18 )
  {
    v18 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>>::Release(v10);
  }
  v11 = v7(a1, v9);
  if ( v9 )
    ((void (__fastcall *)(void ***))(*v9)[2])(v9);
  if ( v11 < 0 )
  {
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !hHandle
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v16) )
    {
      return (unsigned int)v11;
    }
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    RaiseException(v12, 1u, 0, 0);
  }
  if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
  {
    v13 = GetLastError();
    v5 = v13;
    if ( v13 > 0 )
      v5 = (unsigned __int16)v13 | 0x80070000;
    v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
    if ( !hHandle
      || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v16) )
    {
      return v5;
    }
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    RaiseException(v14, 1u, 0, 0);
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 64LL))(a1, a2);
  v16 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v16) )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    RaiseException(v15, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180028878  mov     [rsp-18h+arg_0], rbx
0x18002887d  mov     [rsp-18h+arg_8], rsi
0x180028882  push    rbp
0x180028883  push    rdi
0x180028884  push    r14
0x180028886  mov     rbp, rsp
0x180028889  sub     rsp, 30h
0x18002888d  mov     r14, rdx
0x180028890  mov     rsi, rcx
0x180028893  xor     r9d, r9d; lpName
0x180028896  xor     r8d, r8d; bInitialState
0x180028899  xor     edx, edx; bManualReset
0x18002889b  xor     ecx, ecx; lpEventAttributes
0x18002889d  call    cs:__imp_CreateEventW
0x1800288a3  mov     [rbp+hHandle], rax
0x1800288a7  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800288ae  mov     [rbp+var_10], rcx
0x1800288b2  test    rax, rax
0x1800288b5  jnz     short loc_180028915
0x1800288b7  call    cs:__imp_GetLastError
0x1800288bd  mov     edi, eax
0x1800288bf  mov     ebx, 80070000h
0x1800288c4  test    eax, eax
0x1800288c6  jle     short loc_1800288CD
0x1800288c8  movzx   edi, ax
0x1800288cb  or      edi, ebx
0x1800288cd  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800288d4  mov     [rbp+var_10], rax
0x1800288d8  cmp     [rbp+hHandle], 0
0x1800288dd  jz      short loc_18002890E
0x1800288df  lea     rcx, [rbp+var_10]
0x1800288e3  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800288e8  test    al, al
0x1800288ea  jnz     short loc_18002890E
0x1800288ec  call    cs:__imp_GetLastError
0x1800288f2  test    eax, eax
0x1800288f4  jle     short loc_1800288FB
0x1800288f6  movzx   eax, ax
0x1800288f9  or      eax, ebx
0x1800288fb  xor     r9d, r9d; lpArguments
0x1800288fe  xor     r8d, r8d; nNumberOfArguments
0x180028901  lea     edx, [r9+1]; dwExceptionFlags
0x180028905  mov     ecx, eax; dwExceptionCode
0x180028907  call    cs:__imp_RaiseException
0x18002890d  int     3; Trap to Debugger
0x18002890e  mov     eax, edi
0x180028910  jmp     loc_180028A95
0x180028915  mov     rax, [rsi]
0x180028918  mov     rbx, [rax+30h]
0x18002891c  lea     rax, [rbp+var_10]
0x180028920  mov     [rbp+arg_18], rax
0x180028924  lea     rdx, [rbp+arg_18]
0x180028928  lea     rcx, [rbp+arg_10]
0x18002892c  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_@@$0?0PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@V_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_@@$0?0PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@W4AsyncStatus@67ABI@@@?$DelegateArgTraits@P8?$IAsyncOperationCompletedHandler_impl@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@EAAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@23@W4AsyncStatus@23ABI@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IAsyncOperationCompletedHandler_impl<Windows::Foundation::Collections::IPropertySet *>::*)(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,ABI::Windows::Foundation::AsyncStatus)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>,_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_,-1,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *> *,ABI::Windows::Foundation::AsyncStatus>,_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_>(_lambda_c80181ebfc4b665a2fb3446ac5a0df4e_ &&)
0x180028931  mov     rdi, [rax]
0x180028934  mov     [rbp+arg_18], rdi
0x180028938  mov     qword ptr [rax], 0
0x18002893f  mov     rcx, [rbp+arg_10]
0x180028943  test    rcx, rcx
0x180028946  jz      short loc_180028956
0x180028948  mov     [rbp+arg_10], 0
0x180028950  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>>::Release(void)
0x180028955  nop
0x180028956  mov     rdx, rdi
0x180028959  mov     rcx, rsi
0x18002895c  mov     rax, rbx
0x18002895f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028964  mov     ebx, eax
0x180028966  test    rdi, rdi
0x180028969  jz      short loc_18002897B
0x18002896b  mov     rdx, [rdi]
0x18002896e  mov     rcx, rdi
0x180028971  mov     rax, [rdx+10h]
0x180028975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002897a  nop
0x18002897b  test    ebx, ebx
0x18002897d  jns     short loc_1800289CB
0x18002897f  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180028986  mov     [rbp+var_10], rax
0x18002898a  cmp     [rbp+hHandle], 0
0x18002898f  jz      loc_180028A93
0x180028995  lea     rcx, [rbp+var_10]
0x180028999  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x18002899e  test    al, al
0x1800289a0  jnz     loc_180028A93
0x1800289a6  call    cs:__imp_GetLastError
0x1800289ac  test    eax, eax
0x1800289ae  jle     short loc_1800289B8
0x1800289b0  movzx   eax, ax
0x1800289b3  or      eax, 80070000h
0x1800289b8  xor     r9d, r9d; lpArguments
0x1800289bb  xor     r8d, r8d; nNumberOfArguments
0x1800289be  lea     edx, [r9+1]; dwExceptionFlags
0x1800289c2  mov     ecx, eax; dwExceptionCode
0x1800289c4  call    cs:__imp_RaiseException
0x1800289ca  nop
0x1800289cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800289ce  mov     rcx, [rbp+hHandle]; hHandle
0x1800289d2  call    cs:__imp_WaitForSingleObject
0x1800289d8  test    eax, eax
0x1800289da  jz      short loc_180028A3B
0x1800289dc  call    cs:__imp_GetLastError
0x1800289e2  mov     edi, eax
0x1800289e4  mov     ebx, 80070000h
0x1800289e9  test    eax, eax
0x1800289eb  jle     short loc_1800289F2
0x1800289ed  movzx   edi, ax
0x1800289f0  or      edi, ebx
0x1800289f2  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1800289f9  mov     [rbp+var_10], rax
0x1800289fd  cmp     [rbp+hHandle], 0
0x180028a02  jz      loc_18002890E
0x180028a08  lea     rcx, [rbp+var_10]
0x180028a0c  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180028a11  test    al, al
0x180028a13  jnz     loc_18002890E
0x180028a19  call    cs:__imp_GetLastError
0x180028a1f  test    eax, eax
0x180028a21  jle     short loc_180028A28
0x180028a23  movzx   eax, ax
0x180028a26  or      eax, ebx
0x180028a28  xor     r9d, r9d; lpArguments
0x180028a2b  xor     r8d, r8d; nNumberOfArguments
0x180028a2e  lea     edx, [r9+1]; dwExceptionFlags
0x180028a32  mov     ecx, eax; dwExceptionCode
0x180028a34  call    cs:__imp_RaiseException
0x180028a3a  nop
0x180028a3b  mov     rax, [rsi]
0x180028a3e  mov     rdx, r14
0x180028a41  mov     rcx, rsi
0x180028a44  mov     rax, [rax+40h]
0x180028a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a4d  mov     ebx, eax
0x180028a4f  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180028a56  mov     [rbp+var_10], rax
0x180028a5a  cmp     [rbp+hHandle], 0
0x180028a5f  jz      short loc_180028A93
0x180028a61  lea     rcx, [rbp+var_10]
0x180028a65  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x180028a6a  test    al, al
0x180028a6c  jnz     short loc_180028A93
0x180028a6e  call    cs:__imp_GetLastError
0x180028a74  test    eax, eax
0x180028a76  jle     short loc_180028A80
0x180028a78  movzx   eax, ax
0x180028a7b  or      eax, 80070000h
0x180028a80  xor     r9d, r9d; lpArguments
0x180028a83  xor     r8d, r8d; nNumberOfArguments
0x180028a86  lea     edx, [r9+1]; dwExceptionFlags
0x180028a8a  mov     ecx, eax; dwExceptionCode
0x180028a8c  call    cs:__imp_RaiseException
0x180028a92  int     3; Trap to Debugger
0x180028a93  mov     eax, ebx
0x180028a95  mov     rbx, [rsp+30h+arg_0]
0x180028a9a  mov     rsi, [rsp+30h+arg_8]
0x180028a9f  add     rsp, 30h
0x180028aa3  pop     r14
0x180028aa5  pop     rdi
0x180028aa6  pop     rbp
0x180028aa7  retn
```
