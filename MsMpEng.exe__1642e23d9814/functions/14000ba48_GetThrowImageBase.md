# _GetThrowImageBase

- ea: `0x14000ba48`
- end: `0x14000ba5a`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c63c`
- `0x14000c830`
- `0x14000ca28`
- `0x14000cae8`
- `0x14000cd5c`
- `0x14000d260`
- `0x14000dd18`
- `0x14000de38`
- `0x14000df78`
- `0x14000e1ac`
- `0x14000f238`

## callees

- `0x14000c2e0`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(sub_14000C2E0() + 104);
}

```

## disassembly

```asm
0x14000ba48  sub     rsp, 28h
0x14000ba4c  call    sub_14000C2E0
0x14000ba51  mov     rax, [rax+68h]
0x14000ba55  add     rsp, 28h
0x14000ba59  retn
```
