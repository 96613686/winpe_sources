# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140009da0`
- end: `0x140009eb1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009da0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009e34`
- `KERNEL32!GetModuleHandleW` at `0x140009e34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e50`

## string_xrefs

- `0x140009e2d`: `kernelbase.dll`

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
0x140009da0  mov     [rsp-8+arg_8], rbx
0x140009da5  mov     [rsp-8+arg_10], rdi
0x140009daa  push    rbp
0x140009dab  mov     rbp, rsp
0x140009dae  sub     rsp, 50h
0x140009db2  mov     rbx, rcx
0x140009db5  mov     [rbp+var_2C], 0
0x140009dbc  mov     [rbp+var_1F], 0
0x140009dc0  mov     [rbp+var_1C], 0
0x140009dc7  xor     eax, eax
0x140009dc9  mov     [rbp+var_16], ax
0x140009dcd  mov     eax, [rcx+8]
0x140009dd0  mov     [rbp+var_30], eax
0x140009dd3  mov     rax, [rcx+18h]
0x140009dd7  mov     [rbp+var_28], rax
0x140009ddb  mov     al, [rcx]
0x140009ddd  mov     [rbp+var_20], al
0x140009de0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140009de7  mov     [rbp+var_1E], ax
0x140009deb  movzx   eax, word ptr [rcx+40h]
0x140009def  mov     [rbp+var_18], ax
0x140009df3  mov     [rbp+var_14], 0
0x140009dfa  mov     rax, [rcx+38h]
0x140009dfe  mov     [rbp+var_10], rax
0x140009e02  mov     rax, [rcx+80h]
0x140009e09  mov     [rbp+var_8], rax
0x140009e0d  mov     [rbp+arg_0], 0
0x140009e15  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140009e1c  test    rdi, rdi
0x140009e1f  jnz     short loc_140009E65
0x140009e21  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009e28  test    rax, rax
0x140009e2b  jnz     short loc_140009E46
0x140009e2d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140009e34  call    cs:__imp_GetModuleHandleW
0x140009e3a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009e41  test    rax, rax
0x140009e44  jz      short loc_140009E59
0x140009e46  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140009e4d  mov     rcx, rax; hModule
0x140009e50  call    cs:__imp_GetProcAddress
0x140009e56  mov     rdi, rax
0x140009e59  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140009e60  test    rdi, rdi
0x140009e63  jz      short loc_140009E78
0x140009e65  lea     r8, [rbp+arg_0]
0x140009e69  lea     rdx, [rbp+var_30]
0x140009e6d  xor     ecx, ecx
0x140009e6f  mov     rax, rdi
0x140009e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e77  nop
0x140009e78  mov     eax, dword ptr [rbp+arg_0]
0x140009e7b  mov     [rbx+10h], eax
0x140009e7e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140009e82  sub     ecx, 1
0x140009e85  jz      short loc_140009E9D
0x140009e87  sub     ecx, 1
0x140009e8a  jz      short loc_140009E97
0x140009e8c  cmp     ecx, 1
0x140009e8f  jnz     short loc_140009EA1
0x140009e91  or      dword ptr [rbx+4], 4
0x140009e95  jmp     short loc_140009EA1
0x140009e97  or      dword ptr [rbx+4], 2
0x140009e9b  jmp     short loc_140009EA1
0x140009e9d  or      dword ptr [rbx+4], 1
0x140009ea1  mov     rbx, [rsp+50h+arg_8]
0x140009ea6  mov     rdi, [rsp+50h+arg_10]
0x140009eab  add     rsp, 50h
0x140009eaf  pop     rbp
0x140009eb0  retn
```
