# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1400096a4`
- end: `0x1400096f5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400069a0`
- `0x140009bb0`

## callees

- `0x1400096a4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400096de`
- `KERNEL32!GetProcAddress` at `0x1400096de`
- `KERNEL32!GetModuleHandleW` at `0x1400096c6`
- `KERNEL32!GetModuleHandleW` at `0x1400096c6`

## string_xrefs

- `0x1400096bd`: `kernelbase.dll`

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
0x1400096a4  mov     [rsp+arg_0], rbx
0x1400096a9  push    rdi
0x1400096aa  sub     rsp, 20h
0x1400096ae  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400096b5  mov     rdi, rcx
0x1400096b8  test    rax, rax
0x1400096bb  jnz     short loc_1400096D8
0x1400096bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400096c4  xor     ebx, ebx
0x1400096c6  call    cs:__imp_GetModuleHandleW
0x1400096cc  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400096d3  test    rax, rax
0x1400096d6  jz      short loc_1400096E7
0x1400096d8  mov     rdx, rdi; lpProcName
0x1400096db  mov     rcx, rax; hModule
0x1400096de  call    cs:__imp_GetProcAddress
0x1400096e4  mov     rbx, rax
0x1400096e7  mov     rax, rbx
0x1400096ea  mov     rbx, [rsp+28h+arg_0]
0x1400096ef  add     rsp, 20h
0x1400096f3  pop     rdi
0x1400096f4  retn
```
