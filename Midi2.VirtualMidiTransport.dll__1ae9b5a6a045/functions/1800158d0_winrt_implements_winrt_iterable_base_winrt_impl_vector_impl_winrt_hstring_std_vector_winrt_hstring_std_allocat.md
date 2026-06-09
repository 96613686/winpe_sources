# winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetRuntimeClassName(void)

- ea: `0x1800158d0`
- end: `0x180015961`
- name: `?GetRuntimeClassName@?$implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@winrt@@EEBA?AUhstring@2@XZ`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004626`
- `0x1800158d0`
- `0x18001a0f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001593f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001593f`

## pseudocode

```c
char *__fastcall winrt::implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::GetRuntimeClassName(
        __int64 a1,
        char *a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  struct winrt::impl::shared_hstring_header *v7; // rdi
  _OWORD *v8; // rcx

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x32, a2);
  v7 = v3;
  v8 = (_OWORD *)((char *)v3 + 28);
  if ( v3 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno(v8, v4, v5, v6) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *v8 = winrt::impl::name_v<winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>;
    *(_OWORD *)((char *)v3 + 44) = xmmword_180023F40;
    *(_OWORD *)((char *)v3 + 60) = xmmword_180023F50;
    *(_OWORD *)((char *)v3 + 76) = xmmword_180023F60;
    *(_OWORD *)((char *)v3 + 92) = xmmword_180023F70;
    *(_OWORD *)((char *)v3 + 108) = xmmword_180023F80;
    *((_DWORD *)v3 + 31) = 4063335;
  }
  *(_QWORD *)a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x1800158d0  mov     [rsp+arg_0], rbx
0x1800158d5  push    rdi
0x1800158d6  sub     rsp, 30h
0x1800158da  mov     ecx, 32h ; '2'; this
0x1800158df  mov     rbx, rdx
0x1800158e2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800158e7  mov     rdi, rax
0x1800158ea  lea     rcx, [rax+1Ch]
0x1800158ee  test    rcx, rcx
0x1800158f1  jz      short loc_18001593F
0x1800158f3  movaps  xmm0, cs:??$name_v@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0DD@@std@@B; std::array<ushort,51> const winrt::impl::name_v<winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>
0x1800158fa  movups  xmmword ptr [rcx], xmm0
0x1800158fd  movaps  xmm1, cs:xmmword_180023F40
0x180015904  movups  xmmword ptr [rcx+10h], xmm1
0x180015908  movaps  xmm0, cs:xmmword_180023F50
0x18001590f  movups  xmmword ptr [rcx+20h], xmm0
0x180015913  movaps  xmm1, cs:xmmword_180023F60
0x18001591a  movups  xmmword ptr [rcx+30h], xmm1
0x18001591e  movaps  xmm0, cs:xmmword_180023F70
0x180015925  movups  xmmword ptr [rcx+40h], xmm0
0x180015929  movaps  xmm1, cs:xmmword_180023F80
0x180015930  movups  xmmword ptr [rcx+50h], xmm1
0x180015934  mov     eax, cs:dword_180023F90
0x18001593a  mov     [rcx+60h], eax
0x18001593d  jmp     short loc_180015950
0x18001593f  call    cs:__imp__o__errno
0x180015945  mov     dword ptr [rax], 16h
0x18001594b  call    _invalid_parameter_noinfo
0x180015950  mov     [rbx], rdi
0x180015953  mov     rax, rbx
0x180015956  mov     rbx, [rsp+38h+arg_0]
0x18001595b  add     rsp, 30h
0x18001595f  pop     rdi
0x180015960  retn
```
