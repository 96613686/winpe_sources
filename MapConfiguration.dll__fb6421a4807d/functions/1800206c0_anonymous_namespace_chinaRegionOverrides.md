# _anonymous_namespace_::chinaRegionOverrides

- ea: `0x1800206c0`
- end: `0x180020936`
- name: `_anonymous_namespace_::chinaRegionOverrides`
- size: `630`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001efcc`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c3ac`
- `0x18000c850`
- `0x18000cfcc`
- `0x180011ddc`
- `0x180011e18`
- `0x18001ef80`
- `0x18001fbe4`
- `0x1800236e0`

## string_xrefs

- `0x180020772`: `https://dev.ditu.live.com/`
- `0x1800207b8`: `https://www.bing.com/th?p=0&pid=Local`
- `0x180020796`: `https://ssl.bing.com/api/v2/local`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall anonymous_namespace_::chinaRegionOverrides(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 ValueString; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _DWORD v19[2]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD *v20; // [rsp+28h] [rbp-58h]
  _BYTE v21[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-30h] BYREF

  v20 = a1;
  std::map<enum MapControl::ConfigurationKeys,std::wstring>::map<enum MapControl::ConfigurationKeys,std::wstring>(a1);
  v19[1] = 1;
  v19[0] = 1;
  v2 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v2);
  ValueString = MapControl::EndPoints::getValueString(v21);
  v19[0] = 0;
  v4 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v4, ValueString);
  std::wstring::_Tidy_deallocate(v21);
  v19[0] = 2;
  v5 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::assign(v5, L"2019/11/01 08:00:00");
  std::wstring::wstring((__int64)v22, (__int64)L"https://dev.ditu.live.com/");
  v19[0] = 291;
  v6 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::assign(v6, L"https://ssl.bing.com/api/v2/local");
  v19[0] = 292;
  v7 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::assign(v7, L"https://www.bing.com/th?p=0&pid=Local");
  v8 = std::operator+<unsigned short>(v21, v22, L"REST/v1/Locations");
  v19[0] = 293;
  v9 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v9, v8);
  std::wstring::_Tidy_deallocate(v21);
  v10 = std::operator+<unsigned short>(v21, v22, L"REST/v1/Routes/Driving");
  v19[0] = 294;
  v11 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v11, v10);
  std::wstring::_Tidy_deallocate(v21);
  v12 = std::operator+<unsigned short>(v21, v22, L"REST/v1/Routes/Walking");
  v19[0] = 295;
  v13 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v13, v12);
  std::wstring::_Tidy_deallocate(v21);
  v14 = std::operator+<unsigned short>(v21, v22, L"REST/v1/Routes/Transit");
  v19[0] = 296;
  v15 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::operator=(v15, v14);
  std::wstring::_Tidy_deallocate(v21);
  v19[0] = 300;
  v16 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::assign(v16, a8305419Gs20143);
  v19[0] = 301;
  v17 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](a1, v19);
  std::wstring::assign(v17, a8305419Gs20175);
  std::wstring::_Tidy_deallocate(v22);
  return a1;
}

```

## disassembly

```asm
0x1800206c0  mov     [rsp-8+arg_8], rbx
0x1800206c5  mov     [rsp-8+arg_10], rdi
0x1800206ca  push    rbp
0x1800206cb  mov     rbp, rsp
0x1800206ce  sub     rsp, 80h
0x1800206d5  mov     rax, cs:__security_cookie
0x1800206dc  xor     rax, rsp
0x1800206df  mov     [rbp+var_10], rax
0x1800206e3  mov     rdi, rcx
0x1800206e6  mov     [rbp+var_58], rcx
0x1800206ea  mov     [rbp+var_5C], 0
0x1800206f1  call    ??0?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAA@XZ; std::map<MapControl::ConfigurationKeys,std::wstring>::map<MapControl::ConfigurationKeys,std::wstring>(void)
0x1800206f6  mov     eax, 1
0x1800206fb  mov     [rbp+var_5C], eax
0x1800206fe  mov     [rbp+var_60], eax
0x180020701  lea     rdx, [rbp+var_60]
0x180020705  mov     rcx, rdi
0x180020708  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18002070d  mov     rcx, rax
0x180020710  lea     rdx, ?kDefaultRegion@ChinaEndPoints@MapControl@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const MapControl::ChinaEndPoints::kDefaultRegion
0x180020717  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002071c  lea     rcx, [rbp+var_50]
0x180020720  call    ?getValueString@EndPoints@MapControl@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@2@@Z; MapControl::EndPoints::getValueString(MapControl::ConfigurationKeys)
0x180020725  mov     rbx, rax
0x180020728  mov     [rbp+var_60], 0
0x18002072f  lea     rdx, [rbp+var_60]
0x180020733  mov     rcx, rdi
0x180020736  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18002073b  mov     rcx, rax
0x18002073e  mov     rdx, rbx
0x180020741  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020746  nop
0x180020747  lea     rcx, [rbp+var_50]
0x18002074b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020750  mov     [rbp+var_60], 2
0x180020757  lea     rdx, [rbp+var_60]
0x18002075b  mov     rcx, rdi
0x18002075e  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x180020763  lea     rdx, a20191101080000; "2019/11/01 08:00:00"
0x18002076a  mov     rcx, rax
0x18002076d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180020772  lea     rdx, aHttpsDevDituLi; "https://dev.ditu.live.com/"
0x180020779  lea     rcx, [rbp+var_30]
0x18002077d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020782  nop
0x180020783  mov     [rbp+var_60], 123h
0x18002078a  lea     rdx, [rbp+var_60]
0x18002078e  mov     rcx, rdi
0x180020791  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x180020796  lea     rdx, aHttpsSslBingCo; "https://ssl.bing.com/api/v2/local"
0x18002079d  mov     rcx, rax
0x1800207a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800207a5  mov     [rbp+var_60], 124h
0x1800207ac  lea     rdx, [rbp+var_60]
0x1800207b0  mov     rcx, rdi
0x1800207b3  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800207b8  lea     rdx, aHttpsWwwBingCo; "https://www.bing.com/th?p=0&pid=Local"
0x1800207bf  mov     rcx, rax
0x1800207c2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800207c7  lea     r8, aRestV1Location; "REST/v1/Locations"
0x1800207ce  lea     rdx, [rbp+var_30]
0x1800207d2  lea     rcx, [rbp+var_50]
0x1800207d6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800207db  mov     rbx, rax
0x1800207de  mov     [rbp+var_60], 125h
0x1800207e5  lea     rdx, [rbp+var_60]
0x1800207e9  mov     rcx, rdi
0x1800207ec  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800207f1  mov     rcx, rax
0x1800207f4  mov     rdx, rbx
0x1800207f7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800207fc  nop
0x1800207fd  lea     rcx, [rbp+var_50]
0x180020801  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020806  lea     r8, aRestV1RoutesDr; "REST/v1/Routes/Driving"
0x18002080d  lea     rdx, [rbp+var_30]
0x180020811  lea     rcx, [rbp+var_50]
0x180020815  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002081a  mov     rbx, rax
0x18002081d  mov     [rbp+var_60], 126h
0x180020824  lea     rdx, [rbp+var_60]
0x180020828  mov     rcx, rdi
0x18002082b  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x180020830  mov     rcx, rax
0x180020833  mov     rdx, rbx
0x180020836  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002083b  nop
0x18002083c  lea     rcx, [rbp+var_50]
0x180020840  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020845  lea     r8, aRestV1RoutesWa; "REST/v1/Routes/Walking"
0x18002084c  lea     rdx, [rbp+var_30]
0x180020850  lea     rcx, [rbp+var_50]
0x180020854  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180020859  mov     rbx, rax
0x18002085c  mov     [rbp+var_60], 127h
0x180020863  lea     rdx, [rbp+var_60]
0x180020867  mov     rcx, rdi
0x18002086a  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18002086f  mov     rcx, rax
0x180020872  mov     rdx, rbx
0x180020875  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002087a  nop
0x18002087b  lea     rcx, [rbp+var_50]
0x18002087f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020884  lea     r8, aRestV1RoutesTr; "REST/v1/Routes/Transit"
0x18002088b  lea     rdx, [rbp+var_30]
0x18002088f  lea     rcx, [rbp+var_50]
0x180020893  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180020898  mov     rbx, rax
0x18002089b  mov     [rbp+var_60], 128h
0x1800208a2  lea     rdx, [rbp+var_60]
0x1800208a6  mov     rcx, rdi
0x1800208a9  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800208ae  mov     rcx, rax
0x1800208b1  mov     rdx, rbx
0x1800208b4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800208b9  nop
0x1800208ba  lea     rcx, [rbp+var_50]
0x1800208be  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800208c3  mov     [rbp+var_60], 12Ch
0x1800208ca  lea     rdx, [rbp+var_60]
0x1800208ce  mov     rcx, rdi
0x1800208d1  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800208d6  lea     rdx, a8305419Gs20143; "8.30.54.19:GS(2014)3167"
0x1800208dd  mov     rcx, rax
0x1800208e0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800208e5  mov     [rbp+var_60], 12Dh
0x1800208ec  lea     rdx, [rbp+var_60]
0x1800208f0  mov     rcx, rdi
0x1800208f3  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800208f8  lea     rdx, a8305419Gs20175; "8.30.54.19:GS(2017)515"
0x1800208ff  mov     rcx, rax
0x180020902  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180020907  nop
0x180020908  lea     rcx, [rbp+var_30]
0x18002090c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020911  mov     rax, rdi
0x180020914  mov     rcx, [rbp+var_10]
0x180020918  xor     rcx, rsp; StackCookie
0x18002091b  call    __security_check_cookie
0x180020920  lea     r11, [rsp+80h+var_s0]
0x180020928  mov     rbx, [r11+18h]
0x18002092c  mov     rdi, [r11+20h]
0x180020930  mov     rsp, r11
0x180020933  pop     rbp
0x180020934  retn
```
