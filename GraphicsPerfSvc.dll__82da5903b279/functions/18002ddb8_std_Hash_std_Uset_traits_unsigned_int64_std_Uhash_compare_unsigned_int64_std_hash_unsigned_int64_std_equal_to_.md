# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::clear(void)

- ea: `0x18002ddb8`
- end: `0x18002de27`
- name: `?clear@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAAXXZ`
- size: `111`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028ffc`
- `0x180029254`

## callees

- `0x1800176d4`
- `0x180027e14`
- `0x18002dc40`
- `0x18002ddb8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::clear(
        _QWORD *a1)
{
  __int64 *v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a1[2] )
  {
    v2 = (__int64 *)a1[1];
    if ( a1[7] >> 3 <= a1[2] )
    {
      std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(
        a1,
        v2);
      *(_QWORD *)a1[1] = a1[1];
      *(_QWORD *)(a1[1] + 8LL) = a1[1];
      a1[2] = 0;
      v4 = a1[4];
      v5 = a1[3];
      v6 = a1[1];
      return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned __int64>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned __int64>>>>>(
               v5,
               v4,
               &v6);
    }
    else
    {
      return std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Unchecked_erase(
               a1,
               *v2,
               a1[1]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ddb8  push    rbx
0x18002ddba  sub     rsp, 20h
0x18002ddbe  cmp     qword ptr [rcx+10h], 0
0x18002ddc3  mov     rbx, rcx
0x18002ddc6  jz      short loc_18002DE21
0x18002ddc8  mov     rax, [rcx+38h]
0x18002ddcc  mov     rdx, [rcx+8]
0x18002ddd0  shr     rax, 3
0x18002ddd4  cmp     rax, [rcx+10h]
0x18002ddd8  jbe     short loc_18002DDEA
0x18002ddda  mov     r8, rdx
0x18002dddd  mov     rdx, [rdx]
0x18002dde0  add     rsp, 20h
0x18002dde4  pop     rbx
0x18002dde5  jmp     ?_Unchecked_erase@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@_KPEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Unchecked_erase(std::_List_node<unsigned __int64,void *> *,std::_List_node<unsigned __int64,void *> * const)
0x18002ddea  call    ??$_Free_non_head@V?$allocator@U?$_List_node@_KPEAX@std@@@std@@@?$_List_node@_KPEAX@std@@SAXAEAV?$allocator@U?$_List_node@_KPEAX@std@@@1@PEAU01@@Z; std::_List_node<unsigned __int64,void *>::_Free_non_head<std::allocator<std::_List_node<unsigned __int64,void *>>>(std::allocator<std::_List_node<unsigned __int64,void *>> &,std::_List_node<unsigned __int64,void *> *)
0x18002ddef  mov     rax, [rbx+8]
0x18002ddf3  lea     r8, [rsp+28h+arg_0]
0x18002ddf8  mov     [rax], rax
0x18002ddfb  mov     rax, [rbx+8]
0x18002ddff  mov     [rax+8], rax
0x18002de03  mov     qword ptr [rbx+10h], 0
0x18002de0b  mov     rax, [rbx+8]
0x18002de0f  mov     rdx, [rbx+20h]
0x18002de13  mov     rcx, [rbx+18h]
0x18002de17  mov     [rsp+28h+arg_0], rax
0x18002de1c  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBI_K@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBI_K@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,unsigned __int64>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,unsigned __int64>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,unsigned __int64>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,unsigned __int64>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,unsigned __int64>>>> const &)
0x18002de21  add     rsp, 20h
0x18002de25  pop     rbx
0x18002de26  retn
```
