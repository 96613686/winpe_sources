# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x18000a248`
- end: `0x18000a2ce`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008050`

## callees

- `0x18000a248`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a298`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a298`

## string_xrefs

- `0x18000a275`: `kernelbase.dll`

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
0x18000a248  mov     [rsp+arg_0], rbx
0x18000a24d  mov     [rsp+arg_8], rsi
0x18000a252  push    rdi
0x18000a253  sub     rsp, 20h
0x18000a257  mov     rdi, r8
0x18000a25a  mov     rsi, rdx
0x18000a25d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000a264  test    rbx, rbx
0x18000a267  jnz     short loc_18000A2AD
0x18000a269  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a270  test    rax, rax
0x18000a273  jnz     short loc_18000A28E
0x18000a275  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000a27c  call    cs:__imp_GetModuleHandleW
0x18000a282  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a289  test    rax, rax
0x18000a28c  jz      short loc_18000A2A1
0x18000a28e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000a295  mov     rcx, rax; hModule
0x18000a298  call    cs:__imp_GetProcAddress
0x18000a29e  mov     rbx, rax
0x18000a2a1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x18000a2a8  test    rbx, rbx
0x18000a2ab  jz      short loc_18000A2BE
0x18000a2ad  mov     r8, rdi
0x18000a2b0  mov     rdx, rsi
0x18000a2b3  xor     ecx, ecx
0x18000a2b5  mov     rax, rbx
0x18000a2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2bd  nop
0x18000a2be  mov     rbx, [rsp+28h+arg_0]
0x18000a2c3  mov     rsi, [rsp+28h+arg_8]
0x18000a2c8  add     rsp, 20h
0x18000a2cc  pop     rdi
0x18000a2cd  retn
```
