# _CreateTenantGatewayEntryStruct_::_1_::dtor$1

- ea: `0x18001c3e4`
- end: `0x18001c3f0`
- name: `_CreateTenantGatewayEntryStruct_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fb38`

## pseudocode

```c
__int64 __fastcall CreateTenantGatewayEntryStruct_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 48), a2);
}

```

## disassembly

```asm
0x18001c3e4  mov     rcx, [rdx+30h]
0x18001c3eb  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
