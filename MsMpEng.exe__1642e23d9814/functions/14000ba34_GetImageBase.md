# _GetImageBase

- ea: `0x14000ba34`
- end: `0x14000ba46`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c63c`
- `0x14000c830`
- `0x14000cbac`
- `0x14000cc84`
- `0x14000cd5c`
- `0x14000d7ac`
- `0x14000da10`
- `0x14000dd18`
- `0x14000de38`
- `0x14000df78`
- `0x14000ed04`
- `0x14000ee90`
- `0x14000f238`
- `0x14000f320`

## callees

- `0x14000c2e0`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(sub_14000C2E0() + 96);
}

```

## disassembly

```asm
0x14000ba34  sub     rsp, 28h
0x14000ba38  call    sub_14000C2E0
0x14000ba3d  mov     rax, [rax+60h]
0x14000ba41  add     rsp, 28h
0x14000ba45  retn
```
