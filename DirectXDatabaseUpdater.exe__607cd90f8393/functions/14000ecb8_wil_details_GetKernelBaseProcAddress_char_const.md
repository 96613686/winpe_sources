# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000ecb8`
- end: `0x14000ed09`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000d758`

## callees

- `0x14000ecb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ecf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ecf2`

## string_xrefs

- `0x14000ecd1`: `kernelbase.dll`

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
0x14000ecb8  mov     [rsp+arg_0], rbx
0x14000ecbd  push    rdi
0x14000ecbe  sub     rsp, 20h
0x14000ecc2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ecc9  mov     rdi, rcx
0x14000eccc  test    rax, rax
0x14000eccf  jnz     short loc_14000ECEC
0x14000ecd1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000ecd8  xor     ebx, ebx
0x14000ecda  call    cs:__imp_GetModuleHandleW
0x14000ece0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ece7  test    rax, rax
0x14000ecea  jz      short loc_14000ECFB
0x14000ecec  mov     rdx, rdi; lpProcName
0x14000ecef  mov     rcx, rax; hModule
0x14000ecf2  call    cs:__imp_GetProcAddress
0x14000ecf8  mov     rbx, rax
0x14000ecfb  mov     rax, rbx
0x14000ecfe  mov     rbx, [rsp+28h+arg_0]
0x14000ed03  add     rsp, 20h
0x14000ed07  pop     rdi
0x14000ed08  retn
```
