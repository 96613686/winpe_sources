# AspnetLoadResourceDLL(ushort *,ushort *,int,HINSTANCE__ * *,Names::LanguageIdType)

- ea: `0x140004f24`
- end: `0x140004f2a`
- name: `?AspnetLoadResourceDLL@@YAJPEAG0HPEAPEAUHINSTANCE__@@W4LanguageIdType@Names@@@Z`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002a78`

## import_xrefs

- `webengine4!AspnetLoadResourceDLL` at `0x140004f24`

## pseudocode

```c
// attributes: thunk
__int64 AspnetLoadResourceDLL()
{
  return __imp_?AspnetLoadResourceDLL@@YAJPEAG0HPEAPEAUHINSTANCE__@@W4LanguageIdType@Names@@@Z();
}

```

## disassembly

```asm
0x140004f24  jmp     cs:__imp_?AspnetLoadResourceDLL@@YAJPEAG0HPEAPEAUHINSTANCE__@@W4LanguageIdType@Names@@@Z
```
