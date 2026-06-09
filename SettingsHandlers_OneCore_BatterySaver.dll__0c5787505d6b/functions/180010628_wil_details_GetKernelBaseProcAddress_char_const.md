# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180010628`
- end: `0x180010679`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d8e0`
- `0x180010ad0`

## callees

- `0x180010628`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010662`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010662`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001064a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001064a`

## string_xrefs

- `0x180010641`: `kernelbase.dll`

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
0x180010628  mov     [rsp+arg_0], rbx
0x18001062d  push    rdi
0x18001062e  sub     rsp, 20h
0x180010632  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010639  mov     rdi, rcx
0x18001063c  test    rax, rax
0x18001063f  jnz     short loc_18001065C
0x180010641  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180010648  xor     ebx, ebx
0x18001064a  call    cs:__imp_GetModuleHandleW
0x180010650  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180010657  test    rax, rax
0x18001065a  jz      short loc_18001066B
0x18001065c  mov     rdx, rdi; lpProcName
0x18001065f  mov     rcx, rax; hModule
0x180010662  call    cs:__imp_GetProcAddress
0x180010668  mov     rbx, rax
0x18001066b  mov     rax, rbx
0x18001066e  mov     rbx, [rsp+28h+arg_0]
0x180010673  add     rsp, 20h
0x180010677  pop     rdi
0x180010678  retn
```
