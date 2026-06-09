# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180005768`
- end: `0x1800057b9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800054a8`

## callees

- `0x180005768`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000578a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000578a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057a2`

## string_xrefs

- `0x180005781`: `kernelbase.dll`

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
0x180005768  mov     [rsp+arg_0], rbx
0x18000576d  push    rdi
0x18000576e  sub     rsp, 20h
0x180005772  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005779  mov     rdi, rcx
0x18000577c  test    rax, rax
0x18000577f  jnz     short loc_18000579C
0x180005781  lea     rcx, ModuleName; "kernelbase.dll"
0x180005788  xor     ebx, ebx
0x18000578a  call    cs:__imp_GetModuleHandleW
0x180005790  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005797  test    rax, rax
0x18000579a  jz      short loc_1800057AB
0x18000579c  mov     rdx, rdi; lpProcName
0x18000579f  mov     rcx, rax; hModule
0x1800057a2  call    cs:__imp_GetProcAddress
0x1800057a8  mov     rbx, rax
0x1800057ab  mov     rax, rbx
0x1800057ae  mov     rbx, [rsp+28h+arg_0]
0x1800057b3  add     rsp, 20h
0x1800057b7  pop     rdi
0x1800057b8  retn
```
