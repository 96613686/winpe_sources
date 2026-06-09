# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800114b8`
- end: `0x180011509`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000cfe0`

## callees

- `0x1800114b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800114da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800114da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800114f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800114f2`

## string_xrefs

- `0x1800114d1`: `kernelbase.dll`

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
0x1800114b8  mov     [rsp+arg_0], rbx
0x1800114bd  push    rdi
0x1800114be  sub     rsp, 20h
0x1800114c2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800114c9  mov     rdi, rcx
0x1800114cc  test    rax, rax
0x1800114cf  jnz     short loc_1800114EC
0x1800114d1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800114d8  xor     ebx, ebx
0x1800114da  call    cs:__imp_GetModuleHandleW
0x1800114e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800114e7  test    rax, rax
0x1800114ea  jz      short loc_1800114FB
0x1800114ec  mov     rdx, rdi; lpProcName
0x1800114ef  mov     rcx, rax; hModule
0x1800114f2  call    cs:__imp_GetProcAddress
0x1800114f8  mov     rbx, rax
0x1800114fb  mov     rax, rbx
0x1800114fe  mov     rbx, [rsp+28h+arg_0]
0x180011503  add     rsp, 20h
0x180011507  pop     rdi
0x180011508  retn
```
