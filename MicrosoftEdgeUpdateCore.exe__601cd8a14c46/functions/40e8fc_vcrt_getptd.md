# ___vcrt_getptd

- ea: `0x40e8fc`
- end: `0x40e90a`
- name: `___vcrt_getptd`
- size: `14`
- prototype: `int()`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x40e78e`
- `0x40e7e6`
- `0x40e831`
- `0x40e887`
- `0x40e890`
- `0x40ef49`
- `0x40f0f3`
- `0x40f117`
- `0x40f497`
- `0x40f85a`
- `0x40fa1e`
- `0x40fbed`
- `0x40fdbc`
- `0x40fdfb`
- `0x40fe5d`
- `0x41006c`

## callees

- `0x40e90a`
- `0x4116b0`

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
0x40e8fc  call    ___vcrt_getptd_noexit
0x40e901  test    eax, eax
0x40e903  jz      _abort
0x40e909  retn
```
