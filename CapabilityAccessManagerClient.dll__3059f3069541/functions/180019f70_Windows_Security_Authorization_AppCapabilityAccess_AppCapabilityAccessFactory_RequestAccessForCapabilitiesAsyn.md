# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessForCapabilitiesAsync(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *> * *)

- ea: `0x180019f70`
- end: `0x18001a0aa`
- name: `?RequestAccessForCapabilitiesAsync@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@5@PEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@85@@Z`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800041ac`
- `0x180011ea4`
- `0x180012c84`
- `0x1800132c4`
- `0x180013bb0`
- `0x18001428c`
- `0x180019f70`
- `0x18001b5ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019fd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019fd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019fc4`

## string_xrefs

- `0x180019f96`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x180019fb5`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessForCapabilitiesAsync(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  void (__fastcall ***v6)(_QWORD, __int64); // rax
  __int64 v7; // r8
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+38h] [rbp-40h] BYREF
  __int64 v14; // [rsp+3Ch] [rbp-3Ch]
  __int64 v15[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  void (__fastcall ***v17)(_QWORD, __int64); // [rsp+90h] [rbp+18h] BYREF
  DWORD CurrentThreadId; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)0x80004003LL,
        v11);
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)0x80070057LL,
        v11);
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(v17) = GetCurrentProcessId();
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>(
      &v12,
      a1 & ((unsigned __int128)-(__int128)(unsigned __int64)(a1 - 8) >> 64));
    *a3 = 0;
    lambda_9952fdbc610e2600acf16e55d695658d_::_lambda_9952fdbc610e2600acf16e55d695658d_(
      (unsigned int)v15,
      (unsigned int)&v12,
      a1 - 8,
      (unsigned int)&CurrentThreadId,
      (__int64)&v17);
    v13 = 3;
    v14 = 128;
    v6 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v6;
    if ( v6 )
      v6 = (void (__fastcall ***)(_QWORD, __int64))Windows::Internal::COperationLambdaVar_0__lambda_66f2e60fe7bee591180ab6e1431991d8__Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IMapView_HSTRING_____enum_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus____Windows::Foundation::Collections::IIterable_HSTRING_______::COperationLambdaVar_0__lambda_66f2e60fe7bee591180ab6e1431991d8__Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IMapView_HSTRING_____enum_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus____Windows::Foundation::Collections::IIterable_HSTRING_________lambda_66f2e60fe7bee591180ab6e1431991d8___(
                                                     v6,
                                                     v15,
                                                     a2);
    v8 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *,Windows::Internal::ComTaskPoolHandler>(
           (__int64)&v13,
           a3,
           v7,
           v6);
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(v15);
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(&v12);
    result = v8;
  }
  catch ( ... )
  {
    LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x55,
                     (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
                     v9);
    return (unsigned int)v17;
  }
  return result;
}

```

## disassembly

```asm
0x180019f70  mov     [rsp+arg_0], rbx
0x180019f75  push    rsi
0x180019f76  push    rdi
0x180019f77  push    r14
0x180019f79  sub     rsp, 60h
0x180019f7d  mov     rdi, r8
0x180019f80  mov     rsi, rdx
0x180019f83  mov     r14, rcx
0x180019f86  mov     rcx, [rsp+78h]; this
0x180019f8b  test    r8, r8
0x180019f8e  jnz     short loc_180019FA5
0x180019f90  mov     r9d, 80004003h; char *
0x180019f96  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180019f9d  lea     edx, [rdi+3Ah]; void *
0x180019fa0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019fa5  mov     rcx, [rsp+78h]; this
0x180019faa  test    rsi, rsi
0x180019fad  jnz     short loc_180019FC4
0x180019faf  mov     r9d, 80070057h; char *
0x180019fb5  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x180019fbc  lea     edx, [rsi+3Bh]; void *
0x180019fbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019fc4  call    cs:__imp_GetCurrentThreadId
0x180019fca  mov     [rsp+78h+arg_18], eax
0x180019fd1  call    cs:__imp_GetCurrentProcessId
0x180019fd7  mov     dword ptr [rsp+78h+arg_10], eax
0x180019fde  lea     rax, [r14-8]
0x180019fe2  neg     rax
0x180019fe5  sbb     rdx, rdx
0x180019fe8  and     rdx, r14
0x180019feb  lea     rcx, [rsp+78h+var_48]
0x180019ff0  call    ??0?$com_ptr_t@UIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@@Z; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>(Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *)
0x180019ff5  nop
0x180019ff6  mov     qword ptr [rdi], 0
0x180019ffd  lea     rax, [rsp+78h+arg_10]
0x18001a005  mov     qword ptr [rsp+78h+var_58], rax
0x18001a00a  lea     r9, [rsp+78h+arg_18]
0x18001a012  lea     r8, [r14-8]
0x18001a016  lea     rdx, [rsp+78h+var_48]
0x18001a01b  lea     rcx, [rsp+78h+var_30]
0x18001a020  call    _lambda_9952fdbc610e2600acf16e55d695658d____lambda_9952fdbc610e2600acf16e55d695658d_
0x18001a025  nop
0x18001a026  mov     [rsp+78h+var_40], 3
0x18001a02e  mov     [rsp+78h+var_3C], 80h
0x18001a037  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a03e  mov     ecx, 38h ; '8'; unsigned __int64
0x18001a043  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a048  mov     [rsp+78h+arg_10], rax
0x18001a050  test    rax, rax
0x18001a053  jz      short loc_18001A066
0x18001a055  mov     r8, rsi
0x18001a058  lea     rdx, [rsp+78h+var_30]
0x18001a05d  mov     rcx, rax
0x18001a060  call    Windows__Internal__COperationLambdaVar_0__lambda_66f2e60fe7bee591180ab6e1431991d8__Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IMapView_HSTRING_____enum_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessStatus____Windows__Foundation__Collections__IIterable_HSTRING_________COperationLambdaVar_0__lambda_66f2e60fe7bee591180ab6e1431991d8__Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IMapView_HSTRING_____enum_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessStatus____Windows__Foundation__Collections__IIterable_HSTRING_________lambda_66f2e60fe7bee591180ab6e1431991d8___
0x18001a065  nop
0x18001a066  mov     r9, rax
0x18001a069  mov     rdx, rdi
0x18001a06c  lea     rcx, [rsp+78h+var_40]
0x18001a071  call    ??$MakeAsyncOperationHelper@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@3@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>> *)
0x18001a076  mov     ebx, eax
0x18001a078  lea     rcx, [rsp+78h+var_30]
0x18001a07d  call    ??1?$com_ptr_t@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(void)
0x18001a082  nop
0x18001a083  lea     rcx, [rsp+78h+var_48]
0x18001a088  call    ??1?$com_ptr_t@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(void)
0x18001a08d  mov     eax, ebx
0x18001a08f  jmp     short loc_18001A098
0x18001a091  mov     eax, dword ptr [rsp+78h+arg_10]
0x18001a098  mov     rbx, [rsp+78h+arg_0]
0x18001a0a0  add     rsp, 60h
0x18001a0a4  pop     r14
0x18001a0a6  pop     rdi
0x18001a0a7  pop     rsi
0x18001a0a8  retn
```
