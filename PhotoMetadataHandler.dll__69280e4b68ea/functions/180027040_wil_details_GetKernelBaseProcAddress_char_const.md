# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180027040`
- end: `0x180027090`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `80`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180026bc8`

## callees

- `0x180017682`
- `0x18001768e`
- `0x180027040`

## string_xrefs

- `0x180027059`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(LPCSTR lpProcName)
{
  HMODULE ModuleHandleW_0; // rax
  __int64 v3; // rbx

  ModuleHandleW_0 = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress_0(ModuleHandleW_0, lpProcName);
  v3 = 0;
  ModuleHandleW_0 = GetModuleHandleW_0(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW_0;
  if ( ModuleHandleW_0 )
    return GetProcAddress_0(ModuleHandleW_0, lpProcName);
  return (FARPROC)v3;
}

```

## disassembly

```asm
0x180027040  mov     [rsp+arg_0], rbx
0x180027045  push    rdi
0x180027046  sub     rsp, 20h
0x18002704a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180027051  mov     rdi, rcx
0x180027054  test    rax, rax
0x180027057  jnz     short loc_180027073
0x180027059  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180027060  xor     ebx, ebx
0x180027062  call    GetModuleHandleW_0
0x180027067  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002706e  test    rax, rax
0x180027071  jz      short loc_180027081
0x180027073  mov     rdx, rdi; lpProcName
0x180027076  mov     rcx, rax; hModule
0x180027079  call    GetProcAddress_0
0x18002707e  mov     rbx, rax
0x180027081  mov     rax, rbx
0x180027084  mov     rbx, [rsp+28h+arg_0]
0x180027089  add     rsp, 20h
0x18002708d  pop     rdi
0x18002708e  retn
```
