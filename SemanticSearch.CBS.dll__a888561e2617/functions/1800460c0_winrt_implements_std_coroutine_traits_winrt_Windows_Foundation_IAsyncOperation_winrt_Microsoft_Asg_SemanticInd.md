# winrt::implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(void)

- ea: `0x1800460c0`
- end: `0x1800461a9`
- name: `?GetRuntimeClassName@?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingImageModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@567@@winrt@@EEBA?AUhstring@2@XZ`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x1800460c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800460e3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800460e3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800460ef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800460ef`

## string_xrefs

- `0x180046106`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x6E, (unsigned int)a2);
  v4 = v3;
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    result = a2;
    *a2 = (struct winrt::impl::shared_hstring_header *)-28LL;
  }
  else
  {
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric."
                                               "Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"on.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"cOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"on`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"rosoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"sg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"ticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L".AiFabric.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 172) = *(_OWORD *)L"c.Compatibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 188) = *(_OWORD *)L"ibility.IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 204) = *(_OWORD *)L"IImageEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 220) = *(_OWORD *)L"beddingsModel>";
    *(_QWORD *)((char *)v3 + 236) = *(_QWORD *)L"Model>";
    *((_DWORD *)v3 + 61) = *(_DWORD *)L"l>";
    result = a2;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800460c0  mov     [rsp+arg_0], rbx
0x1800460c5  push    rdi
0x1800460c6  sub     rsp, 30h
0x1800460ca  mov     ecx, 6Eh ; 'n'; this
0x1800460cf  mov     rbx, rdx
0x1800460d2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800460d7  mov     rdi, rax
0x1800460da  lea     r8, [rax+1Ch]
0x1800460de  test    r8, r8
0x1800460e1  jnz     short loc_180046106
0x1800460e3  call    cs:__imp__errno
0x1800460e9  mov     dword ptr [rax], 16h
0x1800460ef  call    cs:__imp__invalid_parameter_noinfo
0x1800460f5  mov     rax, rbx
0x1800460f8  mov     [rbx], rdi
0x1800460fb  mov     rbx, [rsp+38h+arg_0]
0x180046100  add     rsp, 30h
0x180046104  pop     rdi
0x180046105  retn
0x180046106  lea     rcx, ??$name_v@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0GP@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x18004610d  movups  xmm0, xmmword ptr [rcx]
0x180046110  lea     rcx, [rcx+80h]
0x180046117  movups  xmmword ptr [r8], xmm0
0x18004611b  movups  xmm1, xmmword ptr [rcx-70h]
0x18004611f  movups  xmmword ptr [r8+10h], xmm1
0x180046124  movups  xmm0, xmmword ptr [rcx-60h]
0x180046128  movups  xmmword ptr [r8+20h], xmm0
0x18004612d  movups  xmm1, xmmword ptr [rcx-50h]
0x180046131  movups  xmmword ptr [r8+30h], xmm1
0x180046136  movups  xmm0, xmmword ptr [rcx-40h]
0x18004613a  movups  xmmword ptr [r8+40h], xmm0
0x18004613f  movups  xmm1, xmmword ptr [rcx-30h]
0x180046143  movups  xmmword ptr [r8+50h], xmm1
0x180046148  movups  xmm0, xmmword ptr [rcx-20h]
0x18004614c  movups  xmmword ptr [r8+60h], xmm0
0x180046151  sub     r8, 0FFFFFFFFFFFFFF80h
0x180046155  movups  xmm0, xmmword ptr [rcx-10h]
0x180046159  movups  xmmword ptr [r8-10h], xmm0
0x18004615e  movups  xmm1, xmmword ptr [rcx]
0x180046161  movups  xmmword ptr [r8], xmm1
0x180046165  movups  xmm0, xmmword ptr [rcx+10h]
0x180046169  movups  xmmword ptr [r8+10h], xmm0
0x18004616e  movups  xmm1, xmmword ptr [rcx+20h]
0x180046172  movups  xmmword ptr [r8+20h], xmm1
0x180046177  movups  xmm0, xmmword ptr [rcx+30h]
0x18004617b  movups  xmmword ptr [r8+30h], xmm0
0x180046180  movups  xmm1, xmmword ptr [rcx+40h]
0x180046184  movups  xmmword ptr [r8+40h], xmm1
0x180046189  mov     rax, [rcx+50h]
0x18004618d  mov     [r8+50h], rax
0x180046191  mov     eax, [rcx+58h]
0x180046194  mov     [r8+58h], eax
0x180046198  mov     rax, rbx
0x18004619b  mov     [rbx], rdi
0x18004619e  mov     rbx, [rsp+38h+arg_0]
0x1800461a3  add     rsp, 30h
0x1800461a7  pop     rdi
0x1800461a8  retn
```
