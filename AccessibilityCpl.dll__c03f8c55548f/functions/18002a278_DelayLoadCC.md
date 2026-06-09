# DelayLoadCC

- ea: `0x18002a278`
- end: `0x18002a2c2`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a114`
- `0x18002a364`

## callees

- `0x18002a220`
- `0x18002a278`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002a2a6`
- `KERNEL32!LoadLibraryExW` at `0x18002a2a6`

## string_xrefs

- `0x18002a299`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = SHFusionLoadLibrary();
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  g_hinstCC = (HMODULE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18002a278  sub     rsp, 28h
0x18002a27c  cmp     cs:g_hinstCC, 0
0x18002a284  jnz     short loc_18002A2B8
0x18002a286  call    SHFusionLoadLibrary
0x18002a28b  mov     cs:g_hinstCC, rax
0x18002a292  test    rax, rax
0x18002a295  jnz     short loc_18002A2B8
0x18002a297  xor     edx, edx; hFile
0x18002a299  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002a2a0  mov     r8d, 4000h; dwFlags
0x18002a2a6  call    cs:__imp_LoadLibraryExW
0x18002a2ac  mov     cs:g_hinstCC, rax
0x18002a2b3  test    rax, rax
0x18002a2b6  jz      short loc_18002A2BD
0x18002a2b8  mov     eax, 1
0x18002a2bd  add     rsp, 28h
0x18002a2c1  retn
```
