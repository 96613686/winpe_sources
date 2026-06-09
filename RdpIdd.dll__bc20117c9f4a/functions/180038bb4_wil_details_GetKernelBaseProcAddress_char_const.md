# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180038bb4`
- end: `0x180038c0a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180039010`

## callees

- `0x180038bb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038bf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038bf1`

## string_xrefs

- `0x180038bc6`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall wil_details_GetKernelBaseProcAddress(const char *a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v2; // rbx

  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle )
    return GetProcAddress(ModuleHandleW, "LogStagedFeatureUsage");
  v2 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW;
  if ( ModuleHandleW )
    return GetProcAddress(ModuleHandleW, "LogStagedFeatureUsage");
  return (FARPROC)v2;
}

```

## disassembly

```asm
0x180038bb4  push    rbx
0x180038bb6  sub     rsp, 20h
0x180038bba  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180038bc1  test    rax, rax
0x180038bc4  jnz     short loc_180038BE7
0x180038bc6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180038bcd  xor     ebx, ebx
0x180038bcf  call    cs:__imp_GetModuleHandleW
0x180038bd6  nop     dword ptr [rax+rax+00h]
0x180038bdb  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180038be2  test    rax, rax
0x180038be5  jz      short loc_180038C00
0x180038be7  lea     rdx, aLogstagedfeatu; "LogStagedFeatureUsage"
0x180038bee  mov     rcx, rax; hModule
0x180038bf1  call    cs:__imp_GetProcAddress
0x180038bf8  nop     dword ptr [rax+rax+00h]
0x180038bfd  mov     rbx, rax
0x180038c00  mov     rax, rbx
0x180038c03  add     rsp, 20h
0x180038c07  pop     rbx
0x180038c08  retn
```
