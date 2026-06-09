# std::_Hash<std::tr1::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>,0>>::_Init(unsigned __int64)

- ea: `0x180007d60`
- end: `0x180007dbd`
- name: `?_Init@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCaseInsensitiveStringHash@@UCaseInsensitiveStringEquality@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007d34`
- `0x18000f7dc`
- `0x180011a20`

## callees

- `0x180007d60`
- `0x180007e28`
- `0x18000805c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Umap_traits<std::wstring,std::vector<std::wstring>,std::_Hash_compare<std::wstring,CaseInsensitiveStringHash,CaseInsensitiveStringEquality>,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>,0>>::_Init(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v2; // rbp
  __int64 *v4; // rbx
  __int64 v6; // rdx
  __int64 result; // rax
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v2 = 2 * a2;
  v4 = a1 + 4;
  std::vector<std::_List_iterator<std::_List_val<std::pair<std::wstring const,std::vector<std::wstring>>>>>::reserve(
    a1 + 4,
    2 * a2);
  v6 = *v4;
  v8 = a1[1];
  if ( v6 != v4[1] )
    v4[1] = v6;
  std::vector<std::_List_iterator<std::_List_val<std::pair<std::wstring const,std::vector<std::wstring>>>>>::_Insert_n(
    v4,
    v6,
    v2,
    &v8);
  result = a2 - 1;
  a1[9] = a2;
  a1[8] = a2 - 1;
  return result;
}

```

## disassembly

```asm
0x180007d60  push    rbx
0x180007d62  push    rbp
0x180007d63  push    rsi
0x180007d64  push    rdi
0x180007d65  sub     rsp, 28h
0x180007d69  lea     rbp, [rdx+rdx]
0x180007d6d  mov     rsi, rdx
0x180007d70  lea     rbx, [rcx+20h]
0x180007d74  mov     rdi, rcx
0x180007d77  mov     rdx, rbp
0x180007d7a  mov     rcx, rbx
0x180007d7d  call    ?reserve@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::_List_iterator<std::_List_val<std::pair<std::wstring const,std::vector<std::wstring>>>>>::reserve(unsigned __int64)
0x180007d82  mov     rdx, [rbx]
0x180007d85  mov     rax, [rdi+8]
0x180007d89  mov     [rsp+48h+arg_0], rax
0x180007d8e  cmp     rdx, [rbx+8]
0x180007d92  jz      short loc_180007D98
0x180007d94  mov     [rbx+8], rdx
0x180007d98  lea     r9, [rsp+48h+arg_0]
0x180007d9d  mov     r8, rbp
0x180007da0  mov     rcx, rbx
0x180007da3  call    ?_Insert_n@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@@2@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@std@@@2@@std@@@2@_KAEBV?$_List_iterator@V?$_List_val@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@@2@@Z
0x180007da8  lea     rax, [rsi-1]
0x180007dac  mov     [rdi+48h], rsi
0x180007db0  mov     [rdi+40h], rax
0x180007db4  add     rsp, 28h
0x180007db8  pop     rdi
0x180007db9  pop     rsi
0x180007dba  pop     rbp
0x180007dbb  pop     rbx
0x180007dbc  retn
```
