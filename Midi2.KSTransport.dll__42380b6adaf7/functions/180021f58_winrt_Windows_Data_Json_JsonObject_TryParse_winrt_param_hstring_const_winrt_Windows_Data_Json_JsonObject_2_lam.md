# `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)

- ea: `0x180021f58`
- end: `0x180021fed`
- name: `??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020f0c`
- `0x180023ac0`

## callees

- `0x18000d1c0`
- `0x180015348`
- `0x180021f58`
- `0x180041010`

## string_xrefs

- `0x180021f78`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
0x180021f58  mov     rax, rsp
0x180021f5b  push    rbx
0x180021f5c  push    rbp
0x180021f5d  push    rsi
0x180021f5e  push    rdi
0x180021f5f  sub     rsp, 58h
0x180021f63  mov     rdi, [rdx]
0x180021f66  mov     rbx, [rcx+8]
0x180021f6a  mov     rsi, [rcx]
0x180021f6d  mov     dword ptr [rax-40h], 13Ah
0x180021f74  mov     byte ptr [rax+8], 0
0x180021f78  lea     rax, aOnecoreuapInte_10; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180021f7f  mov     [rsp+78h+var_38], rax
0x180021f84  mov     rax, [rdi]
0x180021f87  mov     [rsp+78h+var_30], 0
0x180021f90  mov     rbp, [rax+38h]
0x180021f94  lea     rax, [rsp+78h+var_48]
0x180021f99  cmp     rbx, rax
0x180021f9c  jz      short loc_180021FB3
0x180021f9e  cmp     qword ptr [rbx], 0
0x180021fa2  jz      short loc_180021FAC
0x180021fa4  mov     rcx, rbx
0x180021fa7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021fac  mov     qword ptr [rbx], 0
0x180021fb3  mov     rdx, [rsi]
0x180021fb6  lea     r9, [rsp+78h+arg_0]
0x180021fbe  mov     r8, rbx
0x180021fc1  mov     rcx, rdi
0x180021fc4  mov     rax, rbp
0x180021fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fcc  test    eax, eax
0x180021fce  js      short loc_180021FE0
0x180021fd0  mov     al, [rsp+78h+arg_0]
0x180021fd7  add     rsp, 58h
0x180021fdb  pop     rdi
0x180021fdc  pop     rsi
0x180021fdd  pop     rbp
0x180021fde  pop     rbx
0x180021fdf  retn
0x180021fe0  lea     rdx, [rsp+78h+var_40]
0x180021fe5  mov     ecx, eax
0x180021fe7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
