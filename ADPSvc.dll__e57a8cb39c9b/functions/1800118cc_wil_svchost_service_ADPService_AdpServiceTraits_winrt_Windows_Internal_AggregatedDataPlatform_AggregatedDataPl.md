# wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main(void)

- ea: `0x1800118cc`
- end: `0x180011956`
- name: `?main@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@QEAAXXZ`
- size: `138`
- prototype: `__int64 __fastcall(__int64, const struct winrt::impl::slim_source_location *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000aa80`

## callees

- `0x1800118cc`
- `0x18001195c`
- `0x180011e68`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001190d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001190d`

## string_xrefs

- `0x1800118db`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
__int64 __fastcall wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main(
        __int64 a1,
        const struct winrt::impl::slim_source_location *a2)
{
  SERVICE_STATUS_HANDLE v2; // rax
  const struct winrt::impl::slim_source_location *v3; // rdx
  __int64 result; // rax
  const winrt::hresult_error *v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h] BYREF
  const char *v7; // [rsp+30h] [rbp-18h]
  __int64 v8; // [rsp+38h] [rbp-10h]

  v6 = 383;
  v7 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v8 = 0;
  if ( !ADPService::g_service )
    winrt::throw_last_error((winrt *)&v6, a2);
  v2 = RegisterServiceCtrlHandlerExW(
         L"ADPSvc",
         (LPHANDLER_FUNCTION_EX)`wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::main'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
         &ADPService::g_service);
  qword_18010F9E0 = (__int64)v2;
  v6 = 390;
  v7 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v8 = 0;
  if ( !v2 )
    winrt::throw_last_error((winrt *)&v6, v3);
  try
  {
    result = wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start();
  }
  catch ( const winrt::hresult_error *v5 )
  {
    return wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::stop(
             &ADPService::g_service,
             *((unsigned int *)v5 + 3));
  }
  result = wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start();
}

```

## disassembly

```asm
0x1800118cc  mov     rax, rsp
0x1800118cf  push    rdi
0x1800118d0  sub     rsp, 40h
0x1800118d4  mov     dword ptr [rax-20h], 17Fh
0x1800118db  lea     rdi, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x1800118e2  mov     [rax-18h], rdi
0x1800118e6  mov     qword ptr [rax-10h], 0
0x1800118ee  cmp     cs:?g_service@ADPService@@3V?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@A, 0; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform> ADPService::g_service
0x1800118f6  jz      short loc_180011941
0x1800118f8  lea     r8, ?g_service@ADPService@@3V?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@A; lpContext
0x1800118ff  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??main@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@QEAAXXZ@SA@KKPEAX0@Z; lpHandlerProc
0x180011906  lea     rcx, ServiceName; "ADPSvc"
0x18001190d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011913  mov     cs:qword_18010F9E0, rax
0x18001191a  mov     [rsp+48h+var_20], 186h
0x180011922  mov     [rsp+48h+var_18], rdi
0x180011927  mov     [rsp+48h+var_10], 0
0x180011930  test    rax, rax
0x180011933  jz      short loc_18001194B
0x180011935  call    ?start@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXXZ; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start(void)
0x18001193a  nop
0x18001193b  add     rsp, 40h
0x18001193f  pop     rdi
0x180011940  retn
0x180011941  lea     rcx, [rax-20h]; this
0x180011945  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x18001194b  lea     rcx, [rsp+48h+var_20]; this
0x180011950  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
