# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140003e10`
- end: `0x140003f21`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003e10`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ea4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003ea4`

## string_xrefs

- `0x140003e9d`: `kernelbase.dll`

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
0x140003e10  mov     [rsp-8+arg_8], rbx
0x140003e15  mov     [rsp-8+arg_10], rdi
0x140003e1a  push    rbp
0x140003e1b  mov     rbp, rsp
0x140003e1e  sub     rsp, 50h
0x140003e22  mov     rbx, rcx
0x140003e25  mov     [rbp+var_2C], 0
0x140003e2c  mov     [rbp+var_1F], 0
0x140003e30  mov     [rbp+var_1C], 0
0x140003e37  xor     eax, eax
0x140003e39  mov     [rbp+var_16], ax
0x140003e3d  mov     eax, [rcx+8]
0x140003e40  mov     [rbp+var_30], eax
0x140003e43  mov     rax, [rcx+18h]
0x140003e47  mov     [rbp+var_28], rax
0x140003e4b  mov     al, [rcx]
0x140003e4d  mov     [rbp+var_20], al
0x140003e50  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140003e57  mov     [rbp+var_1E], ax
0x140003e5b  movzx   eax, word ptr [rcx+40h]
0x140003e5f  mov     [rbp+var_18], ax
0x140003e63  mov     [rbp+var_14], 0
0x140003e6a  mov     rax, [rcx+38h]
0x140003e6e  mov     [rbp+var_10], rax
0x140003e72  mov     rax, [rcx+80h]
0x140003e79  mov     [rbp+var_8], rax
0x140003e7d  mov     [rbp+arg_0], 0
0x140003e85  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140003e8c  test    rdi, rdi
0x140003e8f  jnz     short loc_140003ED5
0x140003e91  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140003e98  test    rax, rax
0x140003e9b  jnz     short loc_140003EB6
0x140003e9d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140003ea4  call    cs:__imp_GetModuleHandleW
0x140003eaa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140003eb1  test    rax, rax
0x140003eb4  jz      short loc_140003EC9
0x140003eb6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140003ebd  mov     rcx, rax; hModule
0x140003ec0  call    cs:__imp_GetProcAddress
0x140003ec6  mov     rdi, rax
0x140003ec9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140003ed0  test    rdi, rdi
0x140003ed3  jz      short loc_140003EE8
0x140003ed5  lea     r8, [rbp+arg_0]
0x140003ed9  lea     rdx, [rbp+var_30]
0x140003edd  xor     ecx, ecx
0x140003edf  mov     rax, rdi
0x140003ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ee7  nop
0x140003ee8  mov     eax, dword ptr [rbp+arg_0]
0x140003eeb  mov     [rbx+10h], eax
0x140003eee  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140003ef2  sub     ecx, 1
0x140003ef5  jz      short loc_140003F0D
0x140003ef7  sub     ecx, 1
0x140003efa  jz      short loc_140003F07
0x140003efc  cmp     ecx, 1
0x140003eff  jnz     short loc_140003F11
0x140003f01  or      dword ptr [rbx+4], 4
0x140003f05  jmp     short loc_140003F11
0x140003f07  or      dword ptr [rbx+4], 2
0x140003f0b  jmp     short loc_140003F11
0x140003f0d  or      dword ptr [rbx+4], 1
0x140003f11  mov     rbx, [rsp+50h+arg_8]
0x140003f16  mov     rdi, [rsp+50h+arg_10]
0x140003f1b  add     rsp, 50h
0x140003f1f  pop     rbp
0x140003f20  retn
```
