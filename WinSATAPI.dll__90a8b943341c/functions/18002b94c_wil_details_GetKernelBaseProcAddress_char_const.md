# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18002b94c`
- end: `0x18002b9aa`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002831c`

## callees

- `0x18002b94c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b96e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b96e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b98c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b98c`

## string_xrefs

- `0x18002b967`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW; // rax
  __int64 v2; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  v2 = 0;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, lpProcName);
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, lpProcName);
  return (FARPROC)v2;
}

```

## disassembly

```asm
0x18002b94c  mov     [rsp+arg_0], rbx
0x18002b951  push    rdi
0x18002b952  sub     rsp, 20h
0x18002b956  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002b95d  xor     ebx, ebx
0x18002b95f  mov     rdi, rcx
0x18002b962  test    rax, rax
0x18002b965  jnz     short loc_18002B986
0x18002b967  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002b96e  call    cs:__imp_GetModuleHandleW
0x18002b975  nop     dword ptr [rax+rax+00h]
0x18002b97a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002b981  test    rax, rax
0x18002b984  jz      short loc_18002B99B
0x18002b986  mov     rdx, rdi; lpProcName
0x18002b989  mov     rcx, rax; hModule
0x18002b98c  call    cs:__imp_GetProcAddress
0x18002b993  nop     dword ptr [rax+rax+00h]
0x18002b998  mov     rbx, rax
0x18002b99b  mov     rax, rbx
0x18002b99e  mov     rbx, [rsp+28h+arg_0]
0x18002b9a3  add     rsp, 20h
0x18002b9a7  pop     rdi
0x18002b9a8  retn
```
