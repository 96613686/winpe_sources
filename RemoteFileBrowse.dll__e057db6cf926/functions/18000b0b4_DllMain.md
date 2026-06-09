# DllMain

- ea: `0x18000b0b4`
- end: `0x18000b0e4`
- name: `DllMain`
- size: `48`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001ea4`

## callees

- `0x18000a0e8`
- `0x18000b0b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0d0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason != 1 )
    return 1;
  g_hInstance = hinstDLL;
  if ( (unsigned int)LoadLocalizedString() )
    return 1;
  SetLastError(0xEu);
  return 0;
}

```

## disassembly

```asm
0x18000b0b4  sub     rsp, 28h
0x18000b0b8  cmp     edx, 1
0x18000b0bb  jnz     short loc_18000B0DA
0x18000b0bd  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18000b0c4  call    ?LoadLocalizedString@@YAHXZ; LoadLocalizedString(void)
0x18000b0c9  test    eax, eax
0x18000b0cb  jnz     short loc_18000B0DA
0x18000b0cd  lea     ecx, [rax+0Eh]; dwErrCode
0x18000b0d0  call    cs:__imp_SetLastError
0x18000b0d6  xor     eax, eax
0x18000b0d8  jmp     short loc_18000B0DF
0x18000b0da  mov     eax, 1
0x18000b0df  add     rsp, 28h
0x18000b0e3  retn
```
