# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000fff8`
- end: `0x180010049`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f728`
- `0x1800109f0`

## callees

- `0x18000fff8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001001a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001001a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010032`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010032`

## string_xrefs

- `0x180010011`: `kernelbase.dll`

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
0x18000fff8  mov     [rsp+arg_0], rbx
0x18000fffd  push    rdi
0x18000fffe  sub     rsp, 20h
0x180010002  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010009  mov     rdi, rcx
0x18001000c  test    rax, rax
0x18001000f  jnz     short loc_18001002C
0x180010011  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010018  xor     ebx, ebx
0x18001001a  call    cs:__imp_GetModuleHandleW
0x180010020  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010027  test    rax, rax
0x18001002a  jz      short loc_18001003B
0x18001002c  mov     rdx, rdi; lpProcName
0x18001002f  mov     rcx, rax; hModule
0x180010032  call    cs:__imp_GetProcAddress
0x180010038  mov     rbx, rax
0x18001003b  mov     rax, rbx
0x18001003e  mov     rbx, [rsp+28h+arg_0]
0x180010043  add     rsp, 20h
0x180010047  pop     rdi
0x180010048  retn
```
