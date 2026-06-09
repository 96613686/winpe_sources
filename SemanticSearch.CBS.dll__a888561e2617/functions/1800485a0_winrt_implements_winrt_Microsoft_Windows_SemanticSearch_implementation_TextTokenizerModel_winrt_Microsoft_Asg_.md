# winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::TextTokenizerModel,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>::GetRuntimeClassName(void)

- ea: `0x1800485a0`
- end: `0x18004865c`
- name: `?GetRuntimeClassName@?$implements@UTextTokenizerModel@implementation@SemanticSearch@Windows@Microsoft@winrt@@UITextTokenizer@Compatibility@AiFabric@SemanticIndex@Asg@56@@winrt@@EEBA?AUhstring@2@XZ`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x1800485a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800485c3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800485c3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800485cf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800485cf`

## string_xrefs

- `0x1800485e6`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::TextTokenizerModel,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextTokenizer>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x41, (unsigned int)a2);
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
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.ITextTokenizer";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"Tokenizer";
    *((_WORD *)v3 + 78) = aMicrosoftAsgSe_9[64];
    result = a2;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800485a0  mov     [rsp+arg_0], rbx
0x1800485a5  push    rdi
0x1800485a6  sub     rsp, 30h
0x1800485aa  mov     ecx, 41h ; 'A'; this
0x1800485af  mov     rbx, rdx
0x1800485b2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800485b7  mov     rdi, rax
0x1800485ba  lea     rcx, [rax+1Ch]
0x1800485be  test    rcx, rcx
0x1800485c1  jnz     short loc_1800485E6
0x1800485c3  call    cs:__imp__errno
0x1800485c9  mov     dword ptr [rax], 16h
0x1800485cf  call    cs:__imp__invalid_parameter_noinfo
0x1800485d5  mov     rax, rbx
0x1800485d8  mov     [rbx], rdi
0x1800485db  mov     rbx, [rsp+38h+arg_0]
0x1800485e0  add     rsp, 30h
0x1800485e4  pop     rdi
0x1800485e5  retn
0x1800485e6  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_9; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800485ed  movups  xmmword ptr [rcx], xmm0
0x1800485f0  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_9+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x1800485f7  movups  xmmword ptr [rcx+10h], xmm1
0x1800485fb  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_9+20h; "manticIndex.AiFabric.Compatibility.ITex"...
0x180048602  movups  xmmword ptr [rcx+20h], xmm0
0x180048606  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_9+30h; "dex.AiFabric.Compatibility.ITextTokeniz"...
0x18004860d  movups  xmmword ptr [rcx+30h], xmm1
0x180048611  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_9+40h; "bric.Compatibility.ITextTokenizer"
0x180048618  movups  xmmword ptr [rcx+40h], xmm0
0x18004861c  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_9+50h; "patibility.ITextTokenizer"
0x180048623  movups  xmmword ptr [rcx+50h], xmm1
0x180048627  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe_9+60h; "ty.ITextTokenizer"
0x18004862e  movups  xmmword ptr [rcx+60h], xmm0
0x180048632  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe_9+70h; "Tokenizer"
0x180048639  movups  xmmword ptr [rcx+70h], xmm1
0x18004863d  movzx   eax, word ptr cs:aMicrosoftAsgSe_9+80h; "r"
0x180048644  mov     [rcx+80h], ax
0x18004864b  mov     rax, rbx
0x18004864e  mov     [rbx], rdi
0x180048651  mov     rbx, [rsp+38h+arg_0]
0x180048656  add     rsp, 30h
0x18004865a  pop     rdi
0x18004865b  retn
```
