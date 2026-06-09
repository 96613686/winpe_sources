# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180008888`
- end: `0x1800088ff`
- name: `??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009b90`

## callees

- `0x180007f80`
- `0x180008594`
- `0x180008888`
- `0x180009dc0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(
        __int64 **a1)
{
  __int64 *v1; // rbx
  __int64 *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = (__int64 *)v1[1];
    if ( (unsigned __int64)v1[7] >> 3 <= v1[2] )
    {
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(a1, v2);
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v4 = v1[4];
      v5 = v1[3];
      v6 = v1[1];
      return std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(
               *a1,
               *v2,
               v1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008888  push    rbx
0x18000888a  sub     rsp, 20h
0x18000888e  mov     rbx, [rcx]
0x180008891  test    rbx, rbx
0x180008894  jz      short loc_1800088F9
0x180008896  cmp     qword ptr [rbx+10h], 0
0x18000889b  jz      short loc_1800088F9
0x18000889d  mov     rax, [rbx+38h]
0x1800088a1  mov     rdx, [rbx+8]
0x1800088a5  shr     rax, 3
0x1800088a9  cmp     rax, [rbx+10h]
0x1800088ad  jbe     short loc_1800088C2
0x1800088af  mov     r8, rdx
0x1800088b2  mov     rcx, rbx
0x1800088b5  mov     rdx, [rdx]
0x1800088b8  add     rsp, 20h
0x1800088bc  pop     rbx
0x1800088bd  jmp     ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(std::_List_node<std::wstring,void *> *,std::_List_node<std::wstring,void *> * const)
0x1800088c2  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1800088c7  mov     rax, [rbx+8]
0x1800088cb  lea     r8, [rsp+28h+arg_0]
0x1800088d0  mov     [rax], rax
0x1800088d3  mov     rax, [rbx+8]
0x1800088d7  mov     [rax+8], rax
0x1800088db  mov     qword ptr [rbx+10h], 0
0x1800088e3  mov     rax, [rbx+8]
0x1800088e7  mov     rdx, [rbx+20h]
0x1800088eb  mov     rcx, [rbx+18h]
0x1800088ef  mov     [rsp+28h+arg_0], rax
0x1800088f4  call    ??$fill@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@V12@@std@@YAXQEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> * const,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0> const &)
0x1800088f9  add     rsp, 20h
0x1800088fd  pop     rbx
0x1800088fe  retn
```
