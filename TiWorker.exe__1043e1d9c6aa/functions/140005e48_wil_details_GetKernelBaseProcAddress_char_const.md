# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140005e48`
- end: `0x140005e99`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005c48`

## callees

- `0x140005e48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005e82`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140005e82`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005e6a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x140005e6a`

## string_xrefs

- `0x140005e61`: `kernelbase.dll`

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
0x140005e48  mov     [rsp+arg_0], rbx
0x140005e4d  push    rdi
0x140005e4e  sub     rsp, 20h
0x140005e52  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005e59  mov     rdi, rcx
0x140005e5c  test    rax, rax
0x140005e5f  jnz     short loc_140005E7C
0x140005e61  lea     rcx, LibFileName; "kernelbase.dll"
0x140005e68  xor     ebx, ebx
0x140005e6a  call    cs:__imp_GetModuleHandleW
0x140005e70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005e77  test    rax, rax
0x140005e7a  jz      short loc_140005E8B
0x140005e7c  mov     rdx, rdi; lpProcName
0x140005e7f  mov     rcx, rax; hModule
0x140005e82  call    cs:__imp_GetProcAddress
0x140005e88  mov     rbx, rax
0x140005e8b  mov     rax, rbx
0x140005e8e  mov     rbx, [rsp+28h+arg_0]
0x140005e93  add     rsp, 20h
0x140005e97  pop     rdi
0x140005e98  retn
```
