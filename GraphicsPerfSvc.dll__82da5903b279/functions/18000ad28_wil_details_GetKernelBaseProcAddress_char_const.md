# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000ad28`
- end: `0x18000ad79`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a538`
- `0x18000b1f0`

## callees

- `0x18000ad28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad4a`

## string_xrefs

- `0x18000ad41`: `kernelbase.dll`

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
0x18000ad28  mov     [rsp+arg_0], rbx
0x18000ad2d  push    rdi
0x18000ad2e  sub     rsp, 20h
0x18000ad32  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ad39  mov     rdi, rcx
0x18000ad3c  test    rax, rax
0x18000ad3f  jnz     short loc_18000AD5C
0x18000ad41  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ad48  xor     ebx, ebx
0x18000ad4a  call    cs:__imp_GetModuleHandleW
0x18000ad50  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ad57  test    rax, rax
0x18000ad5a  jz      short loc_18000AD6B
0x18000ad5c  mov     rdx, rdi; lpProcName
0x18000ad5f  mov     rcx, rax; hModule
0x18000ad62  call    cs:__imp_GetProcAddress
0x18000ad68  mov     rbx, rax
0x18000ad6b  mov     rax, rbx
0x18000ad6e  mov     rbx, [rsp+28h+arg_0]
0x18000ad73  add     rsp, 20h
0x18000ad77  pop     rdi
0x18000ad78  retn
```
