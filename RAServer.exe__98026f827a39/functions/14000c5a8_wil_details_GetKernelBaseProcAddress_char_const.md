# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14000c5a8`
- end: `0x14000c5f9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000b7e8`

## callees

- `0x14000c5a8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000c5e2`
- `KERNEL32!GetProcAddress` at `0x14000c5e2`
- `KERNEL32!GetModuleHandleW` at `0x14000c5ca`
- `KERNEL32!GetModuleHandleW` at `0x14000c5ca`

## string_xrefs

- `0x14000c5c1`: `kernelbase.dll`

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
0x14000c5a8  mov     [rsp+arg_0], rbx
0x14000c5ad  push    rdi
0x14000c5ae  sub     rsp, 20h
0x14000c5b2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000c5b9  mov     rdi, rcx
0x14000c5bc  test    rax, rax
0x14000c5bf  jnz     short loc_14000C5DC
0x14000c5c1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000c5c8  xor     ebx, ebx
0x14000c5ca  call    cs:__imp_GetModuleHandleW
0x14000c5d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000c5d7  test    rax, rax
0x14000c5da  jz      short loc_14000C5EB
0x14000c5dc  mov     rdx, rdi; lpProcName
0x14000c5df  mov     rcx, rax; hModule
0x14000c5e2  call    cs:__imp_GetProcAddress
0x14000c5e8  mov     rbx, rax
0x14000c5eb  mov     rax, rbx
0x14000c5ee  mov     rbx, [rsp+28h+arg_0]
0x14000c5f3  add     rsp, 20h
0x14000c5f7  pop     rdi
0x14000c5f8  retn
```
