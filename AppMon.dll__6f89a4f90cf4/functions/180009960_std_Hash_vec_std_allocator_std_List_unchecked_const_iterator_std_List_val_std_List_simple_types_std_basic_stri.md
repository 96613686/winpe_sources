# std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>)

- ea: `0x180009960`
- end: `0x1800099ed`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800011c0`
- `0x180009b90`
- `0x18000b060`
- `0x18000d7d8`
- `0x18000d96c`
- `0x18000e718`

## callees

- `0x180006170`
- `0x180006288`
- `0x180007fe4`
- `0x180008594`
- `0x180009960`

## pseudocode

```c
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 size_of; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = a3;
  if ( (__int64)(a1[1] - *a1) >> 3 >= a2 )
    return std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
             *a1,
             a1[1],
             &v10);
  size_of = std::_Get_size_of_n<8>(a2);
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v8 = (__int64)(a1[2] - *a1) >> 3;
  if ( v8 )
    std::_Deallocate<16>((void *)*a1, 8 * v8);
  result = (__int64)&v7[a2];
  *a1 = v7;
  a1[1] = result;
  a1[2] = result;
  while ( v7 != (_QWORD *)result )
    *v7++ = a3;
  return result;
}

```

## disassembly

```asm
0x180009960  mov     [rsp+arg_10], r8
0x180009965  push    rbx
0x180009966  push    rbp
0x180009967  push    rsi
0x180009968  push    rdi
0x180009969  sub     rsp, 28h
0x18000996d  mov     rbp, rdx
0x180009970  mov     rbx, r8
0x180009973  mov     rdx, [rcx+8]
0x180009977  mov     rsi, rcx
0x18000997a  mov     rax, rdx
0x18000997d  sub     rax, [rcx]
0x180009980  sar     rax, 3
0x180009984  cmp     rax, rbp
0x180009987  jnb     short loc_1800099D7
0x180009989  mov     rcx, rbp
0x18000998c  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180009991  mov     rcx, rax
0x180009994  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009999  mov     rdx, [rsi+10h]
0x18000999d  mov     rdi, rax
0x1800099a0  sub     rdx, [rsi]
0x1800099a3  sar     rdx, 3
0x1800099a7  test    rdx, rdx
0x1800099aa  jz      short loc_1800099B8
0x1800099ac  mov     rcx, [rsi]
0x1800099af  shl     rdx, 3
0x1800099b3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800099b8  lea     rax, [rdi+rbp*8]
0x1800099bc  mov     [rsi], rdi
0x1800099bf  mov     [rsi+8], rax
0x1800099c3  mov     [rsi+10h], rax
0x1800099c7  jmp     short loc_1800099D0
0x1800099c9  mov     [rdi], rbx
0x1800099cc  add     rdi, 8
0x1800099d0  cmp     rdi, rax
0x1800099d3  jnz     short loc_1800099C9
0x1800099d5  jmp     short loc_1800099E4
0x1800099d7  mov     rcx, [rcx]
0x1800099da  lea     r8, [rsp+48h+arg_10]
0x1800099df  call    ??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> const &)
0x1800099e4  add     rsp, 28h
0x1800099e8  pop     rdi
0x1800099e9  pop     rsi
0x1800099ea  pop     rbp
0x1800099eb  pop     rbx
0x1800099ec  retn
```
