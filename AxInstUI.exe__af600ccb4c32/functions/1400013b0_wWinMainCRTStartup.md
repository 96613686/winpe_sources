# wWinMainCRTStartup

- ea: `0x1400013b0`
- end: `0x1400013c2`
- name: `wWinMainCRTStartup`
- size: `18`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001140`
- `0x1400015e4`

## pseudocode

```c
int wWinMainCRTStartup()
{
  _security_init_cookie();
  return _wmainCRTStartup();
}

```

## disassembly

```asm
0x1400013b0  sub     rsp, 28h
0x1400013b4  call    __security_init_cookie
0x1400013b9  add     rsp, 28h
0x1400013bd  jmp     __wmainCRTStartup
```
