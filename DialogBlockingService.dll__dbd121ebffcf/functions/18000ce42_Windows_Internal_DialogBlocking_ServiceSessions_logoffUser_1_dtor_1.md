# _Windows::Internal::DialogBlocking::ServiceSessions::logoffUser_::_1_::dtor$1

- ea: `0x18000ce42`
- end: `0x18000ce4e`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logoffUser_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003f84`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logoffUser_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr>((Windows::Internal::DialogBlocking::HookMgr **)(a2 + 112));
}

```

## disassembly

```asm
0x18000ce42  lea     rcx, [rdx+70h]
0x18000ce49  jmp     ??1?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>::~unique_ptr<Windows::Internal::DialogBlocking::HookMgr>(void)
```
