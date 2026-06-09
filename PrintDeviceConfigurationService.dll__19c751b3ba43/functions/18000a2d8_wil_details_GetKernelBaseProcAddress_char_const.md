# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a2d8`
- end: `0x18000a329`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007290`
- `0x18000a780`

## callees

- `0x18000a2d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a312`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a312`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2fa`

## string_xrefs

- `0x18000a2f1`: `kernelbase.dll`

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
0x18000a2d8  mov     [rsp+arg_0], rbx
0x18000a2dd  push    rdi
0x18000a2de  sub     rsp, 20h
0x18000a2e2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a2e9  mov     rdi, rcx
0x18000a2ec  test    rax, rax
0x18000a2ef  jnz     short loc_18000A30C
0x18000a2f1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a2f8  xor     ebx, ebx
0x18000a2fa  call    cs:__imp_GetModuleHandleW
0x18000a300  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a307  test    rax, rax
0x18000a30a  jz      short loc_18000A31B
0x18000a30c  mov     rdx, rdi; lpProcName
0x18000a30f  mov     rcx, rax; hModule
0x18000a312  call    cs:__imp_GetProcAddress
0x18000a318  mov     rbx, rax
0x18000a31b  mov     rax, rbx
0x18000a31e  mov     rbx, [rsp+28h+arg_0]
0x18000a323  add     rsp, 20h
0x18000a327  pop     rdi
0x18000a328  retn
```
