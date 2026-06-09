# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180016f48`
- end: `0x180016f99`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800137e0`

## callees

- `0x180016f48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016f82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016f6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016f6a`

## string_xrefs

- `0x180016f61`: `kernelbase.dll`

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
0x180016f48  mov     [rsp+arg_0], rbx
0x180016f4d  push    rdi
0x180016f4e  sub     rsp, 20h
0x180016f52  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016f59  mov     rdi, rcx
0x180016f5c  test    rax, rax
0x180016f5f  jnz     short loc_180016F7C
0x180016f61  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016f68  xor     ebx, ebx
0x180016f6a  call    cs:__imp_GetModuleHandleW
0x180016f70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016f77  test    rax, rax
0x180016f7a  jz      short loc_180016F8B
0x180016f7c  mov     rdx, rdi; lpProcName
0x180016f7f  mov     rcx, rax; hModule
0x180016f82  call    cs:__imp_GetProcAddress
0x180016f88  mov     rbx, rax
0x180016f8b  mov     rax, rbx
0x180016f8e  mov     rbx, [rsp+28h+arg_0]
0x180016f93  add     rsp, 20h
0x180016f97  pop     rdi
0x180016f98  retn
```
