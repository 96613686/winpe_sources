# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800051f0`
- end: `0x180005301`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800051f0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005284`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005284`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800052a0`

## string_xrefs

- `0x18000527d`: `kernelbase.dll`

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
0x1800051f0  mov     [rsp-8+arg_8], rbx
0x1800051f5  mov     [rsp-8+arg_10], rdi
0x1800051fa  push    rbp
0x1800051fb  mov     rbp, rsp
0x1800051fe  sub     rsp, 50h
0x180005202  mov     rbx, rcx
0x180005205  mov     [rbp+var_2C], 0
0x18000520c  mov     [rbp+var_1F], 0
0x180005210  mov     [rbp+var_1C], 0
0x180005217  xor     eax, eax
0x180005219  mov     [rbp+var_16], ax
0x18000521d  mov     eax, [rcx+8]
0x180005220  mov     [rbp+var_30], eax
0x180005223  mov     rax, [rcx+18h]
0x180005227  mov     [rbp+var_28], rax
0x18000522b  mov     al, [rcx]
0x18000522d  mov     [rbp+var_20], al
0x180005230  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005237  mov     [rbp+var_1E], ax
0x18000523b  movzx   eax, word ptr [rcx+40h]
0x18000523f  mov     [rbp+var_18], ax
0x180005243  mov     [rbp+var_14], 0
0x18000524a  mov     rax, [rcx+38h]
0x18000524e  mov     [rbp+var_10], rax
0x180005252  mov     rax, [rcx+80h]
0x180005259  mov     [rbp+var_8], rax
0x18000525d  mov     [rbp+arg_0], 0
0x180005265  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000526c  test    rdi, rdi
0x18000526f  jnz     short loc_1800052B5
0x180005271  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005278  test    rax, rax
0x18000527b  jnz     short loc_180005296
0x18000527d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005284  call    cs:__imp_GetModuleHandleW
0x18000528a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005291  test    rax, rax
0x180005294  jz      short loc_1800052A9
0x180005296  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000529d  mov     rcx, rax; hModule
0x1800052a0  call    cs:__imp_GetProcAddress
0x1800052a6  mov     rdi, rax
0x1800052a9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800052b0  test    rdi, rdi
0x1800052b3  jz      short loc_1800052C8
0x1800052b5  lea     r8, [rbp+arg_0]
0x1800052b9  lea     rdx, [rbp+var_30]
0x1800052bd  xor     ecx, ecx
0x1800052bf  mov     rax, rdi
0x1800052c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c7  nop
0x1800052c8  mov     eax, dword ptr [rbp+arg_0]
0x1800052cb  mov     [rbx+10h], eax
0x1800052ce  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800052d2  sub     ecx, 1
0x1800052d5  jz      short loc_1800052ED
0x1800052d7  sub     ecx, 1
0x1800052da  jz      short loc_1800052E7
0x1800052dc  cmp     ecx, 1
0x1800052df  jnz     short loc_1800052F1
0x1800052e1  or      dword ptr [rbx+4], 4
0x1800052e5  jmp     short loc_1800052F1
0x1800052e7  or      dword ptr [rbx+4], 2
0x1800052eb  jmp     short loc_1800052F1
0x1800052ed  or      dword ptr [rbx+4], 1
0x1800052f1  mov     rbx, [rsp+50h+arg_8]
0x1800052f6  mov     rdi, [rsp+50h+arg_10]
0x1800052fb  add     rsp, 50h
0x1800052ff  pop     rbp
0x180005300  retn
```
