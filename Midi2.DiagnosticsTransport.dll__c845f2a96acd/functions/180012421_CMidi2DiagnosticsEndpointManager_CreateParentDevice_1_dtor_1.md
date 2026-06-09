# _CMidi2DiagnosticsEndpointManager::CreateParentDevice_::_1_::dtor$1

- ea: `0x180012421`
- end: `0x18001242d`
- name: `_CMidi2DiagnosticsEndpointManager::CreateParentDevice_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsEndpointManager::CreateParentDevice_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 192));
}

```

## disassembly

```asm
0x180012421  lea     rcx, [rdx+0C0h]
0x180012428  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
