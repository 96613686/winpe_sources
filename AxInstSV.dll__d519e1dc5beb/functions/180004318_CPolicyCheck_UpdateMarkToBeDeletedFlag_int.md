# CPolicyCheck::UpdateMarkToBeDeletedFlag(int)

- ea: `0x180004318`
- end: `0x18000435e`
- name: `?UpdateMarkToBeDeletedFlag@CPolicyCheck@@QEAAJH@Z`
- size: `70`
- prototype: `__int64 __fastcall(CPolicyCheck *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003afc`
- `0x180004364`

## callees

- `0x180002c5c`
- `0x180004318`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::UpdateMarkToBeDeletedFlag(__int64 **this, __int64 a2, __int64 a3)
{
  CPolicyCheck *v3; // r9
  __int64 v4; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+38h] [rbp+10h]

  v7 = a2;
  v3 = (CPolicyCheck *)this;
  v4 = *this[14];
  v6 = v4;
  while ( v4 != *((_QWORD *)v3 + 14) )
  {
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 44LL) = 1;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(
      &v6,
      a2,
      a3,
      (__int64)v3);
    v4 = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180004318  mov     [rsp+arg_8], edx
0x18000431c  sub     rsp, 28h
0x180004320  mov     r9, rcx
0x180004323  mov     rax, [rcx+70h]
0x180004327  mov     rax, [rax]
0x18000432a  mov     [rsp+28h+arg_0], rax
0x18000432f  cmp     rax, [r9+70h]
0x180004333  jz      short loc_180004351
0x180004335  mov     rcx, [rax+20h]
0x180004339  mov     dword ptr [rcx+2Ch], 1
0x180004340  lea     rcx, [rsp+28h+arg_0]
0x180004345  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>,std::_Iterator_base0>::operator++(void)
0x18000434a  mov     rax, [rsp+28h+arg_0]
0x18000434f  jmp     short loc_18000432F
0x180004351  xor     eax, eax
0x180004353  jmp     short loc_180004359
0x180004355  mov     eax, [rsp+28h+arg_8]
0x180004359  add     rsp, 28h
0x18000435d  retn
```
