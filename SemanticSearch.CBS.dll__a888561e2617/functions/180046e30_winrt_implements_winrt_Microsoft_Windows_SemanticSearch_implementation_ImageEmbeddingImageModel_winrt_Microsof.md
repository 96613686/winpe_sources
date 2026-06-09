# winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModel,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>::GetRuntimeClassName(void)

- ea: `0x180046e30`
- end: `0x180046eec`
- name: `?GetRuntimeClassName@?$implements@UImageEmbeddingImageModel@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@56@@winrt@@EEBA?AUhstring@2@XZ`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x180046e30`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180046e53`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180046e53`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180046e5f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180046e5f`

## string_xrefs

- `0x180046e76`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModel,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModel>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x48, (unsigned int)a2);
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *_errno() = 22;
    _invalid_parameter_noinfo();
    result = a2;
    *a2 = (struct winrt::impl::shared_hstring_header *)-28LL;
  }
  else
  {
    result = a2;
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.IImageEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"eEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"ngsModel";
    *a2 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x180046e30  mov     [rsp+arg_0], rbx
0x180046e35  push    rdi
0x180046e36  sub     rsp, 30h
0x180046e3a  mov     ecx, 48h ; 'H'; this
0x180046e3f  mov     rbx, rdx
0x180046e42  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180046e47  mov     rdi, rax
0x180046e4a  lea     rcx, [rax+1Ch]
0x180046e4e  test    rcx, rcx
0x180046e51  jnz     short loc_180046E76
0x180046e53  call    cs:__imp__errno
0x180046e59  mov     dword ptr [rax], 16h
0x180046e5f  call    cs:__imp__invalid_parameter_noinfo
0x180046e65  mov     rax, rbx
0x180046e68  mov     [rbx], rdi
0x180046e6b  mov     rbx, [rsp+38h+arg_0]
0x180046e70  add     rsp, 30h
0x180046e74  pop     rdi
0x180046e75  retn
0x180046e76  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_14; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180046e7d  mov     rax, rbx
0x180046e80  movups  xmmword ptr [rcx], xmm0
0x180046e83  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_14+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x180046e8a  movups  xmmword ptr [rcx+10h], xmm1
0x180046e8e  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_14+20h; "manticIndex.AiFabric.Compatibility.IIma"...
0x180046e95  movups  xmmword ptr [rcx+20h], xmm0
0x180046e99  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_14+30h; "dex.AiFabric.Compatibility.IImageEmbedd"...
0x180046ea0  movups  xmmword ptr [rcx+30h], xmm1
0x180046ea4  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_14+40h; "bric.Compatibility.IImageEmbeddingsMode"...
0x180046eab  movups  xmmword ptr [rcx+40h], xmm0
0x180046eaf  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_14+50h; "patibility.IImageEmbeddingsModel"
0x180046eb6  movups  xmmword ptr [rcx+50h], xmm1
0x180046eba  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_14+60h; "ty.IImageEmbeddingsModel"
0x180046ec1  movups  xmmword ptr [rcx+60h], xmm0
0x180046ec5  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_14+70h; "eEmbeddingsModel"
0x180046ecc  movups  xmmword ptr [rcx+70h], xmm1
0x180046ed0  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_14+80h; "ngsModel"
0x180046ed7  movups  xmmword ptr [rcx+80h], xmm0
0x180046ede  mov     [rbx], rdi
0x180046ee1  mov     rbx, [rsp+38h+arg_0]
0x180046ee6  add     rsp, 30h
0x180046eea  pop     rdi
0x180046eeb  retn
```
