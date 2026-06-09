# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>,void *> * const)

- ea: `0x18000dccc`
- end: `0x18000ddf6`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b474`

## callees

- `0x18000939c`
- `0x18000d560`
- `0x18000dccc`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Unchecked_erase(
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
      std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Range_eraser::_Bump_erased(&v20);
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
        std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Range_eraser::_Bump_erased(&v20);
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
0x18000dccc  mov     r11, rsp
0x18000dccf  mov     [r11+18h], rbx
0x18000dcd3  mov     [r11+8], rcx
0x18000dcd7  push    rbp
0x18000dcd8  push    rsi
0x18000dcd9  push    rdi
0x18000dcda  push    r12
0x18000dcdc  push    r13
0x18000dcde  push    r14
0x18000dce0  push    r15
0x18000dce2  sub     rsp, 40h
0x18000dce6  mov     rdi, r8
0x18000dce9  mov     rbp, rdx
0x18000dcec  mov     rbx, rcx
0x18000dcef  cmp     rdx, r8
0x18000dcf2  jz      short loc_18000DD72
0x18000dcf4  mov     r12, [rdx+8]
0x18000dcf8  lea     rax, [rcx+8]
0x18000dcfc  mov     rsi, [rcx+18h]
0x18000dd00  lea     rcx, [rdx+10h]; unsigned __int8 *
0x18000dd04  mov     r15, [rax]
0x18000dd07  mov     [r11-58h], rax
0x18000dd0b  mov     [r11-50h], r12
0x18000dd0f  mov     r11, rdx
0x18000dd12  mov     [rsp+78h+var_48], rdx
0x18000dd17  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000dd1c  mov     r14, rax
0x18000dd1f  and     r14, [rbx+30h]
0x18000dd23  add     r14, r14
0x18000dd26  mov     rax, [rsi+r14*8+8]
0x18000dd2b  mov     r13, [rsi+r14*8]
0x18000dd2f  mov     [rsp+78h+arg_8], rax
0x18000dd37  cmp     r11, rax
0x18000dd3a  lea     rcx, [rsp+78h+var_58]
0x18000dd3f  setz    bl
0x18000dd42  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000dd47  test    bl, bl
0x18000dd49  jnz     short loc_18000DD8D
0x18000dd4b  mov     r11, [rsp+78h+var_48]
0x18000dd50  mov     rax, [rsp+78h+arg_8]
0x18000dd58  cmp     r11, rdi
0x18000dd5b  jnz     short loc_18000DD37
0x18000dd5d  cmp     r13, rbp
0x18000dd60  jnz     short loc_18000DD66
0x18000dd62  mov     [rsi+r14*8], r11
0x18000dd66  mov     rax, [rsp+78h+var_50]
0x18000dd6b  mov     [rax], r11
0x18000dd6e  mov     [r11+8], rax
0x18000dd72  mov     rbx, [rsp+78h+arg_10]
0x18000dd7a  mov     rax, rdi
0x18000dd7d  add     rsp, 40h
0x18000dd81  pop     r15
0x18000dd83  pop     r14
0x18000dd85  pop     r13
0x18000dd87  pop     r12
0x18000dd89  pop     rdi
0x18000dd8a  pop     rsi
0x18000dd8b  pop     rbp
0x18000dd8c  retn
0x18000dd8d  cmp     r13, rbp
0x18000dd90  jnz     short loc_18000DD99
0x18000dd92  mov     [rsi+r14*8], r15
0x18000dd96  mov     r12, r15
0x18000dd99  mov     [rsi+r14*8+8], r12
0x18000dd9e  mov     rbp, [rsp+78h+arg_0]
0x18000dda6  mov     r11, [rsp+78h+var_48]
0x18000ddab  cmp     r11, rdi
0x18000ddae  jz      short loc_18000DD66
0x18000ddb0  lea     rcx, [r11+10h]; unsigned __int8 *
0x18000ddb4  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000ddb9  mov     r14, rax
0x18000ddbc  and     r14, [rbp+30h]
0x18000ddc0  add     r14, r14
0x18000ddc3  mov     r12, [rsi+r14*8+8]
0x18000ddc8  cmp     r11, r12
0x18000ddcb  lea     rcx, [rsp+78h+var_58]
0x18000ddd0  setz    bl
0x18000ddd3  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000ddd8  test    bl, bl
0x18000ddda  jnz     short loc_18000DDEB
0x18000dddc  mov     r11, [rsp+78h+var_48]
0x18000dde1  cmp     r11, rdi
0x18000dde4  jnz     short loc_18000DDC8
0x18000dde6  jmp     loc_18000DD62
0x18000ddeb  mov     [rsi+r14*8], r15
0x18000ddef  mov     [rsi+r14*8+8], r15
0x18000ddf4  jmp     short loc_18000DDA6
```
