# avpriv_emms_asm

- ea: `0x1800226da`
- end: `0x1800226e0`
- name: `avpriv_emms_asm`
- size: `6`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180003f00`
- `0x180003f90`
- `0x180007460`
- `0x180008340`
- `0x18000a3cc`
- `0x180020ca0`

## import_xrefs

- `avutil_ms!avpriv_emms_asm` at `0x1800226da`

## pseudocode

```c
// attributes: thunk
__int64 avpriv_emms_asm()
{
  return __imp_avpriv_emms_asm();
}

```

## disassembly

```asm
0x1800226da  jmp     cs:__imp_avpriv_emms_asm
```
