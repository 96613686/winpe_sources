# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1400074f8`
- end: `0x14000757e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400064a0`

## callees

- `0x1400074f8`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000752c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000752c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007548`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007548`

## string_xrefs

- `0x140007525`: `kernelbase.dll`

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
0x1400074f8  mov     [rsp+arg_0], rbx
0x1400074fd  mov     [rsp+arg_8], rsi
0x140007502  push    rdi
0x140007503  sub     rsp, 20h
0x140007507  mov     rdi, r8
0x14000750a  mov     rsi, rdx
0x14000750d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140007514  test    rbx, rbx
0x140007517  jnz     short loc_14000755D
0x140007519  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007520  test    rax, rax
0x140007523  jnz     short loc_14000753E
0x140007525  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000752c  call    cs:__imp_GetModuleHandleW
0x140007532  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007539  test    rax, rax
0x14000753c  jz      short loc_140007551
0x14000753e  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140007545  mov     rcx, rax; hModule
0x140007548  call    cs:__imp_GetProcAddress
0x14000754e  mov     rbx, rax
0x140007551  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x140007558  test    rbx, rbx
0x14000755b  jz      short loc_14000756E
0x14000755d  mov     r8, rdi
0x140007560  mov     rdx, rsi
0x140007563  xor     ecx, ecx
0x140007565  mov     rax, rbx
0x140007568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000756d  nop
0x14000756e  mov     rbx, [rsp+28h+arg_0]
0x140007573  mov     rsi, [rsp+28h+arg_8]
0x140007578  add     rsp, 20h
0x14000757c  pop     rdi
0x14000757d  retn
```
