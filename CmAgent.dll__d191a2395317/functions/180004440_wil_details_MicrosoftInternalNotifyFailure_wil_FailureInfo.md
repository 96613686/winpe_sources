# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004440`
- end: `0x18000455e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004440`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800044d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044f6`

## string_xrefs

- `0x1800044cd`: `kernelbase.dll`

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
0x180004440  mov     [rsp-8+arg_8], rbx
0x180004445  mov     [rsp-8+arg_10], rdi
0x18000444a  push    rbp
0x18000444b  mov     rbp, rsp
0x18000444e  sub     rsp, 50h
0x180004452  mov     rbx, rcx
0x180004455  mov     [rbp+var_2C], 0
0x18000445c  mov     [rbp+var_1F], 0
0x180004460  mov     [rbp+var_1C], 0
0x180004467  xor     eax, eax
0x180004469  mov     [rbp+var_16], ax
0x18000446d  mov     eax, [rcx+8]
0x180004470  mov     [rbp+var_30], eax
0x180004473  mov     rax, [rcx+18h]
0x180004477  mov     [rbp+var_28], rax
0x18000447b  mov     al, [rcx]
0x18000447d  mov     [rbp+var_20], al
0x180004480  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004487  mov     [rbp+var_1E], ax
0x18000448b  movzx   eax, word ptr [rcx+40h]
0x18000448f  mov     [rbp+var_18], ax
0x180004493  mov     [rbp+var_14], 0
0x18000449a  mov     rax, [rcx+38h]
0x18000449e  mov     [rbp+var_10], rax
0x1800044a2  mov     rax, [rcx+80h]
0x1800044a9  mov     [rbp+var_8], rax
0x1800044ad  mov     [rbp+arg_0], 0
0x1800044b5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800044bc  test    rdi, rdi
0x1800044bf  jnz     short loc_180004511
0x1800044c1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800044c8  test    rax, rax
0x1800044cb  jnz     short loc_1800044EC
0x1800044cd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800044d4  call    cs:__imp_GetModuleHandleW
0x1800044db  nop     dword ptr [rax+rax+00h]
0x1800044e0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800044e7  test    rax, rax
0x1800044ea  jz      short loc_180004505
0x1800044ec  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800044f3  mov     rcx, rax; hModule
0x1800044f6  call    cs:__imp_GetProcAddress
0x1800044fd  nop     dword ptr [rax+rax+00h]
0x180004502  mov     rdi, rax
0x180004505  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000450c  test    rdi, rdi
0x18000450f  jz      short loc_180004524
0x180004511  lea     r8, [rbp+arg_0]
0x180004515  lea     rdx, [rbp+var_30]
0x180004519  xor     ecx, ecx
0x18000451b  mov     rax, rdi
0x18000451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004523  nop
0x180004524  mov     eax, dword ptr [rbp+arg_0]
0x180004527  mov     [rbx+10h], eax
0x18000452a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000452e  sub     ecx, 1
0x180004531  jz      short loc_180004549
0x180004533  sub     ecx, 1
0x180004536  jz      short loc_180004543
0x180004538  cmp     ecx, 1
0x18000453b  jnz     short loc_18000454D
0x18000453d  or      dword ptr [rbx+4], 4
0x180004541  jmp     short loc_18000454D
0x180004543  or      dword ptr [rbx+4], 2
0x180004547  jmp     short loc_18000454D
0x180004549  or      dword ptr [rbx+4], 1
0x18000454d  mov     rbx, [rsp+50h+arg_8]
0x180004552  mov     rdi, [rsp+50h+arg_10]
0x180004557  add     rsp, 50h
0x18000455b  pop     rbp
0x18000455c  retn
```
