# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Unchecked_erase(std::_List_node<unsigned __int64,void *> *,std::_List_node<unsigned __int64,void *> * const)

- ea: `0x18002dc40`
- end: `0x18002dd75`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@_KPEAX@2@PEAU32@QEAU32@@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ddb8`

## callees

- `0x18001baec`
- `0x18002d6f0`
- `0x18002dc40`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Unchecked_erase(
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
    appended = std::_Fnv1a_append_bytes((__int64)a1, (const unsigned __int8 *const)(a2 + 16), 8u);
    v11 = 2 * (a1[6] & appended);
    v25 = *(_QWORD *)(v8 + 16 * (a1[6] & appended));
    v12 = *(_QWORD *)(v8 + 16 * (a1[6] & appended) + 8);
    v26 = v12;
    while ( 1 )
    {
      v13 = i == v12;
      std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Range_eraser::_Bump_erased(&v21);
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
      v15 = std::_Fnv1a_append_bytes(v14, (const unsigned __int8 *const)(i + 16), 8u);
      v16 = 2 * (a1[6] & v15);
      v17 = *(_QWORD *)(v8 + 16 * (a1[6] & v15) + 8);
      while ( 1 )
      {
        v18 = i == v17;
        std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Range_eraser::_Bump_erased(&v21);
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
0x18002dc40  mov     [rsp-38h+arg_18], rbx
0x18002dc45  mov     [rsp-38h+arg_0], rcx
0x18002dc4a  push    rbp
0x18002dc4b  push    rsi
0x18002dc4c  push    rdi
0x18002dc4d  push    r12
0x18002dc4f  push    r13
0x18002dc51  push    r14
0x18002dc53  push    r15
0x18002dc55  mov     rbp, rsp
0x18002dc58  sub     rsp, 40h
0x18002dc5c  mov     rdi, r8
0x18002dc5f  mov     r14, rdx
0x18002dc62  mov     rbx, rcx
0x18002dc65  cmp     rdx, r8
0x18002dc68  jz      loc_18002DD4A
0x18002dc6e  mov     r13, [rdx+8]
0x18002dc72  lea     rax, [rcx+8]
0x18002dc76  mov     r12, [rax]
0x18002dc79  mov     r11, rdx
0x18002dc7c  mov     rsi, [rcx+18h]
0x18002dc80  mov     r8d, 8; unsigned __int64
0x18002dc86  mov     [rbp+var_10], rdx
0x18002dc8a  add     rdx, 10h; unsigned __int8 *
0x18002dc8e  mov     [rbp+var_20], rax
0x18002dc92  mov     [rbp+var_18], r13
0x18002dc96  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18002dc9b  mov     r15, rax
0x18002dc9e  and     r15, [rbx+30h]
0x18002dca2  add     r15, r15
0x18002dca5  mov     rax, [rsi+r15*8]
0x18002dca9  mov     [rbp+arg_8], rax
0x18002dcad  mov     rax, [rsi+r15*8+8]
0x18002dcb2  mov     [rbp+arg_10], rax
0x18002dcb6  cmp     r11, rax
0x18002dcb9  lea     rcx, [rbp+var_20]
0x18002dcbd  setz    bl
0x18002dcc0  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Range_eraser::_Bump_erased(void)
0x18002dcc5  test    bl, bl
0x18002dcc7  jnz     short loc_18002DCE2
0x18002dcc9  mov     r11, [rbp+var_10]
0x18002dccd  mov     rax, [rbp+arg_10]
0x18002dcd1  cmp     r11, rdi
0x18002dcd4  jnz     short loc_18002DCB6
0x18002dcd6  cmp     [rbp+arg_8], r14
0x18002dcda  jnz     short loc_18002DD3F
0x18002dcdc  mov     [rsi+r15*8], r11
0x18002dce0  jmp     short loc_18002DD3F
0x18002dce2  cmp     [rbp+arg_8], r14
0x18002dce6  jnz     short loc_18002DCEF
0x18002dce8  mov     [rsi+r15*8], r12
0x18002dcec  mov     r13, r12
0x18002dcef  mov     [rsi+r15*8+8], r13
0x18002dcf4  mov     r11, [rbp+var_10]
0x18002dcf8  cmp     r11, rdi
0x18002dcfb  jz      short loc_18002DD3F
0x18002dcfd  mov     r15, [rbp+arg_0]
0x18002dd01  lea     rdx, [r11+10h]; unsigned __int8 *
0x18002dd05  mov     r8d, 8; unsigned __int64
0x18002dd0b  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18002dd10  mov     r14, rax
0x18002dd13  and     r14, [r15+30h]
0x18002dd17  add     r14, r14
0x18002dd1a  mov     r13, [rsi+r14*8+8]
0x18002dd1f  cmp     r11, r13
0x18002dd22  lea     rcx, [rbp+var_20]
0x18002dd26  setz    bl
0x18002dd29  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Range_eraser::_Bump_erased(void)
0x18002dd2e  mov     r11, [rbp+var_10]
0x18002dd32  test    bl, bl
0x18002dd34  jnz     short loc_18002DD65
0x18002dd36  cmp     r11, rdi
0x18002dd39  jnz     short loc_18002DD1F
0x18002dd3b  mov     [rsi+r14*8], r11
0x18002dd3f  mov     rax, [rbp+var_18]
0x18002dd43  mov     [rax], r11
0x18002dd46  mov     [r11+8], rax
0x18002dd4a  mov     rbx, [rsp+40h+arg_18]
0x18002dd52  mov     rax, rdi
0x18002dd55  add     rsp, 40h
0x18002dd59  pop     r15
0x18002dd5b  pop     r14
0x18002dd5d  pop     r13
0x18002dd5f  pop     r12
0x18002dd61  pop     rdi
0x18002dd62  pop     rsi
0x18002dd63  pop     rbp
0x18002dd64  retn
0x18002dd65  mov     [rsi+r14*8], r12
0x18002dd69  mov     [rsi+r14*8+8], r12
0x18002dd6e  cmp     r11, rdi
0x18002dd71  jnz     short loc_18002DD01
0x18002dd73  jmp     short loc_18002DD3F
```
