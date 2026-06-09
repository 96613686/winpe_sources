# _guard_dispatch_icall

- ea: `0x14001ae00`
- end: `0x14001ae06`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `296`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400014c4`
- `0x1400016d4`
- `0x140001790`
- `0x140001a50`
- `0x140001a84`
- `0x140001ac0`
- `0x140001bd0`
- `0x140001cf0`
- `0x140001d64`
- `0x140001e70`
- `0x1400024b8`
- `0x140002500`
- `0x1400025d0`
- `0x140002630`
- `0x140002ab0`
- `0x140002b80`
- `0x140003000`
- `0x1400030f0`
- `0x1400031d0`
- `0x140003330`
- `0x1400037d0`
- `0x140003a80`
- `0x140004050`
- `0x1400040b0`
- `0x1400041d0`
- `0x140004258`
- `0x140004318`
- `0x14000441c`
- `0x1400044dc`
- `0x14000458c`
- `0x140004650`
- `0x14000472c`
- `0x140004810`
- `0x1400048c8`
- `0x14000498c`
- `0x140004a44`
- `0x140004b24`
- `0x140004bf0`
- `0x140005130`
- `0x1400051b8`
- `0x140005298`
- `0x140005830`
- `0x140005900`
- `0x1400059b0`
- `0x140005bb0`
- `0x140005cb0`
- `0x140005d80`
- `0x140005dcc`
- `0x140005f38`
- `0x140006108`

## callees

- `0x14001ae30`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x14001ae00  jmp     cs:__guard_dispatch_icall_fptr
```
