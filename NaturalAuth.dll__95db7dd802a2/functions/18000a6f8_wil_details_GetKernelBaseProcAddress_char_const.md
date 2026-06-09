# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a6f8`
- end: `0x18000a749`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a2f8`

## callees

- `0x18000a6f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a732`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a732`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a71a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a71a`

## string_xrefs

- `0x18000a711`: `kernelbase.dll`

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
0x18000a6f8  mov     [rsp+arg_0], rbx
0x18000a6fd  push    rdi
0x18000a6fe  sub     rsp, 20h
0x18000a702  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a709  mov     rdi, rcx
0x18000a70c  test    rax, rax
0x18000a70f  jnz     short loc_18000A72C
0x18000a711  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a718  xor     ebx, ebx
0x18000a71a  call    cs:__imp_GetModuleHandleW
0x18000a720  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a727  test    rax, rax
0x18000a72a  jz      short loc_18000A73B
0x18000a72c  mov     rdx, rdi; lpProcName
0x18000a72f  mov     rcx, rax; hModule
0x18000a732  call    cs:__imp_GetProcAddress
0x18000a738  mov     rbx, rax
0x18000a73b  mov     rax, rbx
0x18000a73e  mov     rbx, [rsp+28h+arg_0]
0x18000a743  add     rsp, 20h
0x18000a747  pop     rdi
0x18000a748  retn
```
