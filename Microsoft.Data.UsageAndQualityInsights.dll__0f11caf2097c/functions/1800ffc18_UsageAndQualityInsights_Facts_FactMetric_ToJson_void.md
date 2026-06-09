# UsageAndQualityInsights::Facts::FactMetric::ToJson(void)

- ea: `0x1800ffc18`
- end: `0x1800fffe8`
- name: `?ToJson@FactMetric@Facts@UsageAndQualityInsights@@QEBA?AUJsonObject@Json@Data@Windows@winrt@@XZ`
- size: `976`
- prototype: `struct winrt::Windows::Data::Json::JsonObject __high(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180045168`

## callees

- `0x1800040a0`
- `0x180004140`
- `0x180005e7c`
- `0x18000c844`
- `0x18001a8f4`
- `0x1800e2cb4`
- `0x1800e33bc`
- `0x1800e347c`
- `0x1800f8fe4`
- `0x1800ff8e8`
- `0x1800ffc18`
- `0x1800ffff0`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffc6e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffccc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffd3d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffdda`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffde5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffe7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffe8a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800fff21`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800fff50`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffc6e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffccc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffd3d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffdda`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffde5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffe7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800ffe8a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800fff21`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800fff50`

## string_xrefs

- `0x1800fffd6`: `onecore\base\usageandqualityinsights\service\lib\factstore\factmetric.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
winrt::Windows::Data::Json::JsonObject *__fastcall UsageAndQualityInsights::Facts::FactMetric::ToJson(
        __int64 a1,
        winrt::Windows::Data::Json::JsonObject *a2)
{
  double v2; // xmm0_8
  __int64 NumberValue; // rax
  __int64 v6; // rax
  __int64 StringValue; // rax
  void *v8; // rdi
  int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 v11; // rax
  void *v12; // rdi
  int v13; // eax
  HANDLE v14; // rax
  __int64 v15; // rax
  void *v16; // rdi
  int v17; // esi
  HANDLE v18; // rax
  void (__fastcall ***v19)(_QWORD, void *, __int64 *); // rcx
  __int64 v20; // rdi
  unsigned int v22; // eax
  const char *v23; // [rsp+28h] [rbp-58h]
  int *v24; // [rsp+38h] [rbp-48h] BYREF
  int v25; // [rsp+40h] [rbp-40h] BYREF
  int v26; // [rsp+44h] [rbp-3Ch]
  const wchar_t *v27; // [rsp+50h] [rbp-30h]
  __int64 v28; // [rsp+58h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v30; // [rsp+C0h] [rbp+40h] BYREF
  winrt::Windows::Data::Json::JsonObject *v31; // [rsp+C8h] [rbp+48h]
  LPVOID lpMem; // [rsp+D0h] [rbp+50h] BYREF

  v31 = a2;
  winrt::Windows::Data::Json::JsonObject::JsonObject(a2);
  NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v2);
  if ( aMetrictype[10] )
    abort();
  v25 = 1;
  v26 = 10;
  v27 = L"metricType";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    NumberValue);
  if ( v30 )
    v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  v6 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v2);
  if ( aCount[5] )
    abort();
  v25 = 1;
  v26 = 5;
  v27 = L"count";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    v6);
  if ( v30 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  v28 = *(_QWORD *)winrt::to_hstring(&lpMem, *(_QWORD *)(a1 + 16));
  StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v30);
  if ( aDaymask[7] )
    abort();
  v25 = 1;
  v26 = 7;
  v27 = L"dayMask";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    StringValue);
  if ( v30 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  v8 = lpMem;
  if ( lpMem )
  {
    v9 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v8);
    }
  }
  v28 = *(_QWORD *)winrt::to_hstring(&lpMem, *(_QWORD *)(a1 + 24));
  v11 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v30);
  if ( aHourmask[8] )
    abort();
  v25 = 1;
  v26 = 8;
  v27 = L"hourMask";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    v11);
  if ( v30 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  v12 = lpMem;
  if ( lpMem )
  {
    v13 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v13 )
    {
      if ( v13 < 0 )
        abort();
    }
    else
    {
      v14 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v14, 0, v12);
    }
  }
  v28 = *(_QWORD *)winrt::to_hstring(&lpMem, *(_QWORD *)(a1 + 32));
  v15 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v30);
  if ( aMinutemask_1[10] )
    abort();
  v25 = 1;
  v26 = 10;
  v27 = L"minuteMask";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    v15);
  if ( v30 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      v18 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v18, 0, v16);
    }
  }
  if ( *(_BYTE *)a1 )
  {
    v22 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\factstore\\factmetric.cpp",
      (const char *)v22,
      (int)"Unsupported metric type for serialization",
      v23);
  }
  v19 = *(void (__fastcall ****)(_QWORD, void *, __int64 *))UsageAndQualityInsights::Facts::ContinuousMetricFields::ToJson(
                                                              a1 + 40,
                                                              &lpMem);
  v30 = 0;
  if ( v19 )
  {
    (**v19)(v19, &winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v30);
    v20 = v30;
  }
  else
  {
    v20 = 0;
  }
  if ( aContinuousmetr[22] )
    abort();
  v25 = 1;
  v26 = 22;
  v27 = L"continuousMetricFields";
  v24 = &v25;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
    a2,
    &v24,
    &v30);
  if ( v20 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v30);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&lpMem);
  return a2;
}

```

## disassembly

```asm
0x1800ffc18  mov     [rsp-38h+arg_8], rdx
0x1800ffc1d  push    rbp
0x1800ffc1e  push    rbx
0x1800ffc1f  push    rsi
0x1800ffc20  push    rdi
0x1800ffc21  push    r12
0x1800ffc23  push    r14
0x1800ffc25  push    r15
0x1800ffc27  mov     rbp, rsp
0x1800ffc2a  sub     rsp, 80h
0x1800ffc31  mov     rbx, rdx
0x1800ffc34  mov     r14, rcx
0x1800ffc37  xor     r15d, r15d
0x1800ffc3a  mov     [rbp+var_50], r15d
0x1800ffc3e  mov     rcx, rdx; this
0x1800ffc41  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800ffc46  lea     r12d, [r15+1]
0x1800ffc4a  mov     [rbp+var_50], r12d
0x1800ffc4e  movzx   eax, byte ptr [r14]
0x1800ffc52  movd    xmm1, eax
0x1800ffc56  cvtdq2pd xmm1, xmm1
0x1800ffc5a  lea     rcx, [rbp+arg_0]
0x1800ffc5e  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800ffc63  nop
0x1800ffc64  cmp     word ptr cs:aMetrictype+14h, r15w; ""
0x1800ffc6c  jz      short loc_1800FFC75
0x1800ffc6e  call    cs:__imp_abort
0x1800ffc75  mov     [rbp+var_40], r12d
0x1800ffc79  mov     [rbp+var_3C], 0Ah
0x1800ffc80  lea     rcx, aMetrictype; "metricType"
0x1800ffc87  mov     [rbp+var_30], rcx
0x1800ffc8b  lea     rcx, [rbp+var_40]
0x1800ffc8f  mov     [rbp+var_48], rcx
0x1800ffc93  mov     r8, rax
0x1800ffc96  lea     rdx, [rbp+var_48]
0x1800ffc9a  mov     rcx, rbx
0x1800ffc9d  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800ffca2  nop
0x1800ffca3  cmp     [rbp+arg_0], r15
0x1800ffca7  jz      short loc_1800FFCB2
0x1800ffca9  lea     rcx, [rbp+arg_0]
0x1800ffcad  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800ffcb2  movsd   xmm1, qword ptr [r14+8]
0x1800ffcb8  lea     rcx, [rbp+arg_0]
0x1800ffcbc  call    ?CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z; winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)
0x1800ffcc1  nop
0x1800ffcc2  cmp     word ptr cs:aCount+0Ah, r15w; ""
0x1800ffcca  jz      short loc_1800FFCD3
0x1800ffccc  call    cs:__imp_abort
0x1800ffcd3  mov     [rbp+var_40], r12d
0x1800ffcd7  mov     [rbp+var_3C], 5
0x1800ffcde  lea     rcx, aCount; "count"
0x1800ffce5  mov     [rbp+var_30], rcx
0x1800ffce9  lea     rcx, [rbp+var_40]
0x1800ffced  mov     [rbp+var_48], rcx
0x1800ffcf1  mov     r8, rax
0x1800ffcf4  lea     rdx, [rbp+var_48]
0x1800ffcf8  mov     rcx, rbx
0x1800ffcfb  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800ffd00  nop
0x1800ffd01  cmp     [rbp+arg_0], r15
0x1800ffd05  jz      short loc_1800FFD10
0x1800ffd07  lea     rcx, [rbp+arg_0]
0x1800ffd0b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800ffd10  mov     rdx, [r14+10h]
0x1800ffd14  lea     rcx, [rbp+lpMem]
0x1800ffd18  call    ?to_hstring@winrt@@YA?AUhstring@1@_K@Z; winrt::to_hstring(unsigned __int64)
0x1800ffd1d  nop
0x1800ffd1e  mov     rax, [rax]
0x1800ffd21  mov     [rbp+var_28], rax
0x1800ffd25  lea     rdx, [rbp+var_28]
0x1800ffd29  lea     rcx, [rbp+arg_0]; struct winrt::param::hstring *
0x1800ffd2d  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800ffd32  nop
0x1800ffd33  cmp     word ptr cs:aDaymask+0Eh, r15w; ""
0x1800ffd3b  jz      short loc_1800FFD44
0x1800ffd3d  call    cs:__imp_abort
0x1800ffd44  mov     [rbp+var_40], r12d
0x1800ffd48  mov     [rbp+var_3C], 7
0x1800ffd4f  lea     rcx, aDaymask; "dayMask"
0x1800ffd56  mov     [rbp+var_30], rcx
0x1800ffd5a  lea     rcx, [rbp+var_40]
0x1800ffd5e  mov     [rbp+var_48], rcx
0x1800ffd62  mov     r8, rax
0x1800ffd65  lea     rdx, [rbp+var_48]
0x1800ffd69  mov     rcx, rbx
0x1800ffd6c  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800ffd71  nop
0x1800ffd72  cmp     [rbp+arg_0], r15
0x1800ffd76  jz      short loc_1800FFD82
0x1800ffd78  lea     rcx, [rbp+arg_0]
0x1800ffd7c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800ffd81  nop
0x1800ffd82  mov     rdi, [rbp+lpMem]
0x1800ffd86  or      esi, 0FFFFFFFFh
0x1800ffd89  test    rdi, rdi
0x1800ffd8c  jz      short loc_1800FFDAD
0x1800ffd8e  mov     eax, esi
0x1800ffd90  lock xadd [rdi+18h], eax
0x1800ffd95  sub     eax, 1
0x1800ffd98  jnz     short loc_1800FFDE1
0x1800ffd9a  nop
0x1800ffd9b  call    WINRT_IMPL_GetProcessHeap
0x1800ffda0  mov     rcx, rax; hHeap
0x1800ffda3  mov     r8, rdi; lpMem
0x1800ffda6  xor     edx, edx; dwFlags
0x1800ffda8  call    WINRT_IMPL_HeapFree
0x1800ffdad  mov     rdx, [r14+18h]
0x1800ffdb1  lea     rcx, [rbp+lpMem]
0x1800ffdb5  call    ?to_hstring@winrt@@YA?AUhstring@1@_K@Z; winrt::to_hstring(unsigned __int64)
0x1800ffdba  nop
0x1800ffdbb  mov     rax, [rax]
0x1800ffdbe  mov     [rbp+var_28], rax
0x1800ffdc2  lea     rdx, [rbp+var_28]
0x1800ffdc6  lea     rcx, [rbp+arg_0]; struct winrt::param::hstring *
0x1800ffdca  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800ffdcf  nop
0x1800ffdd0  cmp     word ptr cs:aHourmask+10h, r15w; ""
0x1800ffdd8  jz      short loc_1800FFDEC
0x1800ffdda  call    cs:__imp_abort
0x1800ffde1  test    eax, eax
0x1800ffde3  jns     short loc_1800FFDAD
0x1800ffde5  call    cs:__imp_abort
0x1800ffdec  mov     [rbp+var_40], r12d
0x1800ffdf0  mov     [rbp+var_3C], 8
0x1800ffdf7  lea     rcx, aHourmask; "hourMask"
0x1800ffdfe  mov     [rbp+var_30], rcx
0x1800ffe02  lea     rcx, [rbp+var_40]
0x1800ffe06  mov     [rbp+var_48], rcx
0x1800ffe0a  mov     r8, rax
0x1800ffe0d  lea     rdx, [rbp+var_48]
0x1800ffe11  mov     rcx, rbx
0x1800ffe14  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800ffe19  nop
0x1800ffe1a  cmp     [rbp+arg_0], r15
0x1800ffe1e  jz      short loc_1800FFE2A
0x1800ffe20  lea     rcx, [rbp+arg_0]
0x1800ffe24  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800ffe29  nop
0x1800ffe2a  mov     rdi, [rbp+lpMem]
0x1800ffe2e  test    rdi, rdi
0x1800ffe31  jz      short loc_1800FFE52
0x1800ffe33  mov     eax, esi
0x1800ffe35  lock xadd [rdi+18h], eax
0x1800ffe3a  sub     eax, 1
0x1800ffe3d  jnz     short loc_1800FFE86
0x1800ffe3f  nop
0x1800ffe40  call    WINRT_IMPL_GetProcessHeap
0x1800ffe45  mov     rcx, rax; hHeap
0x1800ffe48  mov     r8, rdi; lpMem
0x1800ffe4b  xor     edx, edx; dwFlags
0x1800ffe4d  call    WINRT_IMPL_HeapFree
0x1800ffe52  mov     rdx, [r14+20h]
0x1800ffe56  lea     rcx, [rbp+lpMem]
0x1800ffe5a  call    ?to_hstring@winrt@@YA?AUhstring@1@_K@Z; winrt::to_hstring(unsigned __int64)
0x1800ffe5f  nop
0x1800ffe60  mov     rax, [rax]
0x1800ffe63  mov     [rbp+var_28], rax
0x1800ffe67  lea     rdx, [rbp+var_28]
0x1800ffe6b  lea     rcx, [rbp+arg_0]; struct winrt::param::hstring *
0x1800ffe6f  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800ffe74  nop
0x1800ffe75  cmp     word ptr cs:aMinutemask_1+14h, r15w; ""
0x1800ffe7d  jz      short loc_1800FFE91
0x1800ffe7f  call    cs:__imp_abort
0x1800ffe86  test    eax, eax
0x1800ffe88  jns     short loc_1800FFE52
0x1800ffe8a  call    cs:__imp_abort
0x1800ffe91  mov     [rbp+var_40], r12d
0x1800ffe95  mov     [rbp+var_3C], 0Ah
0x1800ffe9c  lea     rcx, aMinutemask_1; "minuteMask"
0x1800ffea3  mov     [rbp+var_30], rcx
0x1800ffea7  lea     rcx, [rbp+var_40]
0x1800ffeab  mov     [rbp+var_48], rcx
0x1800ffeaf  mov     r8, rax
0x1800ffeb2  lea     rdx, [rbp+var_48]
0x1800ffeb6  mov     rcx, rbx
0x1800ffeb9  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800ffebe  nop
0x1800ffebf  cmp     [rbp+arg_0], r15
0x1800ffec3  jz      short loc_1800FFECF
0x1800ffec5  lea     rcx, [rbp+arg_0]
0x1800ffec9  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800ffece  nop
0x1800ffecf  mov     rdi, [rbp+lpMem]
0x1800ffed3  test    rdi, rdi
0x1800ffed6  jz      short loc_1800FFEF5
0x1800ffed8  lock xadd [rdi+18h], esi
0x1800ffedd  sub     esi, 1
0x1800ffee0  jnz     short loc_1800FFF1D
0x1800ffee2  nop
0x1800ffee3  call    WINRT_IMPL_GetProcessHeap
0x1800ffee8  mov     rcx, rax; hHeap
0x1800ffeeb  mov     r8, rdi; lpMem
0x1800ffeee  xor     edx, edx; dwFlags
0x1800ffef0  call    WINRT_IMPL_HeapFree
0x1800ffef5  cmp     [r14], r15b
0x1800ffef8  jnz     loc_1800FFFB9
0x1800ffefe  lea     rcx, [r14+28h]
0x1800fff02  lea     rdx, [rbp+lpMem]
0x1800fff06  call    ?ToJson@ContinuousMetricFields@Facts@UsageAndQualityInsights@@QEBA?AUJsonObject@Json@Data@Windows@winrt@@XZ; UsageAndQualityInsights::Facts::ContinuousMetricFields::ToJson(void)
0x1800fff0b  nop
0x1800fff0c  mov     rcx, [rax]
0x1800fff0f  mov     [rbp+arg_0], r15
0x1800fff13  test    rcx, rcx
0x1800fff16  jnz     short loc_1800FFF28
0x1800fff18  mov     rdi, r15
0x1800fff1b  jmp     short loc_1800FFF46
0x1800fff1d  test    esi, esi
0x1800fff1f  jns     short loc_1800FFEF5
0x1800fff21  call    cs:__imp_abort
0x1800fff28  mov     rax, [rcx]
0x1800fff2b  lea     r8, [rbp+arg_0]
0x1800fff2f  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x1800fff36  mov     rax, [rax]
0x1800fff39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff3e  mov     rdi, [rbp+arg_0]
0x1800fff42  mov     [rbp+arg_0], rdi
0x1800fff46  cmp     word ptr cs:aContinuousmetr+2Ch, r15w; ""
0x1800fff4e  jz      short loc_1800FFF57
0x1800fff50  call    cs:__imp_abort
0x1800fff57  mov     [rbp+var_40], r12d
0x1800fff5b  mov     [rbp+var_3C], 16h
0x1800fff62  lea     rax, aContinuousmetr; "continuousMetricFields"
0x1800fff69  mov     [rbp+var_30], rax
0x1800fff6d  lea     rax, [rbp+var_40]
0x1800fff71  mov     [rbp+var_48], rax
0x1800fff75  lea     r8, [rbp+arg_0]
0x1800fff79  lea     rdx, [rbp+var_48]
0x1800fff7d  mov     rcx, rbx
0x1800fff80  call    ?SetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800fff85  nop
0x1800fff86  test    rdi, rdi
0x1800fff89  jz      short loc_1800FFF95
0x1800fff8b  lea     rcx, [rbp+arg_0]
0x1800fff8f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800fff94  nop
0x1800fff95  cmp     [rbp+lpMem], r15
0x1800fff99  jz      short loc_1800FFFA4
0x1800fff9b  lea     rcx, [rbp+lpMem]
0x1800fff9f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800fffa4  mov     rax, rbx
0x1800fffa7  add     rsp, 80h
0x1800fffae  pop     r15
0x1800fffb0  pop     r14
0x1800fffb2  pop     r12
0x1800fffb4  pop     rdi
0x1800fffb5  pop     rsi
0x1800fffb6  pop     rbx
0x1800fffb7  pop     rbp
0x1800fffb8  retn
0x1800fffb9  mov     ecx, 80070057h
0x1800fffbe  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800fffc3  mov     r9d, eax; char *
0x1800fffc6  mov     rcx, [rbp+38h]; this
0x1800fffca  lea     rax, aUnsupportedMet; "Unsupported metric type for serializati"...
0x1800fffd1  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800fffd6  lea     r8, aOnecoreBaseUsa_13; "onecore\\base\\usageandqualityinsights"...
0x1800fffdd  mov     edx, 8Bh; void *
0x1800fffe2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
