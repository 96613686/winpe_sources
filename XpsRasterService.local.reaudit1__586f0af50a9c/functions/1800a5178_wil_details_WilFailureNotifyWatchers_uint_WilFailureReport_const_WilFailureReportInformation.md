# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1800a5178`
- end: `0x1800a51fe`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a4670`

## callees

- `0x1800a5178`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a51ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a51ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a51c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a51c8`

## string_xrefs

- `0x1800a51a5`: `kernelbase.dll`

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
0x1800a5178  mov     [rsp+arg_0], rbx
0x1800a517d  mov     [rsp+arg_8], rsi
0x1800a5182  push    rdi
0x1800a5183  sub     rsp, 20h
0x1800a5187  mov     rdi, r8
0x1800a518a  mov     rsi, rdx
0x1800a518d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800a5194  test    rbx, rbx
0x1800a5197  jnz     short loc_1800A51DD
0x1800a5199  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800a51a0  test    rax, rax
0x1800a51a3  jnz     short loc_1800A51BE
0x1800a51a5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800a51ac  call    cs:__imp_GetModuleHandleW
0x1800a51b2  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800a51b9  test    rax, rax
0x1800a51bc  jz      short loc_1800A51D1
0x1800a51be  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800a51c5  mov     rcx, rax; hModule
0x1800a51c8  call    cs:__imp_GetProcAddress
0x1800a51ce  mov     rbx, rax
0x1800a51d1  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x1800a51d8  test    rbx, rbx
0x1800a51db  jz      short loc_1800A51EE
0x1800a51dd  mov     r8, rdi
0x1800a51e0  mov     rdx, rsi
0x1800a51e3  xor     ecx, ecx
0x1800a51e5  mov     rax, rbx
0x1800a51e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a51ed  nop
0x1800a51ee  mov     rbx, [rsp+28h+arg_0]
0x1800a51f3  mov     rsi, [rsp+28h+arg_8]
0x1800a51f8  add     rsp, 20h
0x1800a51fc  pop     rdi
0x1800a51fd  retn
```
