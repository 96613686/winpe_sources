# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006d90`
- end: `0x180006ebd`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006d90`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e32`

## string_xrefs

- `0x180006e2b`: `kernelbase.dll`

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
0x180006d90  mov     [rsp-8+arg_8], rbx
0x180006d95  mov     [rsp-8+arg_10], rdi
0x180006d9a  push    rbp
0x180006d9b  mov     rbp, rsp
0x180006d9e  sub     rsp, 60h
0x180006da2  mov     rax, cs:__security_cookie
0x180006da9  xor     rax, rsp
0x180006dac  mov     [rbp+var_8], rax
0x180006db0  mov     rbx, rcx
0x180006db3  mov     [rbp+var_3C], 0
0x180006dba  mov     [rbp+var_2F], 0
0x180006dbe  mov     [rbp+var_2C], 0
0x180006dc5  xor     eax, eax
0x180006dc7  mov     [rbp+var_26], ax
0x180006dcb  mov     eax, [rcx+8]
0x180006dce  mov     [rbp+var_40], eax
0x180006dd1  mov     rax, [rcx+18h]
0x180006dd5  mov     [rbp+var_38], rax
0x180006dd9  mov     al, [rcx]
0x180006ddb  mov     [rbp+var_30], al
0x180006dde  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006de5  mov     [rbp+var_2E], ax
0x180006de9  movzx   eax, word ptr [rcx+40h]
0x180006ded  mov     [rbp+var_28], ax
0x180006df1  mov     [rbp+var_24], 0
0x180006df8  mov     rax, [rcx+38h]
0x180006dfc  mov     [rbp+var_20], rax
0x180006e00  mov     rax, [rcx+80h]
0x180006e07  mov     [rbp+var_18], rax
0x180006e0b  mov     [rbp+var_10], 0
0x180006e13  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006e1a  test    rdi, rdi
0x180006e1d  jnz     short loc_180006E63
0x180006e1f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006e26  test    rax, rax
0x180006e29  jnz     short loc_180006E44
0x180006e2b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006e32  call    cs:__imp_GetModuleHandleW
0x180006e38  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006e3f  test    rax, rax
0x180006e42  jz      short loc_180006E57
0x180006e44  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006e4b  mov     rcx, rax; hModule
0x180006e4e  call    cs:__imp_GetProcAddress
0x180006e54  mov     rdi, rax
0x180006e57  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006e5e  test    rdi, rdi
0x180006e61  jz      short loc_180006E76
0x180006e63  lea     r8, [rbp+var_10]
0x180006e67  lea     rdx, [rbp+var_40]
0x180006e6b  xor     ecx, ecx
0x180006e6d  mov     rax, rdi
0x180006e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e75  nop
0x180006e76  mov     eax, dword ptr [rbp+var_10]
0x180006e79  mov     [rbx+10h], eax
0x180006e7c  movzx   ecx, byte ptr [rbp+var_10+4]
0x180006e80  sub     ecx, 1
0x180006e83  jz      short loc_180006E9B
0x180006e85  sub     ecx, 1
0x180006e88  jz      short loc_180006E95
0x180006e8a  cmp     ecx, 1
0x180006e8d  jnz     short loc_180006E9F
0x180006e8f  or      dword ptr [rbx+4], 4
0x180006e93  jmp     short loc_180006E9F
0x180006e95  or      dword ptr [rbx+4], 2
0x180006e99  jmp     short loc_180006E9F
0x180006e9b  or      dword ptr [rbx+4], 1
0x180006e9f  mov     rcx, [rbp+var_8]
0x180006ea3  xor     rcx, rsp; StackCookie
0x180006ea6  call    __security_check_cookie
0x180006eab  lea     r11, [rsp+60h+var_s0]
0x180006eb0  mov     rbx, [r11+18h]
0x180006eb4  mov     rdi, [r11+20h]
0x180006eb8  mov     rsp, r11
0x180006ebb  pop     rbp
0x180006ebc  retn
```
