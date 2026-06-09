# _RootCause::addRepair_::_1_::dtor$0

- ea: `0x18001118d`
- end: `0x18001119b`
- name: `_RootCause::addRepair_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `msvcrt!??1exception@@UEAA@XZ` at `0x180011194`

## pseudocode

```c
void __fastcall RootCause::addRepair_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  exception::~exception((exception *)(a2 + 40));
}

```

## disassembly

```asm
0x18001118d  lea     rcx, [rdx+28h]
0x180011194  jmp     cs:__imp_??1exception@@UEAA@XZ; exception::~exception(void)
```
