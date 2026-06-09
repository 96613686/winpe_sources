# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140005da0`
- end: `0x140005ecd`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001460`
- `0x140005da0`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140005e42`
- `KERNEL32!GetModuleHandleW` at `0x140005e42`
- `KERNEL32!GetProcAddress` at `0x140005e5e`
- `KERNEL32!GetProcAddress` at `0x140005e5e`

## string_xrefs

- `0x140005e3b`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140005da0  mov     [rsp-8+arg_8], rbx
0x140005da5  mov     [rsp-8+arg_10], rdi
0x140005daa  push    rbp
0x140005dab  mov     rbp, rsp
0x140005dae  sub     rsp, 60h
0x140005db2  mov     rax, cs:__security_cookie
0x140005db9  xor     rax, rsp
0x140005dbc  mov     [rbp+var_8], rax
0x140005dc0  mov     rbx, rcx
0x140005dc3  mov     [rbp+var_3C], 0
0x140005dca  mov     [rbp+var_2F], 0
0x140005dce  mov     [rbp+var_2C], 0
0x140005dd5  xor     eax, eax
0x140005dd7  mov     [rbp+var_26], ax
0x140005ddb  mov     eax, [rcx+8]
0x140005dde  mov     [rbp+var_40], eax
0x140005de1  mov     rax, [rcx+18h]
0x140005de5  mov     [rbp+var_38], rax
0x140005de9  mov     al, [rcx]
0x140005deb  mov     [rbp+var_30], al
0x140005dee  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140005df5  mov     [rbp+var_2E], ax
0x140005df9  movzx   eax, word ptr [rcx+40h]
0x140005dfd  mov     [rbp+var_28], ax
0x140005e01  mov     [rbp+var_24], 0
0x140005e08  mov     rax, [rcx+38h]
0x140005e0c  mov     [rbp+var_20], rax
0x140005e10  mov     rax, [rcx+80h]
0x140005e17  mov     [rbp+var_18], rax
0x140005e1b  mov     [rbp+var_10], 0
0x140005e23  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140005e2a  test    rdi, rdi
0x140005e2d  jnz     short loc_140005E73
0x140005e2f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005e36  test    rax, rax
0x140005e39  jnz     short loc_140005E54
0x140005e3b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005e42  call    cs:__imp_GetModuleHandleW
0x140005e48  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005e4f  test    rax, rax
0x140005e52  jz      short loc_140005E67
0x140005e54  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x140005e5b  mov     rcx, rax; hModule
0x140005e5e  call    cs:__imp_GetProcAddress
0x140005e64  mov     rdi, rax
0x140005e67  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140005e6e  test    rdi, rdi
0x140005e71  jz      short loc_140005E86
0x140005e73  lea     r8, [rbp+var_10]
0x140005e77  lea     rdx, [rbp+var_40]
0x140005e7b  xor     ecx, ecx
0x140005e7d  mov     rax, rdi
0x140005e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e85  nop
0x140005e86  mov     eax, dword ptr [rbp+var_10]
0x140005e89  mov     [rbx+10h], eax
0x140005e8c  movzx   ecx, byte ptr [rbp+var_10+4]
0x140005e90  sub     ecx, 1
0x140005e93  jz      short loc_140005EAB
0x140005e95  sub     ecx, 1
0x140005e98  jz      short loc_140005EA5
0x140005e9a  cmp     ecx, 1
0x140005e9d  jnz     short loc_140005EAF
0x140005e9f  or      dword ptr [rbx+4], 4
0x140005ea3  jmp     short loc_140005EAF
0x140005ea5  or      dword ptr [rbx+4], 2
0x140005ea9  jmp     short loc_140005EAF
0x140005eab  or      dword ptr [rbx+4], 1
0x140005eaf  mov     rcx, [rbp+var_8]
0x140005eb3  xor     rcx, rsp; StackCookie
0x140005eb6  call    __security_check_cookie
0x140005ebb  lea     r11, [rsp+60h+var_s0]
0x140005ec0  mov     rbx, [r11+18h]
0x140005ec4  mov     rdi, [r11+20h]
0x140005ec8  mov     rsp, r11
0x140005ecb  pop     rbp
0x140005ecc  retn
```
