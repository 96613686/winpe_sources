# wil::ActivateInstance<Windows::Data::Json::IJsonObject>(ushort const *)

- ea: `0x140008450`
- end: `0x1400084eb`
- name: `??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@wil@@YA?AV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ed9c`

## callees

- `0x140002210`
- `0x14000834c`
- `0x140008450`
- `0x140009844`
- `0x14000a04c`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140008499`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140008499`

## string_xrefs

- `0x14000846f`: `Windows.Data.Json.JsonObject`
- `0x1400084ab`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<Windows::Data::Json::IJsonObject>(__int64 a1)
{
  HSTRING_HEADER *v2; // rax
  int v3; // eax
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v6; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v7; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = L"Windows.Data.Json.JsonObject";
  v5 = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v7, &v6);
  v3 = RoActivateInstance(v2[1].Reserved.Reserved1, &v5);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x74D,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v3,
      v5);
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Data::Json::IJsonObject>(&v5, a1);
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(&v5);
  return a1;
}

```

## disassembly

```asm
0x140008450  mov     r11, rsp
0x140008453  push    rbx
0x140008454  sub     rsp, 60h
0x140008458  mov     rax, cs:__security_cookie
0x14000845f  xor     rax, rsp
0x140008462  mov     [rsp+68h+var_10], rax
0x140008467  mov     rbx, rcx
0x14000846a  mov     [rsp+68h+var_40], rcx
0x14000846f  lea     rax, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x140008476  mov     [r11-40h], rax
0x14000847a  mov     qword ptr [r11-48h], 0
0x140008482  lea     rdx, [r11-40h]
0x140008486  lea     rcx, [r11-30h]
0x14000848a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000848f  nop
0x140008490  lea     rdx, [rsp+68h+var_48]
0x140008495  mov     rcx, [rax+18h]
0x140008499  call    cs:__imp_RoActivateInstance
0x14000849f  mov     rcx, [rsp+68h]; this
0x1400084a4  test    eax, eax
0x1400084a6  jns     short loc_1400084BD
0x1400084a8  mov     r9d, eax; char *
0x1400084ab  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400084b2  mov     edx, 74Dh; void *
0x1400084b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400084bd  mov     rdx, rbx
0x1400084c0  lea     rcx, [rsp+68h+var_48]
0x1400084c5  call    ??$query@UIJsonObject@Json@Data@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Data::Json::IJsonObject>(void)
0x1400084ca  nop
0x1400084cb  lea     rcx, [rsp+68h+var_48]
0x1400084d0  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x1400084d5  mov     rax, rbx
0x1400084d8  mov     rcx, [rsp+68h+var_10]
0x1400084dd  xor     rcx, rsp; StackCookie
0x1400084e0  call    __security_check_cookie
0x1400084e5  add     rsp, 60h
0x1400084e9  pop     rbx
0x1400084ea  retn
```
