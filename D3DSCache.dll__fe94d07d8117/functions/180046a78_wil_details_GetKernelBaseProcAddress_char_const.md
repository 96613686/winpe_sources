# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180046a78`
- end: `0x180046ac9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180046380`
- `0x18004f4e0`

## callees

- `0x180046a78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046ab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046ab2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046a9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046a9a`

## string_xrefs

- `0x180046a91`: `kernelbase.dll`

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
0x180046a78  mov     [rsp+arg_0], rbx
0x180046a7d  push    rdi
0x180046a7e  sub     rsp, 20h
0x180046a82  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180046a89  mov     rdi, rcx
0x180046a8c  test    rax, rax
0x180046a8f  jnz     short loc_180046AAC
0x180046a91  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180046a98  xor     ebx, ebx
0x180046a9a  call    cs:__imp_GetModuleHandleW
0x180046aa0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180046aa7  test    rax, rax
0x180046aaa  jz      short loc_180046ABB
0x180046aac  mov     rdx, rdi; lpProcName
0x180046aaf  mov     rcx, rax; hModule
0x180046ab2  call    cs:__imp_GetProcAddress
0x180046ab8  mov     rbx, rax
0x180046abb  mov     rax, rbx
0x180046abe  mov     rbx, [rsp+28h+arg_0]
0x180046ac3  add     rsp, 20h
0x180046ac7  pop     rdi
0x180046ac8  retn
```
