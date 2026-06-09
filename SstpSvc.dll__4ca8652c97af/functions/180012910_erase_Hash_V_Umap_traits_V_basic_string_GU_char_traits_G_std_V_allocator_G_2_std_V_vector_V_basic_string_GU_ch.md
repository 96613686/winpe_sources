# ?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z

- ea: `0x180012910`
- end: `0x180012994`
- name: `?erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014490`
- `0x18001c51f`

## callees

- `0x180011d98`
- `0x180012910`
- `0x180012dc8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::erase(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax

  v6 = std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(
         a1,
         (__int64)(a3 + 2));
  v7 = *(_QWORD *)(a1 + 32);
  v8 = 2 * v6;
  if ( *(_QWORD **)(v7 + 16 * v6 + 8) == a3 )
  {
    if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
    {
      *(_QWORD *)(v7 + 16 * v6) = *(_QWORD *)(a1 + 8);
      v7 = *(_QWORD *)(a1 + 32);
      v9 = *(_QWORD *)(a1 + 8);
    }
    else
    {
      v9 = a3[1];
    }
    *(_QWORD *)(v7 + 8 * v8 + 8) = v9;
  }
  else if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
  {
    *(_QWORD *)(v7 + 16 * v6) = *a3;
  }
  std::list<std::pair<std::wstring const,std::vector<std::wstring>>>::erase(a1 + 8, a2, a3);
  return a2;
}

```

## disassembly

```asm
0x180012910  mov     [rsp+arg_0], rbx
0x180012915  mov     [rsp+arg_8], rsi
0x18001291a  push    rdi
0x18001291b  sub     rsp, 20h
0x18001291f  mov     rsi, rdx
0x180012922  mov     rbx, r8
0x180012925  lea     rdx, [r8+10h]
0x180012929  mov     rdi, rcx
0x18001292c  call    ?_Hashval@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Hashval(std::wstring const &)
0x180012931  mov     rcx, [rdi+20h]
0x180012935  mov     r8, rax
0x180012938  add     r8, r8
0x18001293b  cmp     [rcx+r8*8+8], rbx
0x180012940  jnz     short loc_180012965
0x180012942  cmp     [rcx+r8*8], rbx
0x180012946  jnz     short loc_18001295A
0x180012948  mov     rax, [rdi+8]
0x18001294c  mov     [rcx+r8*8], rax
0x180012950  mov     rcx, [rdi+20h]
0x180012954  mov     rax, [rdi+8]
0x180012958  jmp     short loc_18001295E
0x18001295a  mov     rax, [rbx+8]
0x18001295e  mov     [rcx+r8*8+8], rax
0x180012963  jmp     short loc_180012972
0x180012965  cmp     [rcx+r8*8], rbx
0x180012969  jnz     short loc_180012972
0x18001296b  mov     rax, [rbx]
0x18001296e  mov     [rcx+r8*8], rax
0x180012972  lea     rcx, [rdi+8]
0x180012976  mov     r8, rbx
0x180012979  mov     rdx, rsi
0x18001297c  call    ?erase@?$list@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z
0x180012981  mov     rbx, [rsp+28h+arg_0]
0x180012986  mov     rax, rsi
0x180012989  mov     rsi, [rsp+28h+arg_8]
0x18001298e  add     rsp, 20h
0x180012992  pop     rdi
0x180012993  retn
```
