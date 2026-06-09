# `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)

- ea: `0x1800166ec`
- end: `0x180016781`
- name: `??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015198`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180014974`
- `0x1800166ec`
- `0x180032010`

## string_xrefs

- `0x18001670c`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

## pseudocode

```c
char __fastcall `winrt::Windows::Data::Json::JsonObject::TryParse'::`2'::_lambda_1_::operator()(
        _QWORD *a1,
        __int64 **a2)
{
  __int64 *v2; // rdi
  char *v3; // rbx
  _QWORD *v4; // rsi
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64 *, _QWORD, char *, char *); // rbp
  int v7; // eax
  char v9; // [rsp+30h] [rbp-48h] BYREF
  int v10; // [rsp+38h] [rbp-40h] BYREF
  const char *v11; // [rsp+40h] [rbp-38h]
  __int64 v12; // [rsp+48h] [rbp-30h]
  char v13; // [rsp+80h] [rbp+8h] BYREF

  v2 = *a2;
  v3 = (char *)a1[1];
  v4 = (_QWORD *)*a1;
  v10 = 314;
  v13 = 0;
  v11 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Data.Json.h";
  v5 = *v2;
  v12 = 0;
  v6 = *(__int64 (__fastcall **)(__int64 *, _QWORD, char *, char *))(v5 + 56);
  if ( v3 != &v9 )
  {
    if ( *(_QWORD *)v3 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3);
    *(_QWORD *)v3 = 0;
  }
  v7 = v6(v2, *v4, v3, &v13);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v10);
  return v13;
}

```

## disassembly

```asm
0x1800166ec  mov     rax, rsp
0x1800166ef  push    rbx
0x1800166f0  push    rbp
0x1800166f1  push    rsi
0x1800166f2  push    rdi
0x1800166f3  sub     rsp, 58h
0x1800166f7  mov     rdi, [rdx]
0x1800166fa  mov     rbx, [rcx+8]
0x1800166fe  mov     rsi, [rcx]
0x180016701  mov     dword ptr [rax-40h], 13Ah
0x180016708  mov     byte ptr [rax+8], 0
0x18001670c  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180016713  mov     [rsp+78h+var_38], rax
0x180016718  mov     rax, [rdi]
0x18001671b  mov     [rsp+78h+var_30], 0
0x180016724  mov     rbp, [rax+38h]
0x180016728  lea     rax, [rsp+78h+var_48]
0x18001672d  cmp     rbx, rax
0x180016730  jz      short loc_180016747
0x180016732  cmp     qword ptr [rbx], 0
0x180016736  jz      short loc_180016740
0x180016738  mov     rcx, rbx
0x18001673b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016740  mov     qword ptr [rbx], 0
0x180016747  mov     rdx, [rsi]
0x18001674a  lea     r9, [rsp+78h+arg_0]
0x180016752  mov     r8, rbx
0x180016755  mov     rcx, rdi
0x180016758  mov     rax, rbp
0x18001675b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016760  test    eax, eax
0x180016762  js      short loc_180016774
0x180016764  mov     al, [rsp+78h+arg_0]
0x18001676b  add     rsp, 58h
0x18001676f  pop     rdi
0x180016770  pop     rsi
0x180016771  pop     rbp
0x180016772  pop     rbx
0x180016773  retn
0x180016774  lea     rdx, [rsp+78h+var_40]
0x180016779  mov     ecx, eax
0x18001677b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
