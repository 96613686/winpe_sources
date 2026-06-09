# AppmgmtGetHandleForCallingDll(void)

- ea: `0x180012d70`
- end: `0x180012da6`
- name: `?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ`
- size: `54`
- prototype: `HINSTANCE(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002788`
- `0x18000d2d8`
- `0x18000f634`
- `0x1800116e4`
- `0x18001b1a0`

## callees

- `0x180012d70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012d8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180012d8e`

## pseudocode

```c
HINSTANCE AppmgmtGetHandleForCallingDll(void)
{
  HMODULE phModule; // [rsp+30h] [rbp+8h] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(4u, (LPCWSTR)AppmgmtGetHandleForCallingDll, &phModule) )
    return phModule;
  else
    return 0;
}

```

## disassembly

```asm
0x180012d70  sub     rsp, 28h
0x180012d74  lea     r8, [rsp+28h+phModule]; phModule
0x180012d79  mov     [rsp+28h+phModule], 0
0x180012d82  lea     rdx, ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; lpModuleName
0x180012d89  mov     ecx, 4; dwFlags
0x180012d8e  call    cs:__imp_GetModuleHandleExW
0x180012d94  test    eax, eax
0x180012d96  jnz     short loc_180012D9C
0x180012d98  xor     eax, eax
0x180012d9a  jmp     short loc_180012DA1
0x180012d9c  mov     rax, [rsp+28h+phModule]
0x180012da1  add     rsp, 28h
0x180012da5  retn
```
