# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140009b18`
- end: `0x140009b69`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400093f8`

## callees

- `0x140009b18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009b52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009b52`

## string_xrefs

- `0x140009b31`: `kernelbase.dll`

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
0x140009b18  mov     [rsp+arg_0], rbx
0x140009b1d  push    rdi
0x140009b1e  sub     rsp, 20h
0x140009b22  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009b29  mov     rdi, rcx
0x140009b2c  test    rax, rax
0x140009b2f  jnz     short loc_140009B4C
0x140009b31  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140009b38  xor     ebx, ebx
0x140009b3a  call    cs:__imp_GetModuleHandleW
0x140009b40  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009b47  test    rax, rax
0x140009b4a  jz      short loc_140009B5B
0x140009b4c  mov     rdx, rdi; lpProcName
0x140009b4f  mov     rcx, rax; hModule
0x140009b52  call    cs:__imp_GetProcAddress
0x140009b58  mov     rbx, rax
0x140009b5b  mov     rax, rbx
0x140009b5e  mov     rbx, [rsp+28h+arg_0]
0x140009b63  add     rsp, 20h
0x140009b67  pop     rdi
0x140009b68  retn
```
