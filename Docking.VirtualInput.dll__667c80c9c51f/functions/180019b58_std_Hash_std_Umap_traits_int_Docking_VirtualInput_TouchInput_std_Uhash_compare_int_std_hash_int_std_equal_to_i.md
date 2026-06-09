# std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(void)

- ea: `0x180019b58`
- end: `0x180019b67`
- name: `?bucket_count@?$_Hash@V?$_Umap_traits@HUTouchInput@VirtualInput@Docking@@V?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@V?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@5@$0A@@std@@@std@@QEBA_KXZ`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018960`
- `0x180018a40`
- `0x180019ba0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<int,Docking::VirtualInput::TouchInput,std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>>,0>>::bucket_count(
        __int64 a1)
{
  return *(_QWORD *)(a1 + 56);
}

```

## disassembly

```asm
0x180019b58  mov     [rsp+arg_0], rcx
0x180019b5d  mov     rax, [rsp+arg_0]
0x180019b62  mov     rax, [rax+38h]
0x180019b66  retn
```
