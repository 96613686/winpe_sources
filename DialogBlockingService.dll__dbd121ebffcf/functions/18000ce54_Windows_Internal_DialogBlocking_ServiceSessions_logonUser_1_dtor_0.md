# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$0

- ea: `0x18000ce54`
- end: `0x18000ce60`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003f84`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr>((Windows::Internal::DialogBlocking::HookMgr **)(a2 + 176));
}

```

## disassembly

```asm
0x18000ce54  lea     rcx, [rdx+0B0h]
0x18000ce5b  jmp     ??1?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr>(void)
```
