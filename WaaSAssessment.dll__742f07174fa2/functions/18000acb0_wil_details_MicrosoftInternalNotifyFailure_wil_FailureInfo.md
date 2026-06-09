# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000acb0`
- end: `0x18000adc1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000acb0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad60`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad44`

## string_xrefs

- `0x18000ad3d`: `kernelbase.dll`

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
0x18000acb0  mov     [rsp-8+arg_8], rbx
0x18000acb5  mov     [rsp-8+arg_10], rdi
0x18000acba  push    rbp
0x18000acbb  mov     rbp, rsp
0x18000acbe  sub     rsp, 50h
0x18000acc2  mov     rbx, rcx
0x18000acc5  mov     [rbp+var_2C], 0
0x18000accc  mov     [rbp+var_1F], 0
0x18000acd0  mov     [rbp+var_1C], 0
0x18000acd7  xor     eax, eax
0x18000acd9  mov     [rbp+var_16], ax
0x18000acdd  mov     eax, [rcx+8]
0x18000ace0  mov     [rbp+var_30], eax
0x18000ace3  mov     rax, [rcx+18h]
0x18000ace7  mov     [rbp+var_28], rax
0x18000aceb  mov     al, [rcx]
0x18000aced  mov     [rbp+var_20], al
0x18000acf0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000acf7  mov     [rbp+var_1E], ax
0x18000acfb  movzx   eax, word ptr [rcx+40h]
0x18000acff  mov     [rbp+var_18], ax
0x18000ad03  mov     [rbp+var_14], 0
0x18000ad0a  mov     rax, [rcx+38h]
0x18000ad0e  mov     [rbp+var_10], rax
0x18000ad12  mov     rax, [rcx+80h]
0x18000ad19  mov     [rbp+var_8], rax
0x18000ad1d  mov     [rbp+arg_0], 0
0x18000ad25  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000ad2c  test    rdi, rdi
0x18000ad2f  jnz     short loc_18000AD75
0x18000ad31  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ad38  test    rax, rax
0x18000ad3b  jnz     short loc_18000AD56
0x18000ad3d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000ad44  call    cs:__imp_GetModuleHandleW
0x18000ad4a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000ad51  test    rax, rax
0x18000ad54  jz      short loc_18000AD69
0x18000ad56  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000ad5d  mov     rcx, rax; hModule
0x18000ad60  call    cs:__imp_GetProcAddress
0x18000ad66  mov     rdi, rax
0x18000ad69  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000ad70  test    rdi, rdi
0x18000ad73  jz      short loc_18000AD88
0x18000ad75  lea     r8, [rbp+arg_0]
0x18000ad79  lea     rdx, [rbp+var_30]
0x18000ad7d  xor     ecx, ecx
0x18000ad7f  mov     rax, rdi
0x18000ad82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad87  nop
0x18000ad88  mov     eax, dword ptr [rbp+arg_0]
0x18000ad8b  mov     [rbx+10h], eax
0x18000ad8e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000ad92  sub     ecx, 1
0x18000ad95  jz      short loc_18000ADAD
0x18000ad97  sub     ecx, 1
0x18000ad9a  jz      short loc_18000ADA7
0x18000ad9c  cmp     ecx, 1
0x18000ad9f  jnz     short loc_18000ADB1
0x18000ada1  or      dword ptr [rbx+4], 4
0x18000ada5  jmp     short loc_18000ADB1
0x18000ada7  or      dword ptr [rbx+4], 2
0x18000adab  jmp     short loc_18000ADB1
0x18000adad  or      dword ptr [rbx+4], 1
0x18000adb1  mov     rbx, [rsp+50h+arg_8]
0x18000adb6  mov     rdi, [rsp+50h+arg_10]
0x18000adbb  add     rsp, 50h
0x18000adbf  pop     rbp
0x18000adc0  retn
```
