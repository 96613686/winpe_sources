# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180058370`
- end: `0x1800583ce`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `94`
- prototype: `FARPROC __fastcall(LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180055690`
- `0x1800588b0`

## callees

- `0x180058370`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180058392`
- `KERNEL32!GetModuleHandleW` at `0x180058392`
- `KERNEL32!GetProcAddress` at `0x1800583b0`
- `KERNEL32!GetProcAddress` at `0x1800583b0`

## string_xrefs

- `0x180058389`: `kernelbase.dll`

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
0x180058370  mov     [rsp+arg_0], rbx
0x180058375  push    rdi
0x180058376  sub     rsp, 20h
0x18005837a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180058381  mov     rdi, rcx
0x180058384  test    rax, rax
0x180058387  jnz     short loc_1800583AA
0x180058389  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180058390  xor     ebx, ebx
0x180058392  call    cs:__imp_GetModuleHandleW
0x180058399  nop     dword ptr [rax+rax+00h]
0x18005839e  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800583a5  test    rax, rax
0x1800583a8  jz      short loc_1800583BF
0x1800583aa  mov     rdx, rdi; lpProcName
0x1800583ad  mov     rcx, rax; hModule
0x1800583b0  call    cs:__imp_GetProcAddress
0x1800583b7  nop     dword ptr [rax+rax+00h]
0x1800583bc  mov     rbx, rax
0x1800583bf  mov     rax, rbx
0x1800583c2  mov     rbx, [rsp+28h+arg_0]
0x1800583c7  add     rsp, 20h
0x1800583cb  pop     rdi
0x1800583cc  retn
```
