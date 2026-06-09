# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000a884`
- end: `0x18000a8e2`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009a20`
- `0x18000acc0`

## callees

- `0x18000a884`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a8a6`

## string_xrefs

- `0x18000a89d`: `kernelbase.dll`

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
0x18000a884  mov     [rsp+arg_0], rbx
0x18000a889  push    rdi
0x18000a88a  sub     rsp, 20h
0x18000a88e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a895  mov     rdi, rcx
0x18000a898  test    rax, rax
0x18000a89b  jnz     short loc_18000A8BE
0x18000a89d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a8a4  xor     ebx, ebx
0x18000a8a6  call    cs:__imp_GetModuleHandleW
0x18000a8ad  nop     dword ptr [rax+rax+00h]
0x18000a8b2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a8b9  test    rax, rax
0x18000a8bc  jz      short loc_18000A8D3
0x18000a8be  mov     rdx, rdi; lpProcName
0x18000a8c1  mov     rcx, rax; hModule
0x18000a8c4  call    cs:__imp_GetProcAddress
0x18000a8cb  nop     dword ptr [rax+rax+00h]
0x18000a8d0  mov     rbx, rax
0x18000a8d3  mov     rax, rbx
0x18000a8d6  mov     rbx, [rsp+28h+arg_0]
0x18000a8db  add     rsp, 20h
0x18000a8df  pop     rdi
0x18000a8e0  retn
```
