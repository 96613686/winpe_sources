# `winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun::Initialize(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics const &)

- ea: `0x1400093c0`
- end: `0x140009406`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Initialize@UQIMaintenanceTaskRun@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@SA@XZ@SA@AEBUIUQIMaintenanceTaskRunStatics@456789@@Z`
- size: `70`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400093c0`
- `0x14000b0a8`
- `0x14000c010`

## string_xrefs

- `0x1400093c7`: `onecore\base\usageandqualityinsights\maintenancetask\exe\objfre\amd64\winrt/Windows.Internal.Data.UsageAndQualityInsights.Private.h`

## pseudocode

```c
__int64 __fastcall `winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun::Initialize'::`2'::_lambda_1_::_lambda_invoker_cdecl_(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax
  int v3; // [rsp+20h] [rbp-28h] BYREF
  const char *v4; // [rsp+28h] [rbp-20h]
  __int64 v5; // [rsp+30h] [rbp-18h]

  v1 = *a1;
  v4 = "onecore\\base\\usageandqualityinsights\\maintenancetask\\exe\\objfre\\amd64\\winrt/Windows.Internal.Data.UsageAnd"
       "QualityInsights.Private.h";
  v3 = 230;
  v5 = 0;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 48LL))(v1);
  if ( (int)result < 0 )
    winrt::throw_hresult((unsigned int)result, &v3);
  return result;
}

```

## disassembly

```asm
0x1400093c0  sub     rsp, 48h
0x1400093c4  mov     rcx, [rcx]
0x1400093c7  lea     rax, aOnecoreBaseUsa; "onecore\\base\\usageandqualityinsights"...
0x1400093ce  mov     [rsp+48h+var_20], rax
0x1400093d3  mov     [rsp+48h+var_28], 0E6h
0x1400093db  mov     [rsp+48h+var_18], 0
0x1400093e4  mov     rax, [rcx]
0x1400093e7  mov     rax, [rax+30h]
0x1400093eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093f0  test    eax, eax
0x1400093f2  js      short loc_1400093F9
0x1400093f4  add     rsp, 48h
0x1400093f8  retn
0x1400093f9  lea     rdx, [rsp+48h+var_28]
0x1400093fe  mov     ecx, eax
0x140009400  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
