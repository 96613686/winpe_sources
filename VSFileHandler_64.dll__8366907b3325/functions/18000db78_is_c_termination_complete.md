# _is_c_termination_complete

- ea: `0x18000db78`
- end: `0x18000db7f`
- name: `_is_c_termination_complete`
- size: `7`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007848`

## pseudocode

```c
int __cdecl is_c_termination_complete()
{
  return dword_18003E308;
}

```

## disassembly

```asm
0x18000db78  mov     eax, cs:dword_18003E308
0x18000db7e  retn
```
