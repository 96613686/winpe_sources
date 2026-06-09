# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x18000e224`
- end: `0x18000e2bb`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `151`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000f224`
- `0x180010768`
- `0x1800111fc`

## callees

- `0x18000babc`
- `0x18000e224`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rbp
  const wchar_t *v10; // rdx
  size_t v11; // r8
  const wchar_t *v12; // rcx

  v5 = a1[3];
  v7 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v7 )
  {
    *a2 = v7;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      v10 = (const wchar_t *)(v8 + 2);
      if ( v8[5] > 7u )
        v10 = *(const wchar_t **)v10;
      v11 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v12 = (const wchar_t *)a3;
      else
        v12 = *(const wchar_t **)a3;
      if ( v11 == v8[4] && (!v11 || !wmemcmp(v12, v10, v11)) )
      {
        *a2 = *v8;
        a2[1] = v8;
        return a2;
      }
      if ( v8 == v9 )
        break;
      v8 = (_QWORD *)v8[1];
    }
    *a2 = v8;
  }
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x18000e224  push    rbx
0x18000e226  push    rbp
0x18000e227  push    rsi
0x18000e228  push    rdi
0x18000e229  sub     rsp, 28h
0x18000e22d  mov     rax, [rcx+30h]
0x18000e231  mov     rsi, r8
0x18000e234  mov     r8, [rcx+18h]
0x18000e238  and     rax, r9
0x18000e23b  add     rax, rax
0x18000e23e  mov     rbx, rdx
0x18000e241  mov     rdx, [rcx+8]
0x18000e245  mov     rdi, [r8+rax*8+8]
0x18000e24a  cmp     rdi, rdx
0x18000e24d  jnz     short loc_18000E254
0x18000e24f  mov     [rbx], rdx
0x18000e252  jmp     short loc_18000E2A7
0x18000e254  mov     rbp, [r8+rax*8]
0x18000e258  cmp     qword ptr [rdi+28h], 7
0x18000e25d  lea     rdx, [rdi+10h]
0x18000e261  jbe     short loc_18000E266
0x18000e263  mov     rdx, [rdx]; S2
0x18000e266  cmp     qword ptr [rsi+18h], 7
0x18000e26b  mov     r8, [rsi+10h]; N
0x18000e26f  jbe     short loc_18000E276
0x18000e271  mov     rcx, [rsi]
0x18000e274  jmp     short loc_18000E279
0x18000e276  mov     rcx, rsi; S1
0x18000e279  cmp     r8, [rdi+20h]
0x18000e27d  jnz     short loc_18000E28D
0x18000e27f  test    r8, r8
0x18000e282  jz      short loc_18000E298
0x18000e284  call    wmemcmp
0x18000e289  test    eax, eax
0x18000e28b  jz      short loc_18000E298
0x18000e28d  cmp     rdi, rbp
0x18000e290  jz      short loc_18000E2A4
0x18000e292  mov     rdi, [rdi+8]
0x18000e296  jmp     short loc_18000E258
0x18000e298  mov     rax, [rdi]
0x18000e29b  mov     [rbx], rax
0x18000e29e  mov     [rbx+8], rdi
0x18000e2a2  jmp     short loc_18000E2AF
0x18000e2a4  mov     [rbx], rdi
0x18000e2a7  mov     qword ptr [rbx+8], 0
0x18000e2af  mov     rax, rbx
0x18000e2b2  add     rsp, 28h
0x18000e2b6  pop     rdi
0x18000e2b7  pop     rsi
0x18000e2b8  pop     rbp
0x18000e2b9  pop     rbx
0x18000e2ba  retn
```
