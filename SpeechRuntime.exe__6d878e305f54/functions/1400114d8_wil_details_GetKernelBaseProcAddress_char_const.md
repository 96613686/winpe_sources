# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1400114d8`
- end: `0x140011529`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140010d88`
- `0x1400190a0`

## callees

- `0x1400114d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011512`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011512`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400114fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400114fa`

## string_xrefs

- `0x1400114f1`: `kernelbase.dll`

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
0x1400114d8  mov     [rsp+arg_0], rbx
0x1400114dd  push    rdi
0x1400114de  sub     rsp, 20h
0x1400114e2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400114e9  mov     rdi, rcx
0x1400114ec  test    rax, rax
0x1400114ef  jnz     short loc_14001150C
0x1400114f1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400114f8  xor     ebx, ebx
0x1400114fa  call    cs:__imp_GetModuleHandleW
0x140011500  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140011507  test    rax, rax
0x14001150a  jz      short loc_14001151B
0x14001150c  mov     rdx, rdi; lpProcName
0x14001150f  mov     rcx, rax; hModule
0x140011512  call    cs:__imp_GetProcAddress
0x140011518  mov     rbx, rax
0x14001151b  mov     rax, rbx
0x14001151e  mov     rbx, [rsp+28h+arg_0]
0x140011523  add     rsp, 20h
0x140011527  pop     rdi
0x140011528  retn
```
