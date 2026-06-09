# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180005c48`
- end: `0x180005c99`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005968`

## callees

- `0x180005c48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005c6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c82`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005c82`

## string_xrefs

- `0x180005c61`: `kernelbase.dll`

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
0x180005c48  mov     [rsp+arg_0], rbx
0x180005c4d  push    rdi
0x180005c4e  sub     rsp, 20h
0x180005c52  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005c59  mov     rdi, rcx
0x180005c5c  test    rax, rax
0x180005c5f  jnz     short loc_180005C7C
0x180005c61  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005c68  xor     ebx, ebx
0x180005c6a  call    cs:__imp_GetModuleHandleW
0x180005c70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005c77  test    rax, rax
0x180005c7a  jz      short loc_180005C8B
0x180005c7c  mov     rdx, rdi; lpProcName
0x180005c7f  mov     rcx, rax; hModule
0x180005c82  call    cs:__imp_GetProcAddress
0x180005c88  mov     rbx, rax
0x180005c8b  mov     rax, rbx
0x180005c8e  mov     rbx, [rsp+28h+arg_0]
0x180005c93  add     rsp, 20h
0x180005c97  pop     rdi
0x180005c98  retn
```
