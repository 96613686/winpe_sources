# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::find(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000de70`
- end: `0x18000decf`
- name: `?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b6a8`
- `0x18000b990`
- `0x18000bafc`
- `0x18000c808`
- `0x18000ca20`

## callees

- `0x180007f08`
- `0x180009b54`
- `0x18000de70`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::find(
        unsigned __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // r8
  const unsigned __int8 *v7; // rdx
  unsigned __int64 appended; // rax
  __int64 v9; // r11
  __int64 v10; // rcx
  _BYTE v12[24]; // [rsp+20h] [rbp-18h] BYREF

  v5 = *(_QWORD *)(a3 + 16);
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v7 = (const unsigned __int8 *)a3;
  else
    v7 = *(const unsigned __int8 **)a3;
  appended = std::_Fnv1a_append_bytes(a1, v7, 2 * v5);
  v10 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                      a1,
                      v12,
                      v9,
                      appended)
                  + 8);
  if ( !v10 )
    v10 = *(_QWORD *)(a1 + 8);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x18000de70  mov     [rsp+arg_0], rbx
0x18000de75  push    rdi
0x18000de76  sub     rsp, 30h
0x18000de7a  mov     r11, r8
0x18000de7d  mov     rbx, rdx
0x18000de80  mov     r8, [r8+10h]
0x18000de84  mov     rdi, rcx
0x18000de87  cmp     qword ptr [r11+18h], 7
0x18000de8c  jbe     short loc_18000DE93
0x18000de8e  mov     rdx, [r11]
0x18000de91  jmp     short loc_18000DE96
0x18000de93  mov     rdx, r11; unsigned __int8 *
0x18000de96  add     r8, r8; unsigned __int64
0x18000de99  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18000de9e  mov     r9, rax
0x18000dea1  lea     rdx, [rsp+38h+var_18]
0x18000dea6  mov     rcx, rdi
0x18000dea9  mov     r8, r11
0x18000deac  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000deb1  mov     rcx, [rax+8]
0x18000deb5  test    rcx, rcx
0x18000deb8  jnz     short loc_18000DEBE
0x18000deba  mov     rcx, [rdi+8]
0x18000debe  mov     [rbx], rcx
0x18000dec1  mov     rax, rbx
0x18000dec4  mov     rbx, [rsp+38h+arg_0]
0x18000dec9  add     rsp, 30h
0x18000decd  pop     rdi
0x18000dece  retn
```
