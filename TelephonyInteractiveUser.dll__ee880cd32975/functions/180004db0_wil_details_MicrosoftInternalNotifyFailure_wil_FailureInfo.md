# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004db0`
- end: `0x180004edc`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `300`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180004db0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004e6e`

## string_xrefs

- `0x180004e4b`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h]
  char v10; // [rsp+30h] [rbp-30h]
  char v11; // [rsp+31h] [rbp-2Fh]
  __int16 v12; // [rsp+32h] [rbp-2Eh]
  int v13; // [rsp+34h] [rbp-2Ch]
  __int16 v14; // [rsp+38h] [rbp-28h]
  __int16 v15; // [rsp+3Ah] [rbp-26h]
  int v16; // [rsp+3Ch] [rbp-24h]
  __int64 v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+48h] [rbp-18h]
  __int64 v19; // [rsp+50h] [rbp-10h] BYREF

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
0x180004db0  mov     [rsp-8+arg_8], rbx
0x180004db5  mov     [rsp-8+arg_10], rdi
0x180004dba  push    rbp
0x180004dbb  mov     rbp, rsp
0x180004dbe  sub     rsp, 60h
0x180004dc2  mov     rax, cs:__security_cookie
0x180004dc9  xor     rax, rsp
0x180004dcc  mov     [rbp+var_8], rax
0x180004dd0  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004dd7  xor     eax, eax
0x180004dd9  mov     [rbp+var_26], ax
0x180004ddd  mov     rbx, rcx
0x180004de0  mov     eax, [rcx+8]
0x180004de3  mov     [rbp+var_40], eax
0x180004de6  mov     rax, [rcx+18h]
0x180004dea  mov     [rbp+var_38], rax
0x180004dee  mov     al, [rcx]
0x180004df0  mov     [rbp+var_30], al
0x180004df3  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004dfa  mov     [rbp+var_2E], ax
0x180004dfe  movzx   eax, word ptr [rcx+40h]
0x180004e02  mov     [rbp+var_28], ax
0x180004e06  mov     rax, [rcx+38h]
0x180004e0a  mov     [rbp+var_20], rax
0x180004e0e  mov     rax, [rcx+80h]
0x180004e15  mov     [rbp+var_18], rax
0x180004e19  mov     [rbp+var_3C], 0
0x180004e20  mov     [rbp+var_2F], 0
0x180004e24  mov     [rbp+var_2C], 0
0x180004e2b  mov     [rbp+var_24], 0
0x180004e32  mov     [rbp+var_10], 0
0x180004e3a  test    rdi, rdi
0x180004e3d  jnz     short loc_180004E83
0x180004e3f  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004e46  test    rax, rax
0x180004e49  jnz     short loc_180004E64
0x180004e4b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004e52  call    cs:__imp_GetModuleHandleW
0x180004e58  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004e5f  test    rax, rax
0x180004e62  jz      short loc_180004E77
0x180004e64  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180004e6b  mov     rcx, rax; hModule
0x180004e6e  call    cs:__imp_GetProcAddress
0x180004e74  mov     rdi, rax
0x180004e77  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004e7e  test    rdi, rdi
0x180004e81  jz      short loc_180004E95
0x180004e83  lea     r8, [rbp+var_10]
0x180004e87  xor     ecx, ecx
0x180004e89  lea     rdx, [rbp+var_40]
0x180004e8d  mov     rax, rdi
0x180004e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e95  movzx   ecx, byte ptr [rbp+var_10+4]
0x180004e99  mov     eax, dword ptr [rbp+var_10]
0x180004e9c  mov     [rbx+10h], eax
0x180004e9f  sub     ecx, 1
0x180004ea2  jz      short loc_180004EBA
0x180004ea4  sub     ecx, 1
0x180004ea7  jz      short loc_180004EB4
0x180004ea9  cmp     ecx, 1
0x180004eac  jnz     short loc_180004EBE
0x180004eae  or      dword ptr [rbx+4], 4
0x180004eb2  jmp     short loc_180004EBE
0x180004eb4  or      dword ptr [rbx+4], 2
0x180004eb8  jmp     short loc_180004EBE
0x180004eba  or      dword ptr [rbx+4], 1
0x180004ebe  mov     rcx, [rbp+var_8]
0x180004ec2  xor     rcx, rsp; StackCookie
0x180004ec5  call    __security_check_cookie
0x180004eca  lea     r11, [rsp+60h+var_s0]
0x180004ecf  mov     rbx, [r11+18h]
0x180004ed3  mov     rdi, [r11+20h]
0x180004ed7  mov     rsp, r11
0x180004eda  pop     rbp
0x180004edb  retn
```
