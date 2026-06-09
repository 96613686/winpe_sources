# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180007170`
- end: `0x1800071c1`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006a78`
- `0x18000afe0`

## callees

- `0x180007170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007192`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007192`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071aa`

## string_xrefs

- `0x180007189`: `kernelbase.dll`

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
0x180007170  mov     [rsp+arg_0], rbx
0x180007175  push    rdi
0x180007176  sub     rsp, 20h
0x18000717a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007181  mov     rdi, rcx
0x180007184  test    rax, rax
0x180007187  jnz     short loc_1800071A4
0x180007189  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007190  xor     ebx, ebx
0x180007192  call    cs:__imp_GetModuleHandleW
0x180007198  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000719f  test    rax, rax
0x1800071a2  jz      short loc_1800071B3
0x1800071a4  mov     rdx, rdi; lpProcName
0x1800071a7  mov     rcx, rax; hModule
0x1800071aa  call    cs:__imp_GetProcAddress
0x1800071b0  mov     rbx, rax
0x1800071b3  mov     rax, rbx
0x1800071b6  mov     rbx, [rsp+28h+arg_0]
0x1800071bb  add     rsp, 20h
0x1800071bf  pop     rdi
0x1800071c0  retn
```
