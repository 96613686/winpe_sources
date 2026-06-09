# `winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)'::`2'::_lambda_1_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)

- ea: `0x18001ca5c`
- end: `0x18001caf1`
- name: `??R_lambda_1_@?1??TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@6@AEAU23456@@Z@QEBA@AEBUIJsonObjectStatics@3456@@Z`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bea8`
- `0x18001d680`

## callees

- `0x18001a3fc`
- `0x18001a798`
- `0x18001ca5c`
- `0x180021010`

## string_xrefs

- `0x18001ca7c`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt/Windows.Data.Json.h`

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
0x18001ca5c  mov     rax, rsp
0x18001ca5f  push    rbx
0x18001ca60  push    rbp
0x18001ca61  push    rsi
0x18001ca62  push    rdi
0x18001ca63  sub     rsp, 58h
0x18001ca67  mov     rdi, [rdx]
0x18001ca6a  mov     rbx, [rcx+8]
0x18001ca6e  mov     rsi, [rcx]
0x18001ca71  mov     dword ptr [rax-40h], 13Ah
0x18001ca78  mov     byte ptr [rax+8], 0
0x18001ca7c  lea     rax, aOnecoreuapInte_5; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001ca83  mov     [rsp+78h+var_38], rax
0x18001ca88  mov     rax, [rdi]
0x18001ca8b  mov     [rsp+78h+var_30], 0
0x18001ca94  mov     rbp, [rax+38h]
0x18001ca98  lea     rax, [rsp+78h+var_48]
0x18001ca9d  cmp     rbx, rax
0x18001caa0  jz      short loc_18001CAB7
0x18001caa2  cmp     qword ptr [rbx], 0
0x18001caa6  jz      short loc_18001CAB0
0x18001caa8  mov     rcx, rbx
0x18001caab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001cab0  mov     qword ptr [rbx], 0
0x18001cab7  mov     rdx, [rsi]
0x18001caba  lea     r9, [rsp+78h+arg_0]
0x18001cac2  mov     r8, rbx
0x18001cac5  mov     rcx, rdi
0x18001cac8  mov     rax, rbp
0x18001cacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad0  test    eax, eax
0x18001cad2  js      short loc_18001CAE4
0x18001cad4  mov     al, [rsp+78h+arg_0]
0x18001cadb  add     rsp, 58h
0x18001cadf  pop     rdi
0x18001cae0  pop     rsi
0x18001cae1  pop     rbp
0x18001cae2  pop     rbx
0x18001cae3  retn
0x18001cae4  lea     rdx, [rsp+78h+var_40]
0x18001cae9  mov     ecx, eax
0x18001caeb  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
