# std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Unchecked_erase(std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *> *,std::_List_node<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>,void *> * const)

- ea: `0x18001c198`
- end: `0x18001c2cd`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c67c`

## callees

- `0x18001b400`
- `0x18001baec`
- `0x18001c198`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r13
  _QWORD *v7; // r12
  __int64 v8; // rsi
  __int64 appended; // rax
  __int64 i; // r11
  __int64 v11; // r15
  __int64 v12; // rax
  bool v13; // bl
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r14
  __int64 v17; // r13
  bool v18; // bl
  _QWORD *v19; // rax
  _QWORD *v21; // [rsp+20h] [rbp-20h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-18h]
  __int64 v23; // [rsp+30h] [rbp-10h]
  __int64 v25; // [rsp+88h] [rbp+48h]
  __int64 v26; // [rsp+90h] [rbp+50h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = (_QWORD *)a1[1];
    v8 = a1[3];
    v23 = a2;
    v21 = a1 + 1;
    v22 = v6;
    appended = std::_Fnv1a_append_bytes((__int64)a1, (const unsigned __int8 *const)(a2 + 16), 4u);
    v11 = 2 * (a1[6] & appended);
    v25 = *(_QWORD *)(v8 + 16 * (a1[6] & appended));
    v12 = *(_QWORD *)(v8 + 16 * (a1[6] & appended) + 8);
    v26 = v12;
    while ( 1 )
    {
      v13 = i == v12;
      std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Range_eraser::_Bump_erased(&v21);
      if ( v13 )
        break;
      i = v23;
      v12 = v26;
      if ( v23 == a3 )
      {
        if ( v25 == a2 )
          *(_QWORD *)(v8 + 8 * v11) = v23;
        goto LABEL_14;
      }
    }
    if ( v25 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v11) = v7;
      v6 = v7;
    }
    *(_QWORD *)(v8 + 8 * v11 + 8) = v6;
    for ( i = v23; i != a3; *(_QWORD *)(v8 + 8 * v16 + 8) = v7 )
    {
      v15 = std::_Fnv1a_append_bytes(v14, (const unsigned __int8 *const)(i + 16), 4u);
      v16 = 2 * (a1[6] & v15);
      v17 = *(_QWORD *)(v8 + 16 * (a1[6] & v15) + 8);
      while ( 1 )
      {
        v18 = i == v17;
        std::_Hash<std::_Umap_traits<unsigned int,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Range_eraser::_Bump_erased(&v21);
        i = v23;
        if ( v18 )
          break;
        if ( v23 == a3 )
        {
          *(_QWORD *)(v8 + 8 * v16) = v23;
          goto LABEL_14;
        }
      }
      *(_QWORD *)(v8 + 8 * v16) = v7;
    }
LABEL_14:
    v19 = v22;
    *v22 = i;
    *(_QWORD *)(i + 8) = v19;
  }
  return a3;
}

```

## disassembly

```asm
0x18001c198  mov     [rsp-38h+arg_18], rbx
0x18001c19d  mov     [rsp-38h+arg_0], rcx
0x18001c1a2  push    rbp
0x18001c1a3  push    rsi
0x18001c1a4  push    rdi
0x18001c1a5  push    r12
0x18001c1a7  push    r13
0x18001c1a9  push    r14
0x18001c1ab  push    r15
0x18001c1ad  mov     rbp, rsp
0x18001c1b0  sub     rsp, 40h
0x18001c1b4  mov     rdi, r8
0x18001c1b7  mov     r14, rdx
0x18001c1ba  mov     rbx, rcx
0x18001c1bd  cmp     rdx, r8
0x18001c1c0  jz      loc_18001C2A2
0x18001c1c6  mov     r13, [rdx+8]
0x18001c1ca  lea     rax, [rcx+8]
0x18001c1ce  mov     r12, [rax]
0x18001c1d1  mov     r11, rdx
0x18001c1d4  mov     rsi, [rcx+18h]
0x18001c1d8  mov     r8d, 4; unsigned __int64
0x18001c1de  mov     [rbp+var_10], rdx
0x18001c1e2  add     rdx, 10h; unsigned __int8 *
0x18001c1e6  mov     [rbp+var_20], rax
0x18001c1ea  mov     [rbp+var_18], r13
0x18001c1ee  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c1f3  mov     r15, rax
0x18001c1f6  and     r15, [rbx+30h]
0x18001c1fa  add     r15, r15
0x18001c1fd  mov     rax, [rsi+r15*8]
0x18001c201  mov     [rbp+arg_8], rax
0x18001c205  mov     rax, [rsi+r15*8+8]
0x18001c20a  mov     [rbp+arg_10], rax
0x18001c20e  cmp     r11, rax
0x18001c211  lea     rcx, [rbp+var_20]
0x18001c215  setz    bl
0x18001c218  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c21d  test    bl, bl
0x18001c21f  jnz     short loc_18001C23A
0x18001c221  mov     r11, [rbp+var_10]
0x18001c225  mov     rax, [rbp+arg_10]
0x18001c229  cmp     r11, rdi
0x18001c22c  jnz     short loc_18001C20E
0x18001c22e  cmp     [rbp+arg_8], r14
0x18001c232  jnz     short loc_18001C297
0x18001c234  mov     [rsi+r15*8], r11
0x18001c238  jmp     short loc_18001C297
0x18001c23a  cmp     [rbp+arg_8], r14
0x18001c23e  jnz     short loc_18001C247
0x18001c240  mov     [rsi+r15*8], r12
0x18001c244  mov     r13, r12
0x18001c247  mov     [rsi+r15*8+8], r13
0x18001c24c  mov     r11, [rbp+var_10]
0x18001c250  cmp     r11, rdi
0x18001c253  jz      short loc_18001C297
0x18001c255  mov     r15, [rbp+arg_0]
0x18001c259  lea     rdx, [r11+10h]; unsigned __int8 *
0x18001c25d  mov     r8d, 4; unsigned __int64
0x18001c263  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c268  mov     r14, rax
0x18001c26b  and     r14, [r15+30h]
0x18001c26f  add     r14, r14
0x18001c272  mov     r13, [rsi+r14*8+8]
0x18001c277  cmp     r11, r13
0x18001c27a  lea     rcx, [rbp+var_20]
0x18001c27e  setz    bl
0x18001c281  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@IUMakeResidentStartData@PresentTraceConsumerCore@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUMakeResidentStartData@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,PresentTraceConsumerCore::MakeResidentStartData,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,PresentTraceConsumerCore::MakeResidentStartData>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c286  mov     r11, [rbp+var_10]
0x18001c28a  test    bl, bl
0x18001c28c  jnz     short loc_18001C2BD
0x18001c28e  cmp     r11, rdi
0x18001c291  jnz     short loc_18001C277
0x18001c293  mov     [rsi+r14*8], r11
0x18001c297  mov     rax, [rbp+var_18]
0x18001c29b  mov     [rax], r11
0x18001c29e  mov     [r11+8], rax
0x18001c2a2  mov     rbx, [rsp+40h+arg_18]
0x18001c2aa  mov     rax, rdi
0x18001c2ad  add     rsp, 40h
0x18001c2b1  pop     r15
0x18001c2b3  pop     r14
0x18001c2b5  pop     r13
0x18001c2b7  pop     r12
0x18001c2b9  pop     rdi
0x18001c2ba  pop     rsi
0x18001c2bb  pop     rbp
0x18001c2bc  retn
0x18001c2bd  mov     [rsi+r14*8], r12
0x18001c2c1  mov     [rsi+r14*8+8], r12
0x18001c2c6  cmp     r11, rdi
0x18001c2c9  jnz     short loc_18001C259
0x18001c2cb  jmp     short loc_18001C297
```
