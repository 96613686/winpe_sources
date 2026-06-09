# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x18000e568`
- end: `0x18000e5ee`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e140`

## callees

- `0x18000e568`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e59c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e59c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e5b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e5b8`

## string_xrefs

- `0x18000e595`: `kernelbase.dll`

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
0x18000e568  mov     [rsp+arg_0], rbx
0x18000e56d  mov     [rsp+arg_8], rsi
0x18000e572  push    rdi
0x18000e573  sub     rsp, 20h
0x18000e577  mov     rdi, r8
0x18000e57a  mov     rsi, rdx
0x18000e57d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000e584  test    rbx, rbx
0x18000e587  jnz     short loc_18000E5CD
0x18000e589  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e590  test    rax, rax
0x18000e593  jnz     short loc_18000E5AE
0x18000e595  lea     rcx, ModuleName; "kernelbase.dll"
0x18000e59c  call    cs:__imp_GetModuleHandleW
0x18000e5a2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e5a9  test    rax, rax
0x18000e5ac  jz      short loc_18000E5C1
0x18000e5ae  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000e5b5  mov     rcx, rax; hModule
0x18000e5b8  call    cs:__imp_GetProcAddress
0x18000e5be  mov     rbx, rax
0x18000e5c1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x18000e5c8  test    rbx, rbx
0x18000e5cb  jz      short loc_18000E5DE
0x18000e5cd  mov     r8, rdi
0x18000e5d0  mov     rdx, rsi
0x18000e5d3  xor     ecx, ecx
0x18000e5d5  mov     rax, rbx
0x18000e5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5dd  nop
0x18000e5de  mov     rbx, [rsp+28h+arg_0]
0x18000e5e3  mov     rsi, [rsp+28h+arg_8]
0x18000e5e8  add     rsp, 20h
0x18000e5ec  pop     rdi
0x18000e5ed  retn
```
