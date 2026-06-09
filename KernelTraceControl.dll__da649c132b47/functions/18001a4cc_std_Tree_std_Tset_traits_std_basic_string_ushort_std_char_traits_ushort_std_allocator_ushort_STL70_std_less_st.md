# std::_Tree<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>,0>>::_Node *)

- ea: `0x18001a4cc`
- end: `0x18001a556`
- name: `?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@2@PEAU342@0@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a098`
- `0x18001a4cc`

## callees

- `0x180019ffc`
- `0x18001a4cc`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy(
        __int64 a1,
        __int64 a2,
        int a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  char v8; // [rsp+28h] [rbp-30h]

  v4 = *(_QWORD **)(a1 + 8);
  if ( !*(_BYTE *)(a2 + 65) )
  {
    v8 = *(_BYTE *)(a2 + 64);
    v5 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Buynode(
                     a1,
                     (_DWORD)v4,
                     a3,
                     (_DWORD)v4,
                     a2 + 24,
                     v8,
                     -2);
    v6 = v5;
    if ( *((_BYTE *)v4 + 65) )
      v4 = v5;
    try
    {
      *v5 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy(
              a1,
              *(_QWORD *)a2,
              v5);
      v6[2] = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy(
                a1,
                *(_QWORD *)(a2 + 16),
                v6);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Erase(a1, v4);
      throw;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001a4cc  mov     r11, rsp
0x18001a4cf  mov     [r11+10h], rdx
0x18001a4d3  mov     [r11+8], rcx
0x18001a4d7  push    rbx
0x18001a4d8  push    rsi
0x18001a4d9  push    rdi
0x18001a4da  sub     rsp, 40h
0x18001a4de  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18001a4e6  mov     rsi, rcx
0x18001a4e9  mov     rbx, [rcx+8]
0x18001a4ed  cmp     byte ptr [rdx+41h], 0
0x18001a4f1  jnz     short loc_18001A54B
0x18001a4f3  lea     r9, [rdx+18h]
0x18001a4f7  mov     al, [rdx+40h]
0x18001a4fa  mov     [rsp+58h+var_30], al
0x18001a4fe  mov     [r11-38h], r9
0x18001a502  mov     r9, rbx
0x18001a505  mov     rdx, rbx
0x18001a508  call    ?_Buynode@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@2@PEAU342@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@D@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Buynode(std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,std::wstring const &,char)
0x18001a50d  mov     rdi, rax
0x18001a510  cmp     byte ptr [rbx+41h], 0
0x18001a514  cmovnz  rbx, rax
0x18001a518  mov     [rsp+58h+arg_18], rbx
0x18001a51d  mov     r8, rax
0x18001a520  mov     rdx, [rsp+58h+arg_8]
0x18001a525  mov     rdx, [rdx]
0x18001a528  mov     rcx, rsi
0x18001a52b  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *)
0x18001a530  mov     [rdi], rax
0x18001a533  mov     r8, rdi
0x18001a536  mov     rax, [rsp+58h+arg_8]
0x18001a53b  mov     rdx, [rax+10h]
0x18001a53f  mov     rcx, rsi
0x18001a542  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Node *)
0x18001a547  mov     [rdi+10h], rax
0x18001a54b  mov     rax, rbx
0x18001a54e  add     rsp, 40h
0x18001a552  pop     rdi
0x18001a553  pop     rsi
0x18001a554  pop     rbx
0x18001a555  retn
```
