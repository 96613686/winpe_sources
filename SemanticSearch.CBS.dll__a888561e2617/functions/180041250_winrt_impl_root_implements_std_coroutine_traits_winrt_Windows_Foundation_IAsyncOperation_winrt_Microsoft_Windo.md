# winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x180041250`
- end: `0x1800412ff`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@@std@@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@567@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180040d00`

## callees

- `0x180001f60`
- `0x180041250`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180041273`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180041273`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004127f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18004127f`

## string_xrefs

- `0x180041287`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::guid>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx
  __int64 result; // rax
  _DWORD v5[6]; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x50, (unsigned int)a2);
    if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Windows.Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"Foundation.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"on.IAsyncOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"cOperation`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"on`1<Microsoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"rosoft.Windows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"indows.SemanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"emanticSearch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"earch.Tokenizer>";
      *(_OWORD *)((char *)v3 + 172) = *(_OWORD *)L"kenizer>";
    }
    *a2 = v3;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(v5);
  }
  return result;
}

```

## disassembly

```asm
0x180041250  mov     [rsp+arg_0], rbx
0x180041255  push    rdi
0x180041256  sub     rsp, 30h
0x18004125a  mov     rdi, rdx
0x18004125d  mov     ecx, 50h ; 'P'; this
0x180041262  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180041267  mov     rbx, rax
0x18004126a  lea     rcx, [rax+1Ch]
0x18004126e  test    rcx, rcx
0x180041271  jnz     short loc_180041287
0x180041273  call    cs:__imp__errno
0x180041279  mov     dword ptr [rax], 16h
0x18004127f  call    cs:__imp__invalid_parameter_noinfo
0x180041285  jmp     short loc_1800412E8
0x180041287  lea     rax, ??$name_v@U?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0FB@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x18004128e  movups  xmm0, xmmword ptr [rax]
0x180041291  movups  xmmword ptr [rcx], xmm0
0x180041294  movups  xmm1, xmmword ptr [rax+10h]
0x180041298  movups  xmmword ptr [rcx+10h], xmm1
0x18004129c  movups  xmm0, xmmword ptr [rax+20h]
0x1800412a0  movups  xmmword ptr [rcx+20h], xmm0
0x1800412a4  movups  xmm1, xmmword ptr [rax+30h]
0x1800412a8  movups  xmmword ptr [rcx+30h], xmm1
0x1800412ac  movups  xmm0, xmmword ptr [rax+40h]
0x1800412b0  movups  xmmword ptr [rcx+40h], xmm0
0x1800412b4  movups  xmm1, xmmword ptr [rax+50h]
0x1800412b8  movups  xmmword ptr [rcx+50h], xmm1
0x1800412bc  movups  xmm0, xmmword ptr [rax+60h]
0x1800412c0  movups  xmmword ptr [rcx+60h], xmm0
0x1800412c4  movups  xmm0, xmmword ptr [rax+70h]
0x1800412c8  movups  xmmword ptr [rcx+70h], xmm0
0x1800412cc  movups  xmm1, xmmword ptr [rax+80h]
0x1800412d3  movups  xmmword ptr [rcx+80h], xmm1
0x1800412da  movups  xmm0, xmmword ptr [rax+90h]
0x1800412e1  movups  xmmword ptr [rcx+90h], xmm0
0x1800412e8  mov     [rdi], rbx
0x1800412eb  xor     eax, eax
0x1800412ed  jmp     short loc_1800412F3
0x1800412ef  mov     eax, [rsp+38h+var_18]
0x1800412f3  mov     rbx, [rsp+38h+arg_0]
0x1800412f8  add     rsp, 30h
0x1800412fc  pop     rdi
0x1800412fd  retn
```
