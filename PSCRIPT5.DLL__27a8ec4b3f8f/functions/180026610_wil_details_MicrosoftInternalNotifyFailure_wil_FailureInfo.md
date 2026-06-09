# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180026610`
- end: `0x18002672d`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `285`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180026610`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800266a4`
- `KERNEL32!GetModuleHandleW` at `0x1800266a4`
- `KERNEL32!GetProcAddress` at `0x1800266c6`
- `KERNEL32!GetProcAddress` at `0x1800266c6`

## string_xrefs

- `0x18002669d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+30h] [rbp-20h]
  char v11; // [rsp+31h] [rbp-1Fh]
  __int16 v12; // [rsp+32h] [rbp-1Eh]
  int v13; // [rsp+34h] [rbp-1Ch]
  __int16 v14; // [rsp+38h] [rbp-18h]
  __int16 v15; // [rsp+3Ah] [rbp-16h]
  int v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v15 = 0;
  v8[0] = *((_DWORD *)this + 2);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_BYTE *)this;
  v12 = wil::g_moduleFailureReportFlags;
  v14 = *((_WORD *)this + 32);
  v17 = *((_QWORD *)this + 7);
  v18 = *((_QWORD *)this + 16);
  v8[1] = 0;
  v11 = 0;
  v13 = 0;
  v16 = 0;
  v19 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v8, &v19);
  v5 = BYTE4(v19);
  *((_DWORD *)this + 4) = v19;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
        *((_DWORD *)this + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)this + 1) |= 2u;
    }
  }
  else
  {
    *((_DWORD *)this + 1) |= 1u;
  }
}

```

## disassembly

```asm
0x180026610  mov     [rsp-8+arg_8], rbx
0x180026615  mov     [rsp-8+arg_10], rdi
0x18002661a  push    rbp
0x18002661b  mov     rbp, rsp
0x18002661e  sub     rsp, 50h
0x180026622  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180026629  xor     eax, eax
0x18002662b  mov     [rbp+var_16], ax
0x18002662f  mov     rbx, rcx
0x180026632  mov     eax, [rcx+8]
0x180026635  mov     [rbp+var_30], eax
0x180026638  mov     rax, [rcx+18h]
0x18002663c  mov     [rbp+var_28], rax
0x180026640  mov     al, [rcx]
0x180026642  mov     [rbp+var_20], al
0x180026645  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18002664c  mov     [rbp+var_1E], ax
0x180026650  movzx   eax, word ptr [rcx+40h]
0x180026654  mov     [rbp+var_18], ax
0x180026658  mov     rax, [rcx+38h]
0x18002665c  mov     [rbp+var_10], rax
0x180026660  mov     rax, [rcx+80h]
0x180026667  mov     [rbp+var_8], rax
0x18002666b  mov     [rbp+var_2C], 0
0x180026672  mov     [rbp+var_1F], 0
0x180026676  mov     [rbp+var_1C], 0
0x18002667d  mov     [rbp+var_14], 0
0x180026684  mov     [rbp+arg_0], 0
0x18002668c  test    rdi, rdi
0x18002668f  jnz     short loc_1800266E1
0x180026691  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180026698  test    rax, rax
0x18002669b  jnz     short loc_1800266BC
0x18002669d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800266a4  call    cs:__imp_GetModuleHandleW
0x1800266ab  nop     dword ptr [rax+rax+00h]
0x1800266b0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800266b7  test    rax, rax
0x1800266ba  jz      short loc_1800266D5
0x1800266bc  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800266c3  mov     rcx, rax; hModule
0x1800266c6  call    cs:__imp_GetProcAddress
0x1800266cd  nop     dword ptr [rax+rax+00h]
0x1800266d2  mov     rdi, rax
0x1800266d5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800266dc  test    rdi, rdi
0x1800266df  jz      short loc_1800266F3
0x1800266e1  lea     r8, [rbp+arg_0]
0x1800266e5  xor     ecx, ecx
0x1800266e7  lea     rdx, [rbp+var_30]
0x1800266eb  mov     rax, rdi
0x1800266ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266f3  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800266f7  mov     eax, dword ptr [rbp+arg_0]
0x1800266fa  mov     [rbx+10h], eax
0x1800266fd  sub     ecx, 1
0x180026700  jz      short loc_180026718
0x180026702  sub     ecx, 1
0x180026705  jz      short loc_180026712
0x180026707  cmp     ecx, 1
0x18002670a  jnz     short loc_18002671C
0x18002670c  or      dword ptr [rbx+4], 4
0x180026710  jmp     short loc_18002671C
0x180026712  or      dword ptr [rbx+4], 2
0x180026716  jmp     short loc_18002671C
0x180026718  or      dword ptr [rbx+4], 1
0x18002671c  mov     rbx, [rsp+50h+arg_8]
0x180026721  mov     rdi, [rsp+50h+arg_10]
0x180026726  add     rsp, 50h
0x18002672a  pop     rbp
0x18002672b  retn
```
