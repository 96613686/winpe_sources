# _AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$2

- ea: `0x18000c4a7`
- end: `0x18000c4b3`
- name: `_AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000887c`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSession::GetProcessNameFromProcessId_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 120);
}

```

## disassembly

```asm
0x18000c4a7  lea     rcx, [rdx+78h]
0x18000c4ae  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
