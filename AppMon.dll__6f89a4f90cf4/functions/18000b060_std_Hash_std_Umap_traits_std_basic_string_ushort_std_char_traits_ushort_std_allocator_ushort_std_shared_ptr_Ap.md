# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>(std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>> const &)

- ea: `0x18000b060`
- end: `0x18000b0ce`
- name: `??0?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEAA@AEBV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@1@@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b0d4`

## callees

- `0x180006378`
- `0x180009960`
- `0x18000d4dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>(
        __int64 a1,
        _DWORD *a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rcx

  *(_DWORD *)a1 = *a2;
  v3 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::_Alloc_sentinel_and_proxy(a1 + 8);
  std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>(a1 + 24);
  *(_QWORD *)(a1 + 48) = 7;
  *(_QWORD *)(a1 + 56) = 8;
  *(_DWORD *)a1 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v4,
    16,
    *v3);
  return a1;
}

```

## disassembly

```asm
0x18000b060  mov     [rsp+arg_8], rbx
0x18000b065  mov     [rsp+arg_0], rcx
0x18000b06a  push    rdi
0x18000b06b  sub     rsp, 20h
0x18000b06f  mov     rdi, rcx
0x18000b072  mov     eax, [rdx]
0x18000b074  mov     [rcx], eax
0x18000b076  lea     rbx, [rcx+8]
0x18000b07a  mov     qword ptr [rbx], 0
0x18000b081  mov     qword ptr [rbx+8], 0
0x18000b089  mov     rcx, rbx
0x18000b08c  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>::_Alloc_sentinel_and_proxy(void)
0x18000b091  nop
0x18000b092  lea     rcx, [rdi+18h]
0x18000b096  call    ??0?$vector@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@V?$allocator@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>::vector<std::shared_ptr<AppMon::AppPrinterEndPointBase>>(void)
0x18000b09b  nop
0x18000b09c  mov     qword ptr [rdi+30h], 7
0x18000b0a4  mov     qword ptr [rdi+38h], 8
0x18000b0ac  mov     dword ptr [rdi], 3F800000h
0x18000b0b2  mov     r8, [rbx]
0x18000b0b5  mov     edx, 10h
0x18000b0ba  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18000b0bf  nop
0x18000b0c0  mov     rax, rdi
0x18000b0c3  mov     rbx, [rsp+28h+arg_8]
0x18000b0c8  add     rsp, 20h
0x18000b0cc  pop     rdi
0x18000b0cd  retn
```
