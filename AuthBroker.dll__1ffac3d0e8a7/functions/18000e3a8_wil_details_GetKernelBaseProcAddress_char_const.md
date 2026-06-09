# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000e3a8`
- end: `0x18000e3f9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (__fastcall *__fastcall(const char *procName))()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c4b0`

## callees

- `0x18000e3a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e3ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e3e2`

## string_xrefs

- `0x18000e3c1`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(const char *procName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, procName);
  v3 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, procName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x18000e3a8  mov     [rsp+arg_0], rbx
0x18000e3ad  push    rdi
0x18000e3ae  sub     rsp, 20h
0x18000e3b2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e3b9  mov     rdi, procName
0x18000e3bc  test    rax, rax
0x18000e3bf  jnz     short loc_18000E3DC
0x18000e3c1  lea     procName, aKernelbaseDll; "kernelbase.dll"
0x18000e3c8  xor     ebx, ebx
0x18000e3ca  call    cs:__imp_GetModuleHandleW
0x18000e3d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e3d7  test    rax, rax
0x18000e3da  jz      short loc_18000E3EB
0x18000e3dc  mov     rdx, rdi; lpProcName
0x18000e3df  mov     procName, rax; hModule
0x18000e3e2  call    cs:__imp_GetProcAddress
0x18000e3e8  mov     rbx, rax
0x18000e3eb  mov     rax, rbx
0x18000e3ee  mov     rbx, [rsp+28h+arg_0]
0x18000e3f3  add     rsp, 20h
0x18000e3f7  pop     rdi
0x18000e3f8  retn
```
