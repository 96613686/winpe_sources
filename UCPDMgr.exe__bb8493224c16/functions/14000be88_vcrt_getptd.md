# __vcrt_getptd

- ea: `0x14000be88`
- end: `0x14000bea1`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b1d8`
- `0x14000b874`
- `0x14000b8b4`
- `0x14000b910`
- `0x14000b928`
- `0x14000b940`
- `0x14000b960`
- `0x14000b980`
- `0x14000ba50`
- `0x14000bad8`
- `0x14000bb3c`
- `0x14000bba8`
- `0x14000bbc0`
- `0x14000c4a4`
- `0x14000c9e4`
- `0x14000cf60`
- `0x14000d20c`
- `0x14000d4b0`
- `0x14000d88c`
- `0x14000d928`
- `0x14000d960`

## callees

- `0x14000a353`
- `0x14000be88`
- `0x14000bea8`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x14000be88  sub     rsp, 28h
0x14000be8c  call    __vcrt_getptd_noexit
0x14000be91  test    rax, rax
0x14000be94  jz      short loc_14000BE9B
0x14000be96  add     rsp, 28h
0x14000be9a  retn
0x14000be9b  call    abort
```
