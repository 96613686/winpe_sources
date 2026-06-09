# avcodec_descriptor_get

- ea: `0x18001ba1a`
- end: `0x18001ba20`
- name: `avcodec_descriptor_get`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002318`
- `0x18000a920`
- `0x18000be8c`
- `0x180013478`

## import_xrefs

- `avcodec_ms!avcodec_descriptor_get` at `0x18001ba1a`

## pseudocode

```c
// attributes: thunk
__int64 avcodec_descriptor_get()
{
  return __imp_avcodec_descriptor_get();
}

```

## disassembly

```asm
0x18001ba1a  jmp     cs:__imp_avcodec_descriptor_get
```
