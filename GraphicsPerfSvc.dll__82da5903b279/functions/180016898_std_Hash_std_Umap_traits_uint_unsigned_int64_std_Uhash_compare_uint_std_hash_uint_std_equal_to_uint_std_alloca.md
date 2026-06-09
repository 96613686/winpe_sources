# std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Find_last<uint>(uint const &,unsigned __int64)

- ea: `0x180016898`
- end: `0x1800168ec`
- name: `??$_Find_last@I@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBI_K@std@@PEAX@std@@@1@AEBI_K@Z`
- size: `84`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _DWORD *, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016b6c`
- `0x180016d30`
- `0x180019ee0`
- `0x18001a3a4`

## callees

- `0x180016898`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Find_last<unsigned int>(
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
0x180016898  mov     rax, [rcx+30h]
0x18001689c  mov     r11, [rcx+18h]
0x1800168a0  and     rax, r9
0x1800168a3  mov     r10, [rcx+8]
0x1800168a7  add     rax, rax
0x1800168aa  mov     r9, [r11+rax*8+8]
0x1800168af  cmp     r9, r10
0x1800168b2  jnz     short loc_1800168C1
0x1800168b4  mov     [rdx], r10
0x1800168b7  mov     qword ptr [rdx+8], 0
0x1800168bf  jmp     short loc_1800168E8
0x1800168c1  mov     rcx, [r11+rax*8]
0x1800168c5  mov     eax, [r8]
0x1800168c8  cmp     eax, [r9+10h]
0x1800168cc  jz      short loc_1800168DE
0x1800168ce  cmp     r9, rcx
0x1800168d1  jz      short loc_1800168D9
0x1800168d3  mov     r9, [r9+8]
0x1800168d7  jmp     short loc_1800168C8
0x1800168d9  mov     [rdx], r9
0x1800168dc  jmp     short loc_1800168B7
0x1800168de  mov     rax, [r9]
0x1800168e1  mov     [rdx], rax
0x1800168e4  mov     [rdx+8], r9
0x1800168e8  mov     rax, rdx
0x1800168eb  retn
```
