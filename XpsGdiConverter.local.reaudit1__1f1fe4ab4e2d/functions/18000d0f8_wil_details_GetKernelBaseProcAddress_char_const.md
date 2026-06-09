# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18000d0f8`
- end: `0x18000d149`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ccd8`
- `0x180023730`

## callees

- `0x18000d0f8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000d11a`
- `KERNEL32!GetModuleHandleW` at `0x18000d11a`
- `KERNEL32!GetProcAddress` at `0x18000d132`
- `KERNEL32!GetProcAddress` at `0x18000d132`

## string_xrefs

- `0x18000d111`: `kernelbase.dll`

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
0x18000d0f8  mov     [rsp+arg_0], rbx
0x18000d0fd  push    rdi
0x18000d0fe  sub     rsp, 20h
0x18000d102  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d109  mov     rdi, rcx
0x18000d10c  test    rax, rax
0x18000d10f  jnz     short loc_18000D12C
0x18000d111  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000d118  xor     ebx, ebx
0x18000d11a  call    cs:__imp_GetModuleHandleW
0x18000d120  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000d127  test    rax, rax
0x18000d12a  jz      short loc_18000D13B
0x18000d12c  mov     rdx, rdi; lpProcName
0x18000d12f  mov     rcx, rax; hModule
0x18000d132  call    cs:__imp_GetProcAddress
0x18000d138  mov     rbx, rax
0x18000d13b  mov     rax, rbx
0x18000d13e  mov     rbx, [rsp+28h+arg_0]
0x18000d143  add     rsp, 20h
0x18000d147  pop     rdi
0x18000d148  retn
```
