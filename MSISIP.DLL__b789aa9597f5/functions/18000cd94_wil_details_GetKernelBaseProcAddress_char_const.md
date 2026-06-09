# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000cd94`
- end: `0x18000cde5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800073ec`

## callees

- `0x18000cd94`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cdce`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cdce`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000cdb6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000cdb6`

## string_xrefs

- `0x18000cdad`: `kernelbase.dll`

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
0x18000cd94  mov     [rsp+arg_0], rbx
0x18000cd99  push    rdi
0x18000cd9a  sub     rsp, 20h
0x18000cd9e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cda5  mov     rdi, rcx
0x18000cda8  test    rax, rax
0x18000cdab  jnz     short loc_18000CDC8
0x18000cdad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000cdb4  xor     ebx, ebx
0x18000cdb6  call    cs:__imp_GetModuleHandleW
0x18000cdbc  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000cdc3  test    rax, rax
0x18000cdc6  jz      short loc_18000CDD7
0x18000cdc8  mov     rdx, rdi; lpProcName
0x18000cdcb  mov     rcx, rax; hModule
0x18000cdce  call    cs:__imp_GetProcAddress
0x18000cdd4  mov     rbx, rax
0x18000cdd7  mov     rax, rbx
0x18000cdda  mov     rbx, [rsp+28h+arg_0]
0x18000cddf  add     rsp, 20h
0x18000cde3  pop     rdi
0x18000cde4  retn
```
