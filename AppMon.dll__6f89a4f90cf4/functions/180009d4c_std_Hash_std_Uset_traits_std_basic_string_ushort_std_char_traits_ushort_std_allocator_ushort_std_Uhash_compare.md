# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> * const,std::_List_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,void *> * const)

- ea: `0x180009d4c`
- end: `0x180009d9b`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008428`
- `0x18000ad94`

## callees

- `0x180009d4c`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r10
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r11

  v4 = *(_QWORD **)(a3 + 8);
  ++a1[2];
  *a4 = a3;
  a4[1] = v4;
  *v4 = a4;
  *(_QWORD *)(a3 + 8) = a4;
  v5 = a2 & a1[6];
  v6 = a1[3];
  v7 = 2 * v5;
  v8 = *(_QWORD *)(v6 + 8 * v7);
  if ( v8 == a1[1] )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
LABEL_6:
    *(_QWORD *)(v6 + 8 * v7 + 8) = a4;
    return a4;
  }
  if ( v8 == a3 )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
  }
  else if ( *(_QWORD **)(v6 + 8 * v7 + 8) == v4 )
  {
    goto LABEL_6;
  }
  return a4;
}

```

## disassembly

```asm
0x180009d4c  mov     r10, [r8+8]
0x180009d50  inc     qword ptr [rcx+10h]
0x180009d54  mov     [r9], r8
0x180009d57  mov     [r9+8], r10
0x180009d5b  mov     [r10], r9
0x180009d5e  mov     [r8+8], r9
0x180009d62  mov     rax, [rcx+30h]
0x180009d66  and     rax, rdx
0x180009d69  mov     rdx, [rcx+18h]
0x180009d6d  add     rax, rax
0x180009d70  mov     r11, [rdx+rax*8]
0x180009d74  cmp     r11, [rcx+8]
0x180009d78  jnz     short loc_180009D80
0x180009d7a  mov     [rdx+rax*8], r9
0x180009d7e  jmp     short loc_180009D92
0x180009d80  cmp     r11, r8
0x180009d83  jnz     short loc_180009D8B
0x180009d85  mov     [rdx+rax*8], r9
0x180009d89  jmp     short loc_180009D97
0x180009d8b  cmp     [rdx+rax*8+8], r10
0x180009d90  jnz     short loc_180009D97
0x180009d92  mov     [rdx+rax*8+8], r9
0x180009d97  mov     rax, r9
0x180009d9a  retn
```
