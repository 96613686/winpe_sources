# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180012c88`
- end: `0x180012cd9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010a30`
- `0x180013070`

## callees

- `0x180012c88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012caa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012cc2`

## string_xrefs

- `0x180012ca1`: `kernelbase.dll`

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
0x180012c88  mov     [rsp+arg_0], rbx
0x180012c8d  push    rdi
0x180012c8e  sub     rsp, 20h
0x180012c92  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012c99  mov     rdi, rcx
0x180012c9c  test    rax, rax
0x180012c9f  jnz     short loc_180012CBC
0x180012ca1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180012ca8  xor     ebx, ebx
0x180012caa  call    cs:__imp_GetModuleHandleW
0x180012cb0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012cb7  test    rax, rax
0x180012cba  jz      short loc_180012CCB
0x180012cbc  mov     rdx, rdi; lpProcName
0x180012cbf  mov     rcx, rax; hModule
0x180012cc2  call    cs:__imp_GetProcAddress
0x180012cc8  mov     rbx, rax
0x180012ccb  mov     rax, rbx
0x180012cce  mov     rbx, [rsp+28h+arg_0]
0x180012cd3  add     rsp, 20h
0x180012cd7  pop     rdi
0x180012cd8  retn
```
