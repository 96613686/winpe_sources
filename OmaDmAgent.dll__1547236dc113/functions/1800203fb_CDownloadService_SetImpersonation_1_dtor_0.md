# _CDownloadService::SetImpersonation_::_1_::dtor$0

- ea: `0x1800203fb`
- end: `0x180020407`
- name: `_CDownloadService::SetImpersonation_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002cec`

## pseudocode

```c
__int64 __fastcall CDownloadService::SetImpersonation_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(void ***)(a2 + 32));
}

```

## disassembly

```asm
0x1800203fb  mov     rcx, [rdx+20h]
0x180020402  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
