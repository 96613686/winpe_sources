# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008c60`
- end: `0x180008d71`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008c60`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d10`

## string_xrefs

- `0x180008ced`: `kernelbase.dll`

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
0x180008c60  mov     [rsp-8+arg_8], rbx
0x180008c65  mov     [rsp-8+arg_10], rdi
0x180008c6a  push    rbp
0x180008c6b  mov     rbp, rsp
0x180008c6e  sub     rsp, 50h
0x180008c72  mov     rbx, rcx
0x180008c75  mov     [rbp+var_2C], 0
0x180008c7c  mov     [rbp+var_1F], 0
0x180008c80  mov     [rbp+var_1C], 0
0x180008c87  xor     eax, eax
0x180008c89  mov     [rbp+var_16], ax
0x180008c8d  mov     eax, [rcx+8]
0x180008c90  mov     [rbp+var_30], eax
0x180008c93  mov     rax, [rcx+18h]
0x180008c97  mov     [rbp+var_28], rax
0x180008c9b  mov     al, [rcx]
0x180008c9d  mov     [rbp+var_20], al
0x180008ca0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180008ca7  mov     [rbp+var_1E], ax
0x180008cab  movzx   eax, word ptr [rcx+40h]
0x180008caf  mov     [rbp+var_18], ax
0x180008cb3  mov     [rbp+var_14], 0
0x180008cba  mov     rax, [rcx+38h]
0x180008cbe  mov     [rbp+var_10], rax
0x180008cc2  mov     rax, [rcx+80h]
0x180008cc9  mov     [rbp+var_8], rax
0x180008ccd  mov     [rbp+arg_0], 0
0x180008cd5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180008cdc  test    rdi, rdi
0x180008cdf  jnz     short loc_180008D25
0x180008ce1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008ce8  test    rax, rax
0x180008ceb  jnz     short loc_180008D06
0x180008ced  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008cf4  call    cs:__imp_GetModuleHandleW
0x180008cfa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008d01  test    rax, rax
0x180008d04  jz      short loc_180008D19
0x180008d06  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180008d0d  mov     rcx, rax; hModule
0x180008d10  call    cs:__imp_GetProcAddress
0x180008d16  mov     rdi, rax
0x180008d19  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180008d20  test    rdi, rdi
0x180008d23  jz      short loc_180008D38
0x180008d25  lea     r8, [rbp+arg_0]
0x180008d29  lea     rdx, [rbp+var_30]
0x180008d2d  xor     ecx, ecx
0x180008d2f  mov     rax, rdi
0x180008d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d37  nop
0x180008d38  mov     eax, dword ptr [rbp+arg_0]
0x180008d3b  mov     [rbx+10h], eax
0x180008d3e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180008d42  sub     ecx, 1
0x180008d45  jz      short loc_180008D5D
0x180008d47  sub     ecx, 1
0x180008d4a  jz      short loc_180008D57
0x180008d4c  cmp     ecx, 1
0x180008d4f  jnz     short loc_180008D61
0x180008d51  or      dword ptr [rbx+4], 4
0x180008d55  jmp     short loc_180008D61
0x180008d57  or      dword ptr [rbx+4], 2
0x180008d5b  jmp     short loc_180008D61
0x180008d5d  or      dword ptr [rbx+4], 1
0x180008d61  mov     rbx, [rsp+50h+arg_8]
0x180008d66  mov     rdi, [rsp+50h+arg_10]
0x180008d6b  add     rsp, 50h
0x180008d6f  pop     rbp
0x180008d70  retn
```
