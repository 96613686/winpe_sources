# DelayLoadCC

- ea: `0x180012c5c`
- end: `0x180012cad`
- name: `DelayLoadCC`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001280`
- `0x180012a60`
- `0x180012dd4`

## callees

- `0x180012b6c`
- `0x180012c5c`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180012c91`
- `KERNEL32!LoadLibraryExA` at `0x180012c91`

## string_xrefs

- `0x180012c6a`: `comctl32.dll`
- `0x180012c84`: `comctl32.dll`

## pseudocode

```c
__int64 DelayLoadCC()
{
  __int64 result; // rax

  if ( g_hinstCC )
    return 1;
  g_hinstCC = (HMODULE)SHFusionLoadLibrary("comctl32.dll");
  if ( g_hinstCC )
    return 1;
  result = (__int64)LoadLibraryExA("comctl32.dll", 0, 0x4000u);
  g_hinstCC = (HMODULE)result;
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180012c5c  sub     rsp, 28h
0x180012c60  cmp     cs:g_hinstCC, 0
0x180012c68  jnz     short loc_180012CA3
0x180012c6a  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180012c71  call    SHFusionLoadLibrary
0x180012c76  mov     cs:g_hinstCC, rax
0x180012c7d  test    rax, rax
0x180012c80  jnz     short loc_180012CA3
0x180012c82  xor     edx, edx; hFile
0x180012c84  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180012c8b  mov     r8d, 4000h; dwFlags
0x180012c91  call    cs:__imp_LoadLibraryExA
0x180012c97  mov     cs:g_hinstCC, rax
0x180012c9e  test    rax, rax
0x180012ca1  jz      short loc_180012CA8
0x180012ca3  mov     eax, 1
0x180012ca8  add     rsp, 28h
0x180012cac  retn
```
