# std::_Tree<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_lessstr,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Node *)

- ea: `0x180011ac4`
- end: `0x180011b4e`
- name: `?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@PEAU342@0@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f5e8`
- `0x180011ac4`

## callees

- `0x18000f270`
- `0x180011ac4`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Copy(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rsi
  __int64 v7; // rbx

  v6 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(a2 + 65) )
  {
    v7 = std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<std::wstring &>(
           a1,
           a2 + 24);
    *(_QWORD *)(v7 + 8) = a3;
    *(_BYTE *)(v7 + 64) = *(_BYTE *)(a2 + 64);
    if ( *(_BYTE *)(v6 + 65) )
      v6 = v7;
    try
    {
      *(_QWORD *)v7 = ((__int64 (*)(void))std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Copy)();
      *(_QWORD *)(v7 + 16) = std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Copy(
                               a1,
                               *(_QWORD *)(a2 + 16),
                               v7);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Erase(a1, v6);
      throw;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180011ac4  mov     [rsp+arg_10], rbx
0x180011ac9  mov     [rsp+arg_18], rsi
0x180011ace  mov     [rsp+arg_0], rcx
0x180011ad3  push    rdi
0x180011ad4  push    r14
0x180011ad6  push    r15
0x180011ad8  sub     rsp, 20h
0x180011adc  mov     r15, r8
0x180011adf  mov     r14, rdx
0x180011ae2  mov     rdi, rcx
0x180011ae5  mov     rsi, [rcx+8]
0x180011ae9  cmp     byte ptr [rdx+41h], 0
0x180011aed  jnz     short loc_180011B37
0x180011aef  add     rdx, 18h
0x180011af3  call    ??$_Buynode@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree_val<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Buynode<std::wstring &>(std::wstring &)
0x180011af8  mov     rbx, rax
0x180011afb  mov     [rax+8], r15
0x180011aff  mov     al, [r14+40h]
0x180011b03  mov     [rbx+40h], al
0x180011b06  cmp     byte ptr [rsi+41h], 0
0x180011b0a  cmovnz  rsi, rbx
0x180011b0e  mov     [rsp+38h+arg_8], rsi
0x180011b13  mov     r8, rbx
0x180011b16  mov     rdx, [r14]
0x180011b19  mov     rcx, rdi
0x180011b1c  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *)
0x180011b21  mov     [rbx], rax
0x180011b24  mov     r8, rbx
0x180011b27  mov     rdx, [r14+10h]
0x180011b2b  mov     rcx, rdi
0x180011b2e  call    ?_Copy@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_lessstr@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<std::wstring,_lessstr,std::allocator<std::wstring>,0>>::_Node *)
0x180011b33  mov     [rbx+10h], rax
0x180011b37  mov     rax, rsi
0x180011b3a  mov     rbx, [rsp+38h+arg_10]
0x180011b3f  mov     rsi, [rsp+38h+arg_18]
0x180011b44  add     rsp, 20h
0x180011b48  pop     r15
0x180011b4a  pop     r14
0x180011b4c  pop     rdi
0x180011b4d  retn
```
