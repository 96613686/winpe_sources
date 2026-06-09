# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005560`
- end: `0x180005671`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005560`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005610`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005610`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800055f4`

## string_xrefs

- `0x1800055ed`: `kernelbase.dll`

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
0x180005560  mov     [rsp-8+arg_8], rbx
0x180005565  mov     [rsp-8+arg_10], rdi
0x18000556a  push    rbp
0x18000556b  mov     rbp, rsp
0x18000556e  sub     rsp, 50h
0x180005572  mov     rbx, rcx
0x180005575  mov     [rbp+var_2C], 0
0x18000557c  mov     [rbp+var_1F], 0
0x180005580  mov     [rbp+var_1C], 0
0x180005587  xor     eax, eax
0x180005589  mov     [rbp+var_16], ax
0x18000558d  mov     eax, [rcx+8]
0x180005590  mov     [rbp+var_30], eax
0x180005593  mov     rax, [rcx+18h]
0x180005597  mov     [rbp+var_28], rax
0x18000559b  mov     al, [rcx]
0x18000559d  mov     [rbp+var_20], al
0x1800055a0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800055a7  mov     [rbp+var_1E], ax
0x1800055ab  movzx   eax, word ptr [rcx+40h]
0x1800055af  mov     [rbp+var_18], ax
0x1800055b3  mov     [rbp+var_14], 0
0x1800055ba  mov     rax, [rcx+38h]
0x1800055be  mov     [rbp+var_10], rax
0x1800055c2  mov     rax, [rcx+80h]
0x1800055c9  mov     [rbp+var_8], rax
0x1800055cd  mov     [rbp+arg_0], 0
0x1800055d5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800055dc  test    rdi, rdi
0x1800055df  jnz     short loc_180005625
0x1800055e1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800055e8  test    rax, rax
0x1800055eb  jnz     short loc_180005606
0x1800055ed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800055f4  call    cs:__imp_GetModuleHandleW
0x1800055fa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005601  test    rax, rax
0x180005604  jz      short loc_180005619
0x180005606  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000560d  mov     rcx, rax; hModule
0x180005610  call    cs:__imp_GetProcAddress
0x180005616  mov     rdi, rax
0x180005619  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180005620  test    rdi, rdi
0x180005623  jz      short loc_180005638
0x180005625  lea     r8, [rbp+arg_0]
0x180005629  lea     rdx, [rbp+var_30]
0x18000562d  xor     ecx, ecx
0x18000562f  mov     rax, rdi
0x180005632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005637  nop
0x180005638  mov     eax, dword ptr [rbp+arg_0]
0x18000563b  mov     [rbx+10h], eax
0x18000563e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180005642  sub     ecx, 1
0x180005645  jz      short loc_18000565D
0x180005647  sub     ecx, 1
0x18000564a  jz      short loc_180005657
0x18000564c  cmp     ecx, 1
0x18000564f  jnz     short loc_180005661
0x180005651  or      dword ptr [rbx+4], 4
0x180005655  jmp     short loc_180005661
0x180005657  or      dword ptr [rbx+4], 2
0x18000565b  jmp     short loc_180005661
0x18000565d  or      dword ptr [rbx+4], 1
0x180005661  mov     rbx, [rsp+50h+arg_8]
0x180005666  mov     rdi, [rsp+50h+arg_10]
0x18000566b  add     rsp, 50h
0x18000566f  pop     rbp
0x180005670  retn
```
