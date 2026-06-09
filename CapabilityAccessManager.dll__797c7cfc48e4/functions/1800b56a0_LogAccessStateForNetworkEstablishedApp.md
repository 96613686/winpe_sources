# LogAccessStateForNetworkEstablishedApp

- ea: `0x1800b56a0`
- end: `0x1800b59b2`
- name: `LogAccessStateForNetworkEstablishedApp`
- size: `786`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000186c`
- `0x1800043f4`
- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f85c`
- `0x180020fcc`
- `0x18002392c`
- `0x180029408`
- `0x1800421ec`
- `0x180046610`
- `0x180062198`
- `0x18006874c`
- `0x18006c920`
- `0x180071848`
- `0x1800b52c4`
- `0x1800b56a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b574b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b576f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b574b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b576f`

## string_xrefs

- `0x1800b5971`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b5988`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`
- `0x1800b599f`: `onecore\base\devices\cam\core\capabilityaccessmanagerrpcimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LogAccessStateForNetworkEstablishedApp(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4)
{
  int v7; // eax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // eax
  __int64 v13; // r10
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  const char *v17; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-F8h]
  __int64 v19; // [rsp+40h] [rbp-D8h] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-C0h] BYREF
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v23; // [rsp+60h] [rbp-B8h] BYREF
  std::_Ref_count_base *v24; // [rsp+68h] [rbp-B0h]
  __int64 v25[4]; // [rsp+70h] [rbp-A8h] BYREF
  int v26[8]; // [rsp+90h] [rbp-88h] BYREF
  int v27[8]; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_ba398d49f73833a47629aaaf6d810685_Traceguids);
  }
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80004003LL,
      bIgnoreCase);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80004003LL,
      bIgnoreCase);
  if ( !a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
      (const char *)0x80004003LL,
      bIgnoreCase);
  v7 = CompareStringOrdinal(a4, -1, L"cellularData", -1, 1);
  if ( v7 == 2 || (v8 = CompareStringOrdinal(a4, -1, L"wifiData", -1, 1), v8 == 2) )
  {
    try
    {
      v10 = std::wstring::wstring(v28, a2);
      Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromFullName(v25, v10);
      std::wstring::_Tidy_deallocate(v28);
      std::wstring::wstring(v27, a4);
      std::wstring::wstring(v26, a3);
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithPackageFamilyName(
        (int)&v23,
        (int)v26,
        (int)v27,
        (__int64)v25,
        1);
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(v27);
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressUserConsentPrompt(v23, 1);
      v11 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck((__int64)v23);
      if ( (unsigned int)CapabilityAccessStatusToRPC(v11) != 3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
          WPP_SF_SS(
            *(_QWORD *)(v13 + 16),
            23,
            (unsigned int)&WPP_ba398d49f73833a47629aaaf6d810685_Traceguids,
            v12,
            (__int64)a4);
        }
        v14 = CapabilityAccessTelemetry::Provider();
        if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v14) )
        {
          v19 = 0x1000000;
          v20 = a4;
          v21 = a3;
          v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v15,
            (unsigned int)byte_18014CB53,
            v15,
            v16,
            (__int64)&v22,
            (__int64)&v21,
            (__int64)&v20,
            (__int64)&v19);
        }
      }
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
      std::wstring::_Tidy_deallocate(v25);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x121,
                             (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagerrpcimpl.cpp",
                             v17);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ba398d49f73833a47629aaaf6d810685_Traceguids, a2);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b56a0  mov     [rsp+arg_0], rbx
0x1800b56a5  push    rsi
0x1800b56a6  push    rdi
0x1800b56a7  push    r14
0x1800b56a9  sub     rsp, 100h
0x1800b56b0  mov     rax, cs:__security_cookie
0x1800b56b7  xor     rax, rsp
0x1800b56ba  mov     [rsp+118h+var_28], rax
0x1800b56c2  mov     rbx, r9
0x1800b56c5  mov     rsi, r8
0x1800b56c8  mov     rdi, rdx
0x1800b56cb  lea     r14, WPP_GLOBAL_Control
0x1800b56d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b56d9  cmp     rcx, r14
0x1800b56dc  jz      short loc_1800B56FF
0x1800b56de  test    byte ptr [rcx+1Ch], 1
0x1800b56e2  jz      short loc_1800B56FF
0x1800b56e4  cmp     byte ptr [rcx+19h], 5
0x1800b56e8  jb      short loc_1800B56FF
0x1800b56ea  mov     edx, 15h
0x1800b56ef  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b56f6  mov     rcx, [rcx+10h]
0x1800b56fa  call    WPP_SF_
0x1800b56ff  mov     rcx, [rsp+118h]; this
0x1800b5707  test    rdi, rdi
0x1800b570a  jz      loc_1800B596B
0x1800b5710  mov     rcx, [rsp+118h]; this
0x1800b5718  test    rsi, rsi
0x1800b571b  jz      loc_1800B5982
0x1800b5721  mov     rcx, [rsp+118h]; this
0x1800b5729  test    rbx, rbx
0x1800b572c  jz      loc_1800B5999
0x1800b5732  mov     [rsp+118h+bIgnoreCase], 1; bIgnoreCase
0x1800b573a  or      r9d, 0FFFFFFFFh; cchCount2
0x1800b573e  lea     r8, aCellulardata; "cellularData"
0x1800b5745  or      edx, r9d; cchCount1
0x1800b5748  mov     rcx, rbx; lpString1
0x1800b574b  call    cs:__imp_CompareStringOrdinal
0x1800b5751  cmp     eax, 2
0x1800b5754  jz      short loc_1800B57B1
0x1800b5756  mov     [rsp+118h+bIgnoreCase], 1; bIgnoreCase
0x1800b575e  or      r9d, 0FFFFFFFFh; cchCount2
0x1800b5762  lea     r8, aWifidata; "wifiData"
0x1800b5769  or      edx, r9d; cchCount1
0x1800b576c  mov     rcx, rbx; lpString1
0x1800b576f  call    cs:__imp_CompareStringOrdinal
0x1800b5775  cmp     eax, 2
0x1800b5778  jz      short loc_1800B57B1
0x1800b577a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5781  cmp     rcx, r14
0x1800b5784  jz      short loc_1800B57AA
0x1800b5786  test    byte ptr [rcx+1Ch], 1
0x1800b578a  jz      short loc_1800B57AA
0x1800b578c  cmp     byte ptr [rcx+19h], 4
0x1800b5790  jb      short loc_1800B57AA
0x1800b5792  mov     edx, 16h
0x1800b5797  mov     r9, rdi
0x1800b579a  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b57a1  mov     rcx, [rcx+10h]
0x1800b57a5  call    WPP_SF_S
0x1800b57aa  xor     eax, eax
0x1800b57ac  jmp     loc_1800B5947
0x1800b57b1  mov     rdx, rdi
0x1800b57b4  lea     rcx, [rsp+118h+var_48]
0x1800b57bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b57c1  nop
0x1800b57c2  mov     rdx, rax
0x1800b57c5  lea     rcx, [rsp+118h+var_A8]
0x1800b57ca  call    ?GetPackageFamilyNameFromFullName@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromFullName(std::wstring const &)
0x1800b57cf  nop
0x1800b57d0  lea     rcx, [rsp+118h+var_48]
0x1800b57d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b57dd  mov     rdx, rbx
0x1800b57e0  lea     rcx, [rsp+118h+var_68]
0x1800b57e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b57ed  nop
0x1800b57ee  mov     rdx, rsi
0x1800b57f1  lea     rcx, [rsp+118h+var_88]
0x1800b57f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b57fe  nop
0x1800b57ff  mov     byte ptr [rsp+118h+bIgnoreCase], 1; char
0x1800b5804  lea     r9, [rsp+118h+var_A8]; __int64
0x1800b5809  lea     r8, [rsp+118h+var_68]; int
0x1800b5811  lea     rdx, [rsp+118h+var_88]; int
0x1800b5819  lea     rcx, [rsp+118h+var_B8]; int
0x1800b581e  call    ?CreateWithPackageFamilyName@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@00_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateWithPackageFamilyName(std::wstring const &,std::wstring const &,std::wstring const &,bool)
0x1800b5823  nop
0x1800b5824  lea     rcx, [rsp+118h+var_88]
0x1800b582c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5831  nop
0x1800b5832  lea     rcx, [rsp+118h+var_68]
0x1800b583a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b583f  mov     dl, 1; bool
0x1800b5841  mov     rcx, [rsp+118h+var_B8]; this
0x1800b5846  call    ?put_SuppressUserConsentPrompt@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAX_N@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressUserConsentPrompt(bool)
0x1800b584b  mov     rcx, [rsp+118h+var_B8]
0x1800b5850  call    ?AccessCheck@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4AccessCheckStatus@2345@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck(void)
0x1800b5855  mov     ecx, eax
0x1800b5857  call    ?CapabilityAccessStatusToRPC@@YA?AW4RPCCapabilityAccessStatus@@W4AccessCheckStatus@Private@CapabilityAccess@Internal@Windows@@@Z; CapabilityAccessStatusToRPC(Windows::Internal::CapabilityAccess::Private::AccessCheckStatus)
0x1800b585c  cmp     eax, 3
0x1800b585f  jz      loc_1800B5925
0x1800b5865  mov     r10, cs:WPP_GLOBAL_Control
0x1800b586c  cmp     r10, r14
0x1800b586f  jz      short loc_1800B58A6
0x1800b5871  test    byte ptr [r10+1Ch], 1
0x1800b5876  jz      short loc_1800B58A6
0x1800b5878  cmp     byte ptr [r10+19h], 4
0x1800b587d  jb      short loc_1800B58A6
0x1800b587f  lea     rcx, [rsp+118h+var_A8]
0x1800b5884  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b5889  mov     r9, rax
0x1800b588c  mov     edx, 17h
0x1800b5891  mov     qword ptr [rsp+118h+bIgnoreCase], rbx
0x1800b5896  lea     r8, WPP_ba398d49f73833a47629aaaf6d810685_Traceguids
0x1800b589d  mov     rcx, [r10+10h]
0x1800b58a1  call    WPP_SF_SS
0x1800b58a6  call    ?Provider@CapabilityAccessTelemetry@@SAPEBU_tlgProvider_t@@XZ; CapabilityAccessTelemetry::Provider(void)
0x1800b58ab  mov     r8, rax
0x1800b58ae  mov     ecx, [rax]
0x1800b58b0  cmp     ecx, 5
0x1800b58b3  jbe     short loc_1800B5925
0x1800b58b5  mov     rdx, 400000000000h
0x1800b58bf  mov     rcx, rax
0x1800b58c2  call    _tlgKeywordOn
0x1800b58c7  test    al, al
0x1800b58c9  jz      short loc_1800B5925
0x1800b58cb  mov     [rsp+118h+var_D8], 1000000h
0x1800b58d4  mov     [rsp+118h+var_D0], rbx
0x1800b58d9  mov     [rsp+118h+var_C8], rsi
0x1800b58de  lea     rcx, [rsp+118h+var_A8]
0x1800b58e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b58e8  mov     [rsp+118h+var_C0], rax
0x1800b58ed  lea     rax, [rsp+118h+var_D8]
0x1800b58f2  mov     [rsp+118h+var_E0], rax
0x1800b58f7  lea     rax, [rsp+118h+var_D0]
0x1800b58fc  mov     [rsp+118h+var_E8], rax
0x1800b5901  lea     rax, [rsp+118h+var_C8]
0x1800b5906  mov     [rsp+118h+var_F0], rax
0x1800b590b  lea     rax, [rsp+118h+var_C0]
0x1800b5910  mov     qword ptr [rsp+118h+bIgnoreCase], rax
0x1800b5915  lea     rdx, byte_18014CB53
0x1800b591c  mov     rcx, r8
0x1800b591f  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800b5924  nop
0x1800b5925  mov     rcx, [rsp+118h+var_B0]; this
0x1800b592a  test    rcx, rcx
0x1800b592d  jz      short loc_1800B5935
0x1800b592f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b5934  nop
0x1800b5935  lea     rcx, [rsp+118h+var_A8]
0x1800b593a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b593f  xor     eax, eax
0x1800b5941  jmp     short loc_1800B5947
0x1800b5943  mov     eax, dword ptr [rsp+118h+var_D8]
0x1800b5947  mov     rcx, [rsp+118h+var_28]
0x1800b594f  xor     rcx, rsp; StackCookie
0x1800b5952  call    __security_check_cookie
0x1800b5957  mov     rbx, [rsp+118h+arg_0]
0x1800b595f  add     rsp, 100h
0x1800b5966  pop     r14
0x1800b5968  pop     rdi
0x1800b5969  pop     rsi
0x1800b596a  retn
0x1800b596b  mov     r9d, 80004003h; char *
0x1800b5971  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b5978  mov     edx, 0F8h; void *
0x1800b597d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5982  mov     r9d, 80004003h; char *
0x1800b5988  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b598f  mov     edx, 0F9h; void *
0x1800b5994  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5999  mov     r9d, 80004003h; char *
0x1800b599f  lea     r8, aOnecoreBaseDev_41; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800b59a6  mov     edx, 0FAh; void *
0x1800b59ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
