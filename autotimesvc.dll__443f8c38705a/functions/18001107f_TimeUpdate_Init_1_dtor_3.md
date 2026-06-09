# _TimeUpdate::Init_::_1_::dtor$3

- ea: `0x18001107f`
- end: `0x18001108b`
- name: `_TimeUpdate::Init_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000567c`

## pseudocode

```c
__int64 __fastcall TimeUpdate::Init_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::future<long>::~future<long>(a2 + 88);
}

```

## disassembly

```asm
0x18001107f  lea     rcx, [rdx+58h]
0x180011086  jmp     ??1?$future@J@std@@QEAA@XZ; std::future<long>::~future<long>(void)
```
