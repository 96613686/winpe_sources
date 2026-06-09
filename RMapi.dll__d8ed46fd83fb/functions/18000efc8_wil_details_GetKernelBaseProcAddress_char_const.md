# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000efc8`
- end: `0x18000f019`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000edd8`
- `0x1800170a0`

## callees

- `0x18000efc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f002`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f002`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000efea`

## string_xrefs

- `0x18000efe1`: `kernelbase.dll`

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
0x18000efc8  mov     [rsp+arg_0], rbx
0x18000efcd  push    rdi
0x18000efce  sub     rsp, 20h
0x18000efd2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000efd9  mov     rdi, rcx
0x18000efdc  test    rax, rax
0x18000efdf  jnz     short loc_18000EFFC
0x18000efe1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000efe8  xor     ebx, ebx
0x18000efea  call    cs:__imp_GetModuleHandleW
0x18000eff0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000eff7  test    rax, rax
0x18000effa  jz      short loc_18000F00B
0x18000effc  mov     rdx, rdi; lpProcName
0x18000efff  mov     rcx, rax; hModule
0x18000f002  call    cs:__imp_GetProcAddress
0x18000f008  mov     rbx, rax
0x18000f00b  mov     rax, rbx
0x18000f00e  mov     rbx, [rsp+28h+arg_0]
0x18000f013  add     rsp, 20h
0x18000f017  pop     rdi
0x18000f018  retn
```
