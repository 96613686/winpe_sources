# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800046c0`
- end: `0x1800047d1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800046c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004770`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004754`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004754`

## string_xrefs

- `0x18000474d`: `kernelbase.dll`

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
0x1800046c0  mov     [rsp-8+arg_8], rbx
0x1800046c5  mov     [rsp-8+arg_10], rdi
0x1800046ca  push    rbp
0x1800046cb  mov     rbp, rsp
0x1800046ce  sub     rsp, 50h
0x1800046d2  mov     rbx, rcx
0x1800046d5  mov     [rbp+var_2C], 0
0x1800046dc  mov     [rbp+var_1F], 0
0x1800046e0  mov     [rbp+var_1C], 0
0x1800046e7  xor     eax, eax
0x1800046e9  mov     [rbp+var_16], ax
0x1800046ed  mov     eax, [rcx+8]
0x1800046f0  mov     [rbp+var_30], eax
0x1800046f3  mov     rax, [rcx+18h]
0x1800046f7  mov     [rbp+var_28], rax
0x1800046fb  mov     al, [rcx]
0x1800046fd  mov     [rbp+var_20], al
0x180004700  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004707  mov     [rbp+var_1E], ax
0x18000470b  movzx   eax, word ptr [rcx+40h]
0x18000470f  mov     [rbp+var_18], ax
0x180004713  mov     [rbp+var_14], 0
0x18000471a  mov     rax, [rcx+38h]
0x18000471e  mov     [rbp+var_10], rax
0x180004722  mov     rax, [rcx+80h]
0x180004729  mov     [rbp+var_8], rax
0x18000472d  mov     [rbp+arg_0], 0
0x180004735  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000473c  test    rdi, rdi
0x18000473f  jnz     short loc_180004785
0x180004741  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004748  test    rax, rax
0x18000474b  jnz     short loc_180004766
0x18000474d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004754  call    cs:__imp_GetModuleHandleW
0x18000475a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004761  test    rax, rax
0x180004764  jz      short loc_180004779
0x180004766  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x18000476d  mov     rcx, rax; hModule
0x180004770  call    cs:__imp_GetProcAddress
0x180004776  mov     rdi, rax
0x180004779  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004780  test    rdi, rdi
0x180004783  jz      short loc_180004798
0x180004785  lea     r8, [rbp+arg_0]
0x180004789  lea     rdx, [rbp+var_30]
0x18000478d  xor     ecx, ecx
0x18000478f  mov     rax, rdi
0x180004792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004797  nop
0x180004798  mov     eax, dword ptr [rbp+arg_0]
0x18000479b  mov     [rbx+10h], eax
0x18000479e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800047a2  sub     ecx, 1
0x1800047a5  jz      short loc_1800047BD
0x1800047a7  sub     ecx, 1
0x1800047aa  jz      short loc_1800047B7
0x1800047ac  cmp     ecx, 1
0x1800047af  jnz     short loc_1800047C1
0x1800047b1  or      dword ptr [rbx+4], 4
0x1800047b5  jmp     short loc_1800047C1
0x1800047b7  or      dword ptr [rbx+4], 2
0x1800047bb  jmp     short loc_1800047C1
0x1800047bd  or      dword ptr [rbx+4], 1
0x1800047c1  mov     rbx, [rsp+50h+arg_8]
0x1800047c6  mov     rdi, [rsp+50h+arg_10]
0x1800047cb  add     rsp, 50h
0x1800047cf  pop     rbp
0x1800047d0  retn
```
