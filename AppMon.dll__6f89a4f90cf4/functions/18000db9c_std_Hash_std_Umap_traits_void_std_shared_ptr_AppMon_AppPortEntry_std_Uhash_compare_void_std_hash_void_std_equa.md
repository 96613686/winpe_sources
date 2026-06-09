# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> *,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const)

- ea: `0x18000db9c`
- end: `0x18000dcc6`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b3f4`

## callees

- `0x18000cb08`
- `0x18000d534`
- `0x18000db9c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rsi
  _QWORD *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  _QWORD *v15; // rax
  __int64 v17; // rax
  __int64 v18; // r12
  bool v19; // bl
  _QWORD *v20; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = a1[3];
    v8 = (_QWORD *)a1[1];
    v20 = a1 + 1;
    v21 = v6;
    v22 = a2;
    v9 = std::_Conditionally_enabled_hash<void *,1>::operator()((unsigned __int8 *)(a2 + 16));
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v7 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v24 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(&v20);
      if ( v14 )
        break;
      v10 = v22;
      v12 = v24;
      if ( v22 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v7 + 8 * v11) = v10;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v8;
      v6 = v8;
    }
    for ( *(_QWORD *)(v7 + 8 * v11 + 8) = v6; ; *(_QWORD *)(v7 + 8 * v11 + 8) = v8 )
    {
      v10 = v22;
      if ( v22 == a3 )
        break;
      v17 = std::_Conditionally_enabled_hash<void *,1>::operator()((unsigned __int8 *)(v22 + 16));
      v11 = 2 * (a1[6] & v17);
      v18 = *(_QWORD *)(v7 + 16 * (a1[6] & v17) + 8);
      while ( 1 )
      {
        v19 = v10 == v18;
        std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(&v20);
        if ( v19 )
          break;
        v10 = v22;
        if ( v22 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v7 + 8 * v11) = v8;
    }
LABEL_7:
    v15 = v21;
    *v21 = v10;
    *(_QWORD *)(v10 + 8) = v15;
  }
  return a3;
}

```

## disassembly

```asm
0x18000db9c  mov     r11, rsp
0x18000db9f  mov     [r11+18h], rbx
0x18000dba3  mov     [r11+8], rcx
0x18000dba7  push    rbp
0x18000dba8  push    rsi
0x18000dba9  push    rdi
0x18000dbaa  push    r12
0x18000dbac  push    r13
0x18000dbae  push    r14
0x18000dbb0  push    r15
0x18000dbb2  sub     rsp, 40h
0x18000dbb6  mov     rdi, r8
0x18000dbb9  mov     rbp, rdx
0x18000dbbc  mov     rbx, rcx
0x18000dbbf  cmp     rdx, r8
0x18000dbc2  jz      short loc_18000DC42
0x18000dbc4  mov     r12, [rdx+8]
0x18000dbc8  lea     rax, [rcx+8]
0x18000dbcc  mov     rsi, [rcx+18h]
0x18000dbd0  lea     rcx, [rdx+10h]; unsigned __int8 *
0x18000dbd4  mov     r15, [rax]
0x18000dbd7  mov     [r11-58h], rax
0x18000dbdb  mov     [r11-50h], r12
0x18000dbdf  mov     r11, rdx
0x18000dbe2  mov     [rsp+78h+var_48], rdx
0x18000dbe7  call    ??R?$_Conditionally_enabled_hash@PEAX$00@std@@SA_KAEBQEAX@Z; std::_Conditionally_enabled_hash<void *,1>::operator()(void * const &)
0x18000dbec  mov     r14, rax
0x18000dbef  and     r14, [rbx+30h]
0x18000dbf3  add     r14, r14
0x18000dbf6  mov     rax, [rsi+r14*8+8]
0x18000dbfb  mov     r13, [rsi+r14*8]
0x18000dbff  mov     [rsp+78h+arg_8], rax
0x18000dc07  cmp     r11, rax
0x18000dc0a  lea     rcx, [rsp+78h+var_58]
0x18000dc0f  setz    bl
0x18000dc12  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000dc17  test    bl, bl
0x18000dc19  jnz     short loc_18000DC5D
0x18000dc1b  mov     r11, [rsp+78h+var_48]
0x18000dc20  mov     rax, [rsp+78h+arg_8]
0x18000dc28  cmp     r11, rdi
0x18000dc2b  jnz     short loc_18000DC07
0x18000dc2d  cmp     r13, rbp
0x18000dc30  jnz     short loc_18000DC36
0x18000dc32  mov     [rsi+r14*8], r11
0x18000dc36  mov     rax, [rsp+78h+var_50]
0x18000dc3b  mov     [rax], r11
0x18000dc3e  mov     [r11+8], rax
0x18000dc42  mov     rbx, [rsp+78h+arg_10]
0x18000dc4a  mov     rax, rdi
0x18000dc4d  add     rsp, 40h
0x18000dc51  pop     r15
0x18000dc53  pop     r14
0x18000dc55  pop     r13
0x18000dc57  pop     r12
0x18000dc59  pop     rdi
0x18000dc5a  pop     rsi
0x18000dc5b  pop     rbp
0x18000dc5c  retn
0x18000dc5d  cmp     r13, rbp
0x18000dc60  jnz     short loc_18000DC69
0x18000dc62  mov     [rsi+r14*8], r15
0x18000dc66  mov     r12, r15
0x18000dc69  mov     [rsi+r14*8+8], r12
0x18000dc6e  mov     rbp, [rsp+78h+arg_0]
0x18000dc76  mov     r11, [rsp+78h+var_48]
0x18000dc7b  cmp     r11, rdi
0x18000dc7e  jz      short loc_18000DC36
0x18000dc80  lea     rcx, [r11+10h]; unsigned __int8 *
0x18000dc84  call    ??R?$_Conditionally_enabled_hash@PEAX$00@std@@SA_KAEBQEAX@Z; std::_Conditionally_enabled_hash<void *,1>::operator()(void * const &)
0x18000dc89  mov     r14, rax
0x18000dc8c  and     r14, [rbp+30h]
0x18000dc90  add     r14, r14
0x18000dc93  mov     r12, [rsi+r14*8+8]
0x18000dc98  cmp     r11, r12
0x18000dc9b  lea     rcx, [rsp+78h+var_58]
0x18000dca0  setz    bl
0x18000dca3  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000dca8  test    bl, bl
0x18000dcaa  jnz     short loc_18000DCBB
0x18000dcac  mov     r11, [rsp+78h+var_48]
0x18000dcb1  cmp     r11, rdi
0x18000dcb4  jnz     short loc_18000DC98
0x18000dcb6  jmp     loc_18000DC32
0x18000dcbb  mov     [rsi+r14*8], r15
0x18000dcbf  mov     [rsi+r14*8+8], r15
0x18000dcc4  jmp     short loc_18000DC76
```
