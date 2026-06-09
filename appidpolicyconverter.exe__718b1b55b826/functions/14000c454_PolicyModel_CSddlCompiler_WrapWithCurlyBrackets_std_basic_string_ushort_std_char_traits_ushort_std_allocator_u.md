# PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000c454`
- end: `0x14000c4d8`
- name: `?WrapWithCurlyBrackets@CSddlCompiler@PolicyModel@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000bd68`
- `0x14000cf50`

## callees

- `0x1400070e4`
- `0x14000b710`
- `0x14000c454`
- `0x14000c5bc`

## pseudocode

```c
__int64 __fastcall PolicyModel::CSddlCompiler::WrapWithCurlyBrackets(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // r8
  _QWORD *v6; // rax
  int v7; // r9d
  char v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids);
  if ( (unsigned __int64)a1[3] < 8 )
    LODWORD(v5) = (_DWORD)a1;
  else
    v5 = *a1;
  std::wstring::insert((_DWORD)a1, (unsigned int)&v9, v5, a4, 123);
  v6 = (_QWORD *)std::wstring::end(a1, &v9);
  return std::wstring::insert((_DWORD)a1, (unsigned int)&v10, *v6, v7, 125);
}

```

## disassembly

```asm
0x14000c454  push    rbx
0x14000c456  sub     rsp, 30h
0x14000c45a  mov     rbx, rcx
0x14000c45d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c464  lea     rax, WPP_GLOBAL_Control
0x14000c46b  cmp     rcx, rax
0x14000c46e  jz      short loc_14000C48B
0x14000c470  test    byte ptr [rcx+1Ch], 8
0x14000c474  jz      short loc_14000C48B
0x14000c476  mov     rcx, [rcx+10h]
0x14000c47a  lea     r8, WPP_78e66d69943b3de38e95864888fb0f14_Traceguids
0x14000c481  mov     edx, 0Eh
0x14000c486  call    WPP_SF_
0x14000c48b  cmp     qword ptr [rbx+18h], 8
0x14000c490  jb      short loc_14000C497
0x14000c492  mov     r8, [rbx]
0x14000c495  jmp     short loc_14000C49A
0x14000c497  mov     r8, rbx
0x14000c49a  lea     rdx, [rsp+38h+arg_0]
0x14000c49f  mov     [rsp+38h+var_18], 7Bh ; '{'
0x14000c4a6  mov     rcx, rbx
0x14000c4a9  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@_KG@Z; std::wstring::insert(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64,ushort)
0x14000c4ae  lea     rdx, [rsp+38h+arg_0]
0x14000c4b3  mov     rcx, rbx
0x14000c4b6  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x14000c4bb  lea     rdx, [rsp+38h+arg_8]
0x14000c4c0  mov     [rsp+38h+var_18], 7Dh ; '}'
0x14000c4c7  mov     rcx, rbx
0x14000c4ca  mov     r8, [rax]
0x14000c4cd  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@_KG@Z; std::wstring::insert(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,unsigned __int64,ushort)
0x14000c4d2  add     rsp, 30h
0x14000c4d6  pop     rbx
0x14000c4d7  retn
```
