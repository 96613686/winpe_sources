# std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::find(winrt::hstring const &)

- ea: `0x180025730`
- end: `0x1800257d3`
- name: `?find@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@std@@@std@@@2@AEBUhstring@winrt@@@Z`
- size: `163`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180025730`
- `0x180028f00`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::find(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v5; // rdx
  __int64 v7; // r9
  unsigned __int64 v8; // r8
  __int64 v9; // r10
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD v14[3]; // [rsp+20h] [rbp-18h] BYREF

  v5 = *a3;
  v7 = 0xCBF29CE484222325uLL;
  if ( *a3 )
  {
    v8 = 0;
    v9 = *(_QWORD *)(v5 + 16);
    v10 = 2LL * *(unsigned int *)(v5 + 4);
    if ( v10 )
    {
      do
      {
        v11 = *(unsigned __int8 *)(v9 + v8++);
        v7 = 0x100000001B3LL * (v11 ^ v7);
      }
      while ( v8 < v10 );
    }
  }
  v12 = std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Find_last<winrt::hstring>(
          a1,
          v14,
          a3,
          v7)[1];
  if ( v12 )
    *a2 = v12;
  else
    *a2 = a1[1];
  return a2;
}

```

## disassembly

```asm
0x180025730  mov     [rsp+arg_0], rbx
0x180025735  push    rdi
0x180025736  sub     rsp, 30h
0x18002573a  mov     rbx, rdx
0x18002573d  mov     r11, r8
0x180025740  mov     rdx, [r8]
0x180025743  mov     rdi, rcx
0x180025746  mov     r9, 0CBF29CE484222325h
0x180025750  test    rdx, rdx
0x180025753  jz      short loc_180025794
0x180025755  mov     eax, [rdx+4]
0x180025758  xor     r8d, r8d
0x18002575b  mov     r10, [rdx+10h]
0x18002575f  lea     rdx, [rax+rax]
0x180025763  test    rdx, rdx
0x180025766  jz      short loc_180025794
0x180025768  mov     rcx, 100000001B3h
0x180025772  nop     dword ptr [rax+00h]
0x180025776  nop     word ptr [rax+rax+00000000h]
0x180025780  movzx   eax, byte ptr [r10+r8]
0x180025785  inc     r8
0x180025788  xor     r9, rax
0x18002578b  imul    r9, rcx
0x18002578f  cmp     r8, rdx
0x180025792  jb      short loc_180025780
0x180025794  mov     r8, r11
0x180025797  lea     rdx, [rsp+38h+var_18]
0x18002579c  mov     rcx, rdi
0x18002579f  call    ??$_Find_last@Uhstring@winrt@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@_K@Z; std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Find_last<winrt::hstring>(winrt::hstring const &,unsigned __int64)
0x1800257a4  mov     rcx, [rax+8]
0x1800257a8  test    rcx, rcx
0x1800257ab  jz      short loc_1800257BE
0x1800257ad  mov     [rbx], rcx
0x1800257b0  mov     rax, rbx
0x1800257b3  mov     rbx, [rsp+38h+arg_0]
0x1800257b8  add     rsp, 30h
0x1800257bc  pop     rdi
0x1800257bd  retn
0x1800257be  mov     rax, [rdi+8]
0x1800257c2  mov     [rbx], rax
0x1800257c5  mov     rax, rbx
0x1800257c8  mov     rbx, [rsp+38h+arg_0]
0x1800257cd  add     rsp, 30h
0x1800257d1  pop     rdi
0x1800257d2  retn
```
