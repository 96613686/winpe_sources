# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800117e8`
- end: `0x180011839`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000bfd0`
- `0x180011e70`

## callees

- `0x1800117e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001180a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001180a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011822`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011822`

## string_xrefs

- `0x180011801`: `kernelbase.dll`

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
0x1800117e8  mov     [rsp+arg_0], rbx
0x1800117ed  push    rdi
0x1800117ee  sub     rsp, 20h
0x1800117f2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800117f9  mov     rdi, rcx
0x1800117fc  test    rax, rax
0x1800117ff  jnz     short loc_18001181C
0x180011801  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x180011808  xor     ebx, ebx
0x18001180a  call    cs:__imp_GetModuleHandleW
0x180011810  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180011817  test    rax, rax
0x18001181a  jz      short loc_18001182B
0x18001181c  mov     rdx, rdi; lpProcName
0x18001181f  mov     rcx, rax; hModule
0x180011822  call    cs:__imp_GetProcAddress
0x180011828  mov     rbx, rax
0x18001182b  mov     rax, rbx
0x18001182e  mov     rbx, [rsp+28h+arg_0]
0x180011833  add     rsp, 20h
0x180011837  pop     rdi
0x180011838  retn
```
