# DelayLoadCC

- ea: `0x18000b224`
- end: `0x18000b26e`
- name: `DelayLoadCC`
- size: `74`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b0c0`
- `0x18000b2dc`

## callees

- `0x18000b1cc`
- `0x18000b224`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b252`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b252`

## string_xrefs

- `0x18000b245`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (HMODULE)SHFusionLoadLibrary();
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
0x18000b224  sub     rsp, 28h
0x18000b228  cmp     cs:g_hinstCC, 0
0x18000b230  jnz     short loc_18000B264
0x18000b232  call    SHFusionLoadLibrary
0x18000b237  mov     cs:g_hinstCC, rax
0x18000b23e  test    rax, rax
0x18000b241  jnz     short loc_18000B264
0x18000b243  xor     edx, edx; hFile
0x18000b245  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18000b24c  mov     r8d, 4000h; dwFlags
0x18000b252  call    cs:__imp_LoadLibraryExW
0x18000b258  mov     cs:g_hinstCC, rax
0x18000b25f  test    rax, rax
0x18000b262  jz      short loc_18000B269
0x18000b264  mov     eax, 1
0x18000b269  add     rsp, 28h
0x18000b26d  retn
```
