# std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Unchecked_erase(std::_List_node<std::pair<uint const,unsigned __int64>,void *> *,std::_List_node<std::pair<uint const,unsigned __int64>,void *> * const)

- ea: `0x18001c2d4`
- end: `0x18001c409`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBI_K@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c6f4`

## callees

- `0x18001b434`
- `0x18001baec`
- `0x18001c2d4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Unchecked_erase(
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
      std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Range_eraser::_Bump_erased(&v21);
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
        std::_Hash<std::_Umap_traits<unsigned int,unsigned __int64,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned __int64>>,0>>::_Range_eraser::_Bump_erased(&v21);
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
0x18001c2d4  mov     [rsp-38h+arg_18], rbx
0x18001c2d9  mov     [rsp-38h+arg_0], rcx
0x18001c2de  push    rbp
0x18001c2df  push    rsi
0x18001c2e0  push    rdi
0x18001c2e1  push    r12
0x18001c2e3  push    r13
0x18001c2e5  push    r14
0x18001c2e7  push    r15
0x18001c2e9  mov     rbp, rsp
0x18001c2ec  sub     rsp, 40h
0x18001c2f0  mov     rdi, r8
0x18001c2f3  mov     r14, rdx
0x18001c2f6  mov     rbx, rcx
0x18001c2f9  cmp     rdx, r8
0x18001c2fc  jz      loc_18001C3DE
0x18001c302  mov     r13, [rdx+8]
0x18001c306  lea     rax, [rcx+8]
0x18001c30a  mov     r12, [rax]
0x18001c30d  mov     r11, rdx
0x18001c310  mov     rsi, [rcx+18h]
0x18001c314  mov     r8d, 4; unsigned __int64
0x18001c31a  mov     [rbp+var_10], rdx
0x18001c31e  add     rdx, 10h; unsigned __int8 *
0x18001c322  mov     [rbp+var_20], rax
0x18001c326  mov     [rbp+var_18], r13
0x18001c32a  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c32f  mov     r15, rax
0x18001c332  and     r15, [rbx+30h]
0x18001c336  add     r15, r15
0x18001c339  mov     rax, [rsi+r15*8]
0x18001c33d  mov     [rbp+arg_8], rax
0x18001c341  mov     rax, [rsi+r15*8+8]
0x18001c346  mov     [rbp+arg_10], rax
0x18001c34a  cmp     r11, rax
0x18001c34d  lea     rcx, [rbp+var_20]
0x18001c351  setz    bl
0x18001c354  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c359  test    bl, bl
0x18001c35b  jnz     short loc_18001C376
0x18001c35d  mov     r11, [rbp+var_10]
0x18001c361  mov     rax, [rbp+arg_10]
0x18001c365  cmp     r11, rdi
0x18001c368  jnz     short loc_18001C34A
0x18001c36a  cmp     [rbp+arg_8], r14
0x18001c36e  jnz     short loc_18001C3D3
0x18001c370  mov     [rsi+r15*8], r11
0x18001c374  jmp     short loc_18001C3D3
0x18001c376  cmp     [rbp+arg_8], r14
0x18001c37a  jnz     short loc_18001C383
0x18001c37c  mov     [rsi+r15*8], r12
0x18001c380  mov     r13, r12
0x18001c383  mov     [rsi+r15*8+8], r13
0x18001c388  mov     r11, [rbp+var_10]
0x18001c38c  cmp     r11, rdi
0x18001c38f  jz      short loc_18001C3D3
0x18001c391  mov     r15, [rbp+arg_0]
0x18001c395  lea     rdx, [r11+10h]; unsigned __int8 *
0x18001c399  mov     r8d, 4; unsigned __int64
0x18001c39f  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001c3a4  mov     r14, rax
0x18001c3a7  and     r14, [r15+30h]
0x18001c3ab  add     r14, r14
0x18001c3ae  mov     r13, [rsi+r14*8+8]
0x18001c3b3  cmp     r11, r13
0x18001c3b6  lea     rcx, [rbp+var_20]
0x18001c3ba  setz    bl
0x18001c3bd  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@I_KV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBI_K@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,unsigned __int64,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,unsigned __int64>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001c3c2  mov     r11, [rbp+var_10]
0x18001c3c6  test    bl, bl
0x18001c3c8  jnz     short loc_18001C3F9
0x18001c3ca  cmp     r11, rdi
0x18001c3cd  jnz     short loc_18001C3B3
0x18001c3cf  mov     [rsi+r14*8], r11
0x18001c3d3  mov     rax, [rbp+var_18]
0x18001c3d7  mov     [rax], r11
0x18001c3da  mov     [r11+8], rax
0x18001c3de  mov     rbx, [rsp+40h+arg_18]
0x18001c3e6  mov     rax, rdi
0x18001c3e9  add     rsp, 40h
0x18001c3ed  pop     r15
0x18001c3ef  pop     r14
0x18001c3f1  pop     r13
0x18001c3f3  pop     r12
0x18001c3f5  pop     rdi
0x18001c3f6  pop     rsi
0x18001c3f7  pop     rbp
0x18001c3f8  retn
0x18001c3f9  mov     [rsi+r14*8], r12
0x18001c3fd  mov     [rsi+r14*8+8], r12
0x18001c402  cmp     r11, rdi
0x18001c405  jnz     short loc_18001C395
0x18001c407  jmp     short loc_18001C3D3
```
