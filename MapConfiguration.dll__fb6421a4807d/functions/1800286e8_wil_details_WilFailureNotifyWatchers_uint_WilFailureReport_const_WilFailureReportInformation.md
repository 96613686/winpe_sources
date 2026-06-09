# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800286e8`
- end: `0x18002876e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027bb0`

## callees

- `0x1800286e8`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028738`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002871c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002871c`

## string_xrefs

- `0x180028715`: `kernelbase.dll`

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
0x1800286e8  mov     [rsp+arg_0], rbx
0x1800286ed  mov     [rsp+arg_8], rsi
0x1800286f2  push    rdi
0x1800286f3  sub     rsp, 20h
0x1800286f7  mov     rdi, r8
0x1800286fa  mov     rsi, rdx
0x1800286fd  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180028704  test    rbx, rbx
0x180028707  jnz     short loc_18002874D
0x180028709  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180028710  test    rax, rax
0x180028713  jnz     short loc_18002872E
0x180028715  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002871c  call    cs:__imp_GetModuleHandleW
0x180028722  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180028729  test    rax, rax
0x18002872c  jz      short loc_180028741
0x18002872e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180028735  mov     rcx, rax; hModule
0x180028738  call    cs:__imp_GetProcAddress
0x18002873e  mov     rbx, rax
0x180028741  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180028748  test    rbx, rbx
0x18002874b  jz      short loc_18002875E
0x18002874d  mov     r8, rdi
0x180028750  mov     rdx, rsi
0x180028753  xor     ecx, ecx
0x180028755  mov     rax, rbx
0x180028758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002875d  nop
0x18002875e  mov     rbx, [rsp+28h+arg_0]
0x180028763  mov     rsi, [rsp+28h+arg_8]
0x180028768  add     rsp, 20h
0x18002876c  pop     rdi
0x18002876d  retn
```
