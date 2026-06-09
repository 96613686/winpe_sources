# _CreateTenantGatewayEntryStruct_::_1_::dtor$0

- ea: `0x18001c3d2`
- end: `0x18001c3de`
- name: `_CreateTenantGatewayEntryStruct_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fb60`

## pseudocode

```c
__int64 __fastcall CreateTenantGatewayEntryStruct_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(*(_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x18001c3d2  mov     rcx, [rdx+28h]
0x18001c3d9  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
