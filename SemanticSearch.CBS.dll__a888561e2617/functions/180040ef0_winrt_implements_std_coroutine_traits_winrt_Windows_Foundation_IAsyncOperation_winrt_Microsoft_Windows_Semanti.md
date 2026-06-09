# winrt::implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(void)

- ea: `0x180040ef0`
- end: `0x180040fa8`
- name: `?GetRuntimeClassName@?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@@std@@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@567@@winrt@@EEBA?AUhstring@2@XZ`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x180040ef0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180040f13`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180040f13`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180040f1f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180040f1f`

## string_xrefs

- `0x180040f36`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  _OWORD *v5; // rcx
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x50, (unsigned int)a2);
  v4 = v3;
  v5 = (_OWORD *)((char *)v3 + 28);
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    result = a2;
    *a2 = (struct winrt::impl::shared_hstring_header *)-28LL;
  }
  else
  {
    *v5 = *(_OWORD *)L"Windows.Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"on.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"cOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"on`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"rosoft.Windows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"indows.SemanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"emanticSearch.Tokenizer>";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"earch.Tokenizer>";
    result = a2;
    v5[9] = *(_OWORD *)L"kenizer>";
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180040ef0  mov     [rsp+arg_0], rbx
0x180040ef5  push    rdi
0x180040ef6  sub     rsp, 30h
0x180040efa  mov     ecx, 50h ; 'P'; this
0x180040eff  mov     rbx, rdx
0x180040f02  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180040f07  mov     rdi, rax
0x180040f0a  lea     rcx, [rax+1Ch]
0x180040f0e  test    rcx, rcx
0x180040f11  jnz     short loc_180040F36
0x180040f13  call    cs:__imp__errno
0x180040f19  mov     dword ptr [rax], 16h
0x180040f1f  call    cs:__imp__invalid_parameter_noinfo
0x180040f25  mov     rax, rbx
0x180040f28  mov     [rbx], rdi
0x180040f2b  mov     rbx, [rsp+38h+arg_0]
0x180040f30  add     rsp, 30h
0x180040f34  pop     rdi
0x180040f35  retn
0x180040f36  lea     rax, ??$name_v@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0FB@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x180040f3d  movups  xmm0, xmmword ptr [rax]
0x180040f40  movups  xmmword ptr [rcx], xmm0
0x180040f43  movups  xmm1, xmmword ptr [rax+10h]
0x180040f47  movups  xmmword ptr [rcx+10h], xmm1
0x180040f4b  movups  xmm0, xmmword ptr [rax+20h]
0x180040f4f  movups  xmmword ptr [rcx+20h], xmm0
0x180040f53  movups  xmm1, xmmword ptr [rax+30h]
0x180040f57  movups  xmmword ptr [rcx+30h], xmm1
0x180040f5b  movups  xmm0, xmmword ptr [rax+40h]
0x180040f5f  movups  xmmword ptr [rcx+40h], xmm0
0x180040f63  movups  xmm1, xmmword ptr [rax+50h]
0x180040f67  movups  xmmword ptr [rcx+50h], xmm1
0x180040f6b  movups  xmm0, xmmword ptr [rax+60h]
0x180040f6f  movups  xmmword ptr [rcx+60h], xmm0
0x180040f73  movups  xmm0, xmmword ptr [rax+70h]
0x180040f77  movups  xmmword ptr [rcx+70h], xmm0
0x180040f7b  movups  xmm1, xmmword ptr [rax+80h]
0x180040f82  movups  xmmword ptr [rcx+80h], xmm1
0x180040f89  movups  xmm0, xmmword ptr [rax+90h]
0x180040f90  mov     rax, rbx
0x180040f93  movups  xmmword ptr [rcx+90h], xmm0
0x180040f9a  mov     [rbx], rdi
0x180040f9d  mov     rbx, [rsp+38h+arg_0]
0x180040fa2  add     rsp, 30h
0x180040fa6  pop     rdi
0x180040fa7  retn
```
