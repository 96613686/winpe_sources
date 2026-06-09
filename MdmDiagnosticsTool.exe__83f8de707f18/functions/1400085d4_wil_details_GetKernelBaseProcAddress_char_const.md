# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1400085d4`
- end: `0x14000862a`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `86`
- prototype: `__int64 (*__fastcall(const char *))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007120`

## callees

- `0x1400085d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008611`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008611`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400085ef`

## string_xrefs

- `0x1400085e6`: `kernelbase.dll`

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
0x1400085d4  push    rbx
0x1400085d6  sub     rsp, 20h
0x1400085da  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400085e1  test    rax, rax
0x1400085e4  jnz     short loc_140008607
0x1400085e6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400085ed  xor     ebx, ebx
0x1400085ef  call    cs:__imp_GetModuleHandleW
0x1400085f6  nop     dword ptr [rax+rax+00h]
0x1400085fb  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140008602  test    rax, rax
0x140008605  jz      short loc_140008620
0x140008607  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000860e  mov     rcx, rax; hModule
0x140008611  call    cs:__imp_GetProcAddress
0x140008618  nop     dword ptr [rax+rax+00h]
0x14000861d  mov     rbx, rax
0x140008620  mov     rax, rbx
0x140008623  add     rsp, 20h
0x140008627  pop     rbx
0x140008628  retn
```
