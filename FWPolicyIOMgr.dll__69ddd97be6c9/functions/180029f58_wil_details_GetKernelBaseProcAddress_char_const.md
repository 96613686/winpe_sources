# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180029f58`
- end: `0x180029fa9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800285a0`
- `0x18002a320`

## callees

- `0x180029f58`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029f7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029f7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f92`

## string_xrefs

- `0x180029f71`: `kernelbase.dll`

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
0x180029f58  mov     [rsp+arg_0], rbx
0x180029f5d  push    rdi
0x180029f5e  sub     rsp, 20h
0x180029f62  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180029f69  mov     rdi, rcx
0x180029f6c  test    rax, rax
0x180029f6f  jnz     short loc_180029F8C
0x180029f71  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180029f78  xor     ebx, ebx
0x180029f7a  call    cs:__imp_GetModuleHandleW
0x180029f80  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180029f87  test    rax, rax
0x180029f8a  jz      short loc_180029F9B
0x180029f8c  mov     rdx, rdi; lpProcName
0x180029f8f  mov     rcx, rax; hModule
0x180029f92  call    cs:__imp_GetProcAddress
0x180029f98  mov     rbx, rax
0x180029f9b  mov     rax, rbx
0x180029f9e  mov     rbx, [rsp+28h+arg_0]
0x180029fa3  add     rsp, 20h
0x180029fa7  pop     rdi
0x180029fa8  retn
```
