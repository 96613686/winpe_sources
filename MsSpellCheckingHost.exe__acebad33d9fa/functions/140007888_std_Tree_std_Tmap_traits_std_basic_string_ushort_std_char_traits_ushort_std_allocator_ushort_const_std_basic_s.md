# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::integral_constant<bool,0>)

- ea: `0x140007888`
- end: `0x140007916`
- name: `??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007888`
- `0x14000ae40`

## callees

- `0x1400077ec`
- `0x140007888`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
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
    v9 = std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring const,std::wstring> &>(
           a1,
           a2 + 32);
    *(_QWORD *)(v9 + 8) = a3;
    *(_BYTE *)(v9 + 24) = *(_BYTE *)(a2 + 24);
    if ( *(_BYTE *)(v8 + 25) )
      v8 = v9;
    try
    {
      *(_QWORD *)v9 = ((__int64 (*)(void))std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>)();
      LOBYTE(v10) = a4;
      *(_QWORD *)(v9 + 16) = std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(
                               a1,
                               *(_QWORD *)(a2 + 16),
                               v9,
                               v10);
    }
    catch ( ... )
    {
      std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
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
0x140007888  mov     [rsp+arg_10], rbx
0x14000788d  mov     [rsp+arg_0], rcx
0x140007892  push    rsi
0x140007893  push    rdi
0x140007894  push    r12
0x140007896  push    r14
0x140007898  push    r15
0x14000789a  sub     rsp, 20h
0x14000789e  mov     bl, r9b
0x1400078a1  mov     r12, r8
0x1400078a4  mov     r15, rdx
0x1400078a7  mov     r14, rcx
0x1400078aa  mov     rsi, [rcx]
0x1400078ad  cmp     byte ptr [rdx+19h], 0
0x1400078b1  jnz     short loc_140007901
0x1400078b3  add     rdx, 20h ; ' '
0x1400078b7  call    ??$_Buynode@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree_buy@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@AEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::pair<std::wstring const,std::wstring> &>(std::pair<std::wstring const,std::wstring> &)
0x1400078bc  mov     rdi, rax
0x1400078bf  mov     [rax+8], r12
0x1400078c3  mov     al, [r15+18h]
0x1400078c7  mov     [rdi+18h], al
0x1400078ca  cmp     byte ptr [rsi+19h], 0
0x1400078ce  cmovnz  rsi, rdi
0x1400078d2  mov     [rsp+48h+arg_8], rsi
0x1400078d7  mov     r9b, bl
0x1400078da  mov     r8, rdi
0x1400078dd  mov     rdx, [r15]
0x1400078e0  mov     rcx, r14
0x1400078e3  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::integral_constant<bool,0>)
0x1400078e8  mov     [rdi], rax
0x1400078eb  mov     r9b, bl
0x1400078ee  mov     r8, rdi
0x1400078f1  mov     rdx, [r15+10h]
0x1400078f5  mov     rcx, r14
0x1400078f8  call    ??$_Copy_nodes@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@PEAU21@0U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy_nodes<std::integral_constant<bool,0>>(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::integral_constant<bool,0>)
0x1400078fd  mov     [rdi+10h], rax
0x140007901  mov     rax, rsi
0x140007904  mov     rbx, [rsp+48h+arg_10]
0x140007909  add     rsp, 20h
0x14000790d  pop     r15
0x14000790f  pop     r14
0x140007911  pop     r12
0x140007913  pop     rdi
0x140007914  pop     rsi
0x140007915  retn
```
