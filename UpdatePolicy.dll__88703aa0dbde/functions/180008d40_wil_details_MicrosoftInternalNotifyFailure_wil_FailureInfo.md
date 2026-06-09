# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008d40`
- end: `0x180008e68`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008d40`
- `0x18000ed40`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008df5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008df5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dd9`

## string_xrefs

- `0x180008dd2`: `kernelbase.dll`

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
  ProcAddress = 0;
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
0x180008d40  mov     [rsp-8+arg_8], rbx
0x180008d45  mov     [rsp-8+arg_10], rsi
0x180008d4a  mov     [rsp-8+arg_18], rdi
0x180008d4f  push    rbp
0x180008d50  mov     rbp, rsp
0x180008d53  sub     rsp, 60h
0x180008d57  mov     rax, cs:__security_cookie
0x180008d5e  xor     rax, rsp
0x180008d61  mov     [rbp+var_8], rax
0x180008d65  mov     rbx, rcx
0x180008d68  xor     esi, esi
0x180008d6a  mov     [rbp+var_3C], esi
0x180008d6d  mov     [rbp+var_2F], sil
0x180008d71  mov     [rbp+var_2C], esi
0x180008d74  mov     [rbp+var_26], si
0x180008d78  mov     eax, [rcx+8]
0x180008d7b  mov     [rbp+var_40], eax
0x180008d7e  mov     rax, [rcx+18h]
0x180008d82  mov     [rbp+var_38], rax
0x180008d86  mov     al, [rcx]
0x180008d88  mov     [rbp+var_30], al
0x180008d8b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180008d92  mov     [rbp+var_2E], ax
0x180008d96  movzx   eax, word ptr [rcx+40h]
0x180008d9a  mov     [rbp+var_28], ax
0x180008d9e  mov     [rbp+var_24], esi
0x180008da1  mov     rax, [rcx+38h]
0x180008da5  mov     [rbp+var_20], rax
0x180008da9  mov     rax, [rcx+80h]
0x180008db0  mov     [rbp+var_18], rax
0x180008db4  mov     [rbp+var_10], rsi
0x180008db8  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180008dbf  test    rdi, rdi
0x180008dc2  jnz     short loc_180008E0A
0x180008dc4  mov     edi, esi
0x180008dc6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008dcd  test    rax, rax
0x180008dd0  jnz     short loc_180008DEB
0x180008dd2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008dd9  call    cs:__imp_GetModuleHandleW
0x180008ddf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008de6  test    rax, rax
0x180008de9  jz      short loc_180008DFE
0x180008deb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180008df2  mov     rcx, rax; hModule
0x180008df5  call    cs:__imp_GetProcAddress
0x180008dfb  mov     rdi, rax
0x180008dfe  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180008e05  test    rdi, rdi
0x180008e08  jz      short loc_180008E1D
0x180008e0a  lea     r8, [rbp+var_10]
0x180008e0e  lea     rdx, [rbp+var_40]
0x180008e12  xor     ecx, ecx
0x180008e14  mov     rax, rdi
0x180008e17  call    _guard_dispatch_icall
0x180008e1c  nop
0x180008e1d  mov     eax, dword ptr [rbp+var_10]
0x180008e20  mov     [rbx+10h], eax
0x180008e23  movzx   ecx, byte ptr [rbp+var_10+4]
0x180008e27  sub     ecx, 1
0x180008e2a  jz      short loc_180008E42
0x180008e2c  sub     ecx, 1
0x180008e2f  jz      short loc_180008E3C
0x180008e31  cmp     ecx, 1
0x180008e34  jnz     short loc_180008E46
0x180008e36  or      dword ptr [rbx+4], 4
0x180008e3a  jmp     short loc_180008E46
0x180008e3c  or      dword ptr [rbx+4], 2
0x180008e40  jmp     short loc_180008E46
0x180008e42  or      dword ptr [rbx+4], 1
0x180008e46  mov     rcx, [rbp+var_8]
0x180008e4a  xor     rcx, rsp; StackCookie
0x180008e4d  call    __security_check_cookie
0x180008e52  lea     r11, [rsp+60h+var_s0]
0x180008e57  mov     rbx, [r11+18h]
0x180008e5b  mov     rsi, [r11+20h]
0x180008e5f  mov     rdi, [r11+28h]
0x180008e63  mov     rsp, r11
0x180008e66  pop     rbp
0x180008e67  retn
```
