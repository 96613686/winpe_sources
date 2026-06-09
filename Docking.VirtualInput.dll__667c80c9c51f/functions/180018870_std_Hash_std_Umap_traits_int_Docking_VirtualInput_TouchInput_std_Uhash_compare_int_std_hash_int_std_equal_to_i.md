# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x180018870`
- end: `0x1800188d2`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAAXXZ`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019490`

## callees

- `0x180015f30`
- `0x180018f40`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 v1; // rax
  __int64 result; // rax
  _QWORD *v3; // [rsp+20h] [rbp-18h]

  v3 = (_QWORD *)a1[2];
  a1[2] = *v3;
  v1 = std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(*a1);
  std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(
    v1,
    v3);
  result = *(_QWORD *)(*a1 + 8LL) - 1LL;
  *(_QWORD *)(*a1 + 8LL) = result;
  return result;
}

```

## disassembly

```asm
0x180018870  mov     [rsp+arg_0], rcx
0x180018875  sub     rsp, 38h
0x180018879  mov     rax, [rsp+38h+arg_0]
0x18001887e  mov     rax, [rax+10h]
0x180018882  mov     [rsp+38h+var_18], rax
0x180018887  mov     rax, [rsp+38h+arg_0]
0x18001888c  mov     rcx, [rsp+38h+var_18]
0x180018891  mov     rcx, [rcx]
0x180018894  mov     [rax+10h], rcx
0x180018898  mov     rax, [rsp+38h+arg_0]
0x18001889d  mov     rcx, [rax]
0x1800188a0  call    ?_Getal@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@AEBAAEBV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@2@XZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::_Getal(void)
0x1800188a5  mov     rdx, [rsp+38h+var_18]
0x1800188aa  mov     rcx, rax
0x1800188ad  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>(std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>> &,std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *> *)
0x1800188b2  mov     rax, [rsp+38h+arg_0]
0x1800188b7  mov     rax, [rax]
0x1800188ba  mov     rax, [rax+8]
0x1800188be  dec     rax
0x1800188c1  mov     rcx, [rsp+38h+arg_0]
0x1800188c6  mov     rcx, [rcx]
0x1800188c9  mov     [rcx+8], rax
0x1800188cd  add     rsp, 38h
0x1800188d1  retn
```
