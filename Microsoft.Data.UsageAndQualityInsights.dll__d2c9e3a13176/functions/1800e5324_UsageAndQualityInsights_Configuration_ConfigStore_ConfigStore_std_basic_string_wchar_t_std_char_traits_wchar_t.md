# UsageAndQualityInsights::Configuration::ConfigStore::ConfigStore(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800e5324`
- end: `0x1800e55e2`
- name: `??0ConfigStore@Configuration@UsageAndQualityInsights@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `702`
- prototype: `RTL_SRWLOCK *__fastcall(RTL_SRWLOCK *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e55e8`

## callees

- `0x1800033d0`
- `0x18000c844`
- `0x18000eee0`
- `0x1800107b0`
- `0x180011cd8`
- `0x180012dd4`
- `0x1800137fc`
- `0x180016998`
- `0x180027fdc`
- `0x180028250`
- `0x18002a9c8`
- `0x1800e484c`
- `0x1800e5324`
- `0x1800e574c`
- `0x1800e6e60`
- `0x1800e6f28`
- `0x1800e75bc`
- `0x1800e7da0`
- `0x1800e9d88`
- `0x1800ed99c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e542d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800e542d`

## string_xrefs

- `0x1800e5372`: `Feature_Configs`
- `0x1800e55b4`: `ConfigStore Created`
- `0x1800e53a5`: `aggregated.json`
- `0x1800e53c7`: `UsageAndQualityInsights.json`
- `0x1800e5442`: `UQIConfigArray`

## pseudocode

```c
RTL_SRWLOCK *__fastcall UsageAndQualityInsights::Configuration::ConfigStore::ConfigStore(
        RTL_SRWLOCK *this,
        __int64 a2,
        __int64 a3)
{
  RTL_SRWLOCK *v5; // rsi
  RTL_SRWLOCK *v6; // rdi
  __int64 JsonFromPath; // rax
  unsigned int i; // esi
  __int64 ObjectAt; // rax
  __int64 v11; // [rsp+20h] [rbp-99h] BYREF
  __int128 v12; // [rsp+28h] [rbp-91h] BYREF
  void *v13; // [rsp+38h] [rbp-81h]
  unsigned __int64 v14; // [rsp+40h] [rbp-79h] BYREF
  __int64 v15; // [rsp+48h] [rbp-71h] BYREF
  _DWORD *v16; // [rsp+50h] [rbp-69h] BYREF
  _DWORD v17[4]; // [rsp+58h] [rbp-61h] BYREF
  const wchar_t *v18; // [rsp+68h] [rbp-51h]
  RTL_SRWLOCK *v19; // [rsp+70h] [rbp-49h]
  _BYTE v20[40]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v21[16]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v22[24]; // [rsp+B8h] [rbp-1h] BYREF

  v19 = this;
  this->Ptr = 0;
  v5 = this + 1;
  std::wstring::wstring(&this[1], a2);
  UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(&this[5]);
  std::wstring::wstring(&this[9], a3);
  UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(&this[13]);
  UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(&this[17]);
  v6 = this + 21;
  this[21].Ptr = 0;
  this[22].Ptr = 0;
  this[23].Ptr = 0;
  UsageAndQualityInsights::Configuration::ConfigStore::TryCreatePath(v5);
  UsageAndQualityInsights::Configuration::ConfigStore::TryCreatePath(&this[5]);
  UsageAndQualityInsights::Configuration::ConfigStore::ProcessNewConfigs(this, 0);
  JsonFromPath = UsageAndQualityInsights::Configuration::ConfigStore::LoadJsonFromPath((struct winrt::param::hstring *)&v15);
  v12 = 0;
  v13 = 0;
  if ( aUqiconfigarray[14] )
    abort();
  v17[0] = 1;
  v17[1] = 14;
  v18 = L"UQIConfigArray";
  v16 = v17;
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(
    JsonFromPath,
    &v11,
    &v16);
  v14 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v11);
  if ( v14 > 0x8E38E38E38E38E39uLL * (((__int64)v13 - (__int64)v12) >> 3) )
    std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Reallocate<0>(&v12, &v14);
  for ( i = 0;
        i < (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v11);
        ++i )
  {
    ObjectAt = winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(
                 &v11,
                 &v14,
                 i);
    UsageAndQualityInsights::Configuration::ParseUQIConfig(v20, ObjectAt);
    if ( v14 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v14);
    if ( *((void **)&v12 + 1) == v13 )
    {
      std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::UQIConfig>(
        &v12,
        *((_QWORD *)&v12 + 1),
        v20);
    }
    else
    {
      UsageAndQualityInsights::Configuration::UQIConfig::UQIConfig(*((_QWORD *)&v12 + 1), v20);
      *((_QWORD *)&v12 + 1) += 72LL;
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>,void *>>>(
      v22,
      v22);
    std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>(v21);
    std::wstring::~wstring(v20);
  }
  if ( v11 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v11);
  if ( v6 != (RTL_SRWLOCK *)&v12 )
  {
    std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(&this[21]);
    *(_OWORD *)&v6->Ptr = v12;
    this[23].Ptr = v13;
    v12 = 0;
    v13 = 0;
  }
  std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(&v12);
  if ( v15 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("ConfigStore Created");
  return this;
}

```

## disassembly

```asm
0x1800e5324  push    rbp
0x1800e5326  push    rbx
0x1800e5327  push    rsi
0x1800e5328  push    rdi
0x1800e5329  push    r12
0x1800e532b  push    r14
0x1800e532d  push    r15
0x1800e532f  lea     rbp, [rsp-27h]
0x1800e5334  sub     rsp, 0E0h
0x1800e533b  mov     rax, cs:__security_cookie
0x1800e5342  xor     rax, rsp
0x1800e5345  mov     [rbp+57h+var_40], rax
0x1800e5349  mov     r14, r8
0x1800e534c  mov     rdi, rdx
0x1800e534f  mov     rbx, rcx
0x1800e5352  mov     [rbp+57h+var_A0], rcx
0x1800e5356  xor     eax, eax
0x1800e5358  mov     [rcx], rax
0x1800e535b  lea     rsi, [rcx+8]
0x1800e535f  mov     rcx, rsi
0x1800e5362  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e5367  nop
0x1800e5368  cmp     qword ptr [rdi+18h], 7
0x1800e536d  jbe     short loc_1800E5372
0x1800e536f  mov     rdi, [rdi]
0x1800e5372  lea     r8, aFeatureConfigs; "Feature_Configs"
0x1800e5379  mov     rdx, rdi
0x1800e537c  lea     rcx, [rbx+28h]; Src
0x1800e5380  call    ?JoinPath@ConfigStore@Configuration@UsageAndQualityInsights@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(wchar_t const *,wchar_t const *)
0x1800e5385  nop
0x1800e5386  lea     rdi, [rbx+48h]
0x1800e538a  mov     rdx, r14
0x1800e538d  mov     rcx, rdi
0x1800e5390  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e5395  nop
0x1800e5396  cmp     qword ptr [rsi+18h], 7
0x1800e539b  jbe     short loc_1800E53A2
0x1800e539d  mov     rdx, [rsi]
0x1800e53a0  jmp     short loc_1800E53A5
0x1800e53a2  mov     rdx, rsi
0x1800e53a5  lea     r8, aAggregatedJson; "aggregated.json"
0x1800e53ac  lea     rcx, [rbx+68h]; Src
0x1800e53b0  call    ?JoinPath@ConfigStore@Configuration@UsageAndQualityInsights@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(wchar_t const *,wchar_t const *)
0x1800e53b5  nop
0x1800e53b6  cmp     qword ptr [rdi+18h], 7
0x1800e53bb  jbe     short loc_1800E53C0
0x1800e53bd  mov     rdi, [rdi]
0x1800e53c0  lea     rcx, [rbx+88h]; Src
0x1800e53c7  lea     r8, aUsageandqualit; "UsageAndQualityInsights.json"
0x1800e53ce  mov     rdx, rdi
0x1800e53d1  call    ?JoinPath@ConfigStore@Configuration@UsageAndQualityInsights@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; UsageAndQualityInsights::Configuration::ConfigStore::JoinPath(wchar_t const *,wchar_t const *)
0x1800e53d6  nop
0x1800e53d7  lea     rdi, [rbx+0A8h]
0x1800e53de  xor     r12d, r12d
0x1800e53e1  mov     [rdi], r12
0x1800e53e4  mov     [rdi+8], r12
0x1800e53e8  mov     [rdi+10h], r12
0x1800e53ec  mov     rcx, rsi
0x1800e53ef  call    ?TryCreatePath@ConfigStore@Configuration@UsageAndQualityInsights@@CAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Configuration::ConfigStore::TryCreatePath(std::wstring const &)
0x1800e53f4  lea     rcx, [rbx+28h]
0x1800e53f8  call    ?TryCreatePath@ConfigStore@Configuration@UsageAndQualityInsights@@CAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Configuration::ConfigStore::TryCreatePath(std::wstring const &)
0x1800e53fd  xor     edx, edx; bool
0x1800e53ff  mov     rcx, rbx; this
0x1800e5402  call    ?ProcessNewConfigs@ConfigStore@Configuration@UsageAndQualityInsights@@QEAAX_N@Z; UsageAndQualityInsights::Configuration::ConfigStore::ProcessNewConfigs(bool)
0x1800e5407  lea     rdx, [rbx+68h]
0x1800e540b  lea     rcx, [rbp+57h+var_C8]; struct winrt::param::hstring *
0x1800e540f  call    ?LoadJsonFromPath@ConfigStore@Configuration@UsageAndQualityInsights@@CA?AUJsonObject@Json@Data@Windows@winrt@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Configuration::ConfigStore::LoadJsonFromPath(std::wstring const &)
0x1800e5414  nop
0x1800e5415  xorps   xmm0, xmm0
0x1800e5418  movdqu  [rsp+110h+var_E8], xmm0
0x1800e541e  mov     [rsp+110h+var_D8], r12
0x1800e5423  cmp     word ptr cs:aUqiconfigarray+1Ch, r12w; ""
0x1800e542b  jz      short loc_1800E5434
0x1800e542d  call    cs:__imp_abort
0x1800e5434  mov     [rbp+57h+var_B8], 1
0x1800e543b  mov     [rbp+57h+var_B4], 0Eh
0x1800e5442  lea     rcx, aUqiconfigarray; "UQIConfigArray"
0x1800e5449  mov     [rbp+57h+var_A8], rcx
0x1800e544d  lea     rcx, [rbp+57h+var_B8]
0x1800e5451  mov     [rbp+57h+var_C0], rcx
0x1800e5455  lea     r8, [rbp+57h+var_C0]
0x1800e5459  lea     rdx, [rsp+110h+var_F0]
0x1800e545e  mov     rcx, rax
0x1800e5461  call    ?GetNamedArray@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedArray(winrt::param::hstring const &)
0x1800e5466  nop
0x1800e5467  lea     rcx, [rsp+110h+var_F0]
0x1800e546c  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x1800e5471  mov     ecx, eax
0x1800e5473  mov     [rbp+57h+var_D0], rcx
0x1800e5477  mov     rax, [rsp+110h+var_D8]
0x1800e547c  sub     rax, qword ptr [rsp+110h+var_E8]
0x1800e5481  sar     rax, 3
0x1800e5485  mov     rdx, 8E38E38E38E38E39h
0x1800e548f  imul    rax, rdx
0x1800e5493  cmp     rcx, rax
0x1800e5496  jbe     short loc_1800E54A6
0x1800e5498  lea     rdx, [rbp+57h+var_D0]
0x1800e549c  lea     rcx, [rsp+110h+var_E8]
0x1800e54a1  call    ??$_Reallocate@$0A@@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXAEA_K@Z; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Reallocate<0>(unsigned __int64 &)
0x1800e54a6  mov     esi, r12d
0x1800e54a9  lea     rcx, [rsp+110h+var_F0]
0x1800e54ae  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x1800e54b3  test    eax, eax
0x1800e54b5  jz      loc_1800E554E
0x1800e54bb  mov     r8d, esi
0x1800e54be  lea     rdx, [rbp+57h+var_D0]
0x1800e54c2  lea     rcx, [rsp+110h+var_F0]
0x1800e54c7  call    ?GetObjectAt@?$consume_Windows_Data_Json_IJsonArray@UIJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Data_Json_IJsonArray<winrt::Windows::Data::Json::IJsonArray>::GetObjectAt(uint)
0x1800e54cc  nop
0x1800e54cd  mov     rdx, rax
0x1800e54d0  lea     rcx, [rbp+57h+var_90]
0x1800e54d4  call    ?ParseUQIConfig@Configuration@UsageAndQualityInsights@@YA?AUUQIConfig@12@AEBUJsonObject@Json@Data@Windows@winrt@@@Z; UsageAndQualityInsights::Configuration::ParseUQIConfig(winrt::Windows::Data::Json::JsonObject const &)
0x1800e54d9  nop
0x1800e54da  cmp     [rbp+57h+var_D0], r12
0x1800e54de  jz      short loc_1800E54E9
0x1800e54e0  lea     rcx, [rbp+57h+var_D0]
0x1800e54e4  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e54e9  mov     rax, qword ptr [rsp+110h+var_E8+8]
0x1800e54ee  cmp     rax, [rsp+110h+var_D8]
0x1800e54f3  jz      short loc_1800E5509
0x1800e54f5  lea     rdx, [rbp+57h+var_90]
0x1800e54f9  mov     rcx, rax
0x1800e54fc  call    ??0UQIConfig@Configuration@UsageAndQualityInsights@@QEAA@$$QEAU012@@Z; UsageAndQualityInsights::Configuration::UQIConfig::UQIConfig(UsageAndQualityInsights::Configuration::UQIConfig &&)
0x1800e5501  add     qword ptr [rsp+110h+var_E8+8], 48h ; 'H'
0x1800e5507  jmp     short loc_1800E551B
0x1800e5509  lea     r8, [rbp+57h+var_90]
0x1800e550d  mov     rdx, rax
0x1800e5510  lea     rcx, [rsp+110h+var_E8]
0x1800e5515  call    ??$_Emplace_reallocate@UUQIConfig@Configuration@UsageAndQualityInsights@@@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAPEAUUQIConfig@Configuration@UsageAndQualityInsights@@QEAU234@$$QEAU234@@Z; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Emplace_reallocate<UsageAndQualityInsights::Configuration::UQIConfig>(UsageAndQualityInsights::Configuration::UQIConfig * const,UsageAndQualityInsights::Configuration::UQIConfig &&)
0x1800e551a  nop
0x1800e551b  lea     rdx, [rbp+57h+var_58]
0x1800e551f  lea     rcx, [rbp+57h+var_58]
0x1800e5523  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UConsumptionFact@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UConsumptionFact@Configuration@UsageAndQualityInsights@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UConsumptionFact@Configuration@UsageAndQualityInsights@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::ConsumptionFact>,void *>> &)
0x1800e5528  lea     rcx, [rbp+57h+var_68]
0x1800e552c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFactDefinition@Configuration@UsageAndQualityInsights@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UFactDefinition@Configuration@UsageAndQualityInsights@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,UsageAndQualityInsights::Configuration::FactDefinition,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,UsageAndQualityInsights::Configuration::FactDefinition>>,0>>(void)
0x1800e5531  lea     rcx, [rbp+57h+var_90]; void *
0x1800e5535  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e553a  inc     esi
0x1800e553c  lea     rcx, [rsp+110h+var_F0]
0x1800e5541  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x1800e5546  cmp     esi, eax
0x1800e5548  jb      loc_1800E54BB
0x1800e554e  cmp     [rsp+110h+var_F0], r12
0x1800e5553  jz      short loc_1800E5560
0x1800e5555  lea     rcx, [rsp+110h+var_F0]
0x1800e555a  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e555f  nop
0x1800e5560  lea     rax, [rsp+110h+var_E8]
0x1800e5565  cmp     rdi, rax
0x1800e5568  jz      short loc_1800E559A
0x1800e556a  mov     rcx, rdi
0x1800e556d  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800e5572  mov     rax, qword ptr [rsp+110h+var_E8]
0x1800e5577  mov     [rdi], rax
0x1800e557a  mov     rax, qword ptr [rsp+110h+var_E8+8]
0x1800e557f  mov     [rdi+8], rax
0x1800e5583  mov     rax, [rsp+110h+var_D8]
0x1800e5588  mov     [rdi+10h], rax
0x1800e558c  xorps   xmm0, xmm0
0x1800e558f  movdqu  [rsp+110h+var_E8], xmm0
0x1800e5595  mov     [rsp+110h+var_D8], r12
0x1800e559a  lea     rcx, [rsp+110h+var_E8]
0x1800e559f  call    ?_Tidy@?$vector@UUQIConfig@Configuration@UsageAndQualityInsights@@V?$allocator@UUQIConfig@Configuration@UsageAndQualityInsights@@@std@@@std@@AEAAXXZ; std::vector<UsageAndQualityInsights::Configuration::UQIConfig>::_Tidy(void)
0x1800e55a4  nop
0x1800e55a5  cmp     [rbp+57h+var_C8], r12
0x1800e55a9  jz      short loc_1800E55B4
0x1800e55ab  lea     rcx, [rbp+57h+var_C8]
0x1800e55af  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800e55b4  lea     rcx, aConfigstoreCre; "ConfigStore Created"
0x1800e55bb  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x1800e55c0  nop
0x1800e55c1  mov     rax, rbx
0x1800e55c4  mov     rcx, [rbp+57h+var_40]
0x1800e55c8  xor     rcx, rsp; StackCookie
0x1800e55cb  call    __security_check_cookie
0x1800e55d0  add     rsp, 0E0h
0x1800e55d7  pop     r15
0x1800e55d9  pop     r14
0x1800e55db  pop     r12
0x1800e55dd  pop     rdi
0x1800e55de  pop     rsi
0x1800e55df  pop     rbx
0x1800e55e0  pop     rbp
0x1800e55e1  retn
```
