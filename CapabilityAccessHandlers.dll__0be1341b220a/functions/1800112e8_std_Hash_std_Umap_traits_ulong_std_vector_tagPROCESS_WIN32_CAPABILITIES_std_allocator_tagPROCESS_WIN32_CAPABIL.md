# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::clear(void)

- ea: `0x1800112e8`
- end: `0x180011357`
- name: `?clear@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001032c`

## callees

- `0x18000fbbc`
- `0x18001001c`
- `0x180011188`
- `0x1800112e8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::clear(
        _QWORD *a1)
{
  __int64 *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a1[2] )
  {
    v2 = (__int64 *)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(
        a1,
        v2);
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v4 = a1[4];
      v5 = a1[3];
      v6 = a1[1];
      return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Unchecked_erase(
               a1,
               *v2,
               a1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800112e8  push    rbx
0x1800112ea  sub     rsp, 20h
0x1800112ee  cmp     qword ptr [rcx+10h], 0
0x1800112f3  mov     rbx, rcx
0x1800112f6  jz      short loc_180011351
0x1800112f8  mov     rax, [rcx+38h]
0x1800112fc  mov     rdx, [rcx+8]
0x180011300  shr     rax, 3
0x180011304  cmp     rax, [rcx+10h]
0x180011308  jbe     short loc_18001131A
0x18001130a  mov     r8, rdx
0x18001130d  mov     rdx, [rdx]
0x180011310  add     rsp, 20h
0x180011314  pop     rbx
0x180011315  jmp     ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *> *,std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *> * const)
0x18001131a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>>>(std::allocator<std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *>> &,std::_List_node<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>,void *> *)
0x18001131f  mov     rax, [rbx+8]
0x180011323  lea     r8, [rsp+28h+arg_0]
0x180011328  mov     [rax], rax
0x18001132b  mov     rax, [rbx+8]
0x18001132f  mov     [rax+8], rax
0x180011333  mov     qword ptr [rbx+10h], 0
0x18001133b  mov     rax, [rbx+8]
0x18001133f  mov     rdx, [rbx+20h]
0x180011343  mov     rcx, [rbx+18h]
0x180011347  mov     [rsp+28h+arg_0], rax
0x18001134c  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>>> const &)
0x180011351  add     rsp, 20h
0x180011355  pop     rbx
0x180011356  retn
```
