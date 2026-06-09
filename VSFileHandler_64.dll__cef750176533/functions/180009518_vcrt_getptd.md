# __vcrt_getptd

- ea: `0x180009518`
- end: `0x180009531`
- name: `__vcrt_getptd`
- size: `25`
- prototype: `__int64()`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180008500`
- `0x180008b3c`
- `0x180008b78`
- `0x180008bcc`
- `0x180008be0`
- `0x180008bf4`
- `0x180008c0c`
- `0x180008c24`
- `0x180008cf0`
- `0x180008d64`
- `0x180008db8`
- `0x180009af4`
- `0x180009ff8`
- `0x18000a578`
- `0x18000a80c`
- `0x18000aa20`
- `0x18000ae04`
- `0x18000ae88`
- `0x18000aeb8`

## callees

- `0x180009518`
- `0x180009534`
- `0x18000e7c8`

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
0x180009518  sub     rsp, 28h
0x18000951c  call    __vcrt_getptd_noexit
0x180009521  test    rax, rax
0x180009524  jz      short loc_18000952B
0x180009526  add     rsp, 28h
0x18000952a  retn
0x18000952b  call    abort
```
