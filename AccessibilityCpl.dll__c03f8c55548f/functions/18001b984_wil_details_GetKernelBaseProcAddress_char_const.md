# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18001b984`
- end: `0x18001b9d5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b2e8`
- `0x18001be60`

## callees

- `0x18001b984`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b9be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9a6`

## string_xrefs

- `0x18001b99d`: `kernelbase.dll`

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
0x18001b984  mov     [rsp+arg_0], rbx
0x18001b989  push    rdi
0x18001b98a  sub     rsp, 20h
0x18001b98e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b995  mov     rdi, rcx
0x18001b998  test    rax, rax
0x18001b99b  jnz     short loc_18001B9B8
0x18001b99d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001b9a4  xor     ebx, ebx
0x18001b9a6  call    cs:__imp_GetModuleHandleW
0x18001b9ac  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18001b9b3  test    rax, rax
0x18001b9b6  jz      short loc_18001B9C7
0x18001b9b8  mov     rdx, rdi; lpProcName
0x18001b9bb  mov     rcx, rax; hModule
0x18001b9be  call    cs:__imp_GetProcAddress
0x18001b9c4  mov     rbx, rax
0x18001b9c7  mov     rax, rbx
0x18001b9ca  mov     rbx, [rsp+28h+arg_0]
0x18001b9cf  add     rsp, 20h
0x18001b9d3  pop     rdi
0x18001b9d4  retn
```
