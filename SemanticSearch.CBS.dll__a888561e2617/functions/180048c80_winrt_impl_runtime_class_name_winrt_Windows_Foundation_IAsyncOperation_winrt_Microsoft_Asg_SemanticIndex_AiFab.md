# winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,void>::get(void)

- ea: `0x180048c80`
- end: `0x180048d5d`
- name: `?get@?$runtime_class_name@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047980`
- `0x180049e60`

## callees

- `0x180001f60`
- `0x180048c80`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048ca3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048ca3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048caf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048caf`

## string_xrefs

- `0x180048cc6`: `Windows.Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::impl::runtime_class_name<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,void>::get(
        struct winrt::impl::shared_hstring_header **a1,
        unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x6D, a2);
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
                                               "Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"Foundation.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"on.IAsyncOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"cOperation`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"on`1<Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"rosoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"sg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"ticIndex.AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L".AiFabric.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 172) = *(_OWORD *)L"c.Compatibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 188) = *(_OWORD *)L"ibility.ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 204) = *(_OWORD *)L"ITextEmbeddingsModel>";
    *(_OWORD *)((char *)v3 + 220) = *(_OWORD *)L"eddingsModel>";
    *(_QWORD *)((char *)v3 + 236) = *(_QWORD *)L"odel>";
    *((_WORD *)v3 + 122) = winrt::impl::name_v<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>>[108];
    result = a1;
    *a1 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180048c80  mov     [rsp+arg_0], rbx
0x180048c85  push    rdi
0x180048c86  sub     rsp, 30h
0x180048c8a  mov     rbx, rcx
0x180048c8d  mov     ecx, 6Dh ; 'm'; this
0x180048c92  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180048c97  mov     rdi, rax
0x180048c9a  lea     rdx, [rax+1Ch]
0x180048c9e  test    rdx, rdx
0x180048ca1  jnz     short loc_180048CC6
0x180048ca3  call    cs:__imp__errno
0x180048ca9  mov     dword ptr [rax], 16h
0x180048caf  call    cs:__imp__invalid_parameter_noinfo
0x180048cb5  mov     rax, rbx
0x180048cb8  mov     [rbx], rdi
0x180048cbb  mov     rbx, [rsp+38h+arg_0]
0x180048cc0  add     rsp, 30h
0x180048cc4  pop     rdi
0x180048cc5  retn
0x180048cc6  lea     rcx, ??$name_v@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@_W$0GO@@std@@B; "Windows.Foundation.IAsyncOperation`1<Mi"...
0x180048ccd  movups  xmm0, xmmword ptr [rcx]
0x180048cd0  lea     rcx, [rcx+80h]
0x180048cd7  movups  xmmword ptr [rdx], xmm0
0x180048cda  movups  xmm1, xmmword ptr [rcx-70h]
0x180048cde  movups  xmmword ptr [rdx+10h], xmm1
0x180048ce2  movups  xmm0, xmmword ptr [rcx-60h]
0x180048ce6  movups  xmmword ptr [rdx+20h], xmm0
0x180048cea  movups  xmm1, xmmword ptr [rcx-50h]
0x180048cee  movups  xmmword ptr [rdx+30h], xmm1
0x180048cf2  movups  xmm0, xmmword ptr [rcx-40h]
0x180048cf6  movups  xmmword ptr [rdx+40h], xmm0
0x180048cfa  movups  xmm1, xmmword ptr [rcx-30h]
0x180048cfe  movups  xmmword ptr [rdx+50h], xmm1
0x180048d02  movups  xmm0, xmmword ptr [rcx-20h]
0x180048d06  movups  xmmword ptr [rdx+60h], xmm0
0x180048d0a  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180048d0e  movups  xmm0, xmmword ptr [rcx-10h]
0x180048d12  movups  xmmword ptr [rdx-10h], xmm0
0x180048d16  movups  xmm1, xmmword ptr [rcx]
0x180048d19  movups  xmmword ptr [rdx], xmm1
0x180048d1c  movups  xmm0, xmmword ptr [rcx+10h]
0x180048d20  movups  xmmword ptr [rdx+10h], xmm0
0x180048d24  movups  xmm1, xmmword ptr [rcx+20h]
0x180048d28  movups  xmmword ptr [rdx+20h], xmm1
0x180048d2c  movups  xmm0, xmmword ptr [rcx+30h]
0x180048d30  movups  xmmword ptr [rdx+30h], xmm0
0x180048d34  movups  xmm1, xmmword ptr [rcx+40h]
0x180048d38  movups  xmmword ptr [rdx+40h], xmm1
0x180048d3c  mov     rax, [rcx+50h]
0x180048d40  mov     [rdx+50h], rax
0x180048d44  movzx   eax, word ptr [rcx+58h]
0x180048d48  mov     [rdx+58h], ax
0x180048d4c  mov     rax, rbx
0x180048d4f  mov     [rbx], rdi
0x180048d52  mov     rbx, [rsp+38h+arg_0]
0x180048d57  add     rsp, 30h
0x180048d5b  pop     rdi
0x180048d5c  retn
```
