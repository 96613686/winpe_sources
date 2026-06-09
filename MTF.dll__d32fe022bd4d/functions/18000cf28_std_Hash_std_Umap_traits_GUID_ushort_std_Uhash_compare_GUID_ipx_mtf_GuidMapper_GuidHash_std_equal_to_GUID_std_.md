# std::_Hash<std::_Umap_traits<_GUID,ushort,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,ushort>>,0>>::_Init(unsigned __int64)

- ea: `0x18000cf28`
- end: `0x18000cfb6`
- name: `?_Init@?$_Hash@V?$_Umap_traits@U_GUID@@GV?$_Uhash_compare@U_GUID@@UGuidHash@GuidMapper@mtf@ipx@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@G@std@@@3@$0A@@std@@@std@@IEAAX_K@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008680`

## callees

- `0x18000cf28`
- `0x18000cfbc`
- `0x18000d208`
- `0x18000d2a4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,unsigned short,std::_Uhash_compare<_GUID,ipx::mtf::GuidMapper::GuidHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,unsigned short>>,0>>::_Init(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v2; // rbx
  unsigned __int64 v4; // rdi
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  char v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = a1 + 2;
  v4 = 2 * a2;
  if ( (a1[4] - a1[2]) >> 3 < (unsigned __int64)(2 * a2) )
  {
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>>::_Xlen();
    std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>>::_Reallocate(
      a1 + 2,
      v4);
  }
  v6 = *v2;
  v8 = *a1;
  v2[1] = v6;
  std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>>::_Insert_n(
    (_DWORD)v2,
    (unsigned int)&v9,
    v6,
    v4,
    (__int64)&v8);
  result = a2 - 1;
  a1[5] = a2 - 1;
  a1[6] = a2;
  return result;
}

```

## disassembly

```asm
0x18000cf28  mov     [rsp+arg_10], rbx
0x18000cf2d  push    rsi
0x18000cf2e  push    rdi
0x18000cf2f  push    r14
0x18000cf31  sub     rsp, 30h
0x18000cf35  lea     rbx, [rcx+10h]
0x18000cf39  mov     r14, rdx
0x18000cf3c  mov     rax, [rbx+10h]
0x18000cf40  lea     rdi, [rdx+rdx]
0x18000cf44  sub     rax, [rbx]
0x18000cf47  mov     rsi, rcx
0x18000cf4a  sar     rax, 3
0x18000cf4e  cmp     rax, rdi
0x18000cf51  jnb     short loc_18000CF6D
0x18000cf53  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000cf5d  cmp     rdi, rax
0x18000cf60  ja      short loc_18000CFB0
0x18000cf62  mov     rdx, rdi
0x18000cf65  mov     rcx, rbx
0x18000cf68  call    ?_Reallocate@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>::_Reallocate(unsigned __int64)
0x18000cf6d  mov     rax, [rsi]
0x18000cf70  lea     rdx, [rsp+48h+arg_8]
0x18000cf75  mov     r8, [rbx]
0x18000cf78  mov     r9, rdi
0x18000cf7b  mov     [rsp+48h+arg_0], rax
0x18000cf80  mov     rcx, rbx
0x18000cf83  lea     rax, [rsp+48h+arg_0]
0x18000cf88  mov     [rbx+8], r8
0x18000cf8c  mov     [rsp+48h+var_28], rax
0x18000cf91  call    ?_Insert_n@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@2@@Z; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> const &)
0x18000cf96  mov     rbx, [rsp+48h+arg_10]
0x18000cf9b  lea     rax, [r14-1]
0x18000cf9f  mov     [rsi+28h], rax
0x18000cfa3  mov     [rsi+30h], r14
0x18000cfa7  add     rsp, 30h
0x18000cfab  pop     r14
0x18000cfad  pop     rdi
0x18000cfae  pop     rsi
0x18000cfaf  retn
0x18000cfb0  call    ?_Xlen@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>>::_Xlen(void)
```
