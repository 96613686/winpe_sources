# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_FrameworkDependency,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>,void *> *,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_FrameworkDependency>,void *> *,std::integral_constant<bool,0>)

- ea: `0x18000aa18`
- end: `0x18000aaa7`
- name: `??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000aa18`
- `0x18000b220`

## callees

- `0x18000a8c8`
- `0x18000aa18`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // r9

  v8 = *a1;
  if ( !*(_BYTE *)(a2 + 25) )
  {
    v9 = std::_Tree_buy<std::pair<std::wstring const,_FrameworkDependency>>::_Buynode<std::pair<std::wstring const,_FrameworkDependency> &>(
           a1,
           a2 + 32);
    *(_QWORD *)(v9 + 8) = a3;
    *(_BYTE *)(v9 + 24) = *(_BYTE *)(a2 + 24);
    if ( *(_BYTE *)(v8 + 25) )
      v8 = v9;
    try
    {
      *(_QWORD *)v9 = ((__int64 (*)(void))std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>)();
      LOBYTE(v10) = a4;
      *(_QWORD *)(v9 + 16) = std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                               a1,
                               *(_QWORD *)(a2 + 16),
                               v9,
                               v10);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Erase(
        a1,
        v8);
      throw;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000aa18  mov     [rsp+arg_10], rbx
0x18000aa1d  mov     [rsp+arg_0], rcx
0x18000aa22  push    rsi
0x18000aa23  push    rdi
0x18000aa24  push    r12
0x18000aa26  push    r14
0x18000aa28  push    r15
0x18000aa2a  sub     rsp, 20h
0x18000aa2e  mov     bl, r9b
0x18000aa31  mov     r12, r8
0x18000aa34  mov     r15, rdx
0x18000aa37  mov     r14, rcx
0x18000aa3a  mov     rsi, [rcx]
0x18000aa3d  cmp     byte ptr [rdx+19h], 0
0x18000aa41  jnz     short loc_18000AA91
0x18000aa43  add     rdx, 20h ; ' '
0x18000aa47  call    ??$_Buynode@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,_FrameworkDependency>>::_Buynode<std::pair<std::wstring const,_FrameworkDependency> &>(std::pair<std::wstring const,_FrameworkDependency> &)
0x18000aa4c  mov     rdi, rax
0x18000aa4f  mov     [rax+8], r12
0x18000aa53  mov     al, [r15+18h]
0x18000aa57  mov     [rdi+18h], al
0x18000aa5a  cmp     byte ptr [rsi+19h], 0
0x18000aa5e  cmovnz  rsi, rdi
0x18000aa62  mov     [rsp+48h+arg_8], rsi
0x18000aa67  mov     r9b, bl
0x18000aa6a  mov     r8, rdi
0x18000aa6d  mov     rdx, [r15]
0x18000aa70  mov     rcx, r14
0x18000aa73  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *,std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *,std::integral_constant<bool,0>)
0x18000aa78  mov     [rdi], rax
0x18000aa7b  mov     r9b, bl
0x18000aa7e  mov     r8, rdi
0x18000aa81  mov     rdx, [r15+10h]
0x18000aa85  mov     rcx, r14
0x18000aa88  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FrameworkDependency@@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_FrameworkDependency,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_FrameworkDependency>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *,std::_Tree_node<std::pair<std::wstring const,_FrameworkDependency>,void *> *,std::integral_constant<bool,0>)
0x18000aa8d  mov     [rdi+10h], rax
0x18000aa91  mov     rax, rsi
0x18000aa94  mov     rbx, [rsp+48h+arg_10]
0x18000aa99  add     rsp, 20h
0x18000aa9d  pop     r15
0x18000aa9f  pop     r14
0x18000aaa1  pop     r12
0x18000aaa3  pop     rdi
0x18000aaa4  pop     rsi
0x18000aaa5  retn
```
