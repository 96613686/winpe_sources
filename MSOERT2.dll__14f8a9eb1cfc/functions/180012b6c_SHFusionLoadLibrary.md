# SHFusionLoadLibrary

- ea: `0x180012b6c`
- end: `0x180012bb7`
- name: `SHFusionLoadLibrary`
- size: `75`
- prototype: `__int64 __fastcall(LPCSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012c5c`
- `0x180012e24`

## callees

- `0x1800129d8`
- `0x180012a40`
- `0x180012b6c`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x180012b9b`
- `KERNEL32!LoadLibraryExA` at `0x180012b9b`

## pseudocode

```c
HMODULE __fastcall SHFusionLoadLibrary(LPCSTR lpLibFileName)
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExA(lpLibFileName, 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180012b6c  push    rbx
0x180012b6e  sub     rsp, 20h
0x180012b72  mov     rbx, rcx
0x180012b75  mov     [rsp+28h+ulCookie], 0
0x180012b7e  lea     rcx, [rsp+28h+ulCookie]
0x180012b83  call    SHActivateContext
0x180012b88  test    eax, eax
0x180012b8a  jnz     short loc_180012B90
0x180012b8c  xor     eax, eax
0x180012b8e  jmp     short loc_180012BB1
0x180012b90  xor     edx, edx; hFile
0x180012b92  mov     r8d, 4000h; dwFlags
0x180012b98  mov     rcx, rbx; lpLibFileName
0x180012b9b  call    cs:__imp_LoadLibraryExA
0x180012ba1  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x180012ba6  mov     rbx, rax
0x180012ba9  call    SHDeactivateContext
0x180012bae  mov     rax, rbx
0x180012bb1  add     rsp, 20h
0x180012bb5  pop     rbx
0x180012bb6  retn
```
