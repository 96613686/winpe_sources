# _ExecuteCommands::Execute_::_1_::dtor$1

- ea: `0x14000aaab`
- end: `0x14000aab7`
- name: `_ExecuteCommands::Execute_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000351c`

## pseudocode

```c
__int64 __fastcall ExecuteCommands::Execute_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::function<void (CommandSet const &,Command const &)>::~function<void (CommandSet const &,Command const &)>(
           *(_QWORD *)(a2 + 200),
           a2);
}

```

## disassembly

```asm
0x14000aaab  mov     rcx, [rdx+0C8h]
0x14000aab2  jmp     ??1?$function@$$A6AXAEBUCommandSet@@AEBUCommand@@@Z@std@@QEAA@XZ; std::function<void (CommandSet const &,Command const &)>::~function<void (CommandSet const &,Command const &)>(void)
```
