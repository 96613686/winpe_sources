# winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)

- ea: `0x180017620`
- end: `0x180017688`
- name: `?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800176ec`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180017620`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  signed int v4; // eax
  __int64 v5; // r8
  unsigned int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]

  *a2 = 0;
  v3 = *a1;
  v7 = 118;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v9 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
  if ( v4 < 0 )
    winrt::throw_hresult(v4, &v7, v5);
  return a2;
}

```

## disassembly

```asm
0x180017620  mov     [rsp+arg_8], rdx
0x180017625  push    rbx
0x180017626  sub     rsp, 40h
0x18001762a  mov     rbx, rdx
0x18001762d  mov     [rsp+48h+var_28], 0
0x180017635  xor     eax, eax
0x180017637  mov     [rdx], rax
0x18001763a  mov     [rsp+48h+var_28], 1
0x180017642  mov     rcx, [rcx]
0x180017645  mov     [rsp+48h+var_20], 76h ; 'v'
0x18001764d  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180017654  mov     [rsp+48h+var_18], rax
0x180017659  mov     [rsp+48h+var_10], 0
0x180017662  mov     rax, [rcx]
0x180017665  mov     rax, [rax+30h]
0x180017669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001766e  test    eax, eax
0x180017670  js      short loc_18001767B
0x180017672  mov     rax, rbx
0x180017675  add     rsp, 40h
0x180017679  pop     rbx
0x18001767a  retn
0x18001767b  lea     rdx, [rsp+48h+var_20]
0x180017680  mov     ecx, eax
0x180017682  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
