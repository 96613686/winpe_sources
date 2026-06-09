# _GetStringSIDFromUsername_::_1_::dtor$0

- ea: `0x14001b1c6`
- end: `0x14001b1d2`
- name: `_GetStringSIDFromUsername_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003c10`

## pseudocode

```c
__int64 __fastcall GetStringSIDFromUsername_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(*(_QWORD *)(a2 + 88), a2);
}

```

## disassembly

```asm
0x14001b1c6  mov     rcx, [rdx+58h]
0x14001b1cd  jmp     ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
```
