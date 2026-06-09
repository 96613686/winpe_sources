# __winRT::__windowsCreateString(wchar_t const *,int,HSTRING__ * *)

- ea: `0x140002850`
- end: `0x140002855`
- name: `?__windowsCreateString@__winRT@@YAJPEB_WHPEAPEAUHSTRING__@@@Z`
- size: `5`
- prototype: `HRESULT __stdcall(PCNZWCH sourceString, UINT32 length, HSTRING *string)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x140008020`
- `0x140008060`
- `0x14000e540`
- `0x14000e5e0`
- `0x14000e630`
- `0x14000e6b0`
- `0x14000e6d0`
- `0x14000e700`
- `0x14000e740`
- `0x14001f400`
- `0x14001f440`
- `0x14001f480`
- `0x14001f4c0`
- `0x14001f500`
- `0x14001f560`
- `0x14001f5c0`
- `0x14001f6a0`
- `0x14001f7e0`
- `0x14001f820`
- `0x140023d70`
- `0x1400260b0`
- `0x140026100`
- `0x14002d940`
- `0x14002d980`
- `0x14002da20`
- `0x14002dac0`
- `0x14002db20`
- `0x14002dbc0`
- `0x14002dc40`
- `0x14002dc90`
- `0x14002dce0`
- `0x14002dd30`
- `0x14002dd70`

## callees

- `0x14000399e`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall __winRT::__windowsCreateString(PCNZWCH sourceString, UINT32 length, HSTRING *string)
{
  return WindowsCreateString_0(sourceString, length, string);
}

```

## disassembly

```asm
0x140002850  jmp     WindowsCreateString_0
```
