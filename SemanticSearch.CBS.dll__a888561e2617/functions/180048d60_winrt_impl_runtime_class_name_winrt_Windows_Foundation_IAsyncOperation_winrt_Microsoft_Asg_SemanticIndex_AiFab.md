# winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>,void>::get(void)

- ea: `0x180048d60`
- end: `0x180048e3b`
- name: `?get@?$runtime_class_name@U?$IAsyncOperation@UITextTokenizer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047610`
- `0x180049e30`

## callees

- `0x180001f60`
- `0x180048d60`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048d83`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048d83`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048d8f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048d8f`

## string_xrefs

- `0x180048da6`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>,void>::get(
        struct winrt::impl::shared_hstring_header **a1,
        unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x67, a2);
  v4 = v3;
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    result = a1;
    *a1 = (struct winrt::impl::shared_hstring_header *)-28LL;
  }
  else
  {
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric."
                                               "Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"on.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"cOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"on`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"rosoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"sg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"ticIndex.AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L".AiFabric.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 172) = *(_OWORD *)L"c.Compatibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 188) = *(_OWORD *)L"ibility.ITextTokenizer>";
    *(_OWORD *)((char *)v3 + 204) = *(_OWORD *)L"ITextTokenizer>";
    *(_QWORD *)((char *)v3 + 220) = *(_QWORD *)L"enizer>";
    *((_DWORD *)v3 + 57) = *(_DWORD *)L"er>";
    *((_WORD *)v3 + 116) = winrt::impl::name_v<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>>[102];
    result = a1;
    *a1 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180048d60  mov     [rsp+arg_0], rbx
0x180048d65  push    rdi
0x180048d66  sub     rsp, 30h
0x180048d6a  mov     rbx, rcx
0x180048d6d  mov     ecx, 67h ; 'g'; this
0x180048d72  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180048d77  mov     rdi, rax
0x180048d7a  lea     rdx, [rax+1Ch]
0x180048d7e  test    rdx, rdx
0x180048d81  jnz     short loc_180048DA6
0x180048d83  call    cs:__imp__errno
0x180048d89  mov     dword ptr [rax], 16h
0x180048d8f  call    cs:__imp__invalid_parameter_noinfo
0x180048d95  mov     rax, rbx
0x180048d98  mov     [rbx], rdi
0x180048d9b  mov     rbx, [rsp+38h+arg_0]
0x180048da0  add     rsp, 30h
0x180048da4  pop     rdi
0x180048da5  retn
0x180048da6  lea     rcx, ??$name_v@U?$IAsyncOperation@UITextTokenizer@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0GI@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x180048dad  movups  xmm0, xmmword ptr [rcx]
0x180048db0  lea     rcx, [rcx+80h]
0x180048db7  movups  xmmword ptr [rdx], xmm0
0x180048dba  movups  xmm1, xmmword ptr [rcx-70h]
0x180048dbe  movups  xmmword ptr [rdx+10h], xmm1
0x180048dc2  movups  xmm0, xmmword ptr [rcx-60h]
0x180048dc6  movups  xmmword ptr [rdx+20h], xmm0
0x180048dca  movups  xmm1, xmmword ptr [rcx-50h]
0x180048dce  movups  xmmword ptr [rdx+30h], xmm1
0x180048dd2  movups  xmm0, xmmword ptr [rcx-40h]
0x180048dd6  movups  xmmword ptr [rdx+40h], xmm0
0x180048dda  movups  xmm1, xmmword ptr [rcx-30h]
0x180048dde  movups  xmmword ptr [rdx+50h], xmm1
0x180048de2  movups  xmm0, xmmword ptr [rcx-20h]
0x180048de6  movups  xmmword ptr [rdx+60h], xmm0
0x180048dea  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180048dee  movups  xmm0, xmmword ptr [rcx-10h]
0x180048df2  movups  xmmword ptr [rdx-10h], xmm0
0x180048df6  movups  xmm1, xmmword ptr [rcx]
0x180048df9  movups  xmmword ptr [rdx], xmm1
0x180048dfc  movups  xmm0, xmmword ptr [rcx+10h]
0x180048e00  movups  xmmword ptr [rdx+10h], xmm0
0x180048e04  movups  xmm1, xmmword ptr [rcx+20h]
0x180048e08  movups  xmmword ptr [rdx+20h], xmm1
0x180048e0c  movups  xmm0, xmmword ptr [rcx+30h]
0x180048e10  movups  xmmword ptr [rdx+30h], xmm0
0x180048e14  mov     rax, [rcx+40h]
0x180048e18  mov     [rdx+40h], rax
0x180048e1c  mov     eax, [rcx+48h]
0x180048e1f  mov     [rdx+48h], eax
0x180048e22  movzx   eax, word ptr [rcx+4Ch]
0x180048e26  mov     [rdx+4Ch], ax
0x180048e2a  mov     rax, rbx
0x180048e2d  mov     [rbx], rdi
0x180048e30  mov     rbx, [rsp+38h+arg_0]
0x180048e35  add     rsp, 30h
0x180048e39  pop     rdi
0x180048e3a  retn
```
