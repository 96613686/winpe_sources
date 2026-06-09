# SHFusionLoadLibrary

- ea: `0x180010804`
- end: `0x18001085c`
- name: `SHFusionLoadLibrary`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010900`

## callees

- `0x1800105f8`
- `0x180010804`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180010838`
- `KERNEL32!LoadLibraryExW` at `0x180010838`
- `KERNEL32!DeactivateActCtx` at `0x18001084d`
- `KERNEL32!DeactivateActCtx` at `0x18001084d`

## string_xrefs

- `0x18001082b`: `comctl32.dll`

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
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return Library;
}

```

## disassembly

```asm
0x180010804  mov     [rsp+ulCookie], rcx
0x180010809  push    rbx
0x18001080a  sub     rsp, 20h
0x18001080e  lea     rcx, [rsp+28h+ulCookie]
0x180010813  mov     [rsp+28h+ulCookie], 0
0x18001081c  call    SHActivateContext
0x180010821  test    eax, eax
0x180010823  jnz     short loc_180010829
0x180010825  xor     eax, eax
0x180010827  jmp     short loc_180010856
0x180010829  xor     edx, edx; hFile
0x18001082b  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180010832  mov     r8d, 4000h; dwFlags
0x180010838  call    cs:__imp_LoadLibraryExW
0x18001083e  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180010843  mov     rbx, rax
0x180010846  test    rdx, rdx
0x180010849  jz      short loc_180010853
0x18001084b  xor     ecx, ecx; dwFlags
0x18001084d  call    cs:__imp_DeactivateActCtx
0x180010853  mov     rax, rbx
0x180010856  add     rsp, 20h
0x18001085a  pop     rbx
0x18001085b  retn
```
