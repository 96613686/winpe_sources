# Platform::Details::ReCreateFromException(Platform::Exception *)

- ea: `0x140002910`
- end: `0x140002916`
- name: `?ReCreateFromException@Details@Platform@@YAJPE$AAVException@2@@Z_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140031a10`

## import_xrefs

- `wincorlib!?ReCreateFromException@Details@Platform@@YAJPE$AAVException@2@@Z` at `0x140002910`

## pseudocode

```c
// attributes: thunk
__int64 Platform::Details::ReCreateFromException()
{
  return __imp_?ReCreateFromException@Details@Platform@@YAJPE$AAVException@2@@Z();
}

```

## disassembly

```asm
0x140002910  jmp     cs:__imp_?ReCreateFromException@Details@Platform@@YAJPE$AAVException@2@@Z
```
