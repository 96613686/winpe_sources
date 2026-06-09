# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180007e08`
- end: `0x180007e59`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007988`
- `0x18000cc10`

## callees

- `0x180007e08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e42`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e2a`

## string_xrefs

- `0x180007e21`: `kernelbase.dll`

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
0x180007e08  mov     [rsp+arg_0], rbx
0x180007e0d  push    rdi
0x180007e0e  sub     rsp, 20h
0x180007e12  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007e19  mov     rdi, rcx
0x180007e1c  test    rax, rax
0x180007e1f  jnz     short loc_180007E3C
0x180007e21  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007e28  xor     ebx, ebx
0x180007e2a  call    cs:__imp_GetModuleHandleW
0x180007e30  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007e37  test    rax, rax
0x180007e3a  jz      short loc_180007E4B
0x180007e3c  mov     rdx, rdi; lpProcName
0x180007e3f  mov     rcx, rax; hModule
0x180007e42  call    cs:__imp_GetProcAddress
0x180007e48  mov     rbx, rax
0x180007e4b  mov     rax, rbx
0x180007e4e  mov     rbx, [rsp+28h+arg_0]
0x180007e53  add     rsp, 20h
0x180007e57  pop     rdi
0x180007e58  retn
```
