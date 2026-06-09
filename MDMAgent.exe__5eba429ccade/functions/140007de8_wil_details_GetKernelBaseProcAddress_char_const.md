# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140007de8`
- end: `0x140007e39`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007858`

## callees

- `0x140007de8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007e0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007e22`

## string_xrefs

- `0x140007e01`: `kernelbase.dll`

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
0x140007de8  mov     [rsp+arg_0], rbx
0x140007ded  push    rdi
0x140007dee  sub     rsp, 20h
0x140007df2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007df9  mov     rdi, rcx
0x140007dfc  test    rax, rax
0x140007dff  jnz     short loc_140007E1C
0x140007e01  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140007e08  xor     ebx, ebx
0x140007e0a  call    cs:__imp_GetModuleHandleW
0x140007e10  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007e17  test    rax, rax
0x140007e1a  jz      short loc_140007E2B
0x140007e1c  mov     rdx, rdi; lpProcName
0x140007e1f  mov     rcx, rax; hModule
0x140007e22  call    cs:__imp_GetProcAddress
0x140007e28  mov     rbx, rax
0x140007e2b  mov     rax, rbx
0x140007e2e  mov     rbx, [rsp+28h+arg_0]
0x140007e33  add     rsp, 20h
0x140007e37  pop     rdi
0x140007e38  retn
```
