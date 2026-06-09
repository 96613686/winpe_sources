# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800058a4`
- end: `0x180005902`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005520`
- `0x180012290`

## callees

- `0x1800058a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800058e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800058c6`

## string_xrefs

- `0x1800058bd`: `kernelbase.dll`

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
0x1800058a4  mov     [rsp+arg_0], rbx
0x1800058a9  push    rdi
0x1800058aa  sub     rsp, 20h
0x1800058ae  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800058b5  mov     rdi, rcx
0x1800058b8  test    rax, rax
0x1800058bb  jnz     short loc_1800058DE
0x1800058bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800058c4  xor     ebx, ebx
0x1800058c6  call    cs:__imp_GetModuleHandleW
0x1800058cd  nop     dword ptr [rax+rax+00h]
0x1800058d2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800058d9  test    rax, rax
0x1800058dc  jz      short loc_1800058F3
0x1800058de  mov     rdx, rdi; lpProcName
0x1800058e1  mov     rcx, rax; hModule
0x1800058e4  call    cs:__imp_GetProcAddress
0x1800058eb  nop     dword ptr [rax+rax+00h]
0x1800058f0  mov     rbx, rax
0x1800058f3  mov     rax, rbx
0x1800058f6  mov     rbx, [rsp+28h+arg_0]
0x1800058fb  add     rsp, 20h
0x1800058ff  pop     rdi
0x180005900  retn
```
