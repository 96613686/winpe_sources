# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14001bc5c`
- end: `0x14001bcad`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140017978`
- `0x14001c840`

## callees

- `0x14001bc5c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14001bc96`
- `KERNEL32!GetProcAddress` at `0x14001bc96`
- `KERNEL32!GetModuleHandleW` at `0x14001bc7e`
- `KERNEL32!GetModuleHandleW` at `0x14001bc7e`

## string_xrefs

- `0x14001bc75`: `kernelbase.dll`

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
0x14001bc5c  mov     [rsp+arg_0], rbx
0x14001bc61  push    rdi
0x14001bc62  sub     rsp, 20h
0x14001bc66  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001bc6d  mov     rdi, rcx
0x14001bc70  test    rax, rax
0x14001bc73  jnz     short loc_14001BC90
0x14001bc75  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14001bc7c  xor     ebx, ebx
0x14001bc7e  call    cs:__imp_GetModuleHandleW
0x14001bc84  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14001bc8b  test    rax, rax
0x14001bc8e  jz      short loc_14001BC9F
0x14001bc90  mov     rdx, rdi; lpProcName
0x14001bc93  mov     rcx, rax; hModule
0x14001bc96  call    cs:__imp_GetProcAddress
0x14001bc9c  mov     rbx, rax
0x14001bc9f  mov     rax, rbx
0x14001bca2  mov     rbx, [rsp+28h+arg_0]
0x14001bca7  add     rsp, 20h
0x14001bcab  pop     rdi
0x14001bcac  retn
```
