# wil::details::WilFailureNotifyWatchers(uint,WilFailureReport const *,WilFailureReportInformation *)

- ea: `0x1400056f8`
- end: `0x14000577e`
- name: `?WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *this, __int64, const struct WilFailureReport *, struct WilFailureReportInformation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400048b0`

## callees

- `0x1400056f8`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005748`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005748`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000572c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000572c`

## string_xrefs

- `0x140005725`: `kernelbase.dll`

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
0x1400056f8  mov     [rsp+arg_0], rbx
0x1400056fd  mov     [rsp+arg_8], rsi
0x140005702  push    rdi
0x140005703  sub     rsp, 20h
0x140005707  mov     rdi, r8
0x14000570a  mov     rsi, rdx
0x14000570d  mov     rbx, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140005714  test    rbx, rbx
0x140005717  jnz     short loc_14000575D
0x140005719  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005720  test    rax, rax
0x140005723  jnz     short loc_14000573E
0x140005725  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000572c  call    cs:__imp_GetModuleHandleW
0x140005732  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005739  test    rax, rax
0x14000573c  jz      short loc_140005751
0x14000573e  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x140005745  mov     rcx, rax; hModule
0x140005748  call    cs:__imp_GetProcAddress
0x14000574e  mov     rbx, rax
0x140005751  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rbx
0x140005758  test    rbx, rbx
0x14000575b  jz      short loc_14000576E
0x14000575d  mov     r8, rdi
0x140005760  mov     rdx, rsi
0x140005763  xor     ecx, ecx
0x140005765  mov     rax, rbx
0x140005768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000576d  nop
0x14000576e  mov     rbx, [rsp+28h+arg_0]
0x140005773  mov     rsi, [rsp+28h+arg_8]
0x140005778  add     rsp, 20h
0x14000577c  pop     rdi
0x14000577d  retn
```
