# winrt::impl::runtime_class_name<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel,void>::get(void)

- ea: `0x180048ac0`
- end: `0x180048b98`
- name: `?get@?$runtime_class_name@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@X@impl@winrt@@SA?AUhstring@3@XZ`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180047f30`

## callees

- `0x180001f60`
- `0x180048ac0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048ae3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180048ae3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048aef`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180048aef`

## string_xrefs

- `0x180048b06`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::impl::runtime_class_name<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel,void>::get(
        struct winrt::impl::shared_hstring_header **a1,
        unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x47, a2);
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
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.ITextEmbeddingsModel";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"EmbeddingsModel";
    *(_QWORD *)((char *)v3 + 156) = *(_QWORD *)L"gsModel";
    *((_DWORD *)v3 + 41) = *(_DWORD *)L"del";
    *((_WORD *)v3 + 84) = aMicrosoftAsgSe_7[70];
    result = a1;
    *a1 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180048ac0  mov     [rsp+arg_0], rbx
0x180048ac5  push    rdi
0x180048ac6  sub     rsp, 30h
0x180048aca  mov     rbx, rcx
0x180048acd  mov     ecx, 47h ; 'G'; this
0x180048ad2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180048ad7  mov     rdi, rax
0x180048ada  lea     rcx, [rax+1Ch]
0x180048ade  test    rcx, rcx
0x180048ae1  jnz     short loc_180048B06
0x180048ae3  call    cs:__imp__errno
0x180048ae9  mov     dword ptr [rax], 16h
0x180048aef  call    cs:__imp__invalid_parameter_noinfo
0x180048af5  mov     rax, rbx
0x180048af8  mov     [rbx], rdi
0x180048afb  mov     rbx, [rsp+38h+arg_0]
0x180048b00  add     rsp, 30h
0x180048b04  pop     rdi
0x180048b05  retn
0x180048b06  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_7; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180048b0d  movups  xmmword ptr [rcx], xmm0
0x180048b10  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_7+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x180048b17  movups  xmmword ptr [rcx+10h], xmm1
0x180048b1b  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_7+20h; "manticIndex.AiFabric.Compatibility.ITex"...
0x180048b22  movups  xmmword ptr [rcx+20h], xmm0
0x180048b26  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_7+30h; "dex.AiFabric.Compatibility.ITextEmbeddi"...
0x180048b2d  movups  xmmword ptr [rcx+30h], xmm1
0x180048b31  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_7+40h; "bric.Compatibility.ITextEmbeddingsModel"
0x180048b38  movups  xmmword ptr [rcx+40h], xmm0
0x180048b3c  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_7+50h; "patibility.ITextEmbeddingsModel"
0x180048b43  movups  xmmword ptr [rcx+50h], xmm1
0x180048b47  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_7+60h; "ty.ITextEmbeddingsModel"
0x180048b4e  movups  xmmword ptr [rcx+60h], xmm0
0x180048b52  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_7+70h; "EmbeddingsModel"
0x180048b59  movups  xmmword ptr [rcx+70h], xmm1
0x180048b5d  movsd   xmm0, qword ptr cs:aMicrosoftAsgSe_7+80h; "gsModel"
0x180048b65  movsd   qword ptr [rcx+80h], xmm0
0x180048b6d  mov     eax, dword ptr cs:aMicrosoftAsgSe_7+88h; "del"
0x180048b73  mov     [rcx+88h], eax
0x180048b79  movzx   eax, word ptr cs:aMicrosoftAsgSe_7+8Ch; "l"
0x180048b80  mov     [rcx+8Ch], ax
0x180048b87  mov     rax, rbx
0x180048b8a  mov     [rbx], rdi
0x180048b8d  mov     rbx, [rsp+38h+arg_0]
0x180048b92  add     rsp, 30h
0x180048b96  pop     rdi
0x180048b97  retn
```
