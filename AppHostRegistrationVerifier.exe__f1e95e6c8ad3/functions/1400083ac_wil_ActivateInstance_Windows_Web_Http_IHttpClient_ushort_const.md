# wil::ActivateInstance<Windows::Web::Http::IHttpClient>(ushort const *)

- ea: `0x1400083ac`
- end: `0x140008447`
- name: `??$ActivateInstance@UIHttpClient@Http@Web@Windows@@@wil@@YA?AV?$com_ptr_t@UIHttpClient@Http@Web@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000c848`

## callees

- `0x140002210`
- `0x14000834c`
- `0x1400083ac`
- `0x1400097ec`
- `0x14000a04c`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400083f5`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400083f5`

## string_xrefs

- `0x140008407`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::ActivateInstance<Windows::Web::Http::IHttpClient>(__int64 a1)
{
  HSTRING_HEADER *v2; // rax
  int v3; // eax
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v6; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER v7; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = L"Windows.Web.Http.HttpClient";
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
  wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Web::Http::IHttpClient>(&v5, a1);
  wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(&v5);
  return a1;
}

```

## disassembly

```asm
0x1400083ac  mov     r11, rsp
0x1400083af  push    rbx
0x1400083b0  sub     rsp, 60h
0x1400083b4  mov     rax, cs:__security_cookie
0x1400083bb  xor     rax, rsp
0x1400083be  mov     [rsp+68h+var_10], rax
0x1400083c3  mov     rbx, rcx
0x1400083c6  mov     [rsp+68h+var_40], rcx
0x1400083cb  lea     rax, ?RuntimeClass_Windows_Web_Http_HttpClient@@3QBGB; "Windows.Web.Http.HttpClient"
0x1400083d2  mov     [r11-40h], rax
0x1400083d6  mov     qword ptr [r11-48h], 0
0x1400083de  lea     rdx, [r11-40h]
0x1400083e2  lea     rcx, [r11-30h]
0x1400083e6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400083eb  nop
0x1400083ec  lea     rdx, [rsp+68h+var_48]
0x1400083f1  mov     rcx, [rax+18h]
0x1400083f5  call    cs:__imp_RoActivateInstance
0x1400083fb  mov     rcx, [rsp+68h]; this
0x140008400  test    eax, eax
0x140008402  jns     short loc_140008419
0x140008404  mov     r9d, eax; char *
0x140008407  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000840e  mov     edx, 74Dh; void *
0x140008413  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008419  mov     rdx, rbx
0x14000841c  lea     rcx, [rsp+68h+var_48]
0x140008421  call    ??$query@UIHttpClient@Http@Web@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIHttpClient@Http@Web@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Web::Http::IHttpClient>(void)
0x140008426  nop
0x140008427  lea     rcx, [rsp+68h+var_48]
0x14000842c  call    ??1?$com_ptr_t@UIDynamicAppUriHandlerStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IDynamicAppUriHandlerStatics,wil::err_exception_policy>(void)
0x140008431  mov     rax, rbx
0x140008434  mov     rcx, [rsp+68h+var_10]
0x140008439  xor     rcx, rsp; StackCookie
0x14000843c  call    __security_check_cookie
0x140008441  add     rsp, 60h
0x140008445  pop     rbx
0x140008446  retn
```
