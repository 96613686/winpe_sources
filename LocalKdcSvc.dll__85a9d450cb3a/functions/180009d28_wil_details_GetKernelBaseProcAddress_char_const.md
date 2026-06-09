# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009d28`
- end: `0x180009d79`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800095b8`
- `0x18000a3f0`

## callees

- `0x180009d28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009d4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d62`

## string_xrefs

- `0x180009d41`: `kernelbase.dll`

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
0x180009d28  mov     [rsp+arg_0], rbx
0x180009d2d  push    rdi
0x180009d2e  sub     rsp, 20h
0x180009d32  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009d39  mov     rdi, rcx
0x180009d3c  test    rax, rax
0x180009d3f  jnz     short loc_180009D5C
0x180009d41  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009d48  xor     ebx, ebx
0x180009d4a  call    cs:__imp_GetModuleHandleW
0x180009d50  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009d57  test    rax, rax
0x180009d5a  jz      short loc_180009D6B
0x180009d5c  mov     rdx, rdi; lpProcName
0x180009d5f  mov     rcx, rax; hModule
0x180009d62  call    cs:__imp_GetProcAddress
0x180009d68  mov     rbx, rax
0x180009d6b  mov     rax, rbx
0x180009d6e  mov     rbx, [rsp+28h+arg_0]
0x180009d73  add     rsp, 20h
0x180009d77  pop     rdi
0x180009d78  retn
```
