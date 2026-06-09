# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009df8`
- end: `0x180009e49`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006cd0`
- `0x18000a2e0`

## callees

- `0x180009df8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009e32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e1a`

## string_xrefs

- `0x180009e11`: `kernelbase.dll`

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
0x180009df8  mov     [rsp+arg_0], rbx
0x180009dfd  push    rdi
0x180009dfe  sub     rsp, 20h
0x180009e02  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009e09  mov     rdi, rcx
0x180009e0c  test    rax, rax
0x180009e0f  jnz     short loc_180009E2C
0x180009e11  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009e18  xor     ebx, ebx
0x180009e1a  call    cs:__imp_GetModuleHandleW
0x180009e20  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009e27  test    rax, rax
0x180009e2a  jz      short loc_180009E3B
0x180009e2c  mov     rdx, rdi; lpProcName
0x180009e2f  mov     rcx, rax; hModule
0x180009e32  call    cs:__imp_GetProcAddress
0x180009e38  mov     rbx, rax
0x180009e3b  mov     rax, rbx
0x180009e3e  mov     rbx, [rsp+28h+arg_0]
0x180009e43  add     rsp, 20h
0x180009e47  pop     rdi
0x180009e48  retn
```
