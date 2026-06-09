# std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>>>)

- ea: `0x1800113dc`
- end: `0x1800114c1`
- name: `?erase@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@@Z`
- size: `229`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022809`

## callees

- `0x18000dc0c`
- `0x1800113dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001149d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800114a6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001149d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800114a6`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rbp
  void *v12; // rsi

  _mm_lfence();
  v6 = a1[5];
  v7 = v6
     & ((0x100000001B3LL * (*((unsigned __int8 *)a3 + 16) ^ 0xCBF29CE484222325uLL))
      ^ ((0x100000001B3LL * (*((unsigned __int8 *)a3 + 16) ^ 0xCBF29CE484222325uLL)) >> 32));
  if ( a1[6] <= v7 )
    v7 = v7 - (v6 >> 1) - 1;
  v8 = a1[2];
  v9 = 2 * v7;
  if ( *(_QWORD **)(v8 + 8 * v9 + 8) == a3 )
  {
    if ( *(_QWORD **)(v8 + 8 * v9) == a3 )
    {
      *(_QWORD *)(v8 + 8 * v9) = *a1;
      v8 = a1[2];
      v10 = *a1;
    }
    else
    {
      v10 = a3[1];
    }
    *(_QWORD *)(v8 + 8 * v9 + 8) = v10;
  }
  else if ( *(_QWORD **)(v8 + 8 * v9) == a3 )
  {
    *(_QWORD *)(v8 + 8 * v9) = *a3;
  }
  v11 = *a3;
  if ( a3 != (_QWORD *)*a1 )
  {
    *(_QWORD *)a3[1] = v11;
    *(_QWORD *)(*a3 + 8LL) = a3[1];
    v12 = (void *)a3[3];
    if ( v12 )
    {
      std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(a3[3]);
      operator delete(v12);
    }
    operator delete(a3);
    --a1[1];
  }
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800113dc  push    rbx
0x1800113de  push    rbp
0x1800113df  push    rsi
0x1800113e0  push    rdi
0x1800113e1  push    r14
0x1800113e3  sub     rsp, 20h
0x1800113e7  mov     rbx, r8
0x1800113ea  mov     r14, rdx
0x1800113ed  mov     rdi, rcx
0x1800113f0  lfence
0x1800113f3  movzx   eax, byte ptr [r8+10h]
0x1800113f8  mov     rcx, 0CBF29CE484222325h
0x180011402  xor     rax, rcx
0x180011405  mov     rcx, 100000001B3h
0x18001140f  imul    rax, rcx
0x180011413  mov     rcx, [rdi+28h]
0x180011417  mov     r8, rax
0x18001141a  shr     r8, 20h
0x18001141e  xor     r8, rax
0x180011421  and     r8, rcx
0x180011424  cmp     [rdi+30h], r8
0x180011428  ja      short loc_180011433
0x18001142a  shr     rcx, 1
0x18001142d  sub     r8, rcx
0x180011430  dec     r8
0x180011433  mov     rcx, [rdi+10h]
0x180011437  add     r8, r8
0x18001143a  cmp     [rcx+r8*8+8], rbx
0x18001143f  jnz     short loc_180011462
0x180011441  cmp     [rcx+r8*8], rbx
0x180011445  jnz     short loc_180011457
0x180011447  mov     rax, [rdi]
0x18001144a  mov     [rcx+r8*8], rax
0x18001144e  mov     rcx, [rdi+10h]
0x180011452  mov     rax, [rdi]
0x180011455  jmp     short loc_18001145B
0x180011457  mov     rax, [rbx+8]
0x18001145b  mov     [rcx+r8*8+8], rax
0x180011460  jmp     short loc_18001146F
0x180011462  cmp     [rcx+r8*8], rbx
0x180011466  jnz     short loc_18001146F
0x180011468  mov     rax, [rbx]
0x18001146b  mov     [rcx+r8*8], rax
0x18001146f  mov     rbp, [rbx]
0x180011472  cmp     rbx, [rdi]
0x180011475  jz      short loc_1800114B0
0x180011477  mov     rax, [rbx+8]
0x18001147b  mov     [rax], rbp
0x18001147e  mov     rcx, [rbx]
0x180011481  mov     rax, [rbx+8]
0x180011485  mov     [rcx+8], rax
0x180011489  mov     rsi, [rbx+18h]
0x18001148d  test    rsi, rsi
0x180011490  jz      short loc_1800114A3
0x180011492  mov     rcx, rsi
0x180011495  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18001149a  mov     rcx, rsi
0x18001149d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800114a3  mov     rcx, rbx
0x1800114a6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800114ac  dec     qword ptr [rdi+8]
0x1800114b0  mov     [r14], rbp
0x1800114b3  mov     rax, r14
0x1800114b6  add     rsp, 20h
0x1800114ba  pop     r14
0x1800114bc  pop     rdi
0x1800114bd  pop     rsi
0x1800114be  pop     rbp
0x1800114bf  pop     rbx
0x1800114c0  retn
```
