# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180006d04`
- end: `0x180006d5a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005e40`

## callees

- `0x180006d04`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180006d41`
- `KERNEL32!GetProcAddress` at `0x180006d41`
- `KERNEL32!GetModuleHandleW` at `0x180006d1f`
- `KERNEL32!GetModuleHandleW` at `0x180006d1f`

## string_xrefs

- `0x180006d16`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(const char *a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v2; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  v2 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  return (FARPROC)v2;
}

```

## disassembly

```asm
0x180006d04  push    rbx
0x180006d06  sub     rsp, 20h
0x180006d0a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006d11  test    rax, rax
0x180006d14  jnz     short loc_180006D37
0x180006d16  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006d1d  xor     ebx, ebx
0x180006d1f  call    cs:__imp_GetModuleHandleW
0x180006d26  nop     dword ptr [rax+rax+00h]
0x180006d2b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006d32  test    rax, rax
0x180006d35  jz      short loc_180006D50
0x180006d37  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006d3e  mov     rcx, rax; hModule
0x180006d41  call    cs:__imp_GetProcAddress
0x180006d48  nop     dword ptr [rax+rax+00h]
0x180006d4d  mov     rbx, rax
0x180006d50  mov     rax, rbx
0x180006d53  add     rsp, 20h
0x180006d57  pop     rbx
0x180006d58  retn
```
