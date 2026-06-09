# std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>,0>>::find(FilterType const &)

- ea: `0x18000e21c`
- end: `0x18000e2a1`
- name: `?find@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBW4FilterType@@@Z`
- size: `133`
- prototype: `__int64 **__fastcall(__int64 *, __int64 **, char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009890`
- `0x18000a000`
- `0x18000e010`

## callees

- `0x18000e21c`

## pseudocode

```c
__int64 **__fastcall std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::find(
        __int64 *a1,
        __int64 **a2,
        char *a3)
{
  char v4; // r11
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r8
  __int64 v7; // r10
  __int64 v8; // r8
  __int64 *v9; // rdx
  __int64 *i; // rax
  __int64 v11; // rcx

  _mm_lfence();
  v4 = *a3;
  v5 = a1[5];
  v6 = v5
     & ((0x100000001B3LL * ((unsigned __int8)*a3 ^ 0xCBF29CE484222325uLL))
      ^ ((0x100000001B3LL * ((unsigned __int8)*a3 ^ 0xCBF29CE484222325uLL)) >> 32));
  if ( a1[6] <= v6 )
    v6 = v6 - (v5 >> 1) - 1;
  v7 = a1[2];
  v8 = 2 * v6;
  v9 = (__int64 *)*a1;
  for ( i = *(__int64 **)(v7 + 8 * v8); ; i = (__int64 *)*i )
  {
    v11 = *(__int64 **)(v7 + 8 * v8) == v9 ? (__int64)v9 : **(_QWORD **)(v7 + 8 * v8 + 8);
    if ( i == (__int64 *)v11 )
      break;
    if ( *((_BYTE *)i + 16) == v4 )
    {
      *a2 = i;
      return a2;
    }
  }
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x18000e21c  mov     r9, rdx
0x18000e21f  lfence
0x18000e222  movzx   r11d, byte ptr [r8]
0x18000e226  mov     rdx, 0CBF29CE484222325h
0x18000e230  mov     eax, r11d
0x18000e233  xor     rax, rdx
0x18000e236  mov     rdx, 100000001B3h
0x18000e240  imul    rax, rdx
0x18000e244  mov     rdx, [rcx+28h]
0x18000e248  mov     r8, rax
0x18000e24b  shr     r8, 20h
0x18000e24f  xor     r8, rax
0x18000e252  and     r8, rdx
0x18000e255  cmp     [rcx+30h], r8
0x18000e259  ja      short loc_18000E264
0x18000e25b  shr     rdx, 1
0x18000e25e  sub     r8, rdx
0x18000e261  dec     r8
0x18000e264  mov     r10, [rcx+10h]
0x18000e268  add     r8, r8
0x18000e26b  mov     rdx, [rcx]
0x18000e26e  mov     rax, [r10+r8*8]
0x18000e272  cmp     [r10+r8*8], rdx
0x18000e276  jnz     short loc_18000E27D
0x18000e278  mov     rcx, rdx
0x18000e27b  jmp     short loc_18000E285
0x18000e27d  mov     rcx, [r10+r8*8+8]
0x18000e282  mov     rcx, [rcx]
0x18000e285  cmp     rax, rcx
0x18000e288  jz      short loc_18000E29A
0x18000e28a  cmp     [rax+10h], r11b
0x18000e28e  jz      short loc_18000E295
0x18000e290  mov     rax, [rax]
0x18000e293  jmp     short loc_18000E272
0x18000e295  mov     [r9], rax
0x18000e298  jmp     short loc_18000E29D
0x18000e29a  mov     [r9], rdx
0x18000e29d  mov     rax, r9
0x18000e2a0  retn
```
