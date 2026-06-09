# DelayLoadCC()

- ea: `0x40a372`
- end: `0x40a3ae`
- name: `_DelayLoadCC@0`
- size: `60`
- prototype: `BOOL __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40a256`

## callees

- `0x40a32f`
- `0x40a372`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x40a398`
- `KERNEL32!LoadLibraryExW` at `0x40a398`

## string_xrefs

- `0x40a393`: `comctl32.dll`

## pseudocode

```c
BOOL __stdcall DelayLoadCC()
{
  HMODULE Library; // ecx

  Library = (HMODULE)g_hinstCC;
  if ( !g_hinstCC )
  {
    Library = (HMODULE)SHFusionLoadLibrary();
    g_hinstCC = (int)Library;
    if ( !Library )
    {
      Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
      g_hinstCC = (int)Library;
    }
  }
  return Library != 0;
}

```

## disassembly

```asm
0x40a372  mov     ecx, _g_hinstCC
0x40a378  test    ecx, ecx
0x40a37a  jnz     short loc_40A3A6
0x40a37c  call    _SHFusionLoadLibrary@4; SHFusionLoadLibrary(x)
0x40a381  mov     ecx, eax
0x40a383  mov     _g_hinstCC, ecx
0x40a389  test    ecx, ecx
0x40a38b  jnz     short loc_40A3A6
0x40a38d  push    4000h; dwFlags
0x40a392  push    eax; hFile
0x40a393  push    offset aComctl32Dll; "comctl32.dll"
0x40a398  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x40a39e  mov     ecx, eax
0x40a3a0  mov     _g_hinstCC, ecx
0x40a3a6  xor     eax, eax
0x40a3a8  test    ecx, ecx
0x40a3aa  setnz   al
0x40a3ad  retn
```
