# _TimeUpdate::Init_::_1_::dtor$2

- ea: `0x18001106d`
- end: `0x180011079`
- name: `_TimeUpdate::Init_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005688`

## pseudocode

```c
__int64 __fastcall TimeUpdate::Init_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::promise<long>::~promise<long>(a2 + 112);
}

```

## disassembly

```asm
0x18001106d  lea     rcx, [rdx+70h]
0x180011074  jmp     ??1?$promise@J@std@@QEAA@XZ; std::promise<long>::~promise<long>(void)
```
