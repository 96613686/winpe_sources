# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000d3b0`
- end: `0x18000d401`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ce48`
- `0x18000d7f0`

## callees

- `0x18000d3b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d3ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d3ea`

## string_xrefs

- `0x18000d3c9`: `kernelbase.dll`

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
0x18000d3b0  mov     [rsp+arg_0], rbx
0x18000d3b5  push    rdi
0x18000d3b6  sub     rsp, 20h
0x18000d3ba  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d3c1  mov     rdi, rcx
0x18000d3c4  test    rax, rax
0x18000d3c7  jnz     short loc_18000D3E4
0x18000d3c9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d3d0  xor     ebx, ebx
0x18000d3d2  call    cs:__imp_GetModuleHandleW
0x18000d3d8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d3df  test    rax, rax
0x18000d3e2  jz      short loc_18000D3F3
0x18000d3e4  mov     rdx, rdi; lpProcName
0x18000d3e7  mov     rcx, rax; hModule
0x18000d3ea  call    cs:__imp_GetProcAddress
0x18000d3f0  mov     rbx, rax
0x18000d3f3  mov     rax, rbx
0x18000d3f6  mov     rbx, [rsp+28h+arg_0]
0x18000d3fb  add     rsp, 20h
0x18000d3ff  pop     rdi
0x18000d400  retn
```
