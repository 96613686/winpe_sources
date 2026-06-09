# DisableUnloading(void)

- ea: `0x180001000`
- end: `0x180001058`
- name: `?DisableUnloading@@YAXXZ`
- size: `88`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001058`
- `0x1800010f0`

## callees

- `0x180001000`
- `0x180001540`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000102b`
- `KERNEL32!GetModuleFileNameW` at `0x18000102b`
- `KERNEL32!LoadLibraryW` at `0x18000103a`
- `KERNEL32!LoadLibraryW` at `0x18000103a`

## pseudocode

```c
void DisableUnloading(void)
{
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( GetModuleFileNameW(g_DllInstance, Filename, 0x104u) )
    LoadLibraryW(Filename);
}

```

## disassembly

```asm
0x180001000  sub     rsp, 248h
0x180001007  mov     rax, cs:__security_cookie
0x18000100e  xor     rax, rsp
0x180001011  mov     [rsp+248h+var_18], rax
0x180001019  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180001020  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180001025  mov     r8d, 104h; nSize
0x18000102b  call    cs:__imp_GetModuleFileNameW
0x180001031  test    eax, eax
0x180001033  jz      short loc_180001040
0x180001035  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x18000103a  call    cs:__imp_LoadLibraryW
0x180001040  mov     rcx, [rsp+248h+var_18]
0x180001048  xor     rcx, rsp; StackCookie
0x18000104b  call    __security_check_cookie
0x180001050  add     rsp, 248h
0x180001057  retn
```
