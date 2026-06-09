# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x140004948`
- end: `0x1400049cd`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003dd0`

## callees

- `0x140004948`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004998`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140004998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000497c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000497c`

## string_xrefs

- `0x140004975`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilFailureNotifyWatchers(
        wil::details *this,
        __int64 a2,
        const struct WilFailureReport *a3,
        struct WilFailureReportInformation *a4)
{
  FARPROC ProcAddress; // rbx
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  if ( `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers )
    goto LABEL_6;
  ModuleHandleW = `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle;
  if ( `wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle
    || (ModuleHandleW = GetModuleHandleW(L"kernelbase.dll"),
        (`wil_details_GetKernelBaseProcAddress'::`2'::wil_details_kernelbaseModuleHandle = ModuleHandleW) != 0) )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "WilFailureNotifyWatchers");
  }
  `wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_6:
    ((void (__fastcall *)(_QWORD, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *))ProcAddress)(
      0,
      a2,
      a3,
      a4);
}

```

## disassembly

```asm
0x140004948  mov     [rsp+arg_0], rbx
0x14000494d  mov     [rsp+arg_8], rsi
0x140004952  push    rdi
0x140004953  sub     rsp, 20h
0x140004957  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000495e  mov     rdi, r8
0x140004961  mov     rsi, rdx
0x140004964  test    rbx, rbx
0x140004967  jnz     short loc_1400049AD
0x140004969  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004970  test    rax, rax
0x140004973  jnz     short loc_14000498E
0x140004975  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000497c  call    cs:__imp_GetModuleHandleW
0x140004982  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004989  test    rax, rax
0x14000498c  jz      short loc_1400049A1
0x14000498e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140004995  mov     rcx, rax; hModule
0x140004998  call    cs:__imp_GetProcAddress
0x14000499e  mov     rbx, rax
0x1400049a1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1400049a8  test    rbx, rbx
0x1400049ab  jz      short loc_1400049BD
0x1400049ad  mov     r8, rdi
0x1400049b0  mov     rdx, rsi
0x1400049b3  xor     ecx, ecx
0x1400049b5  mov     rax, rbx
0x1400049b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049bd  mov     rbx, [rsp+28h+arg_0]
0x1400049c2  mov     rsi, [rsp+28h+arg_8]
0x1400049c7  add     rsp, 20h
0x1400049cb  pop     rdi
0x1400049cc  retn
```
