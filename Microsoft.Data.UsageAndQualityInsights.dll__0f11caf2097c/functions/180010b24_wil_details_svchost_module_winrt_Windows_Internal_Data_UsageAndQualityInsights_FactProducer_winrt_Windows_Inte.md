# wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes(void)

- ea: `0x180010b24`
- end: `0x180010d18`
- name: `?populate_winrt_runtime_classes@?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@AEAAXXZ`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000f1c0`

## callees

- `0x1800033d0`
- `0x1800033f4`
- `0x1800040a0`
- `0x180004140`
- `0x18000c6b4`
- `0x18000cc44`
- `0x18000dd08`
- `0x18000e180`
- `0x180010b24`
- `0x18001112c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010d05`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c9e`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180010cbe`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180010cbe`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x180010c96`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x180010c96`

## string_xrefs

- `0x180010c6c`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes(
        __int64 a1)
{
  unsigned int v2; // edx
  struct winrt::impl::shared_hstring_header *v3; // rsi
  unsigned int v4; // edx
  void *v5; // rbx
  int v6; // ecx
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v8; // rsi
  __int64 v9; // rcx
  void *v10; // rbx
  int v11; // edi
  HANDLE v12; // rax
  _QWORD *v13; // rdi
  __int64 v14; // rsi
  DWORD LastError; // ebx
  int v16; // eax
  _OWORD v17[2]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v18; // [rsp+40h] [rbp-59h]
  _OWORD v19[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v20; // [rsp+68h] [rbp-31h]
  int v21; // [rsp+70h] [rbp-29h] BYREF
  const char *v22; // [rsp+78h] [rbp-21h]
  __int64 v23; // [rsp+80h] [rbp-19h]
  LPVOID lpMem[2]; // [rsp+88h] [rbp-11h] BYREF
  __int128 v25; // [rsp+98h] [rbp-1h]
  __int64 v26; // [rsp+A8h] [rbp+Fh]

  *(_OWORD *)lpMem = 0;
  v25 = 0;
  v26 = 0;
  __builtin_array_init_helper_eh<winrt::hstring>(lpMem);
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x3A, v2);
  memcpy_s((char *)v3 + 28, 0x74u, L"Windows.Internal.Data.UsageAndQualityInsights.FactProducer", 0x74u);
  v5 = lpMem[0];
  if ( lpMem[0] )
  {
    v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        goto LABEL_13;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v5);
    }
  }
  lpMem[0] = v3;
  *(_QWORD *)&v19[0] = v3;
  *(_QWORD *)&v17[0] = DllGetActivationFactory;
  v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x3A, v4);
  memcpy_s((char *)v8 + 28, 0x74u, L"Windows.Internal.Data.UsageAndQualityInsights.FactConsumer", 0x74u);
  v10 = lpMem[1];
  if ( !lpMem[1] )
    goto LABEL_8;
  v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem[1] + 6);
  if ( !v11 )
  {
    v12 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v12, 0, v10);
    goto LABEL_8;
  }
  if ( v11 < 0 )
LABEL_13:
    abort();
LABEL_8:
  lpMem[1] = v8;
  *((_QWORD *)&v19[0] + 1) = v8;
  *((_QWORD *)&v17[0] + 1) = DllGetActivationFactory;
  wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes_helper<2>(
    v9,
    (volatile signed __int32 **)lpMem,
    v19,
    v17);
  v21 = 310;
  v22 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v23 = 0;
  v13 = (_QWORD *)(a1 + 8);
  v14 = *(_QWORD *)(a1 + 8);
  if ( v14 )
  {
    LastError = GetLastError();
    RoRevokeActivationFactories(v14);
    SetLastError(LastError);
  }
  *v13 = 0;
  v16 = ((__int64 (__fastcall *)(_OWORD *, _OWORD *, __int64, _QWORD *))RoRegisterActivationFactories)(v19, v17, 5, v13);
  if ( v16 < 0 )
    winrt::throw_hresult((unsigned int)v16, &v21);
  `eh vector destructor iterator'(lpMem, 8u, 5u, (void (*)(void *))winrt::hstring::~hstring);
}

```

## disassembly

```asm
0x180010b24  push    rbp
0x180010b26  push    rbx
0x180010b27  push    rsi
0x180010b28  push    rdi
0x180010b29  push    r14
0x180010b2b  push    r15
0x180010b2d  lea     rbp, [rsp-2Fh]
0x180010b32  sub     rsp, 0C8h
0x180010b39  mov     rax, cs:__security_cookie
0x180010b40  xor     rax, rsp
0x180010b43  mov     [rbp+57h+var_40], rax
0x180010b47  mov     r14, rcx
0x180010b4a  xorps   xmm0, xmm0
0x180010b4d  xor     eax, eax
0x180010b4f  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x180010b53  movups  [rbp+57h+var_58], xmm0
0x180010b57  mov     [rbp+57h+var_48], rax
0x180010b5b  lea     rcx, [rbp+57h+lpMem]
0x180010b5f  call    ??$__builtin_array_init_helper_eh@Uhstring@winrt@@@@YAXPEAUhstring@winrt@@_KP6AXPEAX@Z@Z; __builtin_array_init_helper_eh<winrt::hstring>(winrt::hstring *,unsigned __int64,void (*)(void *))
0x180010b64  nop
0x180010b65  xorps   xmm0, xmm0
0x180010b68  xor     eax, eax
0x180010b6a  movups  [rbp+57h+var_A8], xmm0
0x180010b6e  movups  [rbp+57h+var_98], xmm0
0x180010b72  mov     [rbp+57h+var_88], rax
0x180010b76  xorps   xmm1, xmm1
0x180010b79  movups  [rbp+57h+var_D0], xmm1
0x180010b7d  movups  [rbp+57h+var_C0], xmm1
0x180010b81  mov     [rbp+57h+var_B0], rax
0x180010b85  lea     ecx, [rax+3Ah]; this
0x180010b88  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180010b8d  mov     rsi, rax
0x180010b90  lea     rcx, [rax+1Ch]; Destination
0x180010b94  mov     r15d, 74h ; 't'
0x180010b9a  mov     r9d, r15d; SourceSize
0x180010b9d  lea     r8, aWindowsInterna; "Windows.Internal.Data.UsageAndQualityIn"...
0x180010ba4  mov     edx, r15d; DestinationSize
0x180010ba7  call    memcpy_s
0x180010bac  mov     rbx, [rbp+57h+lpMem]
0x180010bb0  or      edi, 0FFFFFFFFh
0x180010bb3  test    rbx, rbx
0x180010bb6  jz      short loc_180010BE1
0x180010bb8  mov     ecx, edi
0x180010bba  lock xadd [rbx+18h], ecx
0x180010bbf  sub     ecx, 1
0x180010bc2  jnz     short loc_180010BD9
0x180010bc4  nop
0x180010bc5  call    WINRT_IMPL_GetProcessHeap
0x180010bca  mov     rcx, rax; hHeap
0x180010bcd  mov     r8, rbx; lpMem
0x180010bd0  xor     edx, edx; dwFlags
0x180010bd2  call    WINRT_IMPL_HeapFree
0x180010bd7  jmp     short loc_180010BE1
0x180010bd9  test    ecx, ecx
0x180010bdb  js      loc_180010D05
0x180010be1  mov     [rbp+57h+lpMem], rsi
0x180010be5  mov     qword ptr [rbp+57h+var_A8], rsi
0x180010be9  lea     rax, DllGetActivationFactory
0x180010bf0  mov     qword ptr [rbp+57h+var_D0], rax
0x180010bf4  mov     ecx, 3Ah ; ':'; this
0x180010bf9  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180010bfe  mov     rsi, rax
0x180010c01  lea     rcx, [rax+1Ch]; Destination
0x180010c05  mov     r9, r15; SourceSize
0x180010c08  lea     r8, aWindowsInterna_3; "Windows.Internal.Data.UsageAndQualityIn"...
0x180010c0f  mov     rdx, r15; DestinationSize
0x180010c12  call    memcpy_s
0x180010c17  mov     rbx, [rbp+57h+lpMem+8]
0x180010c1b  test    rbx, rbx
0x180010c1e  jz      short loc_180010C41
0x180010c20  lock xadd [rbx+18h], edi
0x180010c25  sub     edi, 1
0x180010c28  jnz     loc_180010CFD
0x180010c2e  nop
0x180010c2f  call    WINRT_IMPL_GetProcessHeap
0x180010c34  mov     rcx, rax; hHeap
0x180010c37  mov     r8, rbx; lpMem
0x180010c3a  xor     edx, edx; dwFlags
0x180010c3c  call    WINRT_IMPL_HeapFree
0x180010c41  mov     [rbp+57h+lpMem+8], rsi
0x180010c45  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x180010c49  lea     rax, DllGetActivationFactory
0x180010c50  mov     qword ptr [rbp+57h+var_D0+8], rax
0x180010c54  lea     r9, [rbp+57h+var_D0]
0x180010c58  lea     r8, [rbp+57h+var_A8]
0x180010c5c  lea     rdx, [rbp+57h+lpMem]
0x180010c60  call    ??$populate_winrt_runtime_classes_helper@$01@?$svchost_module@UFactProducer@UsageAndQualityInsights@Data@Internal@Windows@winrt@@UFactConsumer@23456@UUQIMaintenanceTaskRun@Private@23456@UTestAPI@923456@UTestConfigurationRegistration@923456@@details@wil@@AEAAXAEAV?$array@Uhstring@winrt@@$04@std@@AEAV?$array@PEAUHSTRING__@@$04@4@AEAV?$array@P6AJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z$04@4@@Z; wil::details::svchost_module<winrt::Windows::Internal::Data::UsageAndQualityInsights::FactProducer,winrt::Windows::Internal::Data::UsageAndQualityInsights::FactConsumer,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestAPI,winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::TestConfigurationRegistration>::populate_winrt_runtime_classes_helper<2>(std::array<winrt::hstring,5> &,std::array<HSTRING__ *,5> &,std::array<long (*)(HSTRING__ *,IActivationFactory * *),5> &)
0x180010c65  mov     [rbp+57h+var_80], 136h
0x180010c6c  lea     rax, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x180010c73  mov     [rbp+57h+var_78], rax
0x180010c77  mov     [rbp+57h+var_70], 0
0x180010c7f  lea     rdi, [r14+8]
0x180010c83  mov     rsi, [rdi]
0x180010c86  test    rsi, rsi
0x180010c89  jz      short loc_180010CA4
0x180010c8b  call    cs:__imp_GetLastError
0x180010c91  mov     ebx, eax
0x180010c93  mov     rcx, rsi
0x180010c96  call    cs:__imp_RoRevokeActivationFactories
0x180010c9c  mov     ecx, ebx; dwErrCode
0x180010c9e  call    cs:__imp_SetLastError
0x180010ca4  mov     qword ptr [rdi], 0
0x180010cab  mov     r9, rdi
0x180010cae  mov     ebx, 5
0x180010cb3  mov     r8d, ebx
0x180010cb6  lea     rdx, [rbp+57h+var_D0]
0x180010cba  lea     rcx, [rbp+57h+var_A8]
0x180010cbe  call    cs:__imp_RoRegisterActivationFactories
0x180010cc4  test    eax, eax
0x180010cc6  js      short loc_180010D0C
0x180010cc8  lea     r9, ??1hstring@winrt@@QEAA@XZ; void (*)(void *)
0x180010ccf  mov     r8, rbx; unsigned __int64
0x180010cd2  mov     edx, 8; unsigned __int64
0x180010cd7  lea     rcx, [rbp+57h+lpMem]; void *
0x180010cdb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180010ce0  nop
0x180010ce1  mov     rcx, [rbp+57h+var_40]
0x180010ce5  xor     rcx, rsp; StackCookie
0x180010ce8  call    __security_check_cookie
0x180010ced  add     rsp, 0C8h
0x180010cf4  pop     r15
0x180010cf6  pop     r14
0x180010cf8  pop     rdi
0x180010cf9  pop     rsi
0x180010cfa  pop     rbx
0x180010cfb  pop     rbp
0x180010cfc  retn
0x180010cfd  test    edi, edi
0x180010cff  jns     loc_180010C41
0x180010d05  call    cs:__imp_abort
0x180010d0c  lea     rdx, [rbp+57h+var_80]
0x180010d10  mov     ecx, eax
0x180010d12  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
