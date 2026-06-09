# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18002b780`
- end: `0x18002b891`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002b780`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b830`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b814`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b814`

## string_xrefs

- `0x18002b80d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h]
  char v7; // [rsp+30h] [rbp-20h]
  char v8; // [rsp+31h] [rbp-1Fh]
  __int16 v9; // [rsp+32h] [rbp-1Eh]
  int v10; // [rsp+34h] [rbp-1Ch]
  __int16 v11; // [rsp+38h] [rbp-18h]
  __int16 v12; // [rsp+3Ah] [rbp-16h]
  int v13; // [rsp+3Ch] [rbp-14h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 v15; // [rsp+48h] [rbp-8h]
  __int64 v16; // [rsp+60h] [rbp+10h] BYREF

  v5[1] = 0;
  v8 = 0;
  v10 = 0;
  v12 = 0;
  v5[0] = *((_DWORD *)this + 2);
  v6 = *((_QWORD *)this + 3);
  v7 = *(_BYTE *)this;
  v9 = wil::g_moduleFailureReportFlags;
  v11 = *((_WORD *)this + 32);
  v13 = 0;
  v14 = *((_QWORD *)this + 7);
  v15 = *((_QWORD *)this + 16);
  v16 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v5, &v16);
  *((_DWORD *)this + 4) = v16;
  switch ( BYTE4(v16) )
  {
    case 1u:
      *((_DWORD *)this + 1) |= 1u;
      break;
    case 2u:
      *((_DWORD *)this + 1) |= 2u;
      break;
    case 3u:
      *((_DWORD *)this + 1) |= 4u;
      break;
  }
}

```

## disassembly

```asm
0x18002b780  mov     [rsp-8+arg_8], rbx
0x18002b785  mov     [rsp-8+arg_10], rdi
0x18002b78a  push    rbp
0x18002b78b  mov     rbp, rsp
0x18002b78e  sub     rsp, 50h
0x18002b792  mov     rbx, rcx
0x18002b795  mov     [rbp+var_2C], 0
0x18002b79c  mov     [rbp+var_1F], 0
0x18002b7a0  mov     [rbp+var_1C], 0
0x18002b7a7  xor     eax, eax
0x18002b7a9  mov     [rbp+var_16], ax
0x18002b7ad  mov     eax, [rcx+8]
0x18002b7b0  mov     [rbp+var_30], eax
0x18002b7b3  mov     rax, [rcx+18h]
0x18002b7b7  mov     [rbp+var_28], rax
0x18002b7bb  mov     al, [rcx]
0x18002b7bd  mov     [rbp+var_20], al
0x18002b7c0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18002b7c7  mov     [rbp+var_1E], ax
0x18002b7cb  movzx   eax, word ptr [rcx+40h]
0x18002b7cf  mov     [rbp+var_18], ax
0x18002b7d3  mov     [rbp+var_14], 0
0x18002b7da  mov     rax, [rcx+38h]
0x18002b7de  mov     [rbp+var_10], rax
0x18002b7e2  mov     rax, [rcx+80h]
0x18002b7e9  mov     [rbp+var_8], rax
0x18002b7ed  mov     [rbp+arg_0], 0
0x18002b7f5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18002b7fc  test    rdi, rdi
0x18002b7ff  jnz     short loc_18002B845
0x18002b801  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002b808  test    rax, rax
0x18002b80b  jnz     short loc_18002B826
0x18002b80d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002b814  call    cs:__imp_GetModuleHandleW
0x18002b81a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18002b821  test    rax, rax
0x18002b824  jz      short loc_18002B839
0x18002b826  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18002b82d  mov     rcx, rax; hModule
0x18002b830  call    cs:__imp_GetProcAddress
0x18002b836  mov     rdi, rax
0x18002b839  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18002b840  test    rdi, rdi
0x18002b843  jz      short loc_18002B858
0x18002b845  lea     r8, [rbp+arg_0]
0x18002b849  lea     rdx, [rbp+var_30]
0x18002b84d  xor     ecx, ecx
0x18002b84f  mov     rax, rdi
0x18002b852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b857  nop
0x18002b858  mov     eax, dword ptr [rbp+arg_0]
0x18002b85b  mov     [rbx+10h], eax
0x18002b85e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18002b862  sub     ecx, 1
0x18002b865  jz      short loc_18002B87D
0x18002b867  sub     ecx, 1
0x18002b86a  jz      short loc_18002B877
0x18002b86c  cmp     ecx, 1
0x18002b86f  jnz     short loc_18002B881
0x18002b871  or      dword ptr [rbx+4], 4
0x18002b875  jmp     short loc_18002B881
0x18002b877  or      dword ptr [rbx+4], 2
0x18002b87b  jmp     short loc_18002B881
0x18002b87d  or      dword ptr [rbx+4], 1
0x18002b881  mov     rbx, [rsp+50h+arg_8]
0x18002b886  mov     rdi, [rsp+50h+arg_10]
0x18002b88b  add     rsp, 50h
0x18002b88f  pop     rbp
0x18002b890  retn
```
