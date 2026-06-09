# SHFusionLoadLibrary

- ea: `0x18002a220`
- end: `0x18002a270`
- name: `SHFusionLoadLibrary`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a278`

## callees

- `0x18002a084`
- `0x18002a0f4`
- `0x18002a220`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002a254`
- `KERNEL32!LoadLibraryExW` at `0x18002a254`

## string_xrefs

- `0x18002a247`: `comctl32.dll`

## pseudocode

```c
HMODULE SHFusionLoadLibrary()
{
  HMODULE Library; // rbx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  if ( !(unsigned int)SHActivateContext(&ulCookie) )
    return 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
  SHDeactivateContext(ulCookie);
  return Library;
}

```

## disassembly

```asm
0x18002a220  mov     [rsp+ulCookie], rcx
0x18002a225  push    rbx
0x18002a226  sub     rsp, 20h
0x18002a22a  lea     rcx, [rsp+28h+ulCookie]
0x18002a22f  mov     [rsp+28h+ulCookie], 0
0x18002a238  call    SHActivateContext
0x18002a23d  test    eax, eax
0x18002a23f  jnz     short loc_18002A245
0x18002a241  xor     eax, eax
0x18002a243  jmp     short loc_18002A26A
0x18002a245  xor     edx, edx; hFile
0x18002a247  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18002a24e  mov     r8d, 4000h; dwFlags
0x18002a254  call    cs:__imp_LoadLibraryExW
0x18002a25a  mov     rcx, [rsp+28h+ulCookie]; ulCookie
0x18002a25f  mov     rbx, rax
0x18002a262  call    SHDeactivateContext
0x18002a267  mov     rax, rbx
0x18002a26a  add     rsp, 20h
0x18002a26e  pop     rbx
0x18002a26f  retn
```
