# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x140007264`
- end: `0x1400072b5`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400056d0`

## callees

- `0x140007264`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000729e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000729e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007286`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007286`

## string_xrefs

- `0x14000727d`: `kernelbase.dll`

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
0x140007264  mov     [rsp+arg_0], rbx
0x140007269  push    rdi
0x14000726a  sub     rsp, 20h
0x14000726e  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007275  mov     rdi, rcx
0x140007278  test    rax, rax
0x14000727b  jnz     short loc_140007298
0x14000727d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140007284  xor     ebx, ebx
0x140007286  call    cs:__imp_GetModuleHandleW
0x14000728c  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007293  test    rax, rax
0x140007296  jz      short loc_1400072A7
0x140007298  mov     rdx, rdi; lpProcName
0x14000729b  mov     rcx, rax; hModule
0x14000729e  call    cs:__imp_GetProcAddress
0x1400072a4  mov     rbx, rax
0x1400072a7  mov     rax, rbx
0x1400072aa  mov     rbx, [rsp+28h+arg_0]
0x1400072af  add     rsp, 20h
0x1400072b3  pop     rdi
0x1400072b4  retn
```
