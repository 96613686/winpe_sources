# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006ea0`
- end: `0x180006fbc`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `284`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006ea0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006f3d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180006f3d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006f59`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180006f59`

## string_xrefs

- `0x180006f36`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  char v7; // [rsp+38h] [rbp-28h]
  char v8; // [rsp+39h] [rbp-27h]
  __int16 v9; // [rsp+3Ah] [rbp-26h]
  int v10; // [rsp+3Ch] [rbp-24h]
  __int16 v11; // [rsp+40h] [rbp-20h]
  __int16 v12; // [rsp+42h] [rbp-1Eh]
  int v13; // [rsp+44h] [rbp-1Ch]
  __int64 v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+70h] [rbp+10h] BYREF

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
0x180006ea0  mov     rax, rsp
0x180006ea3  push    rbp
0x180006ea4  mov     rbp, rsp
0x180006ea7  sub     rsp, 60h
0x180006eab  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180006eb3  mov     [rax+10h], rbx
0x180006eb7  mov     [rax+18h], rdi
0x180006ebb  mov     rbx, rcx
0x180006ebe  mov     [rbp+var_34], 0
0x180006ec5  mov     [rbp+var_27], 0
0x180006ec9  mov     [rbp+var_24], 0
0x180006ed0  xor     eax, eax
0x180006ed2  mov     [rbp+var_1E], ax
0x180006ed6  mov     eax, [rcx+8]
0x180006ed9  mov     [rbp+var_38], eax
0x180006edc  mov     rax, [rcx+18h]
0x180006ee0  mov     [rbp+var_30], rax
0x180006ee4  mov     al, [rcx]
0x180006ee6  mov     [rbp+var_28], al
0x180006ee9  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006ef0  mov     [rbp+var_26], ax
0x180006ef4  movzx   eax, word ptr [rcx+40h]
0x180006ef8  mov     [rbp+var_20], ax
0x180006efc  mov     [rbp+var_1C], 0
0x180006f03  mov     rax, [rcx+38h]
0x180006f07  mov     [rbp+var_18], rax
0x180006f0b  mov     rax, [rcx+80h]
0x180006f12  mov     [rbp+var_10], rax
0x180006f16  mov     [rbp+arg_0], 0
0x180006f1e  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180006f25  test    rdi, rdi
0x180006f28  jnz     short loc_180006F6E
0x180006f2a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f31  test    rax, rax
0x180006f34  jnz     short loc_180006F4F
0x180006f36  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180006f3d  call    cs:__imp_GetModuleHandleW
0x180006f43  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180006f4a  test    rax, rax
0x180006f4d  jz      short loc_180006F62
0x180006f4f  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180006f56  mov     rcx, rax; hModule
0x180006f59  call    cs:__imp_GetProcAddress
0x180006f5f  mov     rdi, rax
0x180006f62  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180006f69  test    rdi, rdi
0x180006f6c  jz      short loc_180006F81
0x180006f6e  lea     r8, [rbp+arg_0]
0x180006f72  lea     rdx, [rbp+var_38]
0x180006f76  xor     ecx, ecx
0x180006f78  mov     rax, rdi
0x180006f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f80  nop
0x180006f81  mov     eax, dword ptr [rbp+arg_0]
0x180006f84  mov     [rbx+10h], eax
0x180006f87  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006f8b  sub     ecx, 1
0x180006f8e  jz      short loc_180006FA6
0x180006f90  sub     ecx, 1
0x180006f93  jz      short loc_180006FA0
0x180006f95  cmp     ecx, 1
0x180006f98  jnz     short loc_180006FAA
0x180006f9a  or      dword ptr [rbx+4], 4
0x180006f9e  jmp     short loc_180006FAA
0x180006fa0  or      dword ptr [rbx+4], 2
0x180006fa4  jmp     short loc_180006FAA
0x180006fa6  or      dword ptr [rbx+4], 1
0x180006faa  lea     r11, [rsp+60h+var_s0]
0x180006faf  mov     rbx, [r11+18h]
0x180006fb3  mov     rdi, [r11+20h]
0x180006fb7  mov     rsp, r11
0x180006fba  pop     rbp
0x180006fbb  retn
```
