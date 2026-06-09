# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800066f8`
- end: `0x18000677e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800058b0`

## callees

- `0x1800066f8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006748`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000672c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000672c`

## string_xrefs

- `0x180006725`: `kernelbase.dll`

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
0x1800066f8  mov     [rsp+arg_0], rbx
0x1800066fd  mov     [rsp+arg_8], rsi
0x180006702  push    rdi
0x180006703  sub     rsp, 20h
0x180006707  mov     rdi, r8
0x18000670a  mov     rsi, rdx
0x18000670d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006714  test    rbx, rbx
0x180006717  jnz     short loc_18000675D
0x180006719  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006720  test    rax, rax
0x180006723  jnz     short loc_18000673E
0x180006725  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000672c  call    cs:__imp_GetModuleHandleW
0x180006732  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006739  test    rax, rax
0x18000673c  jz      short loc_180006751
0x18000673e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006745  mov     rcx, rax; hModule
0x180006748  call    cs:__imp_GetProcAddress
0x18000674e  mov     rbx, rax
0x180006751  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180006758  test    rbx, rbx
0x18000675b  jz      short loc_18000676E
0x18000675d  mov     r8, rdi
0x180006760  mov     rdx, rsi
0x180006763  xor     ecx, ecx
0x180006765  mov     rax, rbx
0x180006768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000676d  nop
0x18000676e  mov     rbx, [rsp+28h+arg_0]
0x180006773  mov     rsi, [rsp+28h+arg_8]
0x180006778  add     rsp, 20h
0x18000677c  pop     rdi
0x18000677d  retn
```
