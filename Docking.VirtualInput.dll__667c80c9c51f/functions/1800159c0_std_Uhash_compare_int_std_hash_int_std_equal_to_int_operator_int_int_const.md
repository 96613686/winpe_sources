# std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(int const &)

- ea: `0x1800159c0`
- end: `0x1800159ea`
- name: `??$?RH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_KAEBH@Z`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016100`
- `0x180019b00`
- `0x180019e08`

## callees

- `0x18000b810`
- `0x180016ff0`

## pseudocode

```c
__int64 __fastcall std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int>(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
  return std::_Conditionally_enabled_hash<int,1>::operator()(a2);
}

```

## disassembly

```asm
0x1800159c0  mov     [rsp+arg_8], rdx
0x1800159c5  mov     [rsp+arg_0], rcx
0x1800159ca  sub     rsp, 28h
0x1800159ce  mov     rax, [rsp+28h+arg_0]
0x1800159d3  mov     rcx, rax
0x1800159d6  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800159db  mov     rcx, [rsp+28h+arg_8]
0x1800159e0  call    ??R?$_Conditionally_enabled_hash@H$00@std@@SA_KAEBH@Z; std::_Conditionally_enabled_hash<int,1>::operator()(int const &)
0x1800159e5  add     rsp, 28h
0x1800159e9  retn
```
