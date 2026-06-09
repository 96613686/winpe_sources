# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x18000b474`
- end: `0x18000b4eb`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bafc`
- `0x18000d96c`
- `0x18000fa2c`

## callees

- `0x180008594`
- `0x18000aac0`
- `0x18000b474`
- `0x18000dccc`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Clear_guard::~_Clear_guard(
        _QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)*a1;
  if ( *a1 && v1[2] )
  {
    v2 = (_QWORD *)v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(
        a1,
        v2);
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8LL) = v1[1];
      v1[2] = 0;
      v4 = v1[4];
      v5 = v1[3];
      v6 = v1[1];
      return std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Unchecked_erase(
               *a1,
               *v2,
               v1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b474  push    rbx
0x18000b476  sub     rsp, 20h
0x18000b47a  mov     rbx, [rcx]
0x18000b47d  test    rbx, rbx
0x18000b480  jz      short loc_18000B4E5
0x18000b482  cmp     qword ptr [rbx+10h], 0
0x18000b487  jz      short loc_18000B4E5
0x18000b489  mov     rax, [rbx+38h]
0x18000b48d  mov     rdx, [rbx+8]
0x18000b491  shr     rax, 3
0x18000b495  cmp     rax, [rbx+10h]
0x18000b499  jbe     short loc_18000B4AE
0x18000b49b  mov     r8, rdx
0x18000b49e  mov     rcx, rbx
0x18000b4a1  mov     rdx, [rdx]
0x18000b4a4  add     rsp, 20h
0x18000b4a8  pop     rbx
0x18000b4a9  jmp     ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *,std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> * const)
0x18000b4ae  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *>> &,std::_List_node<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *)
0x18000b4b3  mov     rax, [rbx+8]
0x18000b4b7  lea     r8, [rsp+28h+arg_0]
0x18000b4bc  mov     [rax], rax
0x18000b4bf  mov     rax, [rbx+8]
0x18000b4c3  mov     [rax+8], rax
0x18000b4c7  mov     qword ptr [rbx+10h], 0
0x18000b4cf  mov     rax, [rbx+8]
0x18000b4d3  mov     rdx, [rbx+20h]
0x18000b4d7  mov     rcx, [rbx+18h]
0x18000b4db  mov     [rsp+28h+arg_0], rax
0x18000b4e0  call    ??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> const &)
0x18000b4e5  add     rsp, 20h
0x18000b4e9  pop     rbx
0x18000b4ea  retn
```
