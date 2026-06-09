# winrt::implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::GetRuntimeClassName(void)

- ea: `0x180015840`
- end: `0x1800158c8`
- name: `?GetRuntimeClassName@?$implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@Uhstring@winrt@@@5673@U?$IIterable@Uhstring@winrt@@@5673@@winrt@@EEBA?AUhstring@2@XZ`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004626`
- `0x180015840`
- `0x18001a0f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800158a6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800158a6`

## pseudocode

```c
char *__fastcall winrt::implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::GetRuntimeClassName(
        __int64 a1,
        char *a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  struct winrt::impl::shared_hstring_header *v7; // rdi
  _OWORD *v8; // rcx

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x30, a2);
  v7 = v3;
  v8 = (_OWORD *)((char *)v3 + 28);
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno(v8, v4, v5, v6) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *v8 = winrt::impl::name_v<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>;
    *(_OWORD *)((char *)v3 + 44) = xmmword_180023ED0;
    *(_OWORD *)((char *)v3 + 60) = xmmword_180023EE0;
    *(_OWORD *)((char *)v3 + 76) = xmmword_180023EF0;
    *(_OWORD *)((char *)v3 + 92) = xmmword_180023F00;
    *(_OWORD *)((char *)v3 + 108) = xmmword_180023F10;
  }
  *(_QWORD *)a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x180015840  mov     [rsp+arg_0], rbx
0x180015845  push    rdi
0x180015846  sub     rsp, 30h
0x18001584a  mov     ecx, 30h ; '0'; this
0x18001584f  mov     rbx, rdx
0x180015852  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180015857  mov     rdi, rax
0x18001585a  lea     rcx, [rax+1Ch]
0x18001585e  test    rcx, rcx
0x180015861  jz      short loc_1800158A6
0x180015863  movaps  xmm0, cs:??$name_v@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0DB@@std@@B; std::array<ushort,49> const winrt::impl::name_v<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>
0x18001586a  movups  xmmword ptr [rcx], xmm0
0x18001586d  movaps  xmm1, cs:xmmword_180023ED0
0x180015874  movups  xmmword ptr [rcx+10h], xmm1
0x180015878  movaps  xmm0, cs:xmmword_180023EE0
0x18001587f  movups  xmmword ptr [rcx+20h], xmm0
0x180015883  movaps  xmm1, cs:xmmword_180023EF0
0x18001588a  movups  xmmword ptr [rcx+30h], xmm1
0x18001588e  movaps  xmm0, cs:xmmword_180023F00
0x180015895  movups  xmmword ptr [rcx+40h], xmm0
0x180015899  movaps  xmm1, cs:xmmword_180023F10
0x1800158a0  movups  xmmword ptr [rcx+50h], xmm1
0x1800158a4  jmp     short loc_1800158B7
0x1800158a6  call    cs:__imp__o__errno
0x1800158ac  mov     dword ptr [rax], 16h
0x1800158b2  call    _invalid_parameter_noinfo
0x1800158b7  mov     [rbx], rdi
0x1800158ba  mov     rax, rbx
0x1800158bd  mov     rbx, [rsp+38h+arg_0]
0x1800158c2  add     rsp, 30h
0x1800158c6  pop     rdi
0x1800158c7  retn
```
