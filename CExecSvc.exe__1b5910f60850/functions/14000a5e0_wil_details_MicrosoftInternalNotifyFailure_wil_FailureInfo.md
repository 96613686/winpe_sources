# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x14000a5e0`
- end: `0x14000a70d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002310`
- `0x14000a5e0`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a69e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a69e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a682`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a682`

## string_xrefs

- `0x14000a67b`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  char v7; // [rsp+30h] [rbp-30h]
  char v8; // [rsp+31h] [rbp-2Fh]
  __int16 v9; // [rsp+32h] [rbp-2Eh]
  int v10; // [rsp+34h] [rbp-2Ch]
  __int16 v11; // [rsp+38h] [rbp-28h]
  __int16 v12; // [rsp+3Ah] [rbp-26h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF

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
0x14000a5e0  mov     [rsp-8+arg_8], rbx
0x14000a5e5  mov     [rsp-8+arg_10], rdi
0x14000a5ea  push    rbp
0x14000a5eb  mov     rbp, rsp
0x14000a5ee  sub     rsp, 60h
0x14000a5f2  mov     rax, cs:__security_cookie
0x14000a5f9  xor     rax, rsp
0x14000a5fc  mov     [rbp+var_8], rax
0x14000a600  mov     rbx, rcx
0x14000a603  mov     [rbp+var_3C], 0
0x14000a60a  mov     [rbp+var_2F], 0
0x14000a60e  mov     [rbp+var_2C], 0
0x14000a615  xor     eax, eax
0x14000a617  mov     [rbp+var_26], ax
0x14000a61b  mov     eax, [rcx+8]
0x14000a61e  mov     [rbp+var_40], eax
0x14000a621  mov     rax, [rcx+18h]
0x14000a625  mov     [rbp+var_38], rax
0x14000a629  mov     al, [rcx]
0x14000a62b  mov     [rbp+var_30], al
0x14000a62e  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000a635  mov     [rbp+var_2E], ax
0x14000a639  movzx   eax, word ptr [rcx+40h]
0x14000a63d  mov     [rbp+var_28], ax
0x14000a641  mov     [rbp+var_24], 0
0x14000a648  mov     rax, [rcx+38h]
0x14000a64c  mov     [rbp+var_20], rax
0x14000a650  mov     rax, [rcx+80h]
0x14000a657  mov     [rbp+var_18], rax
0x14000a65b  mov     [rbp+var_10], 0
0x14000a663  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000a66a  test    rdi, rdi
0x14000a66d  jnz     short loc_14000A6B3
0x14000a66f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000a676  test    rax, rax
0x14000a679  jnz     short loc_14000A694
0x14000a67b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000a682  call    cs:__imp_GetModuleHandleW
0x14000a688  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000a68f  test    rax, rax
0x14000a692  jz      short loc_14000A6A7
0x14000a694  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000a69b  mov     rcx, rax; hModule
0x14000a69e  call    cs:__imp_GetProcAddress
0x14000a6a4  mov     rdi, rax
0x14000a6a7  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000a6ae  test    rdi, rdi
0x14000a6b1  jz      short loc_14000A6C6
0x14000a6b3  lea     r8, [rbp+var_10]
0x14000a6b7  lea     rdx, [rbp+var_40]
0x14000a6bb  xor     ecx, ecx
0x14000a6bd  mov     rax, rdi
0x14000a6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6c5  nop
0x14000a6c6  mov     eax, dword ptr [rbp+var_10]
0x14000a6c9  mov     [rbx+10h], eax
0x14000a6cc  movzx   ecx, byte ptr [rbp+var_10+4]
0x14000a6d0  sub     ecx, 1
0x14000a6d3  jz      short loc_14000A6EB
0x14000a6d5  sub     ecx, 1
0x14000a6d8  jz      short loc_14000A6E5
0x14000a6da  cmp     ecx, 1
0x14000a6dd  jnz     short loc_14000A6EF
0x14000a6df  or      dword ptr [rbx+4], 4
0x14000a6e3  jmp     short loc_14000A6EF
0x14000a6e5  or      dword ptr [rbx+4], 2
0x14000a6e9  jmp     short loc_14000A6EF
0x14000a6eb  or      dword ptr [rbx+4], 1
0x14000a6ef  mov     rcx, [rbp+var_8]
0x14000a6f3  xor     rcx, rsp; StackCookie
0x14000a6f6  call    __security_check_cookie
0x14000a6fb  lea     r11, [rsp+60h+var_s0]
0x14000a700  mov     rbx, [r11+18h]
0x14000a704  mov     rdi, [r11+20h]
0x14000a708  mov     rsp, r11
0x14000a70b  pop     rbp
0x14000a70c  retn
```
