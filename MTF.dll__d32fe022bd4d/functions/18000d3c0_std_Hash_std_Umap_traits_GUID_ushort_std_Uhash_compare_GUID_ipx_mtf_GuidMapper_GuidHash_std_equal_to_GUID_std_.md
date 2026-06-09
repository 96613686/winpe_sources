# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)

- ea: `0x18000d3c0`
- end: `0x18000d457`
- name: `?erase@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c4ce`

## callees

- `0x18000ce94`
- `0x18000d3c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d43d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d43d`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // rsi

  v6 = std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Hashval(
         (__int64)a1,
         (__int64)(a3 + 2));
  v7 = a1[2];
  if ( *(_QWORD **)(v7 + 16 * v6 + 8) == a3 )
  {
    if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
    {
      *(_QWORD *)(v7 + 16 * v6) = *a1;
      *(_QWORD *)(a1[2] + 16 * v6 + 8) = *a1;
    }
    else
    {
      *(_QWORD *)(v7 + 16 * v6 + 8) = a3[1];
    }
  }
  else if ( *(_QWORD **)(v7 + 16 * v6) == a3 )
  {
    *(_QWORD *)(v7 + 16 * v6) = *a3;
  }
  v8 = *a3;
  if ( a3 != (_QWORD *)*a1 )
  {
    *(_QWORD *)a3[1] = v8;
    *(_QWORD *)(*a3 + 8LL) = a3[1];
    operator delete(a3);
    --a1[1];
  }
  *a2 = v8;
  return a2;
}

```

## disassembly

```asm
0x18000d3c0  push    rbx
0x18000d3c2  push    rsi
0x18000d3c3  push    rdi
0x18000d3c4  push    r14
0x18000d3c6  sub     rsp, 28h
0x18000d3ca  mov     r14, rdx
0x18000d3cd  mov     rbx, r8
0x18000d3d0  lea     rdx, [r8+10h]
0x18000d3d4  mov     rdi, rcx
0x18000d3d7  call    ?_Hashval@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEBA_KAEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Hashval(_GUID const &)
0x18000d3dc  mov     r9, [rdi+10h]
0x18000d3e0  mov     r8, rax
0x18000d3e3  add     r8, r8
0x18000d3e6  cmp     [r9+r8*8+8], rbx
0x18000d3eb  jnz     short loc_18000D413
0x18000d3ed  cmp     [r9+r8*8], rbx
0x18000d3f1  jnz     short loc_18000D408
0x18000d3f3  mov     rcx, [rdi]
0x18000d3f6  mov     [r9+r8*8], rcx
0x18000d3fa  mov     rcx, [rdi+10h]
0x18000d3fe  mov     rax, [rdi]
0x18000d401  mov     [rcx+r8*8+8], rax
0x18000d406  jmp     short loc_18000D420
0x18000d408  mov     rax, [rbx+8]
0x18000d40c  mov     [r9+r8*8+8], rax
0x18000d411  jmp     short loc_18000D420
0x18000d413  cmp     [r9+r8*8], rbx
0x18000d417  jnz     short loc_18000D420
0x18000d419  mov     rax, [rbx]
0x18000d41c  mov     [r9+r8*8], rax
0x18000d420  mov     rsi, [rbx]
0x18000d423  cmp     rbx, [rdi]
0x18000d426  jz      short loc_18000D447
0x18000d428  mov     rax, [rbx+8]
0x18000d42c  mov     [rax], rsi
0x18000d42f  mov     rcx, [rbx]
0x18000d432  mov     rax, [rbx+8]
0x18000d436  mov     [rcx+8], rax
0x18000d43a  mov     rcx, rbx
0x18000d43d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d443  dec     qword ptr [rdi+8]
0x18000d447  mov     [r14], rsi
0x18000d44a  mov     rax, r14
0x18000d44d  add     rsp, 28h
0x18000d451  pop     r14
0x18000d453  pop     rdi
0x18000d454  pop     rsi
0x18000d455  pop     rbx
0x18000d456  retn
```
