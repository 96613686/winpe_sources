# `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::RunInContext<`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_>(`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::unregister_and_stop_and_wait(void)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::operator()(tagComCallData *)

- ea: `0x180011668`
- end: `0x1800116fd`
- name: `??R_lambda_1_@?1???$RunInContext@V_lambda_1_@?1??unregister_and_stop_and_wait@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAXXZ@@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAX$$QEAV0?1??unregister_and_stop_and_wait@123@AEAAXXZ@@Z@QEBAJPEAUtagComCallData@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ff70`

## callees

- `0x180011668`
- `0x180011c3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001169f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001169f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001168c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001168c`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1800116cd`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1800116cd`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x180011697`
- `api-ms-win-core-winrt-l1-1-0!RoRevokeActivationFactories` at `0x180011697`

## string_xrefs

- `0x1800116b5`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
__int64 __fastcall __R_lambda_1___1____RunInContext_V_lambda_1___1__unregister_and_stop_and_wait___svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAXXZ____svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAX__QEAV0_1__unregister_and_stop_and_wait_123_AEAAXXZ__Z_QEBAJPEAUtagComCallData___Z(
        __int64 a1,
        __int64 a2)
{
  __int64 *v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  DWORD LastError; // ebx
  HRESULT v6; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // [rsp+0h] [rbp-48h] BYREF
  int v12; // [rsp+20h] [rbp-28h] BYREF
  const char *v13; // [rsp+28h] [rbp-20h]
  __int64 v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+50h] [rbp+8h]

  v2 = *(__int64 **)(a2 + 8);
  v3 = *v2;
  v4 = *(_QWORD *)(*v2 + 8);
  if ( v4 )
  {
    LastError = GetLastError();
    RoRevokeActivationFactories(v4);
    SetLastError(LastError);
  }
  *(_QWORD *)(v3 + 8) = 0;
  v12 = 220;
  v13 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v14 = 0;
  v6 = CoDisconnectContext(0xFFFFFFFF);
  if ( v6 < 0 )
  {
    try
    {
      winrt::throw_hresult((unsigned int)v6, &v12);
    }
    catch ( ... )
    {
      *(_DWORD *)(v10 + 80) = wil::details::in1diag3::Return_CaughtException(retaddr, &v11, v8, v9);
      return (unsigned int)v16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011668  mov     [rsp+arg_8], rbx
0x18001166d  mov     [rsp+arg_10], rsi
0x180011672  mov     [rsp+arg_0], rcx
0x180011677  push    rdi
0x180011678  sub     rsp, 40h
0x18001167c  mov     rax, [rdx+8]
0x180011680  mov     rdi, [rax]
0x180011683  mov     rsi, [rdi+8]
0x180011687  test    rsi, rsi
0x18001168a  jz      short loc_1800116A5
0x18001168c  call    cs:__imp_GetLastError
0x180011692  mov     ebx, eax
0x180011694  mov     rcx, rsi
0x180011697  call    cs:__imp_RoRevokeActivationFactories
0x18001169d  mov     ecx, ebx; dwErrCode
0x18001169f  call    cs:__imp_SetLastError
0x1800116a5  mov     qword ptr [rdi+8], 0
0x1800116ad  mov     [rsp+48h+var_28], 0DCh
0x1800116b5  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x1800116bc  mov     [rsp+48h+var_20], rax
0x1800116c1  mov     [rsp+48h+var_18], 0
0x1800116ca  or      ecx, 0FFFFFFFFh; dwTimeout
0x1800116cd  call    cs:__imp_CoDisconnectContext
0x1800116d3  test    eax, eax
0x1800116d5  js      short loc_1800116EF
0x1800116d7  xor     eax, eax
0x1800116d9  jmp     short loc_1800116DF
0x1800116db  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800116df  mov     rbx, [rsp+48h+arg_8]
0x1800116e4  mov     rsi, [rsp+48h+arg_10]
0x1800116e9  add     rsp, 40h
0x1800116ed  pop     rdi
0x1800116ee  retn
0x1800116ef  lea     rdx, [rsp+48h+var_28]
0x1800116f4  mov     ecx, eax
0x1800116f6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
