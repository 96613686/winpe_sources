# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800053c8`
- end: `0x18000544e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004580`

## callees

- `0x1800053c8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800053fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005418`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005418`

## string_xrefs

- `0x1800053f5`: `kernelbase.dll`

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
0x1800053c8  mov     [rsp+arg_0], rbx
0x1800053cd  mov     [rsp+arg_8], rsi
0x1800053d2  push    rdi
0x1800053d3  sub     rsp, 20h
0x1800053d7  mov     rdi, r8
0x1800053da  mov     rsi, rdx
0x1800053dd  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800053e4  test    rbx, rbx
0x1800053e7  jnz     short loc_18000542D
0x1800053e9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800053f0  test    rax, rax
0x1800053f3  jnz     short loc_18000540E
0x1800053f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800053fc  call    cs:__imp_GetModuleHandleW
0x180005402  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005409  test    rax, rax
0x18000540c  jz      short loc_180005421
0x18000540e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180005415  mov     rcx, rax; hModule
0x180005418  call    cs:__imp_GetProcAddress
0x18000541e  mov     rbx, rax
0x180005421  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180005428  test    rbx, rbx
0x18000542b  jz      short loc_18000543E
0x18000542d  mov     r8, rdi
0x180005430  mov     rdx, rsi
0x180005433  xor     ecx, ecx
0x180005435  mov     rax, rbx
0x180005438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543d  nop
0x18000543e  mov     rbx, [rsp+28h+arg_0]
0x180005443  mov     rsi, [rsp+28h+arg_8]
0x180005448  add     rsp, 20h
0x18000544c  pop     rdi
0x18000544d  retn
```
