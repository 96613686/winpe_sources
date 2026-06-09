# std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(ClientsTracker::ClientKey const &)

- ea: `0x18000af6c`
- end: `0x18000afd3`
- name: `?find@?$_Hash@V?$_Umap_traits@UClientKey@ClientsTracker@@UClientValue@2@V?$_Uhash_compare@UClientKey@ClientsTracker@@UClientKeyHasher@2@U?$equal_to@UClientKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUClientKey@ClientsTracker@@UClientValue@2@@std@@@std@@@std@@@2@AEBUClientKey@ClientsTracker@@@Z`
- size: `103`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, unsigned int *)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009128`
- `0x1800098a4`
- `0x180009938`
- `0x18000a198`
- `0x18000a794`
- `0x18000a838`
- `0x180014c00`

## callees

- `0x1800083a4`
- `0x18000ab20`
- `0x18000af6c`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<ClientsTracker::ClientKey,ClientsTracker::ClientValue,std::_Uhash_compare<ClientsTracker::ClientKey,ClientsTracker::ClientKeyHasher,std::equal_to<ClientsTracker::ClientKey>>,std::allocator<std::pair<ClientsTracker::ClientKey const,ClientsTracker::ClientValue>>,0>>::find(
        _QWORD *a1,
        _QWORD *a2,
        unsigned int *a3)
{
  __int64 appended; // rax
  _DWORD *v6; // r11
  __int64 v7; // rcx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = *a3 | (unsigned __int64)((__int64)(int)a3[1] << 32);
  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, (const unsigned __int8 *const)&v10, 8u);
  v7 = std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,enum MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,enum MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(
         a1,
         v9,
         v6,
         appended)[1];
  if ( !v7 )
    v7 = a1[1];
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x18000af6c  mov     [rsp+arg_8], rbx
0x18000af71  push    rdi
0x18000af72  sub     rsp, 30h
0x18000af76  mov     eax, [r8]
0x18000af79  mov     r11, r8
0x18000af7c  movsxd  r9, dword ptr [r8+4]
0x18000af80  mov     rbx, rdx
0x18000af83  shl     r9, 20h
0x18000af87  lea     rdx, [rsp+38h+arg_0]; unsigned __int8 *
0x18000af8c  or      r9, rax
0x18000af8f  mov     r8d, 8; unsigned __int64
0x18000af95  mov     [rsp+38h+arg_0], r9
0x18000af9a  mov     rdi, rcx
0x18000af9d  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18000afa2  mov     r9, rax
0x18000afa5  lea     rdx, [rsp+38h+var_18]
0x18000afaa  mov     rcx, rdi
0x18000afad  mov     r8, r11
0x18000afb0  call    ??$_Find_last@UDataOriginKey@ClientsTracker@@@?$_Hash@V?$_Umap_traits@UDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@V?$_Uhash_compare@UDataOriginKey@ClientsTracker@@UDataOriginKeyHasher@2@U?$equal_to@UDataOriginKey@ClientsTracker@@@std@@@std@@V?$allocator@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUDataOriginKey@ClientsTracker@@W4DataOriginType@MapControl@@@std@@PEAX@std@@@1@AEBUDataOriginKey@ClientsTracker@@_K@Z; std::_Hash<std::_Umap_traits<ClientsTracker::DataOriginKey,MapControl::DataOriginType,std::_Uhash_compare<ClientsTracker::DataOriginKey,ClientsTracker::DataOriginKeyHasher,std::equal_to<ClientsTracker::DataOriginKey>>,std::allocator<std::pair<ClientsTracker::DataOriginKey const,MapControl::DataOriginType>>,0>>::_Find_last<ClientsTracker::DataOriginKey>(ClientsTracker::DataOriginKey const &,unsigned __int64)
0x18000afb5  mov     rcx, [rax+8]
0x18000afb9  test    rcx, rcx
0x18000afbc  jnz     short loc_18000AFC2
0x18000afbe  mov     rcx, [rdi+8]
0x18000afc2  mov     [rbx], rcx
0x18000afc5  mov     rax, rbx
0x18000afc8  mov     rbx, [rsp+38h+arg_8]
0x18000afcd  add     rsp, 30h
0x18000afd1  pop     rdi
0x18000afd2  retn
```
