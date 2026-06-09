# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004c80`
- end: `0x180004d91`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004c80`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d14`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d14`

## string_xrefs

- `0x180004d0d`: `kernelbase.dll`

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
0x180004c80  mov     [rsp-8+arg_8], rbx
0x180004c85  mov     [rsp-8+arg_10], rdi
0x180004c8a  push    rbp
0x180004c8b  mov     rbp, rsp
0x180004c8e  sub     rsp, 50h
0x180004c92  mov     rbx, rcx
0x180004c95  mov     [rbp+var_2C], 0
0x180004c9c  mov     [rbp+var_1F], 0
0x180004ca0  mov     [rbp+var_1C], 0
0x180004ca7  xor     eax, eax
0x180004ca9  mov     [rbp+var_16], ax
0x180004cad  mov     eax, [rcx+8]
0x180004cb0  mov     [rbp+var_30], eax
0x180004cb3  mov     rax, [rcx+18h]
0x180004cb7  mov     [rbp+var_28], rax
0x180004cbb  mov     al, [rcx]
0x180004cbd  mov     [rbp+var_20], al
0x180004cc0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004cc7  mov     [rbp+var_1E], ax
0x180004ccb  movzx   eax, word ptr [rcx+40h]
0x180004ccf  mov     [rbp+var_18], ax
0x180004cd3  mov     [rbp+var_14], 0
0x180004cda  mov     rax, [rcx+38h]
0x180004cde  mov     [rbp+var_10], rax
0x180004ce2  mov     rax, [rcx+80h]
0x180004ce9  mov     [rbp+var_8], rax
0x180004ced  mov     [rbp+arg_0], 0
0x180004cf5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004cfc  test    rdi, rdi
0x180004cff  jnz     short loc_180004D45
0x180004d01  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004d08  test    rax, rax
0x180004d0b  jnz     short loc_180004D26
0x180004d0d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004d14  call    cs:__imp_GetModuleHandleW
0x180004d1a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004d21  test    rax, rax
0x180004d24  jz      short loc_180004D39
0x180004d26  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180004d2d  mov     rcx, rax; hModule
0x180004d30  call    cs:__imp_GetProcAddress
0x180004d36  mov     rdi, rax
0x180004d39  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004d40  test    rdi, rdi
0x180004d43  jz      short loc_180004D58
0x180004d45  lea     r8, [rbp+arg_0]
0x180004d49  lea     rdx, [rbp+var_30]
0x180004d4d  xor     ecx, ecx
0x180004d4f  mov     rax, rdi
0x180004d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d57  nop
0x180004d58  mov     eax, dword ptr [rbp+arg_0]
0x180004d5b  mov     [rbx+10h], eax
0x180004d5e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004d62  sub     ecx, 1
0x180004d65  jz      short loc_180004D7D
0x180004d67  sub     ecx, 1
0x180004d6a  jz      short loc_180004D77
0x180004d6c  cmp     ecx, 1
0x180004d6f  jnz     short loc_180004D81
0x180004d71  or      dword ptr [rbx+4], 4
0x180004d75  jmp     short loc_180004D81
0x180004d77  or      dword ptr [rbx+4], 2
0x180004d7b  jmp     short loc_180004D81
0x180004d7d  or      dword ptr [rbx+4], 1
0x180004d81  mov     rbx, [rsp+50h+arg_8]
0x180004d86  mov     rdi, [rsp+50h+arg_10]
0x180004d8b  add     rsp, 50h
0x180004d8f  pop     rbp
0x180004d90  retn
```
