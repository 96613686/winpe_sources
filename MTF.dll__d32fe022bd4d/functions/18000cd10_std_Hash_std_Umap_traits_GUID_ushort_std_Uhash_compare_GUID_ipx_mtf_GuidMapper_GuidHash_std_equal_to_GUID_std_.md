# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Destroy_if_not_nil(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>)

- ea: `0x18000cd10`
- end: `0x18000cd46`
- name: `?_Destroy_if_not_nil@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAAXV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@Z`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002c508`

## callees

- `0x18000cd10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd36`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd36`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Destroy_if_not_nil(
        _QWORD *a1,
        _QWORD **a2)
{
  if ( a2 != (_QWORD **)*a1 )
  {
    *a2[1] = *a2;
    (*a2)[1] = a2[1];
    operator delete(a2);
    --a1[1];
  }
}

```

## disassembly

```asm
0x18000cd10  push    rbx
0x18000cd12  sub     rsp, 20h
0x18000cd16  mov     rbx, rcx
0x18000cd19  cmp     rdx, [rcx]
0x18000cd1c  jz      short loc_18000CD40
0x18000cd1e  mov     r8, [rdx+8]
0x18000cd22  mov     rcx, rdx
0x18000cd25  mov     rax, [rdx]
0x18000cd28  mov     [r8], rax
0x18000cd2b  mov     r8, [rdx]
0x18000cd2e  mov     rax, [rdx+8]
0x18000cd32  mov     [r8+8], rax
0x18000cd36  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd3c  dec     qword ptr [rbx+8]
0x18000cd40  add     rsp, 20h
0x18000cd44  pop     rbx
0x18000cd45  retn
```
