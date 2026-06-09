# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000bc3c`
- end: `0x14000bc8d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b718`
- `0x14000c100`

## callees

- `0x14000bc3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bc5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bc5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bc76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bc76`

## string_xrefs

- `0x14000bc55`: `kernelbase.dll`

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
0x14000bc3c  mov     [rsp+arg_0], rbx
0x14000bc41  push    rdi
0x14000bc42  sub     rsp, 20h
0x14000bc46  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000bc4d  mov     rdi, rcx
0x14000bc50  test    rax, rax
0x14000bc53  jnz     short loc_14000BC70
0x14000bc55  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000bc5c  xor     ebx, ebx
0x14000bc5e  call    cs:__imp_GetModuleHandleW
0x14000bc64  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000bc6b  test    rax, rax
0x14000bc6e  jz      short loc_14000BC7F
0x14000bc70  mov     rdx, rdi; lpProcName
0x14000bc73  mov     rcx, rax; hModule
0x14000bc76  call    cs:__imp_GetProcAddress
0x14000bc7c  mov     rbx, rax
0x14000bc7f  mov     rax, rbx
0x14000bc82  mov     rbx, [rsp+28h+arg_0]
0x14000bc87  add     rsp, 20h
0x14000bc8b  pop     rdi
0x14000bc8c  retn
```
