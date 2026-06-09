# InfApiAvailable(void)

- ea: `0x180080178`
- end: `0x1800801dc`
- name: `?InfApiAvailable@@YA_NXZ`
- size: `100`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18004f240`
- `0x18005cff4`

## callees

- `0x180080178`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800801c3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800801c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800801ae`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800801ae`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180080196`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180080196`

## string_xrefs

- `0x1800801a4`: `SetupOpenInfFileW`
- `0x180080189`: `setupapi.dll`

## pseudocode

```c
char InfApiAvailable(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx

  if ( !byte_1800D5089 )
  {
    Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
    v1 = Library;
    if ( Library )
    {
      if ( GetProcAddress(Library, "SetupOpenInfFileW") )
        byte_1800D5088 = 1;
      FreeLibrary(v1);
    }
    byte_1800D5089 = 1;
  }
  return byte_1800D5088;
}

```

## disassembly

```asm
0x180080178  push    rbx
0x18008017a  sub     rsp, 20h
0x18008017e  cmp     cs:byte_1800D5089, 0
0x180080185  jnz     short loc_1800801D0
0x180080187  xor     edx, edx; hFile
0x180080189  lea     rcx, aSetupapiDll_0; "setupapi.dll"
0x180080190  mov     r8d, 800h; dwFlags
0x180080196  call    cs:__imp_LoadLibraryExW
0x18008019c  mov     rbx, rax
0x18008019f  test    rax, rax
0x1800801a2  jz      short loc_1800801C9
0x1800801a4  lea     rdx, aSetupopeninffi_0; "SetupOpenInfFileW"
0x1800801ab  mov     rcx, rax; hModule
0x1800801ae  call    cs:__imp_GetProcAddress
0x1800801b4  test    rax, rax
0x1800801b7  jz      short loc_1800801C0
0x1800801b9  mov     cs:byte_1800D5088, 1
0x1800801c0  mov     rcx, rbx; hLibModule
0x1800801c3  call    cs:__imp_FreeLibrary
0x1800801c9  mov     cs:byte_1800D5089, 1
0x1800801d0  mov     al, cs:byte_1800D5088
0x1800801d6  add     rsp, 20h
0x1800801da  pop     rbx
0x1800801db  retn
```
