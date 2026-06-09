# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180009a98`
- end: `0x180009ae9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008908`

## callees

- `0x180009a98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009aba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ad2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ad2`

## string_xrefs

- `0x180009ab1`: `kernelbase.dll`

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
0x180009a98  mov     [rsp+arg_0], rbx
0x180009a9d  push    rdi
0x180009a9e  sub     rsp, 20h
0x180009aa2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009aa9  mov     rdi, rcx
0x180009aac  test    rax, rax
0x180009aaf  jnz     short loc_180009ACC
0x180009ab1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009ab8  xor     ebx, ebx
0x180009aba  call    cs:__imp_GetModuleHandleW
0x180009ac0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009ac7  test    rax, rax
0x180009aca  jz      short loc_180009ADB
0x180009acc  mov     rdx, rdi; lpProcName
0x180009acf  mov     rcx, rax; hModule
0x180009ad2  call    cs:__imp_GetProcAddress
0x180009ad8  mov     rbx, rax
0x180009adb  mov     rax, rbx
0x180009ade  mov     rbx, [rsp+28h+arg_0]
0x180009ae3  add     rsp, 20h
0x180009ae7  pop     rdi
0x180009ae8  retn
```
