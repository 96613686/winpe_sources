# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000b5e8`
- end: `0x18000b639`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007ab0`
- `0x18000bbc0`

## callees

- `0x18000b5e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b622`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b622`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b60a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b60a`

## string_xrefs

- `0x18000b601`: `kernelbase.dll`

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
0x18000b5e8  mov     [rsp+arg_0], rbx
0x18000b5ed  push    rdi
0x18000b5ee  sub     rsp, 20h
0x18000b5f2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b5f9  mov     rdi, rcx
0x18000b5fc  test    rax, rax
0x18000b5ff  jnz     short loc_18000B61C
0x18000b601  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b608  xor     ebx, ebx
0x18000b60a  call    cs:__imp_GetModuleHandleW
0x18000b610  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b617  test    rax, rax
0x18000b61a  jz      short loc_18000B62B
0x18000b61c  mov     rdx, rdi; lpProcName
0x18000b61f  mov     rcx, rax; hModule
0x18000b622  call    cs:__imp_GetProcAddress
0x18000b628  mov     rbx, rax
0x18000b62b  mov     rax, rbx
0x18000b62e  mov     rbx, [rsp+28h+arg_0]
0x18000b633  add     rsp, 20h
0x18000b637  pop     rdi
0x18000b638  retn
```
