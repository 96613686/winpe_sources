# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800407f0`
- end: `0x18004084b`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `91`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003fec8`
- `0x180069780`

## callees

- `0x1800407f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040834`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040834`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004081c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004081c`

## string_xrefs

- `0x180040815`: `kernelbase.dll`

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
0x1800407f0  push    rdi
0x1800407f2  sub     rsp, 30h
0x1800407f6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800407ff  mov     [rsp+38h+arg_0], rbx
0x180040804  mov     rdi, rcx
0x180040807  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18004080e  test    rax, rax
0x180040811  jnz     short loc_18004082E
0x180040813  xor     ebx, ebx
0x180040815  lea     rcx, ModuleName; "kernelbase.dll"
0x18004081c  call    cs:__imp_GetModuleHandleW
0x180040822  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180040829  test    rax, rax
0x18004082c  jz      short loc_18004083D
0x18004082e  mov     rdx, rdi; lpProcName
0x180040831  mov     rcx, rax; hModule
0x180040834  call    cs:__imp_GetProcAddress
0x18004083a  mov     rbx, rax
0x18004083d  mov     rax, rbx
0x180040840  mov     rbx, [rsp+38h+arg_0]
0x180040845  add     rsp, 30h
0x180040849  pop     rdi
0x18004084a  retn
```
