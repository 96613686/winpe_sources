# winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::MoveNext(void)

- ea: `0x180017690`
- end: `0x1800176e4`
- name: `?MoveNext@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800176ec`
- `0x180018710`

## callees

- `0x1800145d8`
- `0x180017690`
- `0x180032010`

## pseudocode

```c
char __fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::MoveNext(
        __int64 **a1)
{
  __int64 *v1; // rcx
  __int64 v2; // rax
  signed int v3; // eax
  __int64 v4; // r8
  unsigned int v6; // [rsp+20h] [rbp-28h] BYREF
  const char *v7; // [rsp+28h] [rbp-20h]
  __int64 v8; // [rsp+30h] [rbp-18h]
  char v9; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  v7 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Foundation.Collections.h";
  v9 = 0;
  v6 = 82;
  v2 = *v1;
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, char *))(v2 + 64))(v1, &v9);
  if ( v3 < 0 )
    winrt::throw_hresult(v3, &v6, v4);
  return v9;
}

```

## disassembly

```asm
0x180017690  sub     rsp, 48h
0x180017694  mov     rcx, [rcx]
0x180017697  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001769e  mov     [rsp+48h+var_20], rax
0x1800176a3  lea     rdx, [rsp+48h+arg_0]
0x1800176a8  mov     [rsp+48h+arg_0], 0
0x1800176ad  mov     [rsp+48h+var_28], 52h ; 'R'
0x1800176b5  mov     rax, [rcx]
0x1800176b8  mov     [rsp+48h+var_18], 0
0x1800176c1  mov     rax, [rax+40h]
0x1800176c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176ca  test    eax, eax
0x1800176cc  js      short loc_1800176D7
0x1800176ce  mov     al, [rsp+48h+arg_0]
0x1800176d2  add     rsp, 48h
0x1800176d6  retn
0x1800176d7  lea     rdx, [rsp+48h+var_28]
0x1800176dc  mov     ecx, eax
0x1800176de  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
