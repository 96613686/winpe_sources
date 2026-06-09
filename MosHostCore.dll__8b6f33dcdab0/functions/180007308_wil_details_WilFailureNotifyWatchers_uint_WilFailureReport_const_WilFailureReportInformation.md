# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180007308`
- end: `0x18000738e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006490`

## callees

- `0x180007308`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000733c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000733c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007358`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007358`

## string_xrefs

- `0x180007335`: `kernelbase.dll`

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
0x180007308  mov     [rsp+arg_0], rbx
0x18000730d  mov     [rsp+arg_8], rsi
0x180007312  push    rdi
0x180007313  sub     rsp, 20h
0x180007317  mov     rdi, r8
0x18000731a  mov     rsi, rdx
0x18000731d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007324  test    rbx, rbx
0x180007327  jnz     short loc_18000736D
0x180007329  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007330  test    rax, rax
0x180007333  jnz     short loc_18000734E
0x180007335  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000733c  call    cs:__imp_GetModuleHandleW
0x180007342  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007349  test    rax, rax
0x18000734c  jz      short loc_180007361
0x18000734e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007355  mov     rcx, rax; hModule
0x180007358  call    cs:__imp_GetProcAddress
0x18000735e  mov     rbx, rax
0x180007361  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180007368  test    rbx, rbx
0x18000736b  jz      short loc_18000737E
0x18000736d  mov     r8, rdi
0x180007370  mov     rdx, rsi
0x180007373  xor     ecx, ecx
0x180007375  mov     rax, rbx
0x180007378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737d  nop
0x18000737e  mov     rbx, [rsp+28h+arg_0]
0x180007383  mov     rsi, [rsp+28h+arg_8]
0x180007388  add     rsp, 20h
0x18000738c  pop     rdi
0x18000738d  retn
```
