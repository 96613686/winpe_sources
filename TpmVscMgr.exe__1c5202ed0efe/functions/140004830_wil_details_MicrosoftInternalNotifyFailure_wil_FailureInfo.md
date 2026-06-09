# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140004830`
- end: `0x140004941`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004830`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400048e0`
- `KERNEL32!GetProcAddress` at `0x1400048e0`
- `KERNEL32!GetModuleHandleW` at `0x1400048c4`
- `KERNEL32!GetModuleHandleW` at `0x1400048c4`

## string_xrefs

- `0x1400048bd`: `kernelbase.dll`

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
0x140004830  mov     [rsp-8+arg_8], rbx
0x140004835  mov     [rsp-8+arg_10], rdi
0x14000483a  push    rbp
0x14000483b  mov     rbp, rsp
0x14000483e  sub     rsp, 50h
0x140004842  mov     rbx, rcx
0x140004845  mov     [rbp+var_2C], 0
0x14000484c  mov     [rbp+var_1F], 0
0x140004850  mov     [rbp+var_1C], 0
0x140004857  xor     eax, eax
0x140004859  mov     [rbp+var_16], ax
0x14000485d  mov     eax, [rcx+8]
0x140004860  mov     [rbp+var_30], eax
0x140004863  mov     rax, [rcx+18h]
0x140004867  mov     [rbp+var_28], rax
0x14000486b  mov     al, [rcx]
0x14000486d  mov     [rbp+var_20], al
0x140004870  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140004877  mov     [rbp+var_1E], ax
0x14000487b  movzx   eax, word ptr [rcx+40h]
0x14000487f  mov     [rbp+var_18], ax
0x140004883  mov     [rbp+var_14], 0
0x14000488a  mov     rax, [rcx+38h]
0x14000488e  mov     [rbp+var_10], rax
0x140004892  mov     rax, [rcx+80h]
0x140004899  mov     [rbp+var_8], rax
0x14000489d  mov     [rbp+arg_0], 0
0x1400048a5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400048ac  test    rdi, rdi
0x1400048af  jnz     short loc_1400048F5
0x1400048b1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400048b8  test    rax, rax
0x1400048bb  jnz     short loc_1400048D6
0x1400048bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400048c4  call    cs:__imp_GetModuleHandleW
0x1400048ca  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400048d1  test    rax, rax
0x1400048d4  jz      short loc_1400048E9
0x1400048d6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1400048dd  mov     rcx, rax; hModule
0x1400048e0  call    cs:__imp_GetProcAddress
0x1400048e6  mov     rdi, rax
0x1400048e9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400048f0  test    rdi, rdi
0x1400048f3  jz      short loc_140004908
0x1400048f5  lea     r8, [rbp+arg_0]
0x1400048f9  lea     rdx, [rbp+var_30]
0x1400048fd  xor     ecx, ecx
0x1400048ff  mov     rax, rdi
0x140004902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004907  nop
0x140004908  mov     eax, dword ptr [rbp+arg_0]
0x14000490b  mov     [rbx+10h], eax
0x14000490e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140004912  sub     ecx, 1
0x140004915  jz      short loc_14000492D
0x140004917  sub     ecx, 1
0x14000491a  jz      short loc_140004927
0x14000491c  cmp     ecx, 1
0x14000491f  jnz     short loc_140004931
0x140004921  or      dword ptr [rbx+4], 4
0x140004925  jmp     short loc_140004931
0x140004927  or      dword ptr [rbx+4], 2
0x14000492b  jmp     short loc_140004931
0x14000492d  or      dword ptr [rbx+4], 1
0x140004931  mov     rbx, [rsp+50h+arg_8]
0x140004936  mov     rdi, [rsp+50h+arg_10]
0x14000493b  add     rsp, 50h
0x14000493f  pop     rbp
0x140004940  retn
```
