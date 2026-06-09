# winrt::impl::runtime_class_name<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,void>::get(void)

- ea: `0x180048ba0`
- end: `0x180048c78`
- name: `?get@?$runtime_class_name@UITextEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047df0`

## callees

- `0x180001f60`
- `0x180048ba0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048bc3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048bc3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048bcf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048bcf`

## string_xrefs

- `0x180048be6`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModelFactory`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::impl::runtime_class_name<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModelFactory,void>::get(
        struct winrt::impl::shared_hstring_header **a1,
        unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x4E, a2);
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
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.ITextEmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"EmbeddingsModelFactory";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"gsModelFactory";
    *(_QWORD *)((char *)v3 + 172) = *(_QWORD *)L"actory";
    *((_DWORD *)v3 + 45) = *(_DWORD *)L"ry";
    result = a1;
    *a1 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180048ba0  mov     [rsp+arg_0], rbx
0x180048ba5  push    rdi
0x180048ba6  sub     rsp, 30h
0x180048baa  mov     rbx, rcx
0x180048bad  mov     ecx, 4Eh ; 'N'; this
0x180048bb2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180048bb7  mov     rdi, rax
0x180048bba  lea     rcx, [rax+1Ch]
0x180048bbe  test    rcx, rcx
0x180048bc1  jnz     short loc_180048BE6
0x180048bc3  call    cs:__imp__errno
0x180048bc9  mov     dword ptr [rax], 16h
0x180048bcf  call    cs:__imp__invalid_parameter_noinfo
0x180048bd5  mov     rax, rbx
0x180048bd8  mov     [rbx], rdi
0x180048bdb  mov     rbx, [rsp+38h+arg_0]
0x180048be0  add     rsp, 30h
0x180048be4  pop     rdi
0x180048be5  retn
0x180048be6  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_6; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180048bed  movups  xmmword ptr [rcx], xmm0
0x180048bf0  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_6+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x180048bf7  movups  xmmword ptr [rcx+10h], xmm1
0x180048bfb  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_6+20h; "manticIndex.AiFabric.Compatibility.ITex"...
0x180048c02  movups  xmmword ptr [rcx+20h], xmm0
0x180048c06  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_6+30h; "dex.AiFabric.Compatibility.ITextEmbeddi"...
0x180048c0d  movups  xmmword ptr [rcx+30h], xmm1
0x180048c11  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_6+40h; "bric.Compatibility.ITextEmbeddingsModel"...
0x180048c18  movups  xmmword ptr [rcx+40h], xmm0
0x180048c1c  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_6+50h; "patibility.ITextEmbeddingsModelFactory"
0x180048c23  movups  xmmword ptr [rcx+50h], xmm1
0x180048c27  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_6+60h; "ty.ITextEmbeddingsModelFactory"
0x180048c2e  movups  xmmword ptr [rcx+60h], xmm0
0x180048c32  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_6+70h; "EmbeddingsModelFactory"
0x180048c39  movups  xmmword ptr [rcx+70h], xmm1
0x180048c3d  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_6+80h; "gsModelFactory"
0x180048c44  movups  xmmword ptr [rcx+80h], xmm0
0x180048c4b  movsd   xmm0, qword ptr cs:aMicrosoftAsgSe_6+90h; "actory"
0x180048c53  movsd   qword ptr [rcx+90h], xmm0
0x180048c5b  mov     eax, dword ptr cs:aMicrosoftAsgSe_6+98h; "ry"
0x180048c61  mov     [rcx+98h], eax
0x180048c67  mov     rax, rbx
0x180048c6a  mov     [rbx], rdi
0x180048c6d  mov     rbx, [rsp+38h+arg_0]
0x180048c72  add     rsp, 30h
0x180048c76  pop     rdi
0x180048c77  retn
```
