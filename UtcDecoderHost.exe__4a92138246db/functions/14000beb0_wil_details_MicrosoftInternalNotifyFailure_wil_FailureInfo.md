# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x14000beb0`
- end: `0x14000bfc1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000beb0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bf44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bf44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bf60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bf60`

## string_xrefs

- `0x14000bf3d`: `kernelbase.dll`

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
0x14000beb0  mov     [rsp-8+arg_8], rbx
0x14000beb5  mov     [rsp-8+arg_10], rdi
0x14000beba  push    rbp
0x14000bebb  mov     rbp, rsp
0x14000bebe  sub     rsp, 50h
0x14000bec2  mov     rbx, rcx
0x14000bec5  mov     [rbp+var_2C], 0
0x14000becc  mov     [rbp+var_1F], 0
0x14000bed0  mov     [rbp+var_1C], 0
0x14000bed7  xor     eax, eax
0x14000bed9  mov     [rbp+var_16], ax
0x14000bedd  mov     eax, [rcx+8]
0x14000bee0  mov     [rbp+var_30], eax
0x14000bee3  mov     rax, [rcx+18h]
0x14000bee7  mov     [rbp+var_28], rax
0x14000beeb  mov     al, [rcx]
0x14000beed  mov     [rbp+var_20], al
0x14000bef0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000bef7  mov     [rbp+var_1E], ax
0x14000befb  movzx   eax, word ptr [rcx+40h]
0x14000beff  mov     [rbp+var_18], ax
0x14000bf03  mov     [rbp+var_14], 0
0x14000bf0a  mov     rax, [rcx+38h]
0x14000bf0e  mov     [rbp+var_10], rax
0x14000bf12  mov     rax, [rcx+80h]
0x14000bf19  mov     [rbp+var_8], rax
0x14000bf1d  mov     [rbp+arg_0], 0
0x14000bf25  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000bf2c  test    rdi, rdi
0x14000bf2f  jnz     short loc_14000BF75
0x14000bf31  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000bf38  test    rax, rax
0x14000bf3b  jnz     short loc_14000BF56
0x14000bf3d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000bf44  call    cs:__imp_GetModuleHandleW
0x14000bf4a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000bf51  test    rax, rax
0x14000bf54  jz      short loc_14000BF69
0x14000bf56  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000bf5d  mov     rcx, rax; hModule
0x14000bf60  call    cs:__imp_GetProcAddress
0x14000bf66  mov     rdi, rax
0x14000bf69  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000bf70  test    rdi, rdi
0x14000bf73  jz      short loc_14000BF88
0x14000bf75  lea     r8, [rbp+arg_0]
0x14000bf79  lea     rdx, [rbp+var_30]
0x14000bf7d  xor     ecx, ecx
0x14000bf7f  mov     rax, rdi
0x14000bf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf87  nop
0x14000bf88  mov     eax, dword ptr [rbp+arg_0]
0x14000bf8b  mov     [rbx+10h], eax
0x14000bf8e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000bf92  sub     ecx, 1
0x14000bf95  jz      short loc_14000BFAD
0x14000bf97  sub     ecx, 1
0x14000bf9a  jz      short loc_14000BFA7
0x14000bf9c  cmp     ecx, 1
0x14000bf9f  jnz     short loc_14000BFB1
0x14000bfa1  or      dword ptr [rbx+4], 4
0x14000bfa5  jmp     short loc_14000BFB1
0x14000bfa7  or      dword ptr [rbx+4], 2
0x14000bfab  jmp     short loc_14000BFB1
0x14000bfad  or      dword ptr [rbx+4], 1
0x14000bfb1  mov     rbx, [rsp+50h+arg_8]
0x14000bfb6  mov     rdi, [rsp+50h+arg_10]
0x14000bfbb  add     rsp, 50h
0x14000bfbf  pop     rbp
0x14000bfc0  retn
```
