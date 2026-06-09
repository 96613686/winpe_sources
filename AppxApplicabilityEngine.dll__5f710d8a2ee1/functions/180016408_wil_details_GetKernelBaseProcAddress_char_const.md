# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180016408`
- end: `0x180016459`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016038`

## callees

- `0x180016408`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016442`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016442`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001642a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001642a`

## string_xrefs

- `0x180016421`: `kernelbase.dll`

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
0x180016408  mov     [rsp+arg_0], rbx
0x18001640d  push    rdi
0x18001640e  sub     rsp, 20h
0x180016412  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016419  mov     rdi, rcx
0x18001641c  test    rax, rax
0x18001641f  jnz     short loc_18001643C
0x180016421  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180016428  xor     ebx, ebx
0x18001642a  call    cs:__imp_GetModuleHandleW
0x180016430  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180016437  test    rax, rax
0x18001643a  jz      short loc_18001644B
0x18001643c  mov     rdx, rdi; lpProcName
0x18001643f  mov     rcx, rax; hModule
0x180016442  call    cs:__imp_GetProcAddress
0x180016448  mov     rbx, rax
0x18001644b  mov     rax, rbx
0x18001644e  mov     rbx, [rsp+28h+arg_0]
0x180016453  add     rsp, 20h
0x180016457  pop     rdi
0x180016458  retn
```
