# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180006f98`
- end: `0x18000701d`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `133`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800062f0`

## callees

- `0x180006f98`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006fcc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fe8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006fe8`

## string_xrefs

- `0x180006fc5`: `kernelbase.dll`

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
0x180006f98  mov     [rsp+arg_0], rbx
0x180006f9d  mov     [rsp+arg_8], rsi
0x180006fa2  push    rdi
0x180006fa3  sub     rsp, 20h
0x180006fa7  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006fae  mov     rdi, r8
0x180006fb1  mov     rsi, rdx
0x180006fb4  test    rbx, rbx
0x180006fb7  jnz     short loc_180006FFD
0x180006fb9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006fc0  test    rax, rax
0x180006fc3  jnz     short loc_180006FDE
0x180006fc5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006fcc  call    cs:__imp_GetModuleHandleW
0x180006fd2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006fd9  test    rax, rax
0x180006fdc  jz      short loc_180006FF1
0x180006fde  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180006fe5  mov     rcx, rax; hModule
0x180006fe8  call    cs:__imp_GetProcAddress
0x180006fee  mov     rbx, rax
0x180006ff1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180006ff8  test    rbx, rbx
0x180006ffb  jz      short loc_18000700D
0x180006ffd  mov     r8, rdi
0x180007000  mov     rdx, rsi
0x180007003  xor     ecx, ecx
0x180007005  mov     rax, rbx
0x180007008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700d  mov     rbx, [rsp+28h+arg_0]
0x180007012  mov     rsi, [rsp+28h+arg_8]
0x180007017  add     rsp, 20h
0x18000701b  pop     rdi
0x18000701c  retn
```
