# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180018b10`
- end: `0x180018b61`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018ab0`
- `0x18002c4e0`

## callees

- `0x180018b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018b4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018b32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018b32`

## string_xrefs

- `0x180018b29`: `kernelbase.dll`

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
0x180018b10  mov     [rsp+arg_0], rbx
0x180018b15  push    rdi
0x180018b16  sub     rsp, 20h
0x180018b1a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180018b21  mov     rdi, rcx
0x180018b24  test    rax, rax
0x180018b27  jnz     short loc_180018B44
0x180018b29  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180018b30  xor     ebx, ebx
0x180018b32  call    cs:__imp_GetModuleHandleW
0x180018b38  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180018b3f  test    rax, rax
0x180018b42  jz      short loc_180018B53
0x180018b44  mov     rdx, rdi; lpProcName
0x180018b47  mov     rcx, rax; hModule
0x180018b4a  call    cs:__imp_GetProcAddress
0x180018b50  mov     rbx, rax
0x180018b53  mov     rax, rbx
0x180018b56  mov     rbx, [rsp+28h+arg_0]
0x180018b5b  add     rsp, 20h
0x180018b5f  pop     rdi
0x180018b60  retn
```
