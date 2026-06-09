# _SendRequestAndWaitForResponse_::_1_::catch$38

- ea: `0x18004e6db`
- end: `0x18004e804`
- name: `_SendRequestAndWaitForResponse_::_1_::catch$38`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000dc43`
- `0x18000ea5c`
- `0x180021a64`
- `0x180022724`
- `0x180030d18`
- `0x1800426d8`
- `0x180047804`
- `0x1800480ec`
- `0x180048d34`
- `0x180049294`
- `0x18004e6db`

## string_xrefs

- `0x18004e71c`: `Not using a config url`
- `0x18004e77f`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x18004e7e9`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`
- `0x18004e770`: `Failed to connect to %ws with proxy config url %ws`
- `0x18004e7e2`: `Failed to connect to %ws with proxy config url %ws`

## pseudocode

```c
void __fastcall __noreturn SendRequestAndWaitForResponse_::_1_::catch_38(__int64 a1, __int64 a2)
{
  wil *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rax
  _QWORD *v6; // rax
  const char *v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // r8d
  __int64 ConfigUrl; // rax
  __int64 v11; // rbx
  const char *v12; // rax
  int v13; // [rsp+20h] [rbp-38h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl'::`2'::impl) )
  {
    v4 = wil::ResultFromCaughtException(v3);
    if ( v4 == -2147012867 )
      v4 = -2143309801;
    v5 = *(_QWORD *)(a2 + 80);
    if ( !*(_BYTE *)(v5 + 2) )
    {
      std::logic_error::logic_error((std::logic_error *)(a2 + 264), "Not using a config url");
      throw (std::logic_error *)(a2 + 264);
    }
    v6 = (_QWORD *)(v5 + 64);
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v7 = *(const char **)(a2 + 96);
    if ( *((_QWORD *)v7 + 3) > 7u )
      v7 = *(const char **)v7;
    wil::details::in1diag3::Log_HrMsg(
      *(wil::details::in1diag3 **)(a2 + 472),
      (void *)0xE2,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      (const char *)v4,
      (int)"Failed to connect to %ws with proxy config url %ws",
      v7,
      v6);
    if ( v4 == -2143309801 )
    {
      v8 = wil::verify_hresult<long>(2151657495LL);
      wil::details::in1diag3::Throw_Hr(*(wil::details::in1diag3 **)(a2 + 472), (void *)0xE5, v9, (const char *)v8, v13);
    }
  }
  else
  {
    ConfigUrl = ProxySettings::GetConfigUrl(*(_QWORD *)(a2 + 80));
    v11 = std::wstring::c_str(ConfigUrl);
    v12 = (const char *)std::wstring::c_str(*(_QWORD *)(a2 + 96));
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      *(wil::details::in1diag3 **)(a2 + 472),
      (void *)0xEA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
      "Failed to connect to %ws with proxy config url %ws",
      v12,
      v11);
  }
  throw;
}

```

## disassembly

```asm
0x18004e6db  mov     [rsp+arg_8], rdx
0x18004e6e0  push    rbx
0x18004e6e1  push    rbp
0x18004e6e2  sub     rsp, 48h
0x18004e6e6  mov     rbp, rdx
0x18004e6e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue> `wil::Feature<__WilFeatureTraits_Feature_ProxyConnectionIssue>::GetImpl(void)'::`2'::impl
0x18004e6f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProxyConnectionIssue@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProxyConnectionIssue>::__private_IsEnabled(void)
0x18004e6f5  test    al, al
0x18004e6f7  jz      loc_18004E7B4
0x18004e6fd  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004e702  mov     ebx, eax
0x18004e704  mov     eax, 803FB017h
0x18004e709  cmp     ebx, 80072EFDh
0x18004e70f  cmovz   ebx, eax
0x18004e712  mov     rax, [rbp+50h]
0x18004e716  cmp     byte ptr [rax+2], 0
0x18004e71a  jnz     short loc_18004E743
0x18004e71c  lea     rdx, aNotUsingAConfi; "Not using a config url"
0x18004e723  lea     rcx, [rbp+108h]; this
0x18004e72a  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18004e72f  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18004e736  lea     rcx, [rbp+108h]; pExceptionObject
0x18004e73d  call    _CxxThrowException_0
0x18004e743  add     rax, 40h ; '@'
0x18004e747  cmp     qword ptr [rax+18h], 7
0x18004e74c  jbe     short loc_18004E751
0x18004e74e  mov     rax, [rax]
0x18004e751  mov     rdx, [rbp+60h]
0x18004e755  cmp     qword ptr [rdx+18h], 7
0x18004e75a  jbe     short loc_18004E75F
0x18004e75c  mov     rdx, [rdx]
0x18004e75f  mov     rcx, [rbp+1D8h]; this
0x18004e766  mov     [rsp+58h+var_28], rax
0x18004e76b  mov     [rsp+58h+var_30], rdx; char *
0x18004e770  lea     rax, aFailedToConnec_1; "Failed to connect to %ws with proxy con"...
0x18004e777  mov     [rsp+58h+var_38], rax; int
0x18004e77c  mov     r9d, ebx; char *
0x18004e77f  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004e786  mov     edx, 0E2h; void *
0x18004e78b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e790  cmp     ebx, 803FB017h
0x18004e796  jnz     short loc_18004E7FA
0x18004e798  mov     ecx, ebx
0x18004e79a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004e79f  mov     r9d, eax; char *
0x18004e7a2  mov     rcx, [rbp+1D8h]; this
0x18004e7a9  mov     edx, 0E5h; void *
0x18004e7ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e7b4  mov     rcx, [rbp+50h]
0x18004e7b8  call    ?GetConfigUrl@ProxySettings@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProxySettings::GetConfigUrl(void)
0x18004e7bd  mov     rcx, rax
0x18004e7c0  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004e7c5  mov     rbx, rax
0x18004e7c8  mov     rcx, [rbp+60h]
0x18004e7cc  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18004e7d1  mov     rcx, [rbp+1D8h]; this
0x18004e7d8  mov     [rsp+58h+var_30], rbx
0x18004e7dd  mov     [rsp+58h+var_38], rax; char *
0x18004e7e2  lea     r9, aFailedToConnec_1; "Failed to connect to %ws with proxy con"...
0x18004e7e9  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004e7f0  mov     edx, 0EAh; void *
0x18004e7f5  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004e7fa  xor     edx, edx; pThrowInfo
0x18004e7fc  xor     ecx, ecx; pExceptionObject
0x18004e7fe  call    _CxxThrowException_0
```
