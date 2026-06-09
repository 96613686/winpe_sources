# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x180016d80`
- end: `0x180016da7`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018bd0`

## callees

- `0x180016d80`
- `0x180019ba0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::_Clear_guard::~_Clear_guard(
        __int64 *a1)
{
  __int64 result; // rax

  result = (__int64)a1;
  if ( *a1 )
    return std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::clear(*a1);
  return result;
}

```

## disassembly

```asm
0x180016d80  mov     [rsp+arg_0], rcx
0x180016d85  sub     rsp, 28h
0x180016d89  mov     rax, [rsp+28h+arg_0]
0x180016d8e  cmp     qword ptr [rax], 0
0x180016d92  jz      short loc_180016DA2
0x180016d94  mov     rax, [rsp+28h+arg_0]
0x180016d99  mov     rcx, [rax]
0x180016d9c  call    ?clear@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::clear(void)
0x180016da1  nop
0x180016da2  add     rsp, 28h
0x180016da6  retn
```
