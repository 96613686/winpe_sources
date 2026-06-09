# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000ced0`
- end: `0x14000cf21`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006de0`
- `0x14000d2e0`

## callees

- `0x14000ced0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cef2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cef2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cf0a`

## string_xrefs

- `0x14000cee9`: `kernelbase.dll`

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
0x14000ced0  mov     [rsp+arg_0], rbx
0x14000ced5  push    rdi
0x14000ced6  sub     rsp, 20h
0x14000ceda  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000cee1  mov     rdi, rcx
0x14000cee4  test    rax, rax
0x14000cee7  jnz     short loc_14000CF04
0x14000cee9  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000cef0  xor     ebx, ebx
0x14000cef2  call    cs:__imp_GetModuleHandleW
0x14000cef8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000ceff  test    rax, rax
0x14000cf02  jz      short loc_14000CF13
0x14000cf04  mov     rdx, rdi; lpProcName
0x14000cf07  mov     rcx, rax; hModule
0x14000cf0a  call    cs:__imp_GetProcAddress
0x14000cf10  mov     rbx, rax
0x14000cf13  mov     rax, rbx
0x14000cf16  mov     rbx, [rsp+28h+arg_0]
0x14000cf1b  add     rsp, 20h
0x14000cf1f  pop     rdi
0x14000cf20  retn
```
