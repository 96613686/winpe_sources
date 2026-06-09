# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x140007608`
- end: `0x14000768e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006910`

## callees

- `0x140007608`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000763c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000763c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007658`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007658`

## string_xrefs

- `0x140007635`: `kernelbase.dll`

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
0x140007608  mov     [rsp+arg_0], rbx
0x14000760d  mov     [rsp+arg_8], rsi
0x140007612  push    rdi
0x140007613  sub     rsp, 20h
0x140007617  mov     rdi, r8
0x14000761a  mov     rsi, rdx
0x14000761d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140007624  test    rbx, rbx
0x140007627  jnz     short loc_14000766D
0x140007629  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007630  test    rax, rax
0x140007633  jnz     short loc_14000764E
0x140007635  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000763c  call    cs:__imp_GetModuleHandleW
0x140007642  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007649  test    rax, rax
0x14000764c  jz      short loc_140007661
0x14000764e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140007655  mov     rcx, rax; hModule
0x140007658  call    cs:__imp_GetProcAddress
0x14000765e  mov     rbx, rax
0x140007661  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x140007668  test    rbx, rbx
0x14000766b  jz      short loc_14000767E
0x14000766d  mov     r8, rdi
0x140007670  mov     rdx, rsi
0x140007673  xor     ecx, ecx
0x140007675  mov     rax, rbx
0x140007678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000767d  nop
0x14000767e  mov     rbx, [rsp+28h+arg_0]
0x140007683  mov     rsi, [rsp+28h+arg_8]
0x140007688  add     rsp, 20h
0x14000768c  pop     rdi
0x14000768d  retn
```
