# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180008968`
- end: `0x1800089b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800080d8`

## callees

- `0x180008968`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800089a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000898a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000898a`

## string_xrefs

- `0x180008981`: `kernelbase.dll`

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
0x180008968  mov     [rsp+arg_0], rbx
0x18000896d  push    rdi
0x18000896e  sub     rsp, 20h
0x180008972  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008979  mov     rdi, rcx
0x18000897c  test    rax, rax
0x18000897f  jnz     short loc_18000899C
0x180008981  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008988  xor     ebx, ebx
0x18000898a  call    cs:__imp_GetModuleHandleW
0x180008990  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008997  test    rax, rax
0x18000899a  jz      short loc_1800089AB
0x18000899c  mov     rdx, rdi; lpProcName
0x18000899f  mov     rcx, rax; hModule
0x1800089a2  call    cs:__imp_GetProcAddress
0x1800089a8  mov     rbx, rax
0x1800089ab  mov     rax, rbx
0x1800089ae  mov     rbx, [rsp+28h+arg_0]
0x1800089b3  add     rsp, 20h
0x1800089b7  pop     rdi
0x1800089b8  retn
```
