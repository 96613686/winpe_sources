# Windows::Globalization::Spelling::SpellerFromCsapi::CCsapiLexicons::InitializeSpellDictionariesPath(ushort *)

- ea: `0x180092514`
- end: `0x180092550`
- name: `?InitializeSpellDictionariesPath@CCsapiLexicons@SpellerFromCsapi@Spelling@Globalization@Windows@@CA_NPEAG@Z`
- size: `60`
- prototype: `bool __fastcall(LPWSTR pszPath)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180092140`
- `0x180092d54`

## callees

- `0x180092514`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18009253b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x18009253b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180092522`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180092522`

## pseudocode

```c
bool __fastcall Windows::Globalization::Spelling::SpellerFromCsapi::CCsapiLexicons::InitializeSpellDictionariesPath(
        LPWSTR pszPath)
{
  return GetSystemWindowsDirectoryW(pszPath, 0x104u) - 1 <= 0x102
      && PathAppendW(pszPath, L"\\Globalization\\ELS\\SpellDictionaries\\");
}

```

## disassembly

```asm
0x180092514  push    rbx
0x180092516  sub     rsp, 20h
0x18009251a  mov     edx, 104h; uSize
0x18009251f  mov     rbx, rcx
0x180092522  call    cs:__imp_GetSystemWindowsDirectoryW
0x180092528  dec     eax
0x18009252a  cmp     eax, 102h
0x18009252f  ja      short loc_180092548
0x180092531  lea     rdx, aGlobalizationE; "\\Globalization\\ELS\\SpellDictionaries"...
0x180092538  mov     rcx, rbx; pszPath
0x18009253b  call    cs:__imp_PathAppendW
0x180092541  test    eax, eax
0x180092543  setnz   al
0x180092546  jmp     short loc_18009254A
0x180092548  xor     al, al
0x18009254a  add     rsp, 20h
0x18009254e  pop     rbx
0x18009254f  retn
```
