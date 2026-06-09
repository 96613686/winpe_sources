# ___vcrt_getptd

- ea: `0x40943c`
- end: `0x40944a`
- name: `___vcrt_getptd`
- size: `14`
- prototype: `int()`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x40900e`
- `0x409066`
- `0x4090b1`
- `0x409107`
- `0x409110`
- `0x4098e9`
- `0x409a93`
- `0x409ab7`
- `0x40a3ab`
- `0x40a76e`
- `0x40a932`
- `0x40ab0d`
- `0x40acdc`
- `0x40ad1b`
- `0x40ad7d`
- `0x40af8c`

## callees

- `0x40944a`
- `0x40c30b`

## pseudocode

```c
int __vcrt_getptd()
{
  int result; // eax

  result = __vcrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x40943c  call    ___vcrt_getptd_noexit
0x409441  test    eax, eax
0x409443  jz      _abort
0x409449  retn
```
