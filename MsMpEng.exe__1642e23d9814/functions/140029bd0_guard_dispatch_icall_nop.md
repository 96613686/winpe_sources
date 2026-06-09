# _guard_dispatch_icall_nop

- ea: `0x140029bd0`
- end: `0x140029bd2`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `89`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1400012b0`
- `0x140001a54`
- `0x140001be0`
- `0x140001fd8`
- `0x140002144`
- `0x14000229c`
- `0x140002780`
- `0x1400027d8`
- `0x1400027f8`
- `0x140002b18`
- `0x140002bd8`
- `0x140002df4`
- `0x1400031e4`
- `0x140003268`
- `0x1400034b0`
- `0x140003520`
- `0x14000361c`
- `0x1400038dc`
- `0x140003a30`
- `0x140003aec`
- `0x140003bf8`
- `0x140003d48`
- `0x140005b78`
- `0x140005c18`
- `0x140005ccc`
- `0x140006140`
- `0x1400069ec`
- `0x140007278`
- `0x140007350`
- `0x1400074cc`
- `0x140007614`
- `0x140007910`
- `0x140007c98`
- `0x140007e78`
- `0x140008048`
- `0x140008188`
- `0x1400081e0`
- `0x140008780`
- `0x1400087a0`
- `0x140008ac0`
- `0x140008af0`
- `0x140008b3c`
- `0x140009124`
- `0x140009188`
- `0x1400091e8`
- `0x1400098b0`
- `0x14000a02c`
- `0x14000a9f4`
- `0x14000aa30`
- `0x14000aec8`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140029bd0  jmp     rax
```
