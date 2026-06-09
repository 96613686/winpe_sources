# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Unchecked_erase(std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> *,std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> * const)

- ea: `0x180009dc0`
- end: `0x180009eea`
- name: `?_Unchecked_erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008888`

## callees

- `0x18000939c`
- `0x1800099f4`
- `0x180009dc0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Unchecked_erase(
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
    v9 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)(a2 + 16));
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v7 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v24 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Range_eraser::_Bump_erased(&v20);
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
      v17 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()((unsigned __int8 *)(v22 + 16));
      v11 = 2 * (a1[6] & v17);
      v18 = *(_QWORD *)(v7 + 16 * (a1[6] & v17) + 8);
      while ( 1 )
      {
        v19 = v10 == v18;
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Range_eraser::_Bump_erased(&v20);
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
0x180009dc0  mov     r11, rsp
0x180009dc3  mov     [r11+18h], rbx
0x180009dc7  mov     [r11+8], rcx
0x180009dcb  push    rbp
0x180009dcc  push    rsi
0x180009dcd  push    rdi
0x180009dce  push    r12
0x180009dd0  push    r13
0x180009dd2  push    r14
0x180009dd4  push    r15
0x180009dd6  sub     rsp, 40h
0x180009dda  mov     rdi, r8
0x180009ddd  mov     rbp, rdx
0x180009de0  mov     rbx, rcx
0x180009de3  cmp     rdx, r8
0x180009de6  jz      short loc_180009E66
0x180009de8  mov     r12, [rdx+8]
0x180009dec  lea     rax, [rcx+8]
0x180009df0  mov     rsi, [rcx+18h]
0x180009df4  lea     rcx, [rdx+10h]; unsigned __int8 *
0x180009df8  mov     r15, [rax]
0x180009dfb  mov     [r11-58h], rax
0x180009dff  mov     [r11-50h], r12
0x180009e03  mov     r11, rdx
0x180009e06  mov     [rsp+78h+var_48], rdx
0x180009e0b  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009e10  mov     r14, rax
0x180009e13  and     r14, [rbx+30h]
0x180009e17  add     r14, r14
0x180009e1a  mov     rax, [rsi+r14*8+8]
0x180009e1f  mov     r13, [rsi+r14*8]
0x180009e23  mov     [rsp+78h+arg_8], rax
0x180009e2b  cmp     r11, rax
0x180009e2e  lea     rcx, [rsp+78h+var_58]
0x180009e33  setz    bl
0x180009e36  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Range_eraser::_Bump_erased(void)
0x180009e3b  test    bl, bl
0x180009e3d  jnz     short loc_180009E81
0x180009e3f  mov     r11, [rsp+78h+var_48]
0x180009e44  mov     rax, [rsp+78h+arg_8]
0x180009e4c  cmp     r11, rdi
0x180009e4f  jnz     short loc_180009E2B
0x180009e51  cmp     r13, rbp
0x180009e54  jnz     short loc_180009E5A
0x180009e56  mov     [rsi+r14*8], r11
0x180009e5a  mov     rax, [rsp+78h+var_50]
0x180009e5f  mov     [rax], r11
0x180009e62  mov     [r11+8], rax
0x180009e66  mov     rbx, [rsp+78h+arg_10]
0x180009e6e  mov     rax, rdi
0x180009e71  add     rsp, 40h
0x180009e75  pop     r15
0x180009e77  pop     r14
0x180009e79  pop     r13
0x180009e7b  pop     r12
0x180009e7d  pop     rdi
0x180009e7e  pop     rsi
0x180009e7f  pop     rbp
0x180009e80  retn
0x180009e81  cmp     r13, rbp
0x180009e84  jnz     short loc_180009E8D
0x180009e86  mov     [rsi+r14*8], r15
0x180009e8a  mov     r12, r15
0x180009e8d  mov     [rsi+r14*8+8], r12
0x180009e92  mov     rbp, [rsp+78h+arg_0]
0x180009e9a  mov     r11, [rsp+78h+var_48]
0x180009e9f  cmp     r11, rdi
0x180009ea2  jz      short loc_180009E5A
0x180009ea4  lea     rcx, [r11+10h]; unsigned __int8 *
0x180009ea8  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180009ead  mov     r14, rax
0x180009eb0  and     r14, [rbp+30h]
0x180009eb4  add     r14, r14
0x180009eb7  mov     r12, [rsi+r14*8+8]
0x180009ebc  cmp     r11, r12
0x180009ebf  lea     rcx, [rsp+78h+var_58]
0x180009ec4  setz    bl
0x180009ec7  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Range_eraser::_Bump_erased(void)
0x180009ecc  test    bl, bl
0x180009ece  jnz     short loc_180009EDF
0x180009ed0  mov     r11, [rsp+78h+var_48]
0x180009ed5  cmp     r11, rdi
0x180009ed8  jnz     short loc_180009EBC
0x180009eda  jmp     loc_180009E56
0x180009edf  mov     [rsi+r14*8], r15
0x180009ee3  mov     [rsi+r14*8+8], r15
0x180009ee8  jmp     short loc_180009E9A
```
