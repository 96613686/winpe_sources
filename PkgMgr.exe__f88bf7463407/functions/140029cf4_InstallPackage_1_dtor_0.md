# _InstallPackage_::_1_::dtor$0

- ea: `0x140029cf4`
- end: `0x140029d00`
- name: `_InstallPackage_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140007040`

## pseudocode

```c
void __fastcall InstallPackage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoScz::~AutoScz((AutoScz *)(a2 + 48));
}

```

## disassembly

```asm
0x140029cf4  lea     rcx, [rdx+30h]; this
0x140029cfb  jmp     ??1AutoScz@@QEAA@XZ; AutoScz::~AutoScz(void)
```
