# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001b5f4`
- end: `0x18001b645`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800193a0`

## callees

- `0x18001b5f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b616`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b616`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b62e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b62e`

## string_xrefs

- `0x18001b60d`: `kernelbase.dll`

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
0x18001b5f4  mov     [rsp+arg_0], rbx
0x18001b5f9  push    rdi
0x18001b5fa  sub     rsp, 20h
0x18001b5fe  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b605  mov     rdi, rcx
0x18001b608  test    rax, rax
0x18001b60b  jnz     short loc_18001B628
0x18001b60d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001b614  xor     ebx, ebx
0x18001b616  call    cs:__imp_GetModuleHandleW
0x18001b61c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b623  test    rax, rax
0x18001b626  jz      short loc_18001B637
0x18001b628  mov     rdx, rdi; lpProcName
0x18001b62b  mov     rcx, rax; hModule
0x18001b62e  call    cs:__imp_GetProcAddress
0x18001b634  mov     rbx, rax
0x18001b637  mov     rax, rbx
0x18001b63a  mov     rbx, [rsp+28h+arg_0]
0x18001b63f  add     rsp, 20h
0x18001b643  pop     rdi
0x18001b644  retn
```
