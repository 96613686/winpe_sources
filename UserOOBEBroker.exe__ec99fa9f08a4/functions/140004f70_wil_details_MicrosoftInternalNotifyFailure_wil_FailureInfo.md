# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140004f70`
- end: `0x140005081`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004f70`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005020`
- `KERNEL32!GetProcAddress` at `0x140005020`
- `KERNEL32!GetModuleHandleW` at `0x140005004`
- `KERNEL32!GetModuleHandleW` at `0x140005004`

## string_xrefs

- `0x140004ffd`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140004f70  mov     [rsp-8+arg_8], rbx
0x140004f75  mov     [rsp-8+arg_10], rdi
0x140004f7a  push    rbp
0x140004f7b  mov     rbp, rsp
0x140004f7e  sub     rsp, 50h
0x140004f82  mov     rbx, rcx
0x140004f85  mov     [rbp+var_2C], 0
0x140004f8c  mov     [rbp+var_1F], 0
0x140004f90  mov     [rbp+var_1C], 0
0x140004f97  xor     eax, eax
0x140004f99  mov     [rbp+var_16], ax
0x140004f9d  mov     eax, [rcx+8]
0x140004fa0  mov     [rbp+var_30], eax
0x140004fa3  mov     rax, [rcx+18h]
0x140004fa7  mov     [rbp+var_28], rax
0x140004fab  mov     al, [rcx]
0x140004fad  mov     [rbp+var_20], al
0x140004fb0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140004fb7  mov     [rbp+var_1E], ax
0x140004fbb  movzx   eax, word ptr [rcx+40h]
0x140004fbf  mov     [rbp+var_18], ax
0x140004fc3  mov     [rbp+var_14], 0
0x140004fca  mov     rax, [rcx+38h]
0x140004fce  mov     [rbp+var_10], rax
0x140004fd2  mov     rax, [rcx+80h]
0x140004fd9  mov     [rbp+var_8], rax
0x140004fdd  mov     [rbp+arg_0], 0
0x140004fe5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140004fec  test    rdi, rdi
0x140004fef  jnz     short loc_140005035
0x140004ff1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004ff8  test    rax, rax
0x140004ffb  jnz     short loc_140005016
0x140004ffd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140005004  call    cs:__imp_GetModuleHandleW
0x14000500a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140005011  test    rax, rax
0x140005014  jz      short loc_140005029
0x140005016  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000501d  mov     rcx, rax; hModule
0x140005020  call    cs:__imp_GetProcAddress
0x140005026  mov     rdi, rax
0x140005029  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140005030  test    rdi, rdi
0x140005033  jz      short loc_140005048
0x140005035  lea     r8, [rbp+arg_0]
0x140005039  lea     rdx, [rbp+var_30]
0x14000503d  xor     ecx, ecx
0x14000503f  mov     rax, rdi
0x140005042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005047  nop
0x140005048  mov     eax, dword ptr [rbp+arg_0]
0x14000504b  mov     [rbx+10h], eax
0x14000504e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140005052  sub     ecx, 1
0x140005055  jz      short loc_14000506D
0x140005057  sub     ecx, 1
0x14000505a  jz      short loc_140005067
0x14000505c  cmp     ecx, 1
0x14000505f  jnz     short loc_140005071
0x140005061  or      dword ptr [rbx+4], 4
0x140005065  jmp     short loc_140005071
0x140005067  or      dword ptr [rbx+4], 2
0x14000506b  jmp     short loc_140005071
0x14000506d  or      dword ptr [rbx+4], 1
0x140005071  mov     rbx, [rsp+50h+arg_8]
0x140005076  mov     rdi, [rsp+50h+arg_10]
0x14000507b  add     rsp, 50h
0x14000507f  pop     rbp
0x140005080  retn
```
