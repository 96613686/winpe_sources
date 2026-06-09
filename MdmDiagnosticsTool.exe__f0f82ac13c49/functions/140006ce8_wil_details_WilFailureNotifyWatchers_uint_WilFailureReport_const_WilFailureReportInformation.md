# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x140006ce8`
- end: `0x140006d6e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005820`

## callees

- `0x140006ce8`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006d1c`

## string_xrefs

- `0x140006d15`: `kernelbase.dll`

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
0x140006ce8  mov     [rsp+arg_0], rbx
0x140006ced  mov     [rsp+arg_8], rsi
0x140006cf2  push    rdi
0x140006cf3  sub     rsp, 20h
0x140006cf7  mov     rdi, r8
0x140006cfa  mov     rsi, rdx
0x140006cfd  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140006d04  test    rbx, rbx
0x140006d07  jnz     short loc_140006D4D
0x140006d09  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006d10  test    rax, rax
0x140006d13  jnz     short loc_140006D2E
0x140006d15  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140006d1c  call    cs:__imp_GetModuleHandleW
0x140006d22  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006d29  test    rax, rax
0x140006d2c  jz      short loc_140006D41
0x140006d2e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140006d35  mov     rcx, rax; hModule
0x140006d38  call    cs:__imp_GetProcAddress
0x140006d3e  mov     rbx, rax
0x140006d41  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x140006d48  test    rbx, rbx
0x140006d4b  jz      short loc_140006D5E
0x140006d4d  mov     r8, rdi
0x140006d50  mov     rdx, rsi
0x140006d53  xor     ecx, ecx
0x140006d55  mov     rax, rbx
0x140006d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d5d  nop
0x140006d5e  mov     rbx, [rsp+28h+arg_0]
0x140006d63  mov     rsi, [rsp+28h+arg_8]
0x140006d68  add     rsp, 20h
0x140006d6c  pop     rdi
0x140006d6d  retn
```
