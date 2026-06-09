# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x180006754`
- end: `0x1800067aa`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005830`

## callees

- `0x180006754`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000676f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000676f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006791`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006791`

## string_xrefs

- `0x180006766`: `kernelbase.dll`

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
0x180006754  push    rbx
0x180006756  sub     rsp, 20h
0x18000675a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006761  test    rax, rax
0x180006764  jnz     short loc_180006787
0x180006766  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000676d  xor     ebx, ebx
0x18000676f  call    cs:__imp_GetModuleHandleW
0x180006776  nop     dword ptr [rax+rax+00h]
0x18000677b  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006782  test    rax, rax
0x180006785  jz      short loc_1800067A0
0x180006787  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000678e  mov     rcx, rax; hModule
0x180006791  call    cs:__imp_GetProcAddress
0x180006798  nop     dword ptr [rax+rax+00h]
0x18000679d  mov     rbx, rax
0x1800067a0  mov     rax, rbx
0x1800067a3  add     rsp, 20h
0x1800067a7  pop     rbx
0x1800067a8  retn
```
