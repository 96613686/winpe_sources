# std::_Hash<std::_Umap_traits<ulong,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::vector<tagPROCESS_WIN32_CAPABILITIES,std::allocator<tagPROCESS_WIN32_CAPABILITIES>>>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)

- ea: `0x18000fb60`
- end: `0x18000fbb4`
- name: `??$_Find_last@K@?$_Hash@V?$_Umap_traits@KV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBKV?$vector@UtagPROCESS_WIN32_CAPABILITIES@@V?$allocator@UtagPROCESS_WIN32_CAPABILITIES@@@std@@@std@@@std@@PEAX@std@@@1@AEBK_K@Z`
- size: `84`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fe60`

## callees

- `0x18000fb60`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned long,std::vector<tagPROCESS_WIN32_CAPABILITIES>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::vector<tagPROCESS_WIN32_CAPABILITIES>>>,0>>::_Find_last<unsigned long>(
        _QWORD *a1,
        _QWORD *a2,
        _DWORD *a3,
        __int64 a4)
{
  __int64 v4; // r11
  __int64 v5; // r10
  __int64 v6; // rax
  __int64 v7; // r9

  v4 = a1[3];
  v5 = a1[1];
  v6 = 2 * (a4 & a1[6]);
  v7 = *(_QWORD *)(v4 + 16 * (a4 & a1[6]) + 8);
  if ( v7 == v5 )
  {
    *a2 = v5;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    while ( *a3 != *(_DWORD *)(v7 + 16) )
    {
      if ( v7 == *(_QWORD *)(v4 + 8 * v6) )
      {
        *a2 = v7;
        goto LABEL_3;
      }
      v7 = *(_QWORD *)(v7 + 8);
    }
    *a2 = *(_QWORD *)v7;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18000fb60  mov     rax, [rcx+30h]
0x18000fb64  mov     r11, [rcx+18h]
0x18000fb68  and     rax, r9
0x18000fb6b  mov     r10, [rcx+8]
0x18000fb6f  add     rax, rax
0x18000fb72  mov     r9, [r11+rax*8+8]
0x18000fb77  cmp     r9, r10
0x18000fb7a  jnz     short loc_18000FB89
0x18000fb7c  mov     [rdx], r10
0x18000fb7f  mov     qword ptr [rdx+8], 0
0x18000fb87  jmp     short loc_18000FBB0
0x18000fb89  mov     rcx, [r11+rax*8]
0x18000fb8d  mov     eax, [r8]
0x18000fb90  cmp     eax, [r9+10h]
0x18000fb94  jz      short loc_18000FBA6
0x18000fb96  cmp     r9, rcx
0x18000fb99  jz      short loc_18000FBA1
0x18000fb9b  mov     r9, [r9+8]
0x18000fb9f  jmp     short loc_18000FB90
0x18000fba1  mov     [rdx], r9
0x18000fba4  jmp     short loc_18000FB7F
0x18000fba6  mov     rax, [r9]
0x18000fba9  mov     [rdx], rax
0x18000fbac  mov     [rdx+8], r9
0x18000fbb0  mov     rax, rdx
0x18000fbb3  retn
```
