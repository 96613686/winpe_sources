# winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IModelFactoryRegistrar>::GetRuntimeClassName(void)

- ea: `0x180045db0`
- end: `0x180045e7a`
- name: `?GetRuntimeClassName@?$implements@UAiFabricModelFactoryRegistrar@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIModelFactoryRegistrar@Compatibility@AiFabric@SemanticIndex@Asg@56@@winrt@@EEBA?AUhstring@2@XZ`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001f60`
- `0x180045db0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180045dd3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180045dd3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180045ddf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180045ddf`

## string_xrefs

- `0x180045df6`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IModelFactoryRegistrar`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::implements<winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactoryRegistrar,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IModelFactoryRegistrar>::GetRuntimeClassName(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  struct winrt::impl::shared_hstring_header *v4; // rdi
  struct winrt::impl::shared_hstring_header **result; // rax

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x49, (unsigned int)a2);
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
    *(_OWORD *)((char *)v3 + 28) = *(_OWORD *)L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 44) = *(_OWORD *)L"t.Asg.SemanticIndex.AiFabric.Compatibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 60) = *(_OWORD *)L"manticIndex.AiFabric.Compatibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 76) = *(_OWORD *)L"dex.AiFabric.Compatibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 92) = *(_OWORD *)L"bric.Compatibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 108) = *(_OWORD *)L"patibility.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 124) = *(_OWORD *)L"ty.IModelFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 140) = *(_OWORD *)L"lFactoryRegistrar";
    *(_OWORD *)((char *)v3 + 156) = *(_OWORD *)L"Registrar";
    *((_WORD *)v3 + 86) = aMicrosoftAsgSe[72];
    result = a2;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180045db0  mov     [rsp+arg_0], rbx
0x180045db5  push    rdi
0x180045db6  sub     rsp, 30h
0x180045dba  mov     ecx, 49h ; 'I'; this
0x180045dbf  mov     rbx, rdx
0x180045dc2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180045dc7  mov     rdi, rax
0x180045dca  lea     rcx, [rax+1Ch]
0x180045dce  test    rcx, rcx
0x180045dd1  jnz     short loc_180045DF6
0x180045dd3  call    cs:__imp__errno
0x180045dd9  mov     dword ptr [rax], 16h
0x180045ddf  call    cs:__imp__invalid_parameter_noinfo
0x180045de5  mov     rax, rbx
0x180045de8  mov     [rbx], rdi
0x180045deb  mov     rbx, [rsp+38h+arg_0]
0x180045df0  add     rsp, 30h
0x180045df4  pop     rdi
0x180045df5  retn
0x180045df6  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180045dfd  movups  xmmword ptr [rcx], xmm0
0x180045e00  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe+10h; "t.Asg.SemanticIndex.AiFabric.Compatibil"...
0x180045e07  movups  xmmword ptr [rcx+10h], xmm1
0x180045e0b  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe+20h; "manticIndex.AiFabric.Compatibility.IMod"...
0x180045e12  movups  xmmword ptr [rcx+20h], xmm0
0x180045e16  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe+30h; "dex.AiFabric.Compatibility.IModelFactor"...
0x180045e1d  movups  xmmword ptr [rcx+30h], xmm1
0x180045e21  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe+40h; "bric.Compatibility.IModelFactoryRegistr"...
0x180045e28  movups  xmmword ptr [rcx+40h], xmm0
0x180045e2c  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe+50h; "patibility.IModelFactoryRegistrar"
0x180045e33  movups  xmmword ptr [rcx+50h], xmm1
0x180045e37  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe+60h; "ty.IModelFactoryRegistrar"
0x180045e3e  movups  xmmword ptr [rcx+60h], xmm0
0x180045e42  movaps  xmm1, xmmword ptr cs:aMicrosoftAsgSe+70h; "lFactoryRegistrar"
0x180045e49  movups  xmmword ptr [rcx+70h], xmm1
0x180045e4d  movaps  xmm0, xmmword ptr cs:aMicrosoftAsgSe+80h; "Registrar"
0x180045e54  movups  xmmword ptr [rcx+80h], xmm0
0x180045e5b  movzx   eax, word ptr cs:aMicrosoftAsgSe+90h; "r"
0x180045e62  mov     [rcx+90h], ax
0x180045e69  mov     rax, rbx
0x180045e6c  mov     [rbx], rdi
0x180045e6f  mov     rbx, [rsp+38h+arg_0]
0x180045e74  add     rsp, 30h
0x180045e78  pop     rdi
0x180045e79  retn
```
