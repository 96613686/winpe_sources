# __vcrt_getptd

- ea: `0x180008fc8`
- end: `0x180008fe1`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x1800081b0`
- `0x18000881c`
- `0x180008858`
- `0x1800088ac`
- `0x1800088c0`
- `0x1800088d4`
- `0x1800088ec`
- `0x180008904`
- `0x180008a80`
- `0x180008af8`
- `0x180008b50`
- `0x1800095ac`
- `0x180009af8`
- `0x18000a060`
- `0x18000a310`
- `0x18000a530`
- `0x18000a8fc`
- `0x18000a994`
- `0x18000a9c4`

## callees

- `0x180007268`
- `0x180008fc8`
- `0x180008fe4`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort_0();
  return result;
}

```

## disassembly

```asm
0x180008fc8  sub     rsp, 28h
0x180008fcc  call    __vcrt_getptd_noexit
0x180008fd1  test    rax, rax
0x180008fd4  jz      short loc_180008FDB
0x180008fd6  add     rsp, 28h
0x180008fda  retn
0x180008fdb  call    abort_0
```
