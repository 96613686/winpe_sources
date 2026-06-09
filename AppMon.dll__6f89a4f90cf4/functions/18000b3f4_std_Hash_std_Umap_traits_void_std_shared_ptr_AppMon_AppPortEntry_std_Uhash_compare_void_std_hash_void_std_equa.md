# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x18000b3f4`
- end: `0x18000b46b`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d7d8`

## callees

- `0x180008594`
- `0x18000aaf8`
- `0x18000b3f4`
- `0x18000db9c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Clear_guard::~_Clear_guard(
        __int64 **a1)
{
  __int64 *v1; // rbx
  __int64 *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (__int64 *)v1[1];
    if ( (unsigned __int64)v1[7] >> 3 <= v1[2] )
    {
      std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(
        a1,
        v2);
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
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
      return std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Unchecked_erase(
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
0x18000b3f4  push    rbx
0x18000b3f6  sub     rsp, 20h
0x18000b3fa  mov     rbx, [rcx]
0x18000b3fd  test    rbx, rbx
0x18000b400  jz      short loc_18000B465
0x18000b402  cmp     qword ptr [rbx+10h], 0
0x18000b407  jz      short loc_18000B465
0x18000b409  mov     rax, [rbx+38h]
0x18000b40d  mov     rdx, [rbx+8]
0x18000b411  shr     rax, 3
0x18000b415  cmp     rax, [rbx+10h]
0x18000b419  jbe     short loc_18000B42E
0x18000b41b  mov     r8, rdx
0x18000b41e  mov     rcx, rbx
0x18000b421  mov     rdx, [rdx]
0x18000b424  add     rsp, 20h
0x18000b428  pop     rbx
0x18000b429  jmp     ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const)
0x18000b42e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Free_non_head<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>> &,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *)
0x18000b433  mov     rax, [rbx+8]
0x18000b437  lea     r8, [rsp+28h+arg_0]
0x18000b43c  mov     [rax], rax
0x18000b43f  mov     rax, [rbx+8]
0x18000b443  mov     [rax+8], rax
0x18000b447  mov     qword ptr [rbx+10h], 0
0x18000b44f  mov     rax, [rbx+8]
0x18000b453  mov     rdx, [rbx+20h]
0x18000b457  mov     rcx, [rbx+18h]
0x18000b45b  mov     [rsp+28h+arg_0], rax
0x18000b460  call    ??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> const &)
0x18000b465  add     rsp, 20h
0x18000b469  pop     rbx
0x18000b46a  retn
```
