# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180022a68`
- end: `0x180022ab9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001ff50`
- `0x180023d00`

## callees

- `0x180022a68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022aa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022aa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022a8a`

## string_xrefs

- `0x180022a83`: `kernelbase.dll`

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
0x180022a68  mov     [rsp+arg_0], rbx
0x180022a6d  push    rdi
0x180022a6e  sub     rsp, 20h
0x180022a72  mov     rdi, rcx
0x180022a75  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180022a7c  test    rax, rax
0x180022a7f  jnz     short loc_180022A9C
0x180022a81  xor     ebx, ebx
0x180022a83  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180022a8a  call    cs:__imp_GetModuleHandleW
0x180022a90  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180022a97  test    rax, rax
0x180022a9a  jz      short loc_180022AAB
0x180022a9c  mov     rdx, rdi; lpProcName
0x180022a9f  mov     rcx, rax; hModule
0x180022aa2  call    cs:__imp_GetProcAddress
0x180022aa8  mov     rbx, rax
0x180022aab  mov     rax, rbx
0x180022aae  mov     rbx, [rsp+28h+arg_0]
0x180022ab3  add     rsp, 20h
0x180022ab7  pop     rdi
0x180022ab8  retn
```
