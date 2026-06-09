# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002ae38`
- end: `0x18002ae89`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800239e0`
- `0x18002b920`

## callees

- `0x18002ae38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ae5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ae5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ae72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ae72`

## string_xrefs

- `0x18002ae51`: `kernelbase.dll`

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
0x18002ae38  mov     [rsp+arg_0], rbx
0x18002ae3d  push    rdi
0x18002ae3e  sub     rsp, 20h
0x18002ae42  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002ae49  mov     rdi, rcx
0x18002ae4c  test    rax, rax
0x18002ae4f  jnz     short loc_18002AE6C
0x18002ae51  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002ae58  xor     ebx, ebx
0x18002ae5a  call    cs:__imp_GetModuleHandleW
0x18002ae60  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002ae67  test    rax, rax
0x18002ae6a  jz      short loc_18002AE7B
0x18002ae6c  mov     rdx, rdi; lpProcName
0x18002ae6f  mov     rcx, rax; hModule
0x18002ae72  call    cs:__imp_GetProcAddress
0x18002ae78  mov     rbx, rax
0x18002ae7b  mov     rax, rbx
0x18002ae7e  mov     rbx, [rsp+28h+arg_0]
0x18002ae83  add     rsp, 20h
0x18002ae87  pop     rdi
0x18002ae88  retn
```
