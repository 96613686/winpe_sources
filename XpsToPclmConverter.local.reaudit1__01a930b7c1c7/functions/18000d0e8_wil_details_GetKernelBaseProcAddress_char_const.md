# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000d0e8`
- end: `0x18000d139`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c978`

## callees

- `0x18000d0e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d122`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d122`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d10a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d10a`

## string_xrefs

- `0x18000d101`: `kernelbase.dll`

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
0x18000d0e8  mov     [rsp+arg_0], rbx
0x18000d0ed  push    rdi
0x18000d0ee  sub     rsp, 20h
0x18000d0f2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d0f9  mov     rdi, rcx
0x18000d0fc  test    rax, rax
0x18000d0ff  jnz     short loc_18000D11C
0x18000d101  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d108  xor     ebx, ebx
0x18000d10a  call    cs:__imp_GetModuleHandleW
0x18000d110  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d117  test    rax, rax
0x18000d11a  jz      short loc_18000D12B
0x18000d11c  mov     rdx, rdi; lpProcName
0x18000d11f  mov     rcx, rax; hModule
0x18000d122  call    cs:__imp_GetProcAddress
0x18000d128  mov     rbx, rax
0x18000d12b  mov     rax, rbx
0x18000d12e  mov     rbx, [rsp+28h+arg_0]
0x18000d133  add     rsp, 20h
0x18000d137  pop     rdi
0x18000d138  retn
```
