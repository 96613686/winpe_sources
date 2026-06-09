# _Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor$2

- ea: `0x18000cd75`
- end: `0x18000cd81`
- name: `_Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008950`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand_::_1_::dtor_2(
        __int64 a1,
        unsigned __int64 a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)(a2 + 40), a2);
}

```

## disassembly

```asm
0x18000cd75  lea     rcx, [rdx+28h]
0x18000cd7c  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
