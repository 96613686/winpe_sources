# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800191a8`
- end: `0x1800191f9`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800148f0`
- `0x180019ac0`

## callees

- `0x1800191a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800191ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800191ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800191e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800191e2`

## string_xrefs

- `0x1800191c1`: `kernelbase.dll`

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
0x1800191a8  mov     [rsp+arg_0], rbx
0x1800191ad  push    rdi
0x1800191ae  sub     rsp, 20h
0x1800191b2  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800191b9  mov     rdi, rcx
0x1800191bc  test    rax, rax
0x1800191bf  jnz     short loc_1800191DC
0x1800191c1  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800191c8  xor     ebx, ebx
0x1800191ca  call    cs:__imp_GetModuleHandleW
0x1800191d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800191d7  test    rax, rax
0x1800191da  jz      short loc_1800191EB
0x1800191dc  mov     rdx, rdi; lpProcName
0x1800191df  mov     rcx, rax; hModule
0x1800191e2  call    cs:__imp_GetProcAddress
0x1800191e8  mov     rbx, rax
0x1800191eb  mov     rax, rbx
0x1800191ee  mov     rbx, [rsp+28h+arg_0]
0x1800191f3  add     rsp, 20h
0x1800191f7  pop     rdi
0x1800191f8  retn
```
