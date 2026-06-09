# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x180044fd8`
- end: `0x18004505e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044230`

## callees

- `0x180044fd8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045028`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045028`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004500c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004500c`

## string_xrefs

- `0x180045005`: `kernelbase.dll`

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
0x180044fd8  mov     [rsp+arg_0], rbx
0x180044fdd  mov     [rsp+arg_8], rsi
0x180044fe2  push    rdi
0x180044fe3  sub     rsp, 20h
0x180044fe7  mov     rdi, r8
0x180044fea  mov     rsi, rdx
0x180044fed  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180044ff4  test    rbx, rbx
0x180044ff7  jnz     short loc_18004503D
0x180044ff9  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180045000  test    rax, rax
0x180045003  jnz     short loc_18004501E
0x180045005  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18004500c  call    cs:__imp_GetModuleHandleW
0x180045012  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180045019  test    rax, rax
0x18004501c  jz      short loc_180045031
0x18004501e  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180045025  mov     rcx, rax; hModule
0x180045028  call    cs:__imp_GetProcAddress
0x18004502e  mov     rbx, rax
0x180045031  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x180045038  test    rbx, rbx
0x18004503b  jz      short loc_18004504E
0x18004503d  mov     r8, rdi
0x180045040  mov     rdx, rsi
0x180045043  xor     ecx, ecx
0x180045045  mov     rax, rbx
0x180045048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004504d  nop
0x18004504e  mov     rbx, [rsp+28h+arg_0]
0x180045053  mov     rsi, [rsp+28h+arg_8]
0x180045058  add     rsp, 20h
0x18004505c  pop     rdi
0x18004505d  retn
```
