# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000b0d8`
- end: `0x18000b129`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a728`
- `0x18000b6e0`

## callees

- `0x18000b0d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b112`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b0fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b0fa`

## string_xrefs

- `0x18000b0f1`: `kernelbase.dll`

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
0x18000b0d8  mov     [rsp+arg_0], rbx
0x18000b0dd  push    rdi
0x18000b0de  sub     rsp, 20h
0x18000b0e2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b0e9  mov     rdi, rcx
0x18000b0ec  test    rax, rax
0x18000b0ef  jnz     short loc_18000B10C
0x18000b0f1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000b0f8  xor     ebx, ebx
0x18000b0fa  call    cs:__imp_GetModuleHandleW
0x18000b100  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000b107  test    rax, rax
0x18000b10a  jz      short loc_18000B11B
0x18000b10c  mov     rdx, rdi; lpProcName
0x18000b10f  mov     rcx, rax; hModule
0x18000b112  call    cs:__imp_GetProcAddress
0x18000b118  mov     rbx, rax
0x18000b11b  mov     rax, rbx
0x18000b11e  mov     rbx, [rsp+28h+arg_0]
0x18000b123  add     rsp, 20h
0x18000b127  pop     rdi
0x18000b128  retn
```
