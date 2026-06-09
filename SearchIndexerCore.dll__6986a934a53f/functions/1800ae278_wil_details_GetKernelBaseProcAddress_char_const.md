# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800ae278`
- end: `0x1800ae2c9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800ab5b0`
- `0x1800ae5d0`

## callees

- `0x1800ae278`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ae29a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ae29a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae2b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ae2b2`

## string_xrefs

- `0x1800ae293`: `kernelbase.dll`

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
0x1800ae278  mov     [rsp+arg_0], rbx
0x1800ae27d  push    rdi
0x1800ae27e  sub     rsp, 20h
0x1800ae282  mov     rdi, rcx
0x1800ae285  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800ae28c  test    rax, rax
0x1800ae28f  jnz     short loc_1800AE2AC
0x1800ae291  xor     ebx, ebx
0x1800ae293  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ae29a  call    cs:__imp_GetModuleHandleW
0x1800ae2a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800ae2a7  test    rax, rax
0x1800ae2aa  jz      short loc_1800AE2BB
0x1800ae2ac  mov     rdx, rdi; lpProcName
0x1800ae2af  mov     rcx, rax; hModule
0x1800ae2b2  call    cs:__imp_GetProcAddress
0x1800ae2b8  mov     rbx, rax
0x1800ae2bb  mov     rax, rbx
0x1800ae2be  mov     rbx, [rsp+28h+arg_0]
0x1800ae2c3  add     rsp, 20h
0x1800ae2c7  pop     rdi
0x1800ae2c8  retn
```
