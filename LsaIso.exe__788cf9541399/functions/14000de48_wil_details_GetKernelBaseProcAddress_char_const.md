# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000de48`
- end: `0x14000de99`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b1b0`

## callees

- `0x14000de48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000de82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000de82`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000de6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000de6a`

## string_xrefs

- `0x14000de61`: `kernelbase.dll`

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
0x14000de48  mov     [rsp+arg_0], rbx
0x14000de4d  push    rdi
0x14000de4e  sub     rsp, 20h
0x14000de52  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000de59  mov     rdi, rcx
0x14000de5c  test    rax, rax
0x14000de5f  jnz     short loc_14000DE7C
0x14000de61  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000de68  xor     ebx, ebx
0x14000de6a  call    cs:__imp_GetModuleHandleW
0x14000de70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000de77  test    rax, rax
0x14000de7a  jz      short loc_14000DE8B
0x14000de7c  mov     rdx, rdi; lpProcName
0x14000de7f  mov     rcx, rax; hModule
0x14000de82  call    cs:__imp_GetProcAddress
0x14000de88  mov     rbx, rax
0x14000de8b  mov     rax, rbx
0x14000de8e  mov     rbx, [rsp+28h+arg_0]
0x14000de93  add     rsp, 20h
0x14000de97  pop     rdi
0x14000de98  retn
```
