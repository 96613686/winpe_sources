# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180014444`
- end: `0x180014495`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012510`
- `0x180014a40`

## callees

- `0x180014444`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001447e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001447e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014466`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014466`

## string_xrefs

- `0x18001445d`: `kernelbase.dll`

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
0x180014444  mov     [rsp+arg_0], rbx
0x180014449  push    rdi
0x18001444a  sub     rsp, 20h
0x18001444e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180014455  mov     rdi, rcx
0x180014458  test    rax, rax
0x18001445b  jnz     short loc_180014478
0x18001445d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180014464  xor     ebx, ebx
0x180014466  call    cs:__imp_GetModuleHandleW
0x18001446c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180014473  test    rax, rax
0x180014476  jz      short loc_180014487
0x180014478  mov     rdx, rdi; lpProcName
0x18001447b  mov     rcx, rax; hModule
0x18001447e  call    cs:__imp_GetProcAddress
0x180014484  mov     rbx, rax
0x180014487  mov     rax, rbx
0x18001448a  mov     rbx, [rsp+28h+arg_0]
0x18001448f  add     rsp, 20h
0x180014493  pop     rdi
0x180014494  retn
```
