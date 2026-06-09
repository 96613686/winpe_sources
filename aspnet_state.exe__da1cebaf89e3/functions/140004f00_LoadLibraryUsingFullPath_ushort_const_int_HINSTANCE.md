# LoadLibraryUsingFullPath(ushort const *,int,HINSTANCE__ * *)

- ea: `0x140004f00`
- end: `0x140004f06`
- name: `?LoadLibraryUsingFullPath@@YAJPEBGHPEAPEAUHINSTANCE__@@@Z`
- size: `6`
- prototype: `int __fastcall(const unsigned __int16 *, int, HINSTANCE *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400011ac`

## import_xrefs

- `webengine4!LoadLibraryUsingFullPath` at `0x140004f00`

## pseudocode

```c
// attributes: thunk
int __fastcall LoadLibraryUsingFullPath(const unsigned __int16 *a1, int a2, HINSTANCE *a3)
{
  return __imp_?LoadLibraryUsingFullPath@@YAJPEBGHPEAPEAUHINSTANCE__@@@Z(a1, a2, a3);
}

```

## disassembly

```asm
0x140004f00  jmp     cs:__imp_?LoadLibraryUsingFullPath@@YAJPEBGHPEAPEAUHINSTANCE__@@@Z
```
