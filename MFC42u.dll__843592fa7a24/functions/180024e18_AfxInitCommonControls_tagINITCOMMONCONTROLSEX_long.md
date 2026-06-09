# _AfxInitCommonControls(tagINITCOMMONCONTROLSEX *,long)

- ea: `0x180024e18`
- end: `0x180024e93`
- name: `?_AfxInitCommonControls@@YAJPEAUtagINITCOMMONCONTROLSEX@@J@Z`
- size: `123`
- prototype: `__int64 __fastcall(INITCOMMONCONTROLSEX *picce, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008930`

## callees

- `0x180024e18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024e4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180024e35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180024e35`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024e82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024e82`
- `COMCTL32!InitCommonControlsEx` at `0x180024e74`
- `COMCTL32!InitCommonControlsEx` at `0x180024e74`
- `COMCTL32!__imp_InitCommonControls` at `0x180024e67`
- `COMCTL32!__imp_InitCommonControls` at `0x180024e67`

## string_xrefs

- `0x180024e28`: `COMCTL32.DLL`
- `0x180024e43`: `InitCommonControlsEx`

## pseudocode

```c
HMODULE __fastcall _AfxInitCommonControls(INITCOMMONCONTROLSEX *picce, unsigned int a2)
{
  HMODULE result; // rax
  HMODULE v5; // rsi
  unsigned int v6; // ebx

  result = LoadLibraryExA("COMCTL32.DLL", 0, 0x800u);
  v5 = result;
  if ( result )
  {
    v6 = 0;
    if ( GetProcAddress(result, "InitCommonControlsEx") )
    {
      if ( InitCommonControlsEx(picce) )
        v6 = a2;
    }
    else if ( (a2 & 0x3FC0) == a2 )
    {
      InitCommonControls();
      v6 = 16320;
    }
    FreeLibrary(v5);
    return (HMODULE)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180024e18  push    rbx
0x180024e1a  push    rbp
0x180024e1b  push    rsi
0x180024e1c  push    rdi
0x180024e1d  sub     rsp, 28h
0x180024e21  mov     edi, edx
0x180024e23  mov     rbp, rcx
0x180024e26  xor     edx, edx; hFile
0x180024e28  lea     rcx, ModuleName; "COMCTL32.DLL"
0x180024e2f  mov     r8d, 800h; dwFlags
0x180024e35  call    cs:__imp_LoadLibraryExA
0x180024e3b  mov     rsi, rax
0x180024e3e  test    rax, rax
0x180024e41  jz      short loc_180024E8A
0x180024e43  lea     rdx, aInitcommoncont_0; "InitCommonControlsEx"
0x180024e4a  mov     rcx, rsi; hModule
0x180024e4d  xor     ebx, ebx
0x180024e4f  call    cs:__imp_GetProcAddress
0x180024e55  test    rax, rax
0x180024e58  jnz     short loc_180024E71
0x180024e5a  mov     eax, edi
0x180024e5c  mov     ebp, 3FC0h
0x180024e61  and     eax, ebp
0x180024e63  cmp     eax, edi
0x180024e65  jnz     short loc_180024E7F
0x180024e67  call    cs:__imp_InitCommonControls
0x180024e6d  mov     ebx, ebp
0x180024e6f  jmp     short loc_180024E7F
0x180024e71  mov     rcx, rbp; picce
0x180024e74  call    cs:__imp_InitCommonControlsEx
0x180024e7a  test    eax, eax
0x180024e7c  cmovnz  ebx, edi
0x180024e7f  mov     rcx, rsi; hLibModule
0x180024e82  call    cs:__imp_FreeLibrary
0x180024e88  mov     eax, ebx
0x180024e8a  add     rsp, 28h
0x180024e8e  pop     rdi
0x180024e8f  pop     rsi
0x180024e90  pop     rbp
0x180024e91  pop     rbx
0x180024e92  retn
```
