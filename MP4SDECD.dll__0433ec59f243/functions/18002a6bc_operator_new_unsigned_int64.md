# operator new[](unsigned __int64)

- ea: `0x18002a6bc`
- end: `0x18002a6c1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e990`
- `0x180012cd0`
- `0x180012df8`
- `0x180012e50`
- `0x180013fa0`
- `0x1800149ac`
- `0x18001863c`
- `0x18001932c`
- `0x18001dea0`
- `0x18001e6c4`
- `0x18001e858`
- `0x18001ea58`
- `0x180025cbc`
- `0x18002ce8c`

## callees

- `0x18002a670`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x18002a6bc  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
