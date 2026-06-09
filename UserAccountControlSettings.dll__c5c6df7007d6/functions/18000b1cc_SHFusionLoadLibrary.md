# SHFusionLoadLibrary

- ea: `0x18000b1cc`
- end: `0x18000b21c`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b224`

## callees

- `0x18000b030`
- `0x18000b0a0`
- `0x18000b1cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b200`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b200`

## string_xrefs

- `0x18000b1f3`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18000b1cc  mov     [rsp+ulCookie], rcx
0x18000b1d1  push    rbx
0x18000b1d2  sub     rsp, 20h
0x18000b1d6  lea     rcx, [rsp+28h+ulCookie]
0x18000b1db  mov     [rsp+28h+ulCookie], 0
0x18000b1e4  call    SHActivateContext
0x18000b1e9  test    eax, eax
0x18000b1eb  jnz     short loc_18000B1F1
0x18000b1ed  xor     eax, eax
0x18000b1ef  jmp     short loc_18000B216
0x18000b1f1  xor     edx, edx; hFile
0x18000b1f3  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18000b1fa  mov     r8d, 4000h; dwFlags
0x18000b200  call    cs:__imp_LoadLibraryExW
0x18000b206  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18000b20b  mov     rbx, rax
0x18000b20e  call    SHDeactivateContext
0x18000b213  mov     rax, rbx
0x18000b216  add     rsp, 20h
0x18000b21a  pop     rbx
0x18000b21b  retn
```
