# DelayLoadCC

- ea: `0x180010900`
- end: `0x18001094a`
- name: `DelayLoadCC`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010668`
- `0x1800106f8`
- `0x180010b0c`

## callees

- `0x180010804`
- `0x180010900`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001092e`
- `KERNEL32!LoadLibraryExW` at `0x18001092e`

## string_xrefs

- `0x180010921`: `comctl32.dll`

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
0x180010900  sub     rsp, 28h
0x180010904  cmp     cs:g_hinstCC, 0
0x18001090c  jnz     short loc_180010940
0x18001090e  call    SHFusionLoadLibrary
0x180010913  mov     cs:g_hinstCC, rax
0x18001091a  test    rax, rax
0x18001091d  jnz     short loc_180010940
0x18001091f  xor     edx, edx; hFile
0x180010921  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180010928  mov     r8d, 4000h; dwFlags
0x18001092e  call    cs:__imp_LoadLibraryExW
0x180010934  mov     cs:g_hinstCC, rax
0x18001093b  test    rax, rax
0x18001093e  jz      short loc_180010945
0x180010940  mov     eax, 1
0x180010945  add     rsp, 28h
0x180010949  retn
```
