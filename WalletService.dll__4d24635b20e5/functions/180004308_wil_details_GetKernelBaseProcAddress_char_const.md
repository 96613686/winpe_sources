# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180004308`
- end: `0x180004359`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004228`
- `0x18000c250`

## callees

- `0x180004308`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004342`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004342`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000432a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000432a`

## string_xrefs

- `0x180004321`: `kernelbase.dll`

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
0x180004308  mov     [rsp+arg_0], rbx
0x18000430d  push    rdi
0x18000430e  sub     rsp, 20h
0x180004312  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004319  mov     rdi, rcx
0x18000431c  test    rax, rax
0x18000431f  jnz     short loc_18000433C
0x180004321  lea     rcx, ModuleName; "kernelbase.dll"
0x180004328  xor     ebx, ebx
0x18000432a  call    cs:__imp_GetModuleHandleW
0x180004330  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004337  test    rax, rax
0x18000433a  jz      short loc_18000434B
0x18000433c  mov     rdx, rdi; lpProcName
0x18000433f  mov     rcx, rax; hModule
0x180004342  call    cs:__imp_GetProcAddress
0x180004348  mov     rbx, rax
0x18000434b  mov     rax, rbx
0x18000434e  mov     rbx, [rsp+28h+arg_0]
0x180004353  add     rsp, 20h
0x180004357  pop     rdi
0x180004358  retn
```
