# std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar,std::allocator<uchar>>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar,std::allocator<uchar>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18002ecdc`
- end: `0x18002ee88`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAX_K@Z`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002eee8`

## callees

- `0x180004b29`
- `0x18001b36c`
- `0x18002e3d8`
- `0x18002e608`
- `0x18002ecdc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ed1c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002ed1c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  unsigned __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r14
  _QWORD *v14; // rsi
  _QWORD *v15; // r8
  _QWORD *v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // r8
  _QWORD *v19; // r8
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  _QWORD *v23; // rax
  __int64 v25; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v25) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v25) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,unsigned int>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>::operator()<EventMetadataKey>(
            (__int64)v8,
            (__int64)(v9 + 2));
    v12 = *v6;
    v13 = 2 * (a1[6] & v11);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v11)) == v4 )
    {
      *(_QWORD *)(v12 + 16 * (a1[6] & v11)) = v9;
      *(_QWORD *)(v12 + 8 * v13 + 8) = v9;
    }
    else
    {
      v14 = *(_QWORD **)(v12 + 16 * (a1[6] & v11) + 8);
      if ( !memcmp_0(v9 + 2, v14 + 2, 0x20u) )
      {
        v15 = (_QWORD *)*v14;
        if ( (_QWORD *)*v14 != v9 )
        {
          v16 = (_QWORD *)v9[1];
          *v16 = v10;
          v8 = (_QWORD *)v10[1];
          *v8 = v15;
          v17 = (_QWORD *)v15[1];
          *v17 = v9;
          v15[1] = v8;
          v10[1] = v16;
          v9[1] = v17;
        }
        *(_QWORD *)(v12 + 8 * v13 + 8) = v9;
      }
      else
      {
        while ( 1 )
        {
          v18 = v14 + 1;
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = (_QWORD *)*v18;
          if ( !memcmp_0(v9 + 2, (const void *)(*v18 + 16LL), 0x20u) )
          {
            v19 = (_QWORD *)*v14;
            v20 = (_QWORD *)v9[1];
            *v20 = v10;
            v8 = (_QWORD *)v10[1];
            *v8 = v19;
            v21 = (_QWORD *)v19[1];
            *v21 = v9;
            v19[1] = v8;
            v10[1] = v20;
            v9[1] = v21;
            goto LABEL_15;
          }
        }
        v22 = (_QWORD *)v9[1];
        *v22 = v10;
        v23 = (_QWORD *)v10[1];
        *v23 = v14;
        v8 = (_QWORD *)*v18;
        *v8 = v9;
        *v18 = v23;
        v10[1] = v22;
        v9[1] = v8;
        *(_QWORD *)(v12 + 8 * v13) = v9;
      }
LABEL_15:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  v25 = 0;
  return std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<unsigned char>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<unsigned char>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
}

```

## disassembly

```asm
0x18002ecdc  push    rbx
0x18002ecde  push    rbp
0x18002ecdf  push    rsi
0x18002ece0  push    rdi
0x18002ece1  push    r12
0x18002ece3  push    r13
0x18002ece5  push    r14
0x18002ece7  push    r15
0x18002ece9  sub     rsp, 28h
0x18002eced  mov     rax, 0FFFFFFFFFFFFFFFh
0x18002ecf7  mov     dword ptr [rsp+68h+arg_8], 0
0x18002ecff  mov     r13, rcx
0x18002ed02  mov     ebx, 1
0x18002ed07  bsr     rcx, rax
0x18002ed0b  mov     eax, ebx
0x18002ed0d  shl     rax, cl
0x18002ed10  cmp     rdx, rax
0x18002ed13  jbe     short loc_18002ED23
0x18002ed15  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18002ed1c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002ed23  mov     rbp, [r13+8]
0x18002ed27  lea     rax, [rdx-1]
0x18002ed2b  or      rax, rbx
0x18002ed2e  mov     dword ptr [rsp+68h+arg_8], 0
0x18002ed36  bsr     rcx, rax
0x18002ed3a  lea     rsi, [r13+18h]
0x18002ed3e  mov     r8, rbp
0x18002ed41  inc     ecx
0x18002ed43  shl     rbx, cl
0x18002ed46  mov     rcx, rsi
0x18002ed49  lea     rdx, [rbx+rbx]
0x18002ed4d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KI@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,uint>>>>)
0x18002ed52  lea     rax, [rbx-1]
0x18002ed56  mov     [r13+38h], rbx
0x18002ed5a  mov     [r13+30h], rax
0x18002ed5e  mov     rbx, [r13+8]
0x18002ed62  mov     rbx, [rbx]
0x18002ed65  mov     rdi, rbx
0x18002ed68  cmp     rbx, rbp
0x18002ed6b  jz      loc_18002EE64
0x18002ed71  mov     rdi, [rdi]
0x18002ed74  lea     r12, [rbx+10h]
0x18002ed78  mov     rdx, r12
0x18002ed7b  call    ??$?RUEventMetadataKey@@@?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@std@@QEBA_KAEBUEventMetadataKey@@@Z; std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>::operator()<EventMetadataKey>(EventMetadataKey const &)
0x18002ed80  mov     r15, [rsi]
0x18002ed83  mov     r14, rax
0x18002ed86  and     r14, [r13+30h]
0x18002ed8a  add     r14, r14
0x18002ed8d  cmp     [r15+r14*8], rbp
0x18002ed91  jnz     short loc_18002EDA1
0x18002ed93  mov     [r15+r14*8], rbx
0x18002ed97  mov     [r15+r14*8+8], rbx
0x18002ed9c  jmp     loc_18002EE5C
0x18002eda1  mov     rsi, [r15+r14*8+8]
0x18002eda6  mov     r8d, 20h ; ' '; Size
0x18002edac  mov     rcx, r12; Buf1
0x18002edaf  lea     rdx, [rsi+10h]; Buf2
0x18002edb3  call    memcmp_0
0x18002edb8  test    eax, eax
0x18002edba  jnz     short loc_18002EDEC
0x18002edbc  mov     r8, [rsi]
0x18002edbf  cmp     r8, rbx
0x18002edc2  jz      short loc_18002EDE5
0x18002edc4  mov     rdx, [rbx+8]
0x18002edc8  mov     [rdx], rdi
0x18002edcb  mov     rcx, [rdi+8]
0x18002edcf  mov     [rcx], r8
0x18002edd2  mov     rax, [r8+8]
0x18002edd6  mov     [rax], rbx
0x18002edd9  mov     [r8+8], rcx
0x18002eddd  mov     [rdi+8], rdx
0x18002ede1  mov     [rbx+8], rax
0x18002ede5  mov     [r15+r14*8+8], rbx
0x18002edea  jmp     short loc_18002EE58
0x18002edec  lea     r8, [rsi+8]
0x18002edf0  cmp     [r15+r14*8], rsi
0x18002edf4  jz      short loc_18002EE35
0x18002edf6  mov     rsi, [r8]
0x18002edf9  mov     rcx, r12; Buf1
0x18002edfc  mov     r8d, 20h ; ' '; Size
0x18002ee02  lea     rdx, [rsi+10h]; Buf2
0x18002ee06  call    memcmp_0
0x18002ee0b  test    eax, eax
0x18002ee0d  jnz     short loc_18002EDEC
0x18002ee0f  mov     r8, [rsi]
0x18002ee12  mov     rdx, [rbx+8]
0x18002ee16  mov     [rdx], rdi
0x18002ee19  mov     rcx, [rdi+8]
0x18002ee1d  mov     [rcx], r8
0x18002ee20  mov     rax, [r8+8]
0x18002ee24  mov     [rax], rbx
0x18002ee27  mov     [r8+8], rcx
0x18002ee2b  mov     [rdi+8], rdx
0x18002ee2f  mov     [rbx+8], rax
0x18002ee33  jmp     short loc_18002EE58
0x18002ee35  mov     rdx, [rbx+8]
0x18002ee39  mov     [rdx], rdi
0x18002ee3c  mov     rax, [rdi+8]
0x18002ee40  mov     [rax], rsi
0x18002ee43  mov     rcx, [r8]
0x18002ee46  mov     [rcx], rbx
0x18002ee49  mov     [r8], rax
0x18002ee4c  mov     [rdi+8], rdx
0x18002ee50  mov     [rbx+8], rcx
0x18002ee54  mov     [r15+r14*8], rbx
0x18002ee58  lea     rsi, [r13+18h]
0x18002ee5c  mov     rbx, rdi
0x18002ee5f  jmp     loc_18002ED68
0x18002ee64  lea     rcx, [rsp+68h+arg_8]
0x18002ee69  mov     [rsp+68h+arg_8], 0
0x18002ee72  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@UEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@V?$_Uhash_compare@UEventMetadataKey@@UEventMetadataKeyHash@@UEventMetadataKeyEqual@@@3@V?$allocator@U?$pair@$$CBUEventMetadataKey@@V?$vector@EV?$allocator@E@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<EventMetadataKey,std::vector<uchar>,std::_Uhash_compare<EventMetadataKey,EventMetadataKeyHash,EventMetadataKeyEqual>,std::allocator<std::pair<EventMetadataKey const,std::vector<uchar>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18002ee77  add     rsp, 28h
0x18002ee7b  pop     r15
0x18002ee7d  pop     r14
0x18002ee7f  pop     r13
0x18002ee81  pop     r12
0x18002ee83  pop     rdi
0x18002ee84  pop     rsi
0x18002ee85  pop     rbp
0x18002ee86  pop     rbx
0x18002ee87  retn
```
