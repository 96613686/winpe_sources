# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180008c40`
- end: `0x180008d6d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `301`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003520`
- `0x180008c40`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ce2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ce2`

## string_xrefs

- `0x180008cdb`: `kernelbase.dll`

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
0x180008c40  mov     [rsp-8+arg_8], rbx
0x180008c45  mov     [rsp-8+arg_10], rdi
0x180008c4a  push    rbp
0x180008c4b  mov     rbp, rsp
0x180008c4e  sub     rsp, 60h
0x180008c52  mov     rax, cs:__security_cookie
0x180008c59  xor     rax, rsp
0x180008c5c  mov     [rbp+var_8], rax
0x180008c60  mov     rbx, rcx
0x180008c63  mov     [rbp+var_3C], 0
0x180008c6a  mov     [rbp+var_2F], 0
0x180008c6e  mov     [rbp+var_2C], 0
0x180008c75  xor     eax, eax
0x180008c77  mov     [rbp+var_26], ax
0x180008c7b  mov     eax, [rcx+8]
0x180008c7e  mov     [rbp+var_40], eax
0x180008c81  mov     rax, [rcx+18h]
0x180008c85  mov     [rbp+var_38], rax
0x180008c89  mov     al, [rcx]
0x180008c8b  mov     [rbp+var_30], al
0x180008c8e  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180008c95  mov     [rbp+var_2E], ax
0x180008c99  movzx   eax, word ptr [rcx+40h]
0x180008c9d  mov     [rbp+var_28], ax
0x180008ca1  mov     [rbp+var_24], 0
0x180008ca8  mov     rax, [rcx+38h]
0x180008cac  mov     [rbp+var_20], rax
0x180008cb0  mov     rax, [rcx+80h]
0x180008cb7  mov     [rbp+var_18], rax
0x180008cbb  mov     [rbp+var_10], 0
0x180008cc3  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180008cca  test    rdi, rdi
0x180008ccd  jnz     short loc_180008D13
0x180008ccf  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008cd6  test    rax, rax
0x180008cd9  jnz     short loc_180008CF4
0x180008cdb  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180008ce2  call    cs:__imp_GetModuleHandleW
0x180008ce8  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008cef  test    rax, rax
0x180008cf2  jz      short loc_180008D07
0x180008cf4  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180008cfb  mov     rcx, rax; hModule
0x180008cfe  call    cs:__imp_GetProcAddress
0x180008d04  mov     rdi, rax
0x180008d07  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180008d0e  test    rdi, rdi
0x180008d11  jz      short loc_180008D26
0x180008d13  lea     r8, [rbp+var_10]
0x180008d17  lea     rdx, [rbp+var_40]
0x180008d1b  xor     ecx, ecx
0x180008d1d  mov     rax, rdi
0x180008d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d25  nop
0x180008d26  mov     eax, dword ptr [rbp+var_10]
0x180008d29  mov     [rbx+10h], eax
0x180008d2c  movzx   ecx, byte ptr [rbp+var_10+4]
0x180008d30  sub     ecx, 1
0x180008d33  jz      short loc_180008D4B
0x180008d35  sub     ecx, 1
0x180008d38  jz      short loc_180008D45
0x180008d3a  cmp     ecx, 1
0x180008d3d  jnz     short loc_180008D4F
0x180008d3f  or      dword ptr [rbx+4], 4
0x180008d43  jmp     short loc_180008D4F
0x180008d45  or      dword ptr [rbx+4], 2
0x180008d49  jmp     short loc_180008D4F
0x180008d4b  or      dword ptr [rbx+4], 1
0x180008d4f  mov     rcx, [rbp+var_8]
0x180008d53  xor     rcx, rsp; StackCookie
0x180008d56  call    __security_check_cookie
0x180008d5b  lea     r11, [rsp+60h+var_s0]
0x180008d60  mov     rbx, [r11+18h]
0x180008d64  mov     rdi, [r11+20h]
0x180008d68  mov     rsp, r11
0x180008d6b  pop     rbp
0x180008d6c  retn
```
