# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140008ff0`
- end: `0x140009101`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008ff0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140009084`
- `KERNEL32!GetModuleHandleW` at `0x140009084`
- `KERNEL32!GetProcAddress` at `0x1400090a0`
- `KERNEL32!GetProcAddress` at `0x1400090a0`

## string_xrefs

- `0x14000907d`: `kernelbase.dll`

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
0x140008ff0  mov     [rsp-8+arg_8], rbx
0x140008ff5  mov     [rsp-8+arg_10], rdi
0x140008ffa  push    rbp
0x140008ffb  mov     rbp, rsp
0x140008ffe  sub     rsp, 50h
0x140009002  mov     rbx, rcx
0x140009005  mov     [rbp+var_2C], 0
0x14000900c  mov     [rbp+var_1F], 0
0x140009010  mov     [rbp+var_1C], 0
0x140009017  xor     eax, eax
0x140009019  mov     [rbp+var_16], ax
0x14000901d  mov     eax, [rcx+8]
0x140009020  mov     [rbp+var_30], eax
0x140009023  mov     rax, [rcx+18h]
0x140009027  mov     [rbp+var_28], rax
0x14000902b  mov     al, [rcx]
0x14000902d  mov     [rbp+var_20], al
0x140009030  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140009037  mov     [rbp+var_1E], ax
0x14000903b  movzx   eax, word ptr [rcx+40h]
0x14000903f  mov     [rbp+var_18], ax
0x140009043  mov     [rbp+var_14], 0
0x14000904a  mov     rax, [rcx+38h]
0x14000904e  mov     [rbp+var_10], rax
0x140009052  mov     rax, [rcx+80h]
0x140009059  mov     [rbp+var_8], rax
0x14000905d  mov     [rbp+arg_0], 0
0x140009065  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000906c  test    rdi, rdi
0x14000906f  jnz     short loc_1400090B5
0x140009071  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009078  test    rax, rax
0x14000907b  jnz     short loc_140009096
0x14000907d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140009084  call    cs:__imp_GetModuleHandleW
0x14000908a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140009091  test    rax, rax
0x140009094  jz      short loc_1400090A9
0x140009096  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000909d  mov     rcx, rax; hModule
0x1400090a0  call    cs:__imp_GetProcAddress
0x1400090a6  mov     rdi, rax
0x1400090a9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400090b0  test    rdi, rdi
0x1400090b3  jz      short loc_1400090C8
0x1400090b5  lea     r8, [rbp+arg_0]
0x1400090b9  lea     rdx, [rbp+var_30]
0x1400090bd  xor     ecx, ecx
0x1400090bf  mov     rax, rdi
0x1400090c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090c7  nop
0x1400090c8  mov     eax, dword ptr [rbp+arg_0]
0x1400090cb  mov     [rbx+10h], eax
0x1400090ce  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1400090d2  sub     ecx, 1
0x1400090d5  jz      short loc_1400090ED
0x1400090d7  sub     ecx, 1
0x1400090da  jz      short loc_1400090E7
0x1400090dc  cmp     ecx, 1
0x1400090df  jnz     short loc_1400090F1
0x1400090e1  or      dword ptr [rbx+4], 4
0x1400090e5  jmp     short loc_1400090F1
0x1400090e7  or      dword ptr [rbx+4], 2
0x1400090eb  jmp     short loc_1400090F1
0x1400090ed  or      dword ptr [rbx+4], 1
0x1400090f1  mov     rbx, [rsp+50h+arg_8]
0x1400090f6  mov     rdi, [rsp+50h+arg_10]
0x1400090fb  add     rsp, 50h
0x1400090ff  pop     rbp
0x140009100  retn
```
