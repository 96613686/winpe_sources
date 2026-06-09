# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180012f68`
- end: `0x180012fb9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012588`
- `0x180013380`

## callees

- `0x180012f68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012f8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012fa2`

## string_xrefs

- `0x180012f81`: `kernelbase.dll`

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
0x180012f68  mov     [rsp+arg_0], rbx
0x180012f6d  push    rdi
0x180012f6e  sub     rsp, 20h
0x180012f72  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012f79  mov     rdi, rcx
0x180012f7c  test    rax, rax
0x180012f7f  jnz     short loc_180012F9C
0x180012f81  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180012f88  xor     ebx, ebx
0x180012f8a  call    cs:__imp_GetModuleHandleW
0x180012f90  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012f97  test    rax, rax
0x180012f9a  jz      short loc_180012FAB
0x180012f9c  mov     rdx, rdi; lpProcName
0x180012f9f  mov     rcx, rax; hModule
0x180012fa2  call    cs:__imp_GetProcAddress
0x180012fa8  mov     rbx, rax
0x180012fab  mov     rax, rbx
0x180012fae  mov     rbx, [rsp+28h+arg_0]
0x180012fb3  add     rsp, 20h
0x180012fb7  pop     rdi
0x180012fb8  retn
```
