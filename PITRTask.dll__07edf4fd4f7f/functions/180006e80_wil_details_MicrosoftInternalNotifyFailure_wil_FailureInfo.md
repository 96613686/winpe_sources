# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006e80`
- end: `0x180006fad`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e80`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006f3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006f22`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006f22`

## string_xrefs

- `0x180006f1b`: `kernelbase.dll`

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
0x180006e80  mov     [rsp-8+arg_8], rbx
0x180006e85  mov     [rsp-8+arg_10], rdi
0x180006e8a  push    rbp
0x180006e8b  mov     rbp, rsp
0x180006e8e  sub     rsp, 60h
0x180006e92  mov     rax, cs:__security_cookie
0x180006e99  xor     rax, rsp
0x180006e9c  mov     [rbp+var_8], rax
0x180006ea0  mov     rbx, rcx
0x180006ea3  mov     [rbp+var_3C], 0
0x180006eaa  mov     [rbp+var_2F], 0
0x180006eae  mov     [rbp+var_2C], 0
0x180006eb5  xor     eax, eax
0x180006eb7  mov     [rbp+var_26], ax
0x180006ebb  mov     eax, [rcx+8]
0x180006ebe  mov     [rbp+var_40], eax
0x180006ec1  mov     rax, [rcx+18h]
0x180006ec5  mov     [rbp+var_38], rax
0x180006ec9  mov     al, [rcx]
0x180006ecb  mov     [rbp+var_30], al
0x180006ece  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006ed5  mov     [rbp+var_2E], ax
0x180006ed9  movzx   eax, word ptr [rcx+40h]
0x180006edd  mov     [rbp+var_28], ax
0x180006ee1  mov     [rbp+var_24], 0
0x180006ee8  mov     rax, [rcx+38h]
0x180006eec  mov     [rbp+var_20], rax
0x180006ef0  mov     rax, [rcx+80h]
0x180006ef7  mov     [rbp+var_18], rax
0x180006efb  mov     [rbp+var_10], 0
0x180006f03  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006f0a  test    rdi, rdi
0x180006f0d  jnz     short loc_180006F53
0x180006f0f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f16  test    rax, rax
0x180006f19  jnz     short loc_180006F34
0x180006f1b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006f22  call    cs:__imp_GetModuleHandleW
0x180006f28  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f2f  test    rax, rax
0x180006f32  jz      short loc_180006F47
0x180006f34  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006f3b  mov     rcx, rax; hModule
0x180006f3e  call    cs:__imp_GetProcAddress
0x180006f44  mov     rdi, rax
0x180006f47  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006f4e  test    rdi, rdi
0x180006f51  jz      short loc_180006F66
0x180006f53  lea     r8, [rbp+var_10]
0x180006f57  lea     rdx, [rbp+var_40]
0x180006f5b  xor     ecx, ecx
0x180006f5d  mov     rax, rdi
0x180006f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f65  nop
0x180006f66  mov     eax, dword ptr [rbp+var_10]
0x180006f69  mov     [rbx+10h], eax
0x180006f6c  movzx   ecx, byte ptr [rbp+var_10+4]
0x180006f70  sub     ecx, 1
0x180006f73  jz      short loc_180006F8B
0x180006f75  sub     ecx, 1
0x180006f78  jz      short loc_180006F85
0x180006f7a  cmp     ecx, 1
0x180006f7d  jnz     short loc_180006F8F
0x180006f7f  or      dword ptr [rbx+4], 4
0x180006f83  jmp     short loc_180006F8F
0x180006f85  or      dword ptr [rbx+4], 2
0x180006f89  jmp     short loc_180006F8F
0x180006f8b  or      dword ptr [rbx+4], 1
0x180006f8f  mov     rcx, [rbp+var_8]
0x180006f93  xor     rcx, rsp; StackCookie
0x180006f96  call    __security_check_cookie
0x180006f9b  lea     r11, [rsp+60h+var_s0]
0x180006fa0  mov     rbx, [r11+18h]
0x180006fa4  mov     rdi, [r11+20h]
0x180006fa8  mov     rsp, r11
0x180006fab  pop     rbp
0x180006fac  retn
```
