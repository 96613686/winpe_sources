# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18002d974`
- end: `0x18002daed`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002833c`

## callees

- `0x18001b36c`
- `0x18001baec`
- `0x180028ffc`
- `0x18002d974`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d9ad`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d9ad`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rsi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 **v7; // rcx
  _QWORD *v8; // r11
  _QWORD *v9; // rbx
  __int64 appended; // rax
  __int64 ***v11; // rdx
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 *v16; // r10
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 **v19; // r10
  __int64 *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rdx
  __int64 *v24; // rax
  __int64 v26; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(v26) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v26) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    appended = std::_Fnv1a_append_bytes((__int64)v7, (const unsigned __int8 *const)v8 + 16, 8u);
    v13 = a1[3];
    v14 = 2 * (a1[6] & appended);
    if ( *(_QWORD **)(v13 + 16 * (a1[6] & appended)) == v4 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & appended)) = v12;
LABEL_7:
      *(_QWORD *)(v13 + 8 * v14 + 8) = v12;
      goto LABEL_15;
    }
    v15 = *(__int64 **)(v13 + 16 * (a1[6] & appended) + 8);
    v7 = *v11;
    if ( *v11 == (__int64 **)v15[2] )
    {
      v16 = (__int64 *)*v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v9;
        v7 = (__int64 **)v9[1];
        *v7 = v16;
        v18 = (_QWORD *)v16[1];
        *v18 = v12;
        v16[1] = (__int64)v7;
        v9[1] = v17;
        *(_QWORD *)(v12 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (__int64 **)(v15 + 1);
      if ( *(__int64 **)(v13 + 8 * v14) == v15 )
        break;
      v15 = *v19;
      if ( v7 == (__int64 **)(*v19)[2] )
      {
        v20 = (__int64 *)*v15;
        v21 = *(_QWORD **)(v12 + 8);
        *v21 = v9;
        v7 = (__int64 **)v9[1];
        *v7 = v20;
        v22 = (_QWORD *)v20[1];
        *v22 = v12;
        v20[1] = (__int64)v7;
        v9[1] = v21;
        *(_QWORD *)(v12 + 8) = v22;
        goto LABEL_15;
      }
    }
    v23 = *(_QWORD **)(v12 + 8);
    *v23 = v9;
    v7 = (__int64 **)v9[1];
    *v7 = v15;
    v24 = *v19;
    *v24 = v12;
    *v19 = (__int64 *)v7;
    v9[1] = v23;
    *(_QWORD *)(v12 + 8) = v24;
    *(_QWORD *)(v13 + 8 * v14) = v12;
LABEL_15:
    v8 = v9;
  }
  v26 = 0;
  return std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Clear_guard::~_Clear_guard(&v26);
}

```

## disassembly

```asm
0x18002d974  push    rbx
0x18002d976  push    rsi
0x18002d977  push    rdi
0x18002d978  push    r14
0x18002d97a  sub     rsp, 28h
0x18002d97e  mov     rax, 0FFFFFFFFFFFFFFFh
0x18002d988  mov     dword ptr [rsp+48h+arg_8], 0
0x18002d990  mov     rdi, rcx
0x18002d993  mov     ebx, 1
0x18002d998  bsr     rcx, rax
0x18002d99c  mov     eax, ebx
0x18002d99e  shl     rax, cl
0x18002d9a1  cmp     rdx, rax
0x18002d9a4  jbe     short loc_18002D9B4
0x18002d9a6  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18002d9ad  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002d9b4  mov     rsi, [rdi+8]
0x18002d9b8  lea     rax, [rdx-1]
0x18002d9bc  or      rax, rbx
0x18002d9bf  mov     dword ptr [rsp+48h+arg_8], 0
0x18002d9c7  bsr     rcx, rax
0x18002d9cb  mov     r8, rsi
0x18002d9ce  inc     ecx
0x18002d9d0  shl     rbx, cl
0x18002d9d3  lea     rcx, [rdi+18h]
0x18002d9d7  lea     rdx, [rbx+rbx]
0x18002d9db  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x18002d9e0  mov     [rdi+38h], rbx
0x18002d9e4  lea     rax, [rbx-1]
0x18002d9e8  mov     [rdi+30h], rax
0x18002d9ec  mov     r11, [rdi+8]
0x18002d9f0  mov     r11, [r11]
0x18002d9f3  mov     rbx, r11
0x18002d9f6  cmp     r11, rsi
0x18002d9f9  jz      loc_18002DAD0
0x18002d9ff  mov     rbx, [rbx]
0x18002da02  lea     rdx, [r11+10h]; unsigned __int8 *
0x18002da06  mov     r8d, 8; unsigned __int64
0x18002da0c  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18002da11  mov     r9, [rdi+18h]
0x18002da15  mov     r8, rax
0x18002da18  and     r8, [rdi+30h]
0x18002da1c  add     r8, r8
0x18002da1f  cmp     [r9+r8*8], rsi
0x18002da23  jnz     short loc_18002DA33
0x18002da25  mov     [r9+r8*8], r11
0x18002da29  mov     [r9+r8*8+8], r11
0x18002da2e  jmp     loc_18002DAC8
0x18002da33  mov     rax, [r9+r8*8+8]
0x18002da38  mov     rcx, [rdx]
0x18002da3b  cmp     rcx, [rax+10h]
0x18002da3f  jnz     short loc_18002DA6C
0x18002da41  mov     r10, [rax]
0x18002da44  cmp     r10, r11
0x18002da47  jz      short loc_18002DA29
0x18002da49  mov     rdx, [r11+8]
0x18002da4d  mov     [rdx], rbx
0x18002da50  mov     rcx, [rbx+8]
0x18002da54  mov     [rcx], r10
0x18002da57  mov     rax, [r10+8]
0x18002da5b  mov     [rax], r11
0x18002da5e  mov     [r10+8], rcx
0x18002da62  mov     [rbx+8], rdx
0x18002da66  mov     [r11+8], rax
0x18002da6a  jmp     short loc_18002DA29
0x18002da6c  lea     r10, [rax+8]
0x18002da70  cmp     [r9+r8*8], rax
0x18002da74  jz      short loc_18002DAA5
0x18002da76  mov     rax, [r10]
0x18002da79  cmp     rcx, [rax+10h]
0x18002da7d  jnz     short loc_18002DA6C
0x18002da7f  mov     r8, [rax]
0x18002da82  mov     rdx, [r11+8]
0x18002da86  mov     [rdx], rbx
0x18002da89  mov     rcx, [rbx+8]
0x18002da8d  mov     [rcx], r8
0x18002da90  mov     rax, [r8+8]
0x18002da94  mov     [rax], r11
0x18002da97  mov     [r8+8], rcx
0x18002da9b  mov     [rbx+8], rdx
0x18002da9f  mov     [r11+8], rax
0x18002daa3  jmp     short loc_18002DAC8
0x18002daa5  mov     rdx, [r11+8]
0x18002daa9  mov     [rdx], rbx
0x18002daac  mov     rcx, [rbx+8]
0x18002dab0  mov     [rcx], rax
0x18002dab3  mov     rax, [r10]
0x18002dab6  mov     [rax], r11
0x18002dab9  mov     [r10], rcx
0x18002dabc  mov     [rbx+8], rdx
0x18002dac0  mov     [r11+8], rax
0x18002dac4  mov     [r9+r8*8], r11
0x18002dac8  mov     r11, rbx
0x18002dacb  jmp     loc_18002D9F6
0x18002dad0  lea     rcx, [rsp+48h+arg_8]
0x18002dad5  mov     [rsp+48h+arg_8], 0
0x18002dade  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Clear_guard::~_Clear_guard(void)
0x18002dae3  add     rsp, 28h
0x18002dae7  pop     r14
0x18002dae9  pop     rdi
0x18002daea  pop     rsi
0x18002daeb  pop     rbx
0x18002daec  retn
```
