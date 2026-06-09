# UsageAndQualityInsights::Configuration::MetricEventConfigToJson(UsageAndQualityInsights::Configuration::MetricEventConfig const &)

- ea: `0x1800f2958`
- end: `0x1800f34f9`
- name: `?MetricEventConfigToJson@Configuration@UsageAndQualityInsights@@YA?AUJsonObject@Json@Data@Windows@winrt@@AEBUMetricEventConfig@12@@Z`
- size: `2977`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f3500`

## callees

- `0x1800033d0`
- `0x1800040a0`
- `0x180004140`
- `0x18000c6b4`
- `0x18000c844`
- `0x18000cc44`
- `0x18000eee0`
- `0x18001112c`
- `0x1800e2cb4`
- `0x1800e33bc`
- `0x1800e347c`
- `0x1800e36c0`
- `0x1800f1040`
- `0x1800f1eb8`
- `0x1800f2958`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3445`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f344c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3453`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f345a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3461`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3468`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f346f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3476`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f347d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3484`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f348b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3492`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3499`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34a0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34a7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34ae`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34b5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34bc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34c3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3445`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f344c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3453`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f345a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3461`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3468`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f346f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3476`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f347d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3484`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f348b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3492`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f3499`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34a0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34a7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34ae`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34b5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34bc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800f34c3`

## string_xrefs

- `0x1800f31d9`: `OneCoreUap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
winrt::Windows::Data::Json::JsonObject *__fastcall UsageAndQualityInsights::Configuration::MetricEventConfigToJson(
        winrt::Windows::Data::Json::JsonObject *a1,
        __int64 ***a2)
{
  double v2; // xmm0_8
  int v5; // r12d
  __int64 *v6; // rdi
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  __int64 StringValue; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 *v13; // rbx
  unsigned int v14; // edx
  _QWORD *v15; // r14
  __int64 v16; // r15
  struct winrt::impl::shared_hstring_header *v17; // rsi
  __int64 v18; // rax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  unsigned int v22; // edx
  const void *v23; // r15
  __int64 v24; // r14
  struct winrt::impl::shared_hstring_header *v25; // rsi
  __int64 v26; // rax
  int v27; // eax
  HANDLE v28; // rax
  _QWORD *v29; // r14
  unsigned int v30; // edx
  __int64 v31; // r15
  struct winrt::impl::shared_hstring_header *v32; // rsi
  int v33; // eax
  HANDLE v34; // rax
  __int64 **v35; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v38; // rax
  unsigned int v39; // edx
  const void *v40; // r14
  __int64 v41; // rsi
  struct winrt::impl::shared_hstring_header *v42; // rbx
  __int64 v43; // rax
  int v44; // eax
  HANDLE v45; // rax
  unsigned int v46; // edx
  const void *v47; // r14
  __int64 v48; // rsi
  struct winrt::impl::shared_hstring_header *v49; // rbx
  __int64 v50; // rax
  int v51; // eax
  HANDLE v52; // rax
  __int64 NumberValue; // rax
  __int64 v54; // rdx
  int v55; // eax
  int v56; // r12d
  __int64 v57; // rax
  unsigned int v58; // edx
  const void *v59; // r14
  __int64 v60; // rsi
  struct winrt::impl::shared_hstring_header *v61; // rbx
  int v62; // eax
  HANDLE v63; // rax
  __int64 **v64; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  char v68; // [rsp+20h] [rbp-E0h] BYREF
  struct winrt::impl::shared_hstring_header *v69; // [rsp+28h] [rbp-D8h] BYREF
  int *v70; // [rsp+30h] [rbp-D0h] BYREF
  int v71; // [rsp+38h] [rbp-C8h] BYREF
  int v72; // [rsp+3Ch] [rbp-C4h]
  const wchar_t *v73; // [rsp+48h] [rbp-B8h]
  void (__fastcall ***v74)(_QWORD, __int64 *, struct winrt::impl::shared_hstring_header **); // [rsp+50h] [rbp-B0h] BYREF
  int v75; // [rsp+58h] [rbp-A8h]
  void (__fastcall ***v76)(_QWORD, __int64 *, struct winrt::impl::shared_hstring_header **); // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall ***v77)(_QWORD, __int64 *, struct winrt::impl::shared_hstring_header **); // [rsp+68h] [rbp-98h] BYREF
  struct winrt::impl::shared_hstring_header *v78; // [rsp+70h] [rbp-90h] BYREF
  struct winrt::impl::shared_hstring_header *v79; // [rsp+78h] [rbp-88h] BYREF
  struct winrt::impl::shared_hstring_header *v80; // [rsp+80h] [rbp-80h] BYREF
  struct winrt::impl::shared_hstring_header *v81; // [rsp+88h] [rbp-78h] BYREF
  struct winrt::impl::shared_hstring_header *v82; // [rsp+90h] [rbp-70h] BYREF
  void (__fastcall ***v83)(_QWORD, __int64 *, struct winrt::impl::shared_hstring_header **); // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v87; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v90; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v91; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v92; // [rsp+E0h] [rbp-20h]
  winrt::Windows::Data::Json::JsonObject *v93; // [rsp+E8h] [rbp-18h]
  struct winrt::impl::shared_hstring_header *v94; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v95[2]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD *v96; // [rsp+108h] [rbp+8h]
  char *Src[4]; // [rsp+110h] [rbp+10h] BYREF

  v93 = a1;
  winrt::Windows::Data::Json::JsonObject::JsonObject(a1);
  v5 = 1;
  v75 = 1;
  v6 = **a2;
  while ( !*((_BYTE *)v6 + 25) )
  {
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v74);
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v77);
    v7 = v6[10];
    v8 = v6 + 8;
    if ( (unsigned __int64)v6[11] > 7 )
      v8 = (_QWORD *)*v8;
    if ( (_DWORD)v7 )
    {
      if ( *((_WORD *)v8 + (unsigned int)v7) )
        abort();
      LODWORD(v95[0]) = 1;
      HIDWORD(v95[0]) = v7;
      v96 = v8;
      v94 = (struct winrt::impl::shared_hstring_header *)v95;
    }
    else
    {
      v94 = 0;
    }
    StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v84);
    if ( aSourceeventful[19] )
      abort();
    v71 = 1;
    v72 = 19;
    v73 = L"SourceEventFullName";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v77,
      &v70,
      StringValue);
    if ( v84 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v84);
    v10 = v6[14];
    if ( (unsigned __int64)v6[15] <= 7 )
      v11 = v6 + 12;
    else
      v11 = (_QWORD *)v6[12];
    if ( (_DWORD)v10 )
    {
      if ( *((_WORD *)v11 + (unsigned int)v10) )
        abort();
      LODWORD(v95[0]) = 1;
      HIDWORD(v95[0]) = v10;
      v96 = v11;
      v94 = (struct winrt::impl::shared_hstring_header *)v95;
    }
    else
    {
      v94 = 0;
    }
    v12 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v85);
    if ( aSourceeventpro[23] )
      abort();
    v71 = 1;
    v72 = 23;
    v73 = L"SourceEventProviderGuid";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v77,
      &v70,
      v12);
    if ( v85 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v85);
    if ( v77 )
    {
      v69 = 0;
      (**v77)(v77, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v69);
      v78 = v69;
    }
    else
    {
      v78 = 0;
    }
    if ( aSourceeventinf[15] )
      abort();
    v71 = 1;
    v72 = 15;
    v73 = L"SourceEventInfo";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      &v78);
    if ( v78 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v78);
    winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v83);
    v13 = *(__int64 **)v6[16];
    while ( !*((_BYTE *)v13 + 25) )
    {
      winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v76);
      v15 = v13 + 8;
      if ( (unsigned __int64)v13[11] > 7 )
        v15 = (_QWORD *)*v15;
      v16 = *((unsigned int *)v13 + 20);
      if ( (_DWORD)v16 )
      {
        v17 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v16, v14);
        memcpy_s((char *)v17 + 28, 2 * v16, v15, 2 * v16);
      }
      else
      {
        v17 = 0;
      }
      v69 = v17;
      v94 = v17;
      v18 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v86);
      if ( aSourceeventfie[20] )
        abort();
      v71 = 1;
      v72 = 20;
      v73 = L"SourceEventFieldName";
      v70 = &v71;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
        &v76,
        &v70,
        v18);
      if ( v86 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v86);
      if ( v17 )
      {
        v19 = _InterlockedDecrement((volatile signed __int32 *)v17 + 6);
        if ( v19 )
        {
          if ( v19 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v17);
        }
      }
      v21 = UsageAndQualityInsights::Configuration::Join(Src);
      if ( *(_QWORD *)(v21 + 24) <= 7u )
        v23 = (const void *)v21;
      else
        v23 = *(const void **)v21;
      v24 = *(unsigned int *)(v21 + 16);
      if ( (_DWORD)v24 )
      {
        v25 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v24, v22);
        memcpy_s((char *)v25 + 28, 2 * v24, v23, 2 * v24);
      }
      else
      {
        v25 = 0;
      }
      v69 = v25;
      v94 = v25;
      v26 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v87);
      if ( aMode[4] )
        abort();
      v71 = 1;
      v72 = 4;
      v73 = L"Mode";
      v70 = &v71;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
        &v76,
        &v70,
        v26);
      if ( v87 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v87);
      if ( v25 )
      {
        v27 = _InterlockedDecrement((volatile signed __int32 *)v25 + 6);
        if ( v27 )
        {
          if ( v27 < 0 )
            abort();
        }
        else
        {
          v28 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v28, 0, v25);
        }
      }
      v29 = v13 + 4;
      std::wstring::~wstring(Src);
      if ( v76 )
      {
        v69 = 0;
        (**v76)(v76, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v69);
        v79 = v69;
      }
      else
      {
        v79 = 0;
      }
      if ( (unsigned __int64)v13[7] > 7 )
        v29 = (_QWORD *)*v29;
      v31 = *((unsigned int *)v13 + 12);
      if ( (_DWORD)v31 )
      {
        v32 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v31, v30);
        memcpy_s((char *)v32 + 28, 2 * v31, v29, 2 * v31);
      }
      else
      {
        v32 = 0;
      }
      v69 = v32;
      Src[0] = (char *)v32;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
        &v83,
        Src,
        &v79);
      if ( v32 )
      {
        v33 = _InterlockedDecrement((volatile signed __int32 *)v32 + 6);
        if ( v33 )
        {
          if ( v33 < 0 )
            abort();
        }
        else
        {
          v34 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v34, 0, v32);
        }
      }
      if ( v79 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v79);
      if ( v76 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v76);
      v35 = (__int64 **)v13[2];
      if ( *((_BYTE *)v35 + 25) )
      {
        for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v13 = i;
        v13 = i;
      }
      else
      {
        v13 = (__int64 *)v13[2];
        for ( j = *v35; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v13 = j;
      }
    }
    if ( v83 )
    {
      v69 = 0;
      (**v83)(v83, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v69);
      v80 = v69;
    }
    else
    {
      v80 = 0;
    }
    if ( aEventfields[11] )
      abort();
    v71 = 1;
    v72 = 11;
    v73 = L"EventFields";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      &v80);
    if ( v80 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v80);
    v38 = UsageAndQualityInsights::Configuration::Join(&v94);
    if ( *(_QWORD *)(v38 + 24) <= 7u )
      v40 = (const void *)v38;
    else
      v40 = *(const void **)v38;
    v41 = *(unsigned int *)(v38 + 16);
    if ( (_DWORD)v41 )
    {
      v42 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v41, v39);
      memcpy_s((char *)v42 + 28, 2 * v41, v40, 2 * v41);
    }
    else
    {
      v42 = 0;
    }
    v69 = v42;
    Src[0] = (char *)v42;
    v43 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v88);
    if ( aPrivacydatatag[14] )
      abort();
    v71 = 1;
    v72 = 14;
    v73 = L"PrivacyDataTag";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      v43);
    if ( v88 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v88);
    if ( v42 )
    {
      v44 = _InterlockedDecrement((volatile signed __int32 *)v42 + 6);
      if ( v44 )
      {
        if ( v44 < 0 )
          abort();
      }
      else
      {
        v45 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v45, 0, v42);
      }
    }
    std::wstring::~wstring((char **)&v94);
    if ( (unsigned __int64)v6[24] <= 7 )
      v47 = v6 + 21;
    else
      v47 = (const void *)v6[21];
    v48 = *((unsigned int *)v6 + 46);
    if ( (_DWORD)v48 )
    {
      v49 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v48, v46);
      memcpy_s((char *)v49 + 28, 2 * v48, v47, 2 * v48);
    }
    else
    {
      v49 = 0;
    }
    v69 = v49;
    Src[0] = (char *)v49;
    v50 = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v89);
    if ( aMetricgroup[11] )
      abort();
    v71 = 1;
    v72 = 11;
    v73 = L"MetricGroup";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      v50);
    if ( v89 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v89);
    if ( v49 )
    {
      v51 = _InterlockedDecrement((volatile signed __int32 *)v49 + 6);
      if ( v51 )
      {
        if ( v51 < 0 )
          abort();
      }
      else
      {
        v52 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v52, 0, v49);
      }
    }
    NumberValue = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v2);
    if ( aAggregationwin[21] )
      abort();
    v71 = 1;
    v72 = 21;
    v73 = L"AggregationWindowMins";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      NumberValue);
    if ( v90 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v90);
    v68 = *((_BYTE *)v6 + 208);
    v69 = (struct winrt::impl::shared_hstring_header *)&v68;
    v92 = &qword_180159C38;
    _InterlockedAdd64(&qword_180159C38, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> )
    {
      v69 = 0;
      LODWORD(v94) = 602;
      v95[0] = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
      v95[1] = 0;
      LOBYTE(v54) = v68;
      v55 = (*(__int64 (__fastcall **)(__int64, __int64, struct winrt::impl::shared_hstring_header **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics> + 64LL))(
              winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonValue,winrt::Windows::Data::Json::IJsonValueStatics>,
              v54,
              &v69);
      if ( v55 < 0 )
        winrt::throw_hresult((unsigned int)v55, &v94);
      v81 = v69;
      v56 = v5 | 0x1C;
      _InterlockedDecrement64(&qword_180159C38);
    }
    else
    {
      _InterlockedDecrement64(&qword_180159C38);
      ___call_AEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_winrt__SA__N_Z____factory_cache_entry_UJsonValue_Json_Data_Windows_winrt__UIJsonValueStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateBooleanValue_JsonValue_Json_Data_Windows_2_SA__N_Z__Z(
        0,
        &v81,
        (_BYTE **)&v69);
      v56 = v5 | 4;
    }
    v5 = v56 | 2;
    v75 = v5;
    if ( aUploadsourceev[18] )
      abort();
    v71 = 1;
    v72 = 18;
    v73 = L"UploadSourceEvents";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      &v81);
    if ( v81 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v81);
    v57 = winrt::Windows::Data::Json::JsonValue::CreateNumberValue(v2);
    if ( aMaxdimensionse[24] )
      abort();
    v71 = 1;
    v72 = 24;
    v73 = L"MaxDimensionSetsPerEvent";
    v70 = &v71;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      &v74,
      &v70,
      v57);
    if ( v91 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v91);
    if ( v74 )
    {
      v69 = 0;
      (**v74)(v74, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v69);
      v82 = v69;
    }
    else
    {
      v82 = 0;
    }
    if ( (unsigned __int64)v6[7] <= 7 )
      v59 = v6 + 4;
    else
      v59 = (const void *)v6[4];
    v60 = *((unsigned int *)v6 + 12);
    if ( (_DWORD)v60 )
    {
      v61 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v60, v58);
      memcpy_s((char *)v61 + 28, 2 * v60, v59, 2 * v60);
    }
    else
    {
      v61 = 0;
    }
    v92 = (__int64 *)v61;
    Src[0] = (char *)v61;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(
      a1,
      Src,
      &v82);
    if ( v61 )
    {
      v62 = _InterlockedDecrement((volatile signed __int32 *)v61 + 6);
      if ( v62 )
      {
        if ( v62 < 0 )
          abort();
      }
      else
      {
        v63 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v63, 0, v61);
      }
    }
    if ( v82 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v82);
    if ( v83 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v83);
    if ( v77 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v77);
    if ( v74 )
      v2 = winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v74);
    v64 = (__int64 **)v6[2];
    if ( *((_BYTE *)v64 + 25) )
    {
      for ( k = (__int64 *)v6[1]; !*((_BYTE *)k + 25) && v6 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v6 = k;
      v6 = k;
    }
    else
    {
      v6 = (__int64 *)v6[2];
      for ( m = *v64; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v6 = m;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800f2958  push    rbp
0x1800f295a  push    rbx
0x1800f295b  push    rsi
0x1800f295c  push    rdi
0x1800f295d  push    r12
0x1800f295f  push    r13
0x1800f2961  push    r14
0x1800f2963  push    r15
0x1800f2965  lea     rbp, [rsp-48h]
0x1800f296a  sub     rsp, 148h
0x1800f2971  mov     rax, cs:__security_cookie
0x1800f2978  xor     rax, rsp
0x1800f297b  mov     [rbp+80h+var_50], rax
0x1800f297f  mov     rdi, rdx
0x1800f2982  mov     r13, rcx
0x1800f2985  mov     [rbp+80h+var_98], rcx
0x1800f2989  xor     r15d, r15d
0x1800f298c  mov     [rsp+180h+var_128], r15d
0x1800f2991  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800f2996  lea     r12d, [r15+1]
0x1800f299a  mov     [rsp+180h+var_128], r12d
0x1800f299f  mov     rdi, [rdi]
0x1800f29a2  mov     rdi, [rdi]
0x1800f29a5  cmp     [rdi+19h], r15b
0x1800f29a9  jnz     loc_1800F34CA
0x1800f29af  lea     rcx, [rsp+180h+var_130]; this
0x1800f29b4  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800f29b9  nop
0x1800f29ba  lea     rcx, [rsp+180h+var_118]; this
0x1800f29bf  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800f29c4  nop
0x1800f29c5  mov     rdx, [rdi+50h]
0x1800f29c9  lea     rcx, [rdi+40h]
0x1800f29cd  cmp     qword ptr [rdi+58h], 7
0x1800f29d2  jbe     short loc_1800F29D7
0x1800f29d4  mov     rcx, [rcx]
0x1800f29d7  test    edx, edx
0x1800f29d9  jnz     short loc_1800F29E1
0x1800f29db  mov     [rbp+80h+var_90], r15
0x1800f29df  jmp     short loc_1800F2A04
0x1800f29e1  mov     eax, edx
0x1800f29e3  cmp     [rcx+rax*2], r15w
0x1800f29e8  jnz     loc_1800F34C3
0x1800f29ee  mov     dword ptr [rbp+80h+var_88], 1
0x1800f29f5  mov     dword ptr [rbp+80h+var_88+4], edx
0x1800f29f8  mov     [rbp+80h+var_78], rcx
0x1800f29fc  lea     rax, [rbp+80h+var_88]
0x1800f2a00  mov     [rbp+80h+var_90], rax
0x1800f2a04  lea     rdx, [rbp+80h+var_90]
0x1800f2a08  lea     rcx, [rbp+80h+var_E0]; struct winrt::param::hstring *
0x1800f2a0c  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800f2a11  nop
0x1800f2a12  cmp     word ptr cs:aSourceeventful+26h, r15w; ""
0x1800f2a1a  jnz     loc_1800F34BC
0x1800f2a20  mov     [rsp+180h+var_148], 1
0x1800f2a28  mov     [rsp+180h+var_144], 13h
0x1800f2a30  lea     rcx, aSourceeventful; "SourceEventFullName"
0x1800f2a37  mov     [rsp+180h+var_138], rcx
0x1800f2a3c  lea     rcx, [rsp+180h+var_148]
0x1800f2a41  mov     [rsp+180h+var_150], rcx
0x1800f2a46  mov     r8, rax
0x1800f2a49  lea     rdx, [rsp+180h+var_150]
0x1800f2a4e  lea     rcx, [rsp+180h+var_118]
0x1800f2a53  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800f2a58  nop
0x1800f2a59  cmp     [rbp+80h+var_E0], r15
0x1800f2a5d  jz      short loc_1800F2A68
0x1800f2a5f  lea     rcx, [rbp+80h+var_E0]
0x1800f2a63  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f2a68  mov     rdx, [rdi+70h]
0x1800f2a6c  cmp     qword ptr [rdi+78h], 7
0x1800f2a71  jbe     short loc_1800F2A79
0x1800f2a73  mov     rcx, [rdi+60h]
0x1800f2a77  jmp     short loc_1800F2A7D
0x1800f2a79  lea     rcx, [rdi+60h]
0x1800f2a7d  test    edx, edx
0x1800f2a7f  jnz     short loc_1800F2A87
0x1800f2a81  mov     [rbp+80h+var_90], r15
0x1800f2a85  jmp     short loc_1800F2AAA
0x1800f2a87  mov     eax, edx
0x1800f2a89  cmp     [rcx+rax*2], r15w
0x1800f2a8e  jnz     loc_1800F34B5
0x1800f2a94  mov     dword ptr [rbp+80h+var_88], 1
0x1800f2a9b  mov     dword ptr [rbp+80h+var_88+4], edx
0x1800f2a9e  mov     [rbp+80h+var_78], rcx
0x1800f2aa2  lea     rax, [rbp+80h+var_88]
0x1800f2aa6  mov     [rbp+80h+var_90], rax
0x1800f2aaa  lea     rdx, [rbp+80h+var_90]
0x1800f2aae  lea     rcx, [rbp+80h+var_D8]; struct winrt::param::hstring *
0x1800f2ab2  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800f2ab7  nop
0x1800f2ab8  cmp     word ptr cs:aSourceeventpro+2Eh, r15w; ""
0x1800f2ac0  jnz     loc_1800F34AE
0x1800f2ac6  mov     [rsp+180h+var_148], 1
0x1800f2ace  mov     [rsp+180h+var_144], 17h
0x1800f2ad6  lea     rcx, aSourceeventpro; "SourceEventProviderGuid"
0x1800f2add  mov     [rsp+180h+var_138], rcx
0x1800f2ae2  lea     rcx, [rsp+180h+var_148]
0x1800f2ae7  mov     [rsp+180h+var_150], rcx
0x1800f2aec  mov     r8, rax
0x1800f2aef  lea     rdx, [rsp+180h+var_150]
0x1800f2af4  lea     rcx, [rsp+180h+var_118]
0x1800f2af9  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800f2afe  nop
0x1800f2aff  cmp     [rbp+80h+var_D8], r15
0x1800f2b03  jz      short loc_1800F2B0E
0x1800f2b05  lea     rcx, [rbp+80h+var_D8]
0x1800f2b09  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f2b0e  mov     rcx, [rsp+180h+var_118]
0x1800f2b13  test    rcx, rcx
0x1800f2b16  jnz     short loc_1800F2B1F
0x1800f2b18  mov     [rsp+180h+var_110], r15
0x1800f2b1d  jmp     short loc_1800F2B45
0x1800f2b1f  mov     [rsp+180h+var_158], r15
0x1800f2b24  mov     rax, [rcx]
0x1800f2b27  lea     r8, [rsp+180h+var_158]
0x1800f2b2c  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x1800f2b33  mov     rax, [rax]
0x1800f2b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b3b  mov     rax, [rsp+180h+var_158]
0x1800f2b40  mov     [rsp+180h+var_110], rax
0x1800f2b45  cmp     word ptr cs:aSourceeventinf+1Eh, r15w; ""
0x1800f2b4d  jnz     loc_1800F34A7
0x1800f2b53  mov     [rsp+180h+var_148], 1
0x1800f2b5b  mov     [rsp+180h+var_144], 0Fh
0x1800f2b63  lea     rax, aSourceeventinf; "SourceEventInfo"
0x1800f2b6a  mov     [rsp+180h+var_138], rax
0x1800f2b6f  lea     rax, [rsp+180h+var_148]
0x1800f2b74  mov     [rsp+180h+var_150], rax
0x1800f2b79  lea     r8, [rsp+180h+var_110]
0x1800f2b7e  lea     rdx, [rsp+180h+var_150]
0x1800f2b83  lea     rcx, [rsp+180h+var_130]
0x1800f2b88  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800f2b8d  nop
0x1800f2b8e  cmp     [rsp+180h+var_110], r15
0x1800f2b93  jz      short loc_1800F2B9F
0x1800f2b95  lea     rcx, [rsp+180h+var_110]
0x1800f2b9a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f2b9f  lea     rcx, [rbp+80h+var_E8]; this
0x1800f2ba3  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800f2ba8  nop
0x1800f2ba9  mov     rbx, [rdi+80h]
0x1800f2bb0  mov     rbx, [rbx]
0x1800f2bb3  cmp     [rbx+19h], r15b
0x1800f2bb7  jnz     loc_1800F2ED4
0x1800f2bbd  lea     rcx, [rsp+180h+var_120]; this
0x1800f2bc2  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x1800f2bc7  nop
0x1800f2bc8  lea     r14, [rbx+40h]
0x1800f2bcc  cmp     qword ptr [rbx+58h], 7
0x1800f2bd1  jbe     short loc_1800F2BD6
0x1800f2bd3  mov     r14, [r14]
0x1800f2bd6  mov     r15d, [rbx+50h]
0x1800f2bda  test    r15d, r15d
0x1800f2bdd  jnz     short loc_1800F2BE7
0x1800f2bdf  xor     r14d, r14d
0x1800f2be2  mov     esi, r14d
0x1800f2be5  jmp     short loc_1800F2C0A
0x1800f2be7  mov     ecx, r15d; this
0x1800f2bea  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800f2bef  mov     rsi, rax
0x1800f2bf2  mov     rdx, r15
0x1800f2bf5  add     rdx, rdx; DestinationSize
0x1800f2bf8  lea     rcx, [rax+1Ch]; Destination
0x1800f2bfc  mov     r9, rdx; SourceSize
0x1800f2bff  mov     r8, r14; Source
0x1800f2c02  call    memcpy_s
0x1800f2c07  xor     r14d, r14d
0x1800f2c0a  mov     [rsp+180h+var_158], rsi
0x1800f2c0f  mov     [rbp+80h+var_90], rsi
0x1800f2c13  lea     rdx, [rbp+80h+var_90]
0x1800f2c17  lea     rcx, [rbp+80h+var_D0]; struct winrt::param::hstring *
0x1800f2c1b  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800f2c20  nop
0x1800f2c21  cmp     word ptr cs:aSourceeventfie+28h, r14w; ""
0x1800f2c29  jnz     loc_1800F3461
0x1800f2c2f  mov     [rsp+180h+var_148], 1
0x1800f2c37  mov     [rsp+180h+var_144], 14h
0x1800f2c3f  lea     rcx, aSourceeventfie; "SourceEventFieldName"
0x1800f2c46  mov     [rsp+180h+var_138], rcx
0x1800f2c4b  lea     rcx, [rsp+180h+var_148]
0x1800f2c50  mov     [rsp+180h+var_150], rcx
0x1800f2c55  mov     r8, rax
0x1800f2c58  lea     rdx, [rsp+180h+var_150]
0x1800f2c5d  lea     rcx, [rsp+180h+var_120]
0x1800f2c62  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800f2c67  nop
0x1800f2c68  cmp     [rbp+80h+var_D0], r14
0x1800f2c6c  jz      short loc_1800F2C78
0x1800f2c6e  lea     rcx, [rbp+80h+var_D0]
0x1800f2c72  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f2c77  nop
0x1800f2c78  test    rsi, rsi
0x1800f2c7b  jz      short loc_1800F2CA7
0x1800f2c7d  or      eax, 0FFFFFFFFh
0x1800f2c80  lock xadd [rsi+18h], eax
0x1800f2c85  sub     eax, 1
0x1800f2c88  jnz     short loc_1800F2C9F
0x1800f2c8a  nop
0x1800f2c8b  call    WINRT_IMPL_GetProcessHeap
0x1800f2c90  mov     rcx, rax; hHeap
0x1800f2c93  mov     r8, rsi; lpMem
0x1800f2c96  xor     edx, edx; dwFlags
0x1800f2c98  call    WINRT_IMPL_HeapFree
0x1800f2c9d  jmp     short loc_1800F2CA7
0x1800f2c9f  test    eax, eax
0x1800f2ca1  js      loc_1800F3445
0x1800f2ca7  lea     rdx, [rbx+60h]
0x1800f2cab  lea     rcx, [rbp+80h+Src]; Src
0x1800f2caf  call    UsageAndQualityInsights__Configuration__Join
0x1800f2cb4  nop
0x1800f2cb5  cmp     qword ptr [rax+18h], 7
0x1800f2cba  jbe     short loc_1800F2CC1
0x1800f2cbc  mov     r15, [rax]
0x1800f2cbf  jmp     short loc_1800F2CC4
0x1800f2cc1  mov     r15, rax
0x1800f2cc4  mov     r14d, [rax+10h]
0x1800f2cc8  test    r14d, r14d
0x1800f2ccb  jnz     short loc_1800F2CD5
0x1800f2ccd  xor     r15d, r15d
0x1800f2cd0  mov     esi, r15d
0x1800f2cd3  jmp     short loc_1800F2CF8
0x1800f2cd5  mov     ecx, r14d; this
0x1800f2cd8  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800f2cdd  mov     rsi, rax
0x1800f2ce0  mov     rdx, r14
0x1800f2ce3  add     rdx, rdx; DestinationSize
0x1800f2ce6  lea     rcx, [rax+1Ch]; Destination
0x1800f2cea  mov     r9, rdx; SourceSize
0x1800f2ced  mov     r8, r15; Source
0x1800f2cf0  call    memcpy_s
0x1800f2cf5  xor     r15d, r15d
0x1800f2cf8  mov     [rsp+180h+var_158], rsi
0x1800f2cfd  mov     [rbp+80h+var_90], rsi
0x1800f2d01  lea     rdx, [rbp+80h+var_90]
0x1800f2d05  lea     rcx, [rbp+80h+var_C8]; struct winrt::param::hstring *
0x1800f2d09  call    ?CreateStringValue@JsonValue@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonValue::CreateStringValue(winrt::param::hstring const &)
0x1800f2d0e  nop
0x1800f2d0f  cmp     word ptr cs:aMode+8, r15w; ""
0x1800f2d17  jnz     loc_1800F345A
0x1800f2d1d  mov     [rsp+180h+var_148], 1
0x1800f2d25  mov     [rsp+180h+var_144], 4
0x1800f2d2d  lea     rcx, aMode; "Mode"
0x1800f2d34  mov     [rsp+180h+var_138], rcx
0x1800f2d39  lea     rcx, [rsp+180h+var_148]
0x1800f2d3e  mov     [rsp+180h+var_150], rcx
0x1800f2d43  mov     r8, rax
0x1800f2d46  lea     rdx, [rsp+180h+var_150]
0x1800f2d4b  lea     rcx, [rsp+180h+var_120]
0x1800f2d50  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIJsonValue@Json@Data@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Insert(winrt::param::hstring const &,winrt::Windows::Data::Json::IJsonValue const &)
0x1800f2d55  nop
0x1800f2d56  cmp     [rbp+80h+var_C8], r15
0x1800f2d5a  jz      short loc_1800F2D66
0x1800f2d5c  lea     rcx, [rbp+80h+var_C8]
0x1800f2d60  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800f2d65  nop
0x1800f2d66  test    rsi, rsi
0x1800f2d69  jz      short loc_1800F2D95
0x1800f2d6b  or      eax, 0FFFFFFFFh
0x1800f2d6e  lock xadd [rsi+18h], eax
0x1800f2d73  sub     eax, 1
0x1800f2d76  jnz     short loc_1800F2D8D
0x1800f2d78  nop
0x1800f2d79  call    WINRT_IMPL_GetProcessHeap
0x1800f2d7e  mov     rcx, rax; hHeap
0x1800f2d81  mov     r8, rsi; lpMem
0x1800f2d84  xor     edx, edx; dwFlags
0x1800f2d86  call    WINRT_IMPL_HeapFree
0x1800f2d8b  jmp     short loc_1800F2D95
0x1800f2d8d  test    eax, eax
0x1800f2d8f  js      loc_1800F344C
0x1800f2d95  lea     r14, [rbx+20h]
0x1800f2d99  lea     rcx, [rbp+80h+Src]; void *
0x1800f2d9d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f2da2  mov     rcx, [rsp+180h+var_120]
0x1800f2da7  test    rcx, rcx
0x1800f2daa  jnz     short loc_1800F2DB3
0x1800f2dac  mov     [rsp+180h+var_108], r15
0x1800f2db1  jmp     short loc_1800F2DD9
0x1800f2db3  mov     [rsp+180h+var_158], r15
0x1800f2db8  mov     rax, [rcx]
0x1800f2dbb  lea     r8, [rsp+180h+var_158]
0x1800f2dc0  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x1800f2dc7  mov     rax, [rax]
0x1800f2dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2dcf  mov     rax, [rsp+180h+var_158]
0x1800f2dd4  mov     [rsp+180h+var_108], rax
0x1800f2dd9  cmp     qword ptr [r14+18h], 7
0x1800f2dde  jbe     short loc_1800F2DE3
0x1800f2de0  mov     r14, [r14]
0x1800f2de3  mov     r15d, [rbx+30h]
0x1800f2de7  test    r15d, r15d
0x1800f2dea  jnz     short loc_1800F2DF4
0x1800f2dec  xor     r15d, r15d
0x1800f2def  mov     esi, r15d
0x1800f2df2  jmp     short loc_1800F2E17
0x1800f2df4  mov     ecx, r15d; this
0x1800f2df7  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800f2dfc  mov     rsi, rax
0x1800f2dff  mov     rdx, r15
  ... truncated ...
```
