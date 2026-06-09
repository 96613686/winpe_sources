# _UpdateRPCCacheEntry_::_1_::dtor$1

- ea: `0x18000fbb2`
- end: `0x18000fbbe`
- name: `_UpdateRPCCacheEntry_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800036c0`

## pseudocode

```c
__int64 __fastcall UpdateRPCCacheEntry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::string::~string(a2 + 80);
}

```

## disassembly

```asm
0x18000fbb2  lea     rcx, [rdx+50h]
0x18000fbb9  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@XZ; std::string::~string(void)
```
