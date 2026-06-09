# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004f70`
- end: `0x180005081`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004f70`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005004`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005004`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005020`

## string_xrefs

- `0x180004ffd`: `kernelbase.dll`

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
0x180004f70  mov     [rsp-8+arg_8], rbx
0x180004f75  mov     [rsp-8+arg_10], rdi
0x180004f7a  push    rbp
0x180004f7b  mov     rbp, rsp
0x180004f7e  sub     rsp, 50h
0x180004f82  mov     rbx, rcx
0x180004f85  mov     [rbp+var_2C], 0
0x180004f8c  mov     [rbp+var_1F], 0
0x180004f90  mov     [rbp+var_1C], 0
0x180004f97  xor     eax, eax
0x180004f99  mov     [rbp+var_16], ax
0x180004f9d  mov     eax, [rcx+8]
0x180004fa0  mov     [rbp+var_30], eax
0x180004fa3  mov     rax, [rcx+18h]
0x180004fa7  mov     [rbp+var_28], rax
0x180004fab  mov     al, [rcx]
0x180004fad  mov     [rbp+var_20], al
0x180004fb0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004fb7  mov     [rbp+var_1E], ax
0x180004fbb  movzx   eax, word ptr [rcx+40h]
0x180004fbf  mov     [rbp+var_18], ax
0x180004fc3  mov     [rbp+var_14], 0
0x180004fca  mov     rax, [rcx+38h]
0x180004fce  mov     [rbp+var_10], rax
0x180004fd2  mov     rax, [rcx+80h]
0x180004fd9  mov     [rbp+var_8], rax
0x180004fdd  mov     [rbp+arg_0], 0
0x180004fe5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004fec  test    rdi, rdi
0x180004fef  jnz     short loc_180005035
0x180004ff1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004ff8  test    rax, rax
0x180004ffb  jnz     short loc_180005016
0x180004ffd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005004  call    cs:__imp_GetModuleHandleW
0x18000500a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005011  test    rax, rax
0x180005014  jz      short loc_180005029
0x180005016  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000501d  mov     rcx, rax; hModule
0x180005020  call    cs:__imp_GetProcAddress
0x180005026  mov     rdi, rax
0x180005029  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005030  test    rdi, rdi
0x180005033  jz      short loc_180005048
0x180005035  lea     r8, [rbp+arg_0]
0x180005039  lea     rdx, [rbp+var_30]
0x18000503d  xor     ecx, ecx
0x18000503f  mov     rax, rdi
0x180005042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005047  nop
0x180005048  mov     eax, dword ptr [rbp+arg_0]
0x18000504b  mov     [rbx+10h], eax
0x18000504e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005052  sub     ecx, 1
0x180005055  jz      short loc_18000506D
0x180005057  sub     ecx, 1
0x18000505a  jz      short loc_180005067
0x18000505c  cmp     ecx, 1
0x18000505f  jnz     short loc_180005071
0x180005061  or      dword ptr [rbx+4], 4
0x180005065  jmp     short loc_180005071
0x180005067  or      dword ptr [rbx+4], 2
0x18000506b  jmp     short loc_180005071
0x18000506d  or      dword ptr [rbx+4], 1
0x180005071  mov     rbx, [rsp+50h+arg_8]
0x180005076  mov     rdi, [rsp+50h+arg_10]
0x18000507b  add     rsp, 50h
0x18000507f  pop     rbp
0x180005080  retn
```
