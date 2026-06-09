# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180007898`
- end: `0x1800078e9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800074d8`
- `0x18000b8d0`

## callees

- `0x180007898`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078ba`

## string_xrefs

- `0x1800078b1`: `kernelbase.dll`

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
0x180007898  mov     [rsp+arg_0], rbx
0x18000789d  push    rdi
0x18000789e  sub     rsp, 20h
0x1800078a2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800078a9  mov     rdi, rcx
0x1800078ac  test    rax, rax
0x1800078af  jnz     short loc_1800078CC
0x1800078b1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800078b8  xor     ebx, ebx
0x1800078ba  call    cs:__imp_GetModuleHandleW
0x1800078c0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800078c7  test    rax, rax
0x1800078ca  jz      short loc_1800078DB
0x1800078cc  mov     rdx, rdi; lpProcName
0x1800078cf  mov     rcx, rax; hModule
0x1800078d2  call    cs:__imp_GetProcAddress
0x1800078d8  mov     rbx, rax
0x1800078db  mov     rax, rbx
0x1800078de  mov     rbx, [rsp+28h+arg_0]
0x1800078e3  add     rsp, 20h
0x1800078e7  pop     rdi
0x1800078e8  retn
```
