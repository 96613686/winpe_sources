# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800238f0`
- end: `0x180023941`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180013d30`
- `0x18002b210`

## callees

- `0x1800238f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002392a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002392a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023912`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180023912`

## string_xrefs

- `0x180023909`: `kernelbase.dll`

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
0x1800238f0  mov     [rsp+arg_0], rbx
0x1800238f5  push    rdi
0x1800238f6  sub     rsp, 20h
0x1800238fa  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180023901  mov     rdi, rcx
0x180023904  test    rax, rax
0x180023907  jnz     short loc_180023924
0x180023909  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180023910  xor     ebx, ebx
0x180023912  call    cs:__imp_GetModuleHandleW
0x180023918  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002391f  test    rax, rax
0x180023922  jz      short loc_180023933
0x180023924  mov     rdx, rdi; lpProcName
0x180023927  mov     rcx, rax; hModule
0x18002392a  call    cs:__imp_GetProcAddress
0x180023930  mov     rbx, rax
0x180023933  mov     rax, rbx
0x180023936  mov     rbx, [rsp+28h+arg_0]
0x18002393b  add     rsp, 20h
0x18002393f  pop     rdi
0x180023940  retn
```
