# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x18000c438`
- end: `0x18000c4be`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a770`

## callees

- `0x18000c438`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c46c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c46c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c488`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c488`

## string_xrefs

- `0x18000c465`: `kernelbase.dll`

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
0x18000c438  mov     [rsp+arg_0], rbx
0x18000c43d  mov     [rsp+arg_8], rsi
0x18000c442  push    rdi
0x18000c443  sub     rsp, 20h
0x18000c447  mov     rdi, r8
0x18000c44a  mov     rsi, rdx
0x18000c44d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000c454  test    rbx, rbx
0x18000c457  jnz     short loc_18000C49D
0x18000c459  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c460  test    rax, rax
0x18000c463  jnz     short loc_18000C47E
0x18000c465  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c46c  call    cs:__imp_GetModuleHandleW
0x18000c472  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000c479  test    rax, rax
0x18000c47c  jz      short loc_18000C491
0x18000c47e  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000c485  mov     rcx, rax; hModule
0x18000c488  call    cs:__imp_GetProcAddress
0x18000c48e  mov     rbx, rax
0x18000c491  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x18000c498  test    rbx, rbx
0x18000c49b  jz      short loc_18000C4AE
0x18000c49d  mov     r8, rdi
0x18000c4a0  mov     rdx, rsi
0x18000c4a3  xor     ecx, ecx
0x18000c4a5  mov     rax, rbx
0x18000c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ad  nop
0x18000c4ae  mov     rbx, [rsp+28h+arg_0]
0x18000c4b3  mov     rsi, [rsp+28h+arg_8]
0x18000c4b8  add     rsp, 20h
0x18000c4bc  pop     rdi
0x18000c4bd  retn
```
