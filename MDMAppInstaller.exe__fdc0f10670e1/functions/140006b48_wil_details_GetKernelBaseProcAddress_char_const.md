# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140006b48`
- end: `0x140006b99`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140006108`
- `0x140013570`

## callees

- `0x140006b48`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140006b82`
- `KERNEL32!GetProcAddress` at `0x140006b82`
- `KERNEL32!GetModuleHandleW` at `0x140006b6a`
- `KERNEL32!GetModuleHandleW` at `0x140006b6a`

## string_xrefs

- `0x140006b61`: `kernelbase.dll`

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
0x140006b48  mov     [rsp+arg_0], rbx
0x140006b4d  push    rdi
0x140006b4e  sub     rsp, 20h
0x140006b52  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006b59  mov     rdi, rcx
0x140006b5c  test    rax, rax
0x140006b5f  jnz     short loc_140006B7C
0x140006b61  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006b68  xor     ebx, ebx
0x140006b6a  call    cs:__imp_GetModuleHandleW
0x140006b70  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006b77  test    rax, rax
0x140006b7a  jz      short loc_140006B8B
0x140006b7c  mov     rdx, rdi; lpProcName
0x140006b7f  mov     rcx, rax; hModule
0x140006b82  call    cs:__imp_GetProcAddress
0x140006b88  mov     rbx, rax
0x140006b8b  mov     rax, rbx
0x140006b8e  mov     rbx, [rsp+28h+arg_0]
0x140006b93  add     rsp, 20h
0x140006b97  pop     rdi
0x140006b98  retn
```
