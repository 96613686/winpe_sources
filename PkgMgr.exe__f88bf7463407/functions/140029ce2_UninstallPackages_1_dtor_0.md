# _UninstallPackages_::_1_::dtor$0

- ea: `0x140029ce2`
- end: `0x140029cee`
- name: `_UninstallPackages_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140007040`

## pseudocode

```c
void __fastcall UninstallPackages_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  AutoScz::~AutoScz((AutoScz *)(a2 + 56));
}

```

## disassembly

```asm
0x140029ce2  lea     rcx, [rdx+38h]; this
0x140029ce9  jmp     ??1AutoScz@@QEAA@XZ; AutoScz::~AutoScz(void)
```
