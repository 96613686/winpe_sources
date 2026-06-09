# _FindSessionIDFromUserSid_::_1_::dtor$1

- ea: `0x14001b15a`
- end: `0x14001b166`
- name: `_FindSessionIDFromUserSid_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003c10`

## pseudocode

```c
__int64 __fastcall FindSessionIDFromUserSid_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(a2 + 184, a2);
}

```

## disassembly

```asm
0x14001b15a  lea     rcx, [rdx+0B8h]
0x14001b161  jmp     ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
```
