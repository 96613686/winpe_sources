# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180025e00`
- end: `0x180025e4f`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `79`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180025998`

## callees

- `0x180016c32`
- `0x180016c3e`
- `0x180025e00`

## string_xrefs

- `0x180025e19`: `kernelbase.dll`

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
0x180025e00  mov     [rsp+arg_0], rbx
0x180025e05  push    rdi
0x180025e06  sub     rsp, 20h
0x180025e0a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025e11  mov     rdi, rcx
0x180025e14  test    rax, rax
0x180025e17  jnz     short loc_180025E33
0x180025e19  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180025e20  xor     ebx, ebx
0x180025e22  call    GetModuleHandleW_0
0x180025e27  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180025e2e  test    rax, rax
0x180025e31  jz      short loc_180025E41
0x180025e33  mov     rdx, rdi; lpProcName
0x180025e36  mov     rcx, rax; hModule
0x180025e39  call    GetProcAddress_0
0x180025e3e  mov     rbx, rax
0x180025e41  mov     rax, rbx
0x180025e44  mov     rbx, [rsp+28h+arg_0]
0x180025e49  add     rsp, 20h
0x180025e4d  pop     rdi
0x180025e4e  retn
```
