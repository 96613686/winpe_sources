# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000ea98`
- end: `0x18000eae9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e348`
- `0x18000ef20`

## callees

- `0x18000ea98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ead2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ead2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eaba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000eaba`

## string_xrefs

- `0x18000eab1`: `kernelbase.dll`

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
0x18000ea98  mov     [rsp+arg_0], rbx
0x18000ea9d  push    rdi
0x18000ea9e  sub     rsp, 20h
0x18000eaa2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000eaa9  mov     rdi, rcx
0x18000eaac  test    rax, rax
0x18000eaaf  jnz     short loc_18000EACC
0x18000eab1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000eab8  xor     ebx, ebx
0x18000eaba  call    cs:__imp_GetModuleHandleW
0x18000eac0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000eac7  test    rax, rax
0x18000eaca  jz      short loc_18000EADB
0x18000eacc  mov     rdx, rdi; lpProcName
0x18000eacf  mov     rcx, rax; hModule
0x18000ead2  call    cs:__imp_GetProcAddress
0x18000ead8  mov     rbx, rax
0x18000eadb  mov     rax, rbx
0x18000eade  mov     rbx, [rsp+28h+arg_0]
0x18000eae3  add     rsp, 20h
0x18000eae7  pop     rdi
0x18000eae8  retn
```
