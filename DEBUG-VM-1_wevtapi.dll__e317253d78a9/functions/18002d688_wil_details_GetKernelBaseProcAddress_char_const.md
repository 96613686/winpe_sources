# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002d688`
- end: `0x18002d6d9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002b830`
- `0x18002daa0`

## callees

- `0x18002d688`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d6c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d6c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d6aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d6aa`

## string_xrefs

- `0x18002d6a1`: `kernelbase.dll`

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
0x18002d688  mov     [rsp+arg_0], rbx
0x18002d68d  push    rdi
0x18002d68e  sub     rsp, 20h
0x18002d692  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002d699  mov     rdi, rcx
0x18002d69c  test    rax, rax
0x18002d69f  jnz     short loc_18002D6BC
0x18002d6a1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002d6a8  xor     ebx, ebx
0x18002d6aa  call    cs:__imp_GetModuleHandleW
0x18002d6b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002d6b7  test    rax, rax
0x18002d6ba  jz      short loc_18002D6CB
0x18002d6bc  mov     rdx, rdi; lpProcName
0x18002d6bf  mov     rcx, rax; hModule
0x18002d6c2  call    cs:__imp_GetProcAddress
0x18002d6c8  mov     rbx, rax
0x18002d6cb  mov     rax, rbx
0x18002d6ce  mov     rbx, [rsp+28h+arg_0]
0x18002d6d3  add     rsp, 20h
0x18002d6d7  pop     rdi
0x18002d6d8  retn
```
