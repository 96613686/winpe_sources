# _TimeUpdate::Init_::_1_::dtor$14

- ea: `0x1800110a3`
- end: `0x1800110af`
- name: `_TimeUpdate::Init_::_1_::dtor$14`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000567c`

## pseudocode

```c
__int64 __fastcall TimeUpdate::Init_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  return std::future<long>::~future<long>(a2 + 64);
}

```

## disassembly

```asm
0x1800110a3  lea     rcx, [rdx+40h]
0x1800110aa  jmp     ??1?$future@J@std@@QEAA@XZ; std::future<long>::~future<long>(void)
```
