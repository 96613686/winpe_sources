# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessForCapabilitiesForUserAsync(Windows::System::IUser *,Windows::Foundation::Collections::IIterable<HSTRING__ *> *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *> * *)

- ea: `0x18001a0b0`
- end: `0x18001a21e`
- name: `?RequestAccessForCapabilitiesForUserAsync@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAUIUser@System@5@PEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@5@PEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@5@@Z`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800041ac`
- `0x180011f9c`
- `0x180012c84`
- `0x1800132c4`
- `0x180013bb0`
- `0x18001428c`
- `0x18001a0b0`
- `0x18001b5ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a136`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a136`

## string_xrefs

- `0x18001a0e2`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a104`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a127`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessForCapabilitiesForUserAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  void (__fastcall ***v8)(_QWORD, __int64); // rax
  __int64 v9; // r8
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-68h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+44h] [rbp-44h]
  __int64 v18[4]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  void (__fastcall ***v20)(_QWORD, __int64); // [rsp+A8h] [rbp+20h] BYREF

  try
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)0x80004003LL,
        v13);
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)0x80070057LL,
        v13);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)0x80070057LL,
        v13);
    CurrentThreadId = GetCurrentThreadId();
    LODWORD(v20) = GetCurrentProcessId();
    *a4 = 0;
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>(
      &v15,
      a1 & ((unsigned __int128)-(__int128)(unsigned __int64)(a1 - 8) >> 64));
    lambda_9952fdbc610e2600acf16e55d695658d_::_lambda_9952fdbc610e2600acf16e55d695658d_(
      (unsigned int)v18,
      (unsigned int)&v15,
      a1 - 8,
      (unsigned int)&CurrentThreadId,
      (__int64)&v20);
    v16 = 3;
    v17 = 128;
    v8 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v20 = v8;
    if ( v8 )
      v8 = (void (__fastcall ***)(_QWORD, __int64))Windows::Internal::COperationLambdaVar_0__lambda_9952fdbc610e2600acf16e55d695658d__Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IMapView_HSTRING_____enum_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus____Windows::Foundation::Collections::IIterable_HSTRING______Windows::System::IUser_::COperationLambdaVar_0__lambda_9952fdbc610e2600acf16e55d695658d__Windows::Internal::CMarshaledInterfaceResult_Windows::Foundation::Collections::IMapView_HSTRING_____enum_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus____Windows::Foundation::Collections::IIterable_HSTRING______Windows::System::IUser___lambda_9952fdbc610e2600acf16e55d695658d___(
                                                     v8,
                                                     v18,
                                                     a3,
                                                     a2);
    v10 = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *,Windows::Internal::ComTaskPoolHandler>(
            (__int64)&v16,
            a4,
            v9,
            v8);
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(v18);
    wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(&v15);
    result = v10;
  }
  catch ( ... )
  {
    LODWORD(v20) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x78,
                     (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
                     v11);
    return (unsigned int)v20;
  }
  return result;
}

```

## disassembly

```asm
0x18001a0b0  mov     [rsp+arg_0], rbx
0x18001a0b5  mov     [rsp+arg_8], rsi
0x18001a0ba  push    rdi
0x18001a0bb  push    r14
0x18001a0bd  push    r15
0x18001a0bf  sub     rsp, 70h
0x18001a0c3  mov     rdi, r9
0x18001a0c6  mov     rsi, r8
0x18001a0c9  mov     r14, rdx
0x18001a0cc  mov     r15, rcx
0x18001a0cf  mov     rcx, [rsp+88h]; this
0x18001a0d7  test    r9, r9
0x18001a0da  jnz     short loc_18001A0F1
0x18001a0dc  mov     r9d, 80004003h; char *
0x18001a0e2  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a0e9  lea     edx, [rdi+5Ch]; void *
0x18001a0ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a0f1  mov     rcx, [rsp+88h]; this
0x18001a0f9  test    r14, r14
0x18001a0fc  jnz     short loc_18001A114
0x18001a0fe  mov     r9d, 80070057h; char *
0x18001a104  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a10b  lea     edx, [r14+5Dh]; void *
0x18001a10f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a114  mov     rcx, [rsp+88h]; this
0x18001a11c  test    rsi, rsi
0x18001a11f  jnz     short loc_18001A136
0x18001a121  mov     r9d, 80070057h; char *
0x18001a127  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a12e  lea     edx, [rsi+5Eh]; void *
0x18001a131  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a136  call    cs:__imp_GetCurrentThreadId
0x18001a13c  mov     [rsp+88h+var_58], eax
0x18001a140  call    cs:__imp_GetCurrentProcessId
0x18001a146  mov     dword ptr [rsp+88h+arg_18], eax
0x18001a14d  mov     qword ptr [rdi], 0
0x18001a154  lea     rax, [r15-8]
0x18001a158  neg     rax
0x18001a15b  sbb     rdx, rdx
0x18001a15e  and     rdx, r15
0x18001a161  lea     rcx, [rsp+88h+var_50]
0x18001a166  call    ??0?$com_ptr_t@UIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@@Z; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics,wil::err_returncode_policy>(Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *)
0x18001a16b  nop
0x18001a16c  lea     rax, [rsp+88h+arg_18]
0x18001a174  mov     qword ptr [rsp+88h+var_68], rax
0x18001a179  lea     r9, [rsp+88h+var_58]
0x18001a17e  lea     r8, [r15-8]
0x18001a182  lea     rdx, [rsp+88h+var_50]
0x18001a187  lea     rcx, [rsp+88h+var_38]
0x18001a18c  call    _lambda_9952fdbc610e2600acf16e55d695658d____lambda_9952fdbc610e2600acf16e55d695658d_
0x18001a191  nop
0x18001a192  mov     [rsp+88h+var_48], 3
0x18001a19a  mov     [rsp+88h+var_44], 80h
0x18001a1a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a1aa  mov     ecx, 40h ; '@'; unsigned __int64
0x18001a1af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a1b4  mov     [rsp+88h+arg_18], rax
0x18001a1bc  test    rax, rax
0x18001a1bf  jz      short loc_18001A1D5
0x18001a1c1  mov     r9, r14
0x18001a1c4  mov     r8, rsi
0x18001a1c7  lea     rdx, [rsp+88h+var_38]
0x18001a1cc  mov     rcx, rax
0x18001a1cf  call    Windows__Internal__COperationLambdaVar_0__lambda_9952fdbc610e2600acf16e55d695658d__Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IMapView_HSTRING_____enum_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessStatus____Windows__Foundation__Collections__IIterable_HSTRING______Windows__System__IUser___COperationLambdaVar_0__lambda_9952fdbc610e2600acf16e55d695658d__Windows__Internal__CMarshaledInterfaceResult_Windows__Foundation__Collections__IMapView_HSTRING_____enum_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessStatus____Windows__Foundation__Collections__IIterable_HSTRING______Windows__System__IUser___lambda_9952fdbc610e2600acf16e55d695658d___
0x18001a1d4  nop
0x18001a1d5  mov     r9, rax
0x18001a1d8  mov     rdx, rdi
0x18001a1db  lea     rcx, [rsp+88h+var_48]
0x18001a1e0  call    ??$MakeAsyncOperationHelper@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@3@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@U?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Collections@Foundation@Windows@@@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>> *)
0x18001a1e5  mov     ebx, eax
0x18001a1e7  lea     rcx, [rsp+88h+var_38]
0x18001a1ec  call    ??1?$com_ptr_t@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(void)
0x18001a1f1  nop
0x18001a1f2  lea     rcx, [rsp+88h+var_50]
0x18001a1f7  call    ??1?$com_ptr_t@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability,wil::err_returncode_policy>(void)
0x18001a1fc  mov     eax, ebx
0x18001a1fe  jmp     short loc_18001A207
0x18001a200  mov     eax, dword ptr [rsp+88h+arg_18]
0x18001a207  lea     r11, [rsp+88h+var_18]
0x18001a20c  mov     rbx, [r11+20h]
0x18001a210  mov     rsi, [r11+28h]
0x18001a214  mov     rsp, r11
0x18001a217  pop     r15
0x18001a219  pop     r14
0x18001a21b  pop     rdi
0x18001a21c  retn
```
