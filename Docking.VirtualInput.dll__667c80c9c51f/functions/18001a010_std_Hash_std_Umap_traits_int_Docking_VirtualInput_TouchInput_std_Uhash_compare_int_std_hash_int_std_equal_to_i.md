# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::size(void)

- ea: `0x18001a010`
- end: `0x18001a02f`
- name: `?size@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800174bc`
- `0x18001984c`
- `0x18001a5d0`

## callees

- `0x18001a064`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::size(
        __int64 a1)
{
  return std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::size(a1 + 8);
}

```

## disassembly

```asm
0x18001a010  mov     [rsp+arg_0], rcx
0x18001a015  sub     rsp, 28h
0x18001a019  mov     rax, [rsp+28h+arg_0]
0x18001a01e  add     rax, 8
0x18001a022  mov     rcx, rax
0x18001a025  call    ?size@?$list@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@2@@std@@QEBA_KXZ; std::list<std::pair<int const,Docking::VirtualInput::TouchInput>>::size(void)
0x18001a02a  add     rsp, 28h
0x18001a02e  retn
```
