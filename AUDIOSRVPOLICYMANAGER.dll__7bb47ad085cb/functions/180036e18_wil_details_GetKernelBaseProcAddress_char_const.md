# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180036e18`
- end: `0x180036e69`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180023300`
- `0x180037230`

## callees

- `0x180036e18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036e3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036e3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036e52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036e52`

## string_xrefs

- `0x180036e31`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  v3 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x180036e18  mov     [rsp+arg_0], rbx
0x180036e1d  push    rdi
0x180036e1e  sub     rsp, 20h
0x180036e22  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036e29  mov     rdi, rcx
0x180036e2c  test    rax, rax
0x180036e2f  jnz     short loc_180036E4C
0x180036e31  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180036e38  xor     ebx, ebx
0x180036e3a  call    cs:__imp_GetModuleHandleW
0x180036e40  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180036e47  test    rax, rax
0x180036e4a  jz      short loc_180036E5B
0x180036e4c  mov     rdx, rdi; lpProcName
0x180036e4f  mov     rcx, rax; hModule
0x180036e52  call    cs:__imp_GetProcAddress
0x180036e58  mov     rbx, rax
0x180036e5b  mov     rax, rbx
0x180036e5e  mov     rbx, [rsp+28h+arg_0]
0x180036e63  add     rsp, 20h
0x180036e67  pop     rdi
0x180036e68  retn
```
