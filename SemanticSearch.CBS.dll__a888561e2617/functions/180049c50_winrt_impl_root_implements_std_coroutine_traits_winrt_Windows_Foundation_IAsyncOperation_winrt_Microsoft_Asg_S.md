# winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x180049c50`
- end: `0x180049d33`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingImageModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@567@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045ed0`

## callees

- `0x180001f60`
- `0x180049c50`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049c73`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180049c73`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180049c7f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180049c7f`

## string_xrefs

- `0x180049c8a`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel>`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>,winrt::Windows::Foundation::IAsyncInfo>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rbx
  __int64 result; // rax
  int v6[6]; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x6E, (unsigned int)a2);
    v4 = v3;
    if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabri"
                                                 "c.Compatibility.IImageEmbeddingsModel>";
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
    }
    *a2 = v4;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180049c50  mov     [rsp+arg_0], rbx
0x180049c55  push    rdi
0x180049c56  sub     rsp, 30h
0x180049c5a  mov     rdi, rdx
0x180049c5d  mov     ecx, 6Eh ; 'n'; this
0x180049c62  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180049c67  mov     rbx, rax
0x180049c6a  lea     r8, [rax+1Ch]
0x180049c6e  test    r8, r8
0x180049c71  jnz     short loc_180049C8A
0x180049c73  call    cs:__imp__errno
0x180049c79  mov     dword ptr [rax], 16h
0x180049c7f  call    cs:__imp__invalid_parameter_noinfo
0x180049c85  jmp     loc_180049D1C
0x180049c8a  lea     rcx, ??$name_v@U?$IAsyncOperation@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0GP@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x180049c91  movups  xmm0, xmmword ptr [rcx]
0x180049c94  movups  xmmword ptr [r8], xmm0
0x180049c98  movups  xmm1, xmmword ptr [rcx+10h]
0x180049c9c  movups  xmmword ptr [r8+10h], xmm1
0x180049ca1  movups  xmm0, xmmword ptr [rcx+20h]
0x180049ca5  movups  xmmword ptr [r8+20h], xmm0
0x180049caa  movups  xmm1, xmmword ptr [rcx+30h]
0x180049cae  movups  xmmword ptr [r8+30h], xmm1
0x180049cb3  movups  xmm0, xmmword ptr [rcx+40h]
0x180049cb7  movups  xmmword ptr [r8+40h], xmm0
0x180049cbc  movups  xmm1, xmmword ptr [rcx+50h]
0x180049cc0  movups  xmmword ptr [r8+50h], xmm1
0x180049cc5  movups  xmm0, xmmword ptr [rcx+60h]
0x180049cc9  movups  xmmword ptr [r8+60h], xmm0
0x180049cce  sub     r8, 0FFFFFFFFFFFFFF80h
0x180049cd2  movups  xmm0, xmmword ptr [rcx+70h]
0x180049cd6  movups  xmmword ptr [r8-10h], xmm0
0x180049cdb  lea     rcx, [rcx+80h]
0x180049ce2  movups  xmm1, xmmword ptr [rcx]
0x180049ce5  movups  xmmword ptr [r8], xmm1
0x180049ce9  movups  xmm0, xmmword ptr [rcx+10h]
0x180049ced  movups  xmmword ptr [r8+10h], xmm0
0x180049cf2  movups  xmm1, xmmword ptr [rcx+20h]
0x180049cf6  movups  xmmword ptr [r8+20h], xmm1
0x180049cfb  movups  xmm0, xmmword ptr [rcx+30h]
0x180049cff  movups  xmmword ptr [r8+30h], xmm0
0x180049d04  movups  xmm1, xmmword ptr [rcx+40h]
0x180049d08  movups  xmmword ptr [r8+40h], xmm1
0x180049d0d  mov     rax, [rcx+50h]
0x180049d11  mov     [r8+50h], rax
0x180049d15  mov     eax, [rcx+58h]
0x180049d18  mov     [r8+58h], eax
0x180049d1c  mov     [rdi], rbx
0x180049d1f  xor     eax, eax
0x180049d21  jmp     short loc_180049D27
0x180049d23  mov     eax, [rsp+38h+var_18]
0x180049d27  mov     rbx, [rsp+38h+arg_0]
0x180049d2c  add     rsp, 30h
0x180049d30  pop     rdi
0x180049d31  retn
```
