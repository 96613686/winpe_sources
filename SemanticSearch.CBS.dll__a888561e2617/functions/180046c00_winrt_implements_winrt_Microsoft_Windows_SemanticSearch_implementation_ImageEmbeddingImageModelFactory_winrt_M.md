# winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::GetRuntimeClassName(void)

- ea: `0x180046c00`
- end: `0x180046ce6`
- name: `?GetRuntimeClassName@?$implements@UImageEmbeddingImageModelFactory@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIImageEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@56@UIEmbeddingsModelFactory@89SemanticIndex@Asg@56@@winrt@@EEBA?AUhstring@2@XZ`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x180046c00`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180046c23`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180046c23`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180046c2f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180046c2f`

## string_xrefs

- `0x180046c46`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModelFactory`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingImageModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsModelFactory,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x4F, (unsigned int)a2);
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
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.IImageEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"eEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"ngsModelFactory";
    *(_QWORD *)((char *)v3 + 172) = *(_QWORD *)L"Factory";
    *((_DWORD *)v3 + 45) = *(_DWORD *)L"ory";
    *((_WORD *)v3 + 92) = aMicrosoftAsgSe_1[78];
    result = a2;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180046c00  mov     [rsp+arg_0], rbx
0x180046c05  push    rdi
0x180046c06  sub     rsp, 30h
0x180046c0a  mov     ecx, 4Fh ; 'O'; this
0x180046c0f  mov     rbx, rdx
0x180046c12  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180046c17  mov     rdi, rax
0x180046c1a  lea     rcx, [rax+1Ch]
0x180046c1e  test    rcx, rcx
0x180046c21  jnz     short loc_180046C46
0x180046c23  call    cs:__imp__errno
0x180046c29  mov     dword ptr [rax], 16h
0x180046c2f  call    cs:__imp__invalid_parameter_noinfo
0x180046c35  mov     rax, rbx
0x180046c38  mov     [rbx], rdi
0x180046c3b  mov     rbx, [rsp+38h+arg_0]
0x180046c40  add     rsp, 30h
0x180046c44  pop     rdi
0x180046c45  retn
0x180046c46  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_1; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180046c4d  movups  xmmword ptr [rcx], xmm0
0x180046c50  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_1+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x180046c57  movups  xmmword ptr [rcx+10h], xmm1
0x180046c5b  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_1+20h; "manticIndex.AiFabric.Compatibility.IIma"...
0x180046c62  movups  xmmword ptr [rcx+20h], xmm0
0x180046c66  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_1+30h; "dex.AiFabric.Compatibility.IImageEmbedd"...
0x180046c6d  movups  xmmword ptr [rcx+30h], xmm1
0x180046c71  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_1+40h; "bric.Compatibility.IImageEmbeddingsMode"...
0x180046c78  movups  xmmword ptr [rcx+40h], xmm0
0x180046c7c  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_1+50h; "patibility.IImageEmbeddingsModelFactory"
0x180046c83  movups  xmmword ptr [rcx+50h], xmm1
0x180046c87  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_1+60h; "ty.IImageEmbeddingsModelFactory"
0x180046c8e  movups  xmmword ptr [rcx+60h], xmm0
0x180046c92  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_1+70h; "eEmbeddingsModelFactory"
0x180046c99  movups  xmmword ptr [rcx+70h], xmm1
0x180046c9d  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_1+80h; "ngsModelFactory"
0x180046ca4  movups  xmmword ptr [rcx+80h], xmm0
0x180046cab  movsd   xmm0, qword ptr cs:aMicrosoftAsgSe_1+90h; "Factory"
0x180046cb3  movsd   qword ptr [rcx+90h], xmm0
0x180046cbb  mov     eax, dword ptr cs:aMicrosoftAsgSe_1+98h; "ory"
0x180046cc1  mov     [rcx+98h], eax
0x180046cc7  movzx   eax, word ptr cs:aMicrosoftAsgSe_1+9Ch; "y"
0x180046cce  mov     [rcx+9Ch], ax
0x180046cd5  mov     rax, rbx
0x180046cd8  mov     [rbx], rdi
0x180046cdb  mov     rbx, [rsp+38h+arg_0]
0x180046ce0  add     rsp, 30h
0x180046ce4  pop     rdi
0x180046ce5  retn
```
