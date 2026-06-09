# std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Iterator_base0> const &)

- ea: `0x180008594`
- end: `0x1800085fd`
- name: `??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z`
- size: `105`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008888`
- `0x180009960`
- `0x18000b3f4`
- `0x18000b474`

## callees

- `0x180008594`

## pseudocode

```c
unsigned __int64 __fastcall std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
        unsigned __int64 *a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3)
{
  unsigned __int64 result; // rax
  unsigned __int64 *v5; // r9
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx

  result = 0;
  v5 = a1;
  v6 = (unsigned __int64)((char *)a2 - (char *)a1 + 7) >> 3;
  if ( a1 > a2 )
    v6 = 0;
  if ( v6 >= 2 )
  {
    if ( a1 > a3 || (result = (unsigned __int64)&a1[v6 - 1], result < (unsigned __int64)a3) )
    {
      result = *a3;
      v7 = v6 & 0xFFFFFFFFFFFFFFFEuLL;
      memset64(a1, *a3, (v7 * 8) >> 3);
      v5 = &a1[v7];
    }
  }
  while ( v5 != a2 )
  {
    result = *a3;
    *v5++ = *a3;
  }
  return result;
}

```

## disassembly

```asm
0x180008594  mov     [rsp+arg_0], rdi
0x180008599  mov     r10, rdx
0x18000859c  xor     eax, eax
0x18000859e  sub     rdx, rcx
0x1800085a1  mov     r9, rcx
0x1800085a4  add     rdx, 7
0x1800085a8  shr     rdx, 3
0x1800085ac  cmp     rcx, r10
0x1800085af  cmova   rdx, rax
0x1800085b3  cmp     rdx, 2
0x1800085b7  jb      short loc_1800085F2
0x1800085b9  cmp     rcx, r8
0x1800085bc  ja      short loc_1800085CB
0x1800085be  lea     rax, [rcx-8]
0x1800085c2  lea     rax, [rax+rdx*8]
0x1800085c6  cmp     rax, r8
0x1800085c9  jnb     short loc_1800085F2
0x1800085cb  mov     rax, [r8]
0x1800085ce  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1800085d2  mov     rdi, r9
0x1800085d5  shl     rdx, 3
0x1800085d9  mov     rcx, rdx
0x1800085dc  shr     rcx, 3
0x1800085e0  rep stosq
0x1800085e3  add     r9, rdx
0x1800085e6  jmp     short loc_1800085F2
0x1800085e8  mov     rax, [r8]
0x1800085eb  mov     [r9], rax
0x1800085ee  add     r9, 8
0x1800085f2  cmp     r9, r10
0x1800085f5  jnz     short loc_1800085E8
0x1800085f7  mov     rdi, [rsp+arg_0]
0x1800085fc  retn
```
