# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180006bc8`
- end: `0x180006c19`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006708`
- `0x18000e1d0`

## callees

- `0x180006bc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006bea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006bea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c02`

## string_xrefs

- `0x180006be1`: `kernelbase.dll`

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
0x180006bc8  mov     [rsp+arg_0], rbx
0x180006bcd  push    rdi
0x180006bce  sub     rsp, 20h
0x180006bd2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006bd9  mov     rdi, rcx
0x180006bdc  test    rax, rax
0x180006bdf  jnz     short loc_180006BFC
0x180006be1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006be8  xor     ebx, ebx
0x180006bea  call    cs:__imp_GetModuleHandleW
0x180006bf0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006bf7  test    rax, rax
0x180006bfa  jz      short loc_180006C0B
0x180006bfc  mov     rdx, rdi; lpProcName
0x180006bff  mov     rcx, rax; hModule
0x180006c02  call    cs:__imp_GetProcAddress
0x180006c08  mov     rbx, rax
0x180006c0b  mov     rax, rbx
0x180006c0e  mov     rbx, [rsp+28h+arg_0]
0x180006c13  add     rsp, 20h
0x180006c17  pop     rdi
0x180006c18  retn
```
