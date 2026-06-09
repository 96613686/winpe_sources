# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180009a98`
- end: `0x180009b1e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800089a0`

## callees

- `0x180009a98`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009acc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009acc`

## string_xrefs

- `0x180009ac5`: `kernelbase.dll`

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
0x180009a98  mov     [rsp+arg_0], rbx
0x180009a9d  mov     [rsp+arg_8], rsi
0x180009aa2  push    rdi
0x180009aa3  sub     rsp, 20h
0x180009aa7  mov     rdi, r8
0x180009aaa  mov     rsi, rdx
0x180009aad  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180009ab4  test    rbx, rbx
0x180009ab7  jnz     short loc_180009AFD
0x180009ab9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009ac0  test    rax, rax
0x180009ac3  jnz     short loc_180009ADE
0x180009ac5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009acc  call    cs:__imp_GetModuleHandleW
0x180009ad2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009ad9  test    rax, rax
0x180009adc  jz      short loc_180009AF1
0x180009ade  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180009ae5  mov     rcx, rax; hModule
0x180009ae8  call    cs:__imp_GetProcAddress
0x180009aee  mov     rbx, rax
0x180009af1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180009af8  test    rbx, rbx
0x180009afb  jz      short loc_180009B0E
0x180009afd  mov     r8, rdi
0x180009b00  mov     rdx, rsi
0x180009b03  xor     ecx, ecx
0x180009b05  mov     rax, rbx
0x180009b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0d  nop
0x180009b0e  mov     rbx, [rsp+28h+arg_0]
0x180009b13  mov     rsi, [rsp+28h+arg_8]
0x180009b18  add     rsp, 20h
0x180009b1c  pop     rdi
0x180009b1d  retn
```
