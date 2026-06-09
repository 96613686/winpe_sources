# ThrowPeFmtException

- ea: `0x180005400`
- end: `0x180005414`
- name: `ThrowPeFmtException`
- size: `20`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180004db8`
- `0x180004e98`
- `0x180004ef0`
- `0x1800050bc`
- `0x180005338`
- `0x180005934`
- `0x180005d5c`
- `0x180005f64`
- `0x1800061e4`
- `0x180006b98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000540d`

## pseudocode

```c
void ThrowPeFmtException()
{
  RaiseException(0xE0000001, 0, 0, 0);
}

```

## disassembly

```asm
0x180005400  xor     r9d, r9d
0x180005403  xor     r8d, r8d
0x180005406  xor     edx, edx
0x180005408  mov     ecx, 0E0000001h
0x18000540d  jmp     cs:__imp_RaiseException
```
