# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180056914`
- end: `0x180056965`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180053c00`
- `0x180056e30`

## callees

- `0x180056914`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180056936`
- `KERNEL32!GetModuleHandleW` at `0x180056936`
- `KERNEL32!GetProcAddress` at `0x18005694e`
- `KERNEL32!GetProcAddress` at `0x18005694e`

## string_xrefs

- `0x18005692d`: `kernelbase.dll`

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
0x180056914  mov     [rsp+arg_0], rbx
0x180056919  push    rdi
0x18005691a  sub     rsp, 20h
0x18005691e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180056925  mov     rdi, rcx
0x180056928  test    rax, rax
0x18005692b  jnz     short loc_180056948
0x18005692d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180056934  xor     ebx, ebx
0x180056936  call    cs:__imp_GetModuleHandleW
0x18005693c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180056943  test    rax, rax
0x180056946  jz      short loc_180056957
0x180056948  mov     rdx, rdi; lpProcName
0x18005694b  mov     rcx, rax; hModule
0x18005694e  call    cs:__imp_GetProcAddress
0x180056954  mov     rbx, rax
0x180056957  mov     rax, rbx
0x18005695a  mov     rbx, [rsp+28h+arg_0]
0x18005695f  add     rsp, 20h
0x180056963  pop     rdi
0x180056964  retn
```
