# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180028818`
- end: `0x180028869`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800281a8`
- `0x180028f90`

## callees

- `0x180028818`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002883a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002883a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028852`

## string_xrefs

- `0x180028831`: `kernelbase.dll`

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
0x180028818  mov     [rsp+arg_0], rbx
0x18002881d  push    rdi
0x18002881e  sub     rsp, 20h
0x180028822  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180028829  mov     rdi, rcx
0x18002882c  test    rax, rax
0x18002882f  jnz     short loc_18002884C
0x180028831  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180028838  xor     ebx, ebx
0x18002883a  call    cs:__imp_GetModuleHandleW
0x180028840  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180028847  test    rax, rax
0x18002884a  jz      short loc_18002885B
0x18002884c  mov     rdx, rdi; lpProcName
0x18002884f  mov     rcx, rax; hModule
0x180028852  call    cs:__imp_GetProcAddress
0x180028858  mov     rbx, rax
0x18002885b  mov     rax, rbx
0x18002885e  mov     rbx, [rsp+28h+arg_0]
0x180028863  add     rsp, 20h
0x180028867  pop     rdi
0x180028868  retn
```
