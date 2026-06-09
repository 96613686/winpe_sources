# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Erase<void *>(void * const &)

- ea: `0x18000a900`
- end: `0x18000a9a0`
- name: `??$_Erase@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@AEAA_KAEBQEAX@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a2d4`

## callees

- `0x18000a900`
- `0x18000aa58`
- `0x18000ab5c`
- `0x18000cb08`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Erase<void *>(
        __int64 a1,
        unsigned __int8 *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = std::_Conditionally_enabled_hash<void *,1>::operator()(a2);
  v5 = *(_QWORD **)(std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(
                      v3,
                      v11,
                      v4,
                      v2)
                  + 8);
  if ( !v5 )
    return 0;
  v6 = qword_180016588;
  v7 = 2 * (v2 & qword_1800165A0);
  if ( *(_QWORD **)(qword_180016588 + 16 * (v2 & qword_1800165A0) + 8) == v5 )
  {
    if ( *(_QWORD **)(qword_180016588 + 16 * (v2 & qword_1800165A0)) == v5 )
    {
      v8 = qword_180016578;
      *(_QWORD *)(qword_180016588 + 16 * (v2 & qword_1800165A0)) = qword_180016578;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(qword_180016588 + 16 * (v2 & qword_1800165A0)) == v5 )
  {
    *(_QWORD *)(qword_180016588 + 16 * (v2 & qword_1800165A0)) = *v5;
  }
  v9 = *v5;
  --qword_180016580;
  *(_QWORD *)v5[1] = v9;
  *(_QWORD *)(v9 + 8) = v5[1];
  std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x18000a900  push    rbx
0x18000a902  sub     rsp, 30h
0x18000a906  mov     rcx, rdx; unsigned __int8 *
0x18000a909  mov     r11, rdx
0x18000a90c  call    ??R?$_Conditionally_enabled_hash@PEAX$00@std@@SA_KAEBQEAX@Z; std::_Conditionally_enabled_hash<void *,1>::operator()(void * const &)
0x18000a911  mov     r9, rax
0x18000a914  lea     rdx, [rsp+38h+var_18]
0x18000a919  mov     r8, r11
0x18000a91c  mov     rbx, rax
0x18000a91f  call    ??$_Find_last@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@AEBQEAX_K@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(void * const &,unsigned __int64)
0x18000a924  mov     rdx, [rax+8]
0x18000a928  test    rdx, rdx
0x18000a92b  jz      short loc_18000A998
0x18000a92d  mov     rcx, cs:qword_1800165A0
0x18000a934  mov     r8, cs:qword_180016588
0x18000a93b  and     rcx, rbx
0x18000a93e  add     rcx, rcx
0x18000a941  cmp     [r8+rcx*8+8], rdx
0x18000a946  jnz     short loc_18000A966
0x18000a948  cmp     [r8+rcx*8], rdx
0x18000a94c  jnz     short loc_18000A95B
0x18000a94e  mov     rax, cs:qword_180016578
0x18000a955  mov     [r8+rcx*8], rax
0x18000a959  jmp     short loc_18000A95F
0x18000a95b  mov     rax, [rdx+8]
0x18000a95f  mov     [r8+rcx*8+8], rax
0x18000a964  jmp     short loc_18000A973
0x18000a966  cmp     [r8+rcx*8], rdx
0x18000a96a  jnz     short loc_18000A973
0x18000a96c  mov     rax, [rdx]
0x18000a96f  mov     [r8+rcx*8], rax
0x18000a973  mov     r8, [rdx]
0x18000a976  dec     cs:qword_180016580
0x18000a97d  mov     rcx, [rdx+8]
0x18000a981  mov     [rcx], r8
0x18000a984  mov     rcx, [rdx+8]
0x18000a988  mov     [r8+8], rcx
0x18000a98c  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>>>(std::allocator<std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *>> &,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *)
0x18000a991  mov     eax, 1
0x18000a996  jmp     short loc_18000A99A
0x18000a998  xor     eax, eax
0x18000a99a  add     rsp, 30h
0x18000a99e  pop     rbx
0x18000a99f  retn
```
