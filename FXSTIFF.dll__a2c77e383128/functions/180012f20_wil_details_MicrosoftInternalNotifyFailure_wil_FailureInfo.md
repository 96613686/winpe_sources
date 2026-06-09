# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180012f20`
- end: `0x180013031`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012f20`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180012fb4`
- `KERNEL32!GetModuleHandleW` at `0x180012fb4`
- `KERNEL32!GetProcAddress` at `0x180012fd0`
- `KERNEL32!GetProcAddress` at `0x180012fd0`

## string_xrefs

- `0x180012fad`: `kernelbase.dll`

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
0x180012f20  mov     [rsp-8+arg_8], rbx
0x180012f25  mov     [rsp-8+arg_10], rdi
0x180012f2a  push    rbp
0x180012f2b  mov     rbp, rsp
0x180012f2e  sub     rsp, 50h
0x180012f32  mov     rbx, rcx
0x180012f35  mov     [rbp+var_2C], 0
0x180012f3c  mov     [rbp+var_1F], 0
0x180012f40  mov     [rbp+var_1C], 0
0x180012f47  xor     eax, eax
0x180012f49  mov     [rbp+var_16], ax
0x180012f4d  mov     eax, [rcx+8]
0x180012f50  mov     [rbp+var_30], eax
0x180012f53  mov     rax, [rcx+18h]
0x180012f57  mov     [rbp+var_28], rax
0x180012f5b  mov     al, [rcx]
0x180012f5d  mov     [rbp+var_20], al
0x180012f60  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180012f67  mov     [rbp+var_1E], ax
0x180012f6b  movzx   eax, word ptr [rcx+40h]
0x180012f6f  mov     [rbp+var_18], ax
0x180012f73  mov     [rbp+var_14], 0
0x180012f7a  mov     rax, [rcx+38h]
0x180012f7e  mov     [rbp+var_10], rax
0x180012f82  mov     rax, [rcx+80h]
0x180012f89  mov     [rbp+var_8], rax
0x180012f8d  mov     [rbp+arg_0], 0
0x180012f95  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180012f9c  test    rdi, rdi
0x180012f9f  jnz     short loc_180012FE5
0x180012fa1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012fa8  test    rax, rax
0x180012fab  jnz     short loc_180012FC6
0x180012fad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180012fb4  call    cs:__imp_GetModuleHandleW
0x180012fba  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180012fc1  test    rax, rax
0x180012fc4  jz      short loc_180012FD9
0x180012fc6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180012fcd  mov     rcx, rax; hModule
0x180012fd0  call    cs:__imp_GetProcAddress
0x180012fd6  mov     rdi, rax
0x180012fd9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180012fe0  test    rdi, rdi
0x180012fe3  jz      short loc_180012FF8
0x180012fe5  lea     r8, [rbp+arg_0]
0x180012fe9  lea     rdx, [rbp+var_30]
0x180012fed  xor     ecx, ecx
0x180012fef  mov     rax, rdi
0x180012ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff7  nop
0x180012ff8  mov     eax, dword ptr [rbp+arg_0]
0x180012ffb  mov     [rbx+10h], eax
0x180012ffe  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180013002  sub     ecx, 1
0x180013005  jz      short loc_18001301D
0x180013007  sub     ecx, 1
0x18001300a  jz      short loc_180013017
0x18001300c  cmp     ecx, 1
0x18001300f  jnz     short loc_180013021
0x180013011  or      dword ptr [rbx+4], 4
0x180013015  jmp     short loc_180013021
0x180013017  or      dword ptr [rbx+4], 2
0x18001301b  jmp     short loc_180013021
0x18001301d  or      dword ptr [rbx+4], 1
0x180013021  mov     rbx, [rsp+50h+arg_8]
0x180013026  mov     rdi, [rsp+50h+arg_10]
0x18001302b  add     rsp, 50h
0x18001302f  pop     rbp
0x180013030  retn
```
