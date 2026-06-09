# Dns_GetBufferLengthForStringCopy_New

- ea: `0x180013538`
- end: `0x18001353d`
- name: `Dns_GetBufferLengthForStringCopy_New`
- size: `5`
- prototype: `__int64 __fastcall(const CHAR *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013544`
- `0x1800135ec`
- `0x18001399c`

## callees

- `0x180013344`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Dns_GetBufferLengthForStringCopy_New(const CHAR *a1, int a2)
{
  return Dns_GetBufferLengthForStringCopyU(a1, a2);
}

```

## disassembly

```asm
0x180013538  jmp     Dns_GetBufferLengthForStringCopyU
```
