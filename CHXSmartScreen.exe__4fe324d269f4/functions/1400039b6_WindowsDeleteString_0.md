# WindowsDeleteString_0

- ea: `0x1400039b6`
- end: `0x1400039bc`
- name: `WindowsDeleteString_0`
- size: `6`
- prototype: `HRESULT __stdcall(HSTRING string)`
- caller_count: `51`
- callee_count: `0`
- tags: ``

## callers

- `0x140003bbc`
- `0x140004518`
- `0x140005bb0`
- `0x140005d24`
- `0x140005fa4`
- `0x140008550`
- `0x140008900`
- `0x14000898c`
- `0x14000bae0`
- `0x14000bd70`
- `0x14000bfd8`
- `0x14000c280`
- `0x14000c784`
- `0x14000d3c0`
- `0x140011cd0`
- `0x1400129fc`
- `0x1400151c0`
- `0x1400152b8`
- `0x140016c10`
- `0x140016db0`
- `0x140017f94`
- `0x14001a050`
- `0x14001a120`
- `0x140021360`
- `0x1400232c0`
- `0x1400234e0`
- `0x140024894`
- `0x140024c88`
- `0x140024de0`
- `0x140024e4c`
- `0x140024ed0`
- `0x1400252c0`
- `0x140025430`
- `0x140025610`
- `0x140025a20`
- `0x140025d4c`
- `0x140025d94`
- `0x1400265d0`
- `0x1400273b0`
- `0x1400274d0`
- `0x140027990`
- `0x140027a40`
- `0x140027b10`
- `0x140027cc0`
- `0x14002983c`
- `0x1400298dc`
- `0x14002a6c0`
- `0x14002b69c`
- `0x14002c8e4`
- `0x14002c958`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400039b6`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall WindowsDeleteString_0(HSTRING string)
{
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x1400039b6  jmp     cs:__imp_WindowsDeleteString
```
