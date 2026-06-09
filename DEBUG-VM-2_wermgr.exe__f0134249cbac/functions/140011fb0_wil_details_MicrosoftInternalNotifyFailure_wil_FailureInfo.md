# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140011fb0`
- end: `0x1400120c1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140011fb0`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012060`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012044`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012044`

## string_xrefs

- `0x14001203d`: `kernelbase.dll`

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
0x140011fb0  mov     [rsp-8+arg_8], rbx
0x140011fb5  mov     [rsp-8+arg_10], rdi
0x140011fba  push    rbp
0x140011fbb  mov     rbp, rsp
0x140011fbe  sub     rsp, 50h
0x140011fc2  mov     rbx, rcx
0x140011fc5  mov     [rbp+var_2C], 0
0x140011fcc  mov     [rbp+var_1F], 0
0x140011fd0  mov     [rbp+var_1C], 0
0x140011fd7  xor     eax, eax
0x140011fd9  mov     [rbp+var_16], ax
0x140011fdd  mov     eax, [rcx+8]
0x140011fe0  mov     [rbp+var_30], eax
0x140011fe3  mov     rax, [rcx+18h]
0x140011fe7  mov     [rbp+var_28], rax
0x140011feb  mov     al, [rcx]
0x140011fed  mov     [rbp+var_20], al
0x140011ff0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140011ff7  mov     [rbp+var_1E], ax
0x140011ffb  movzx   eax, word ptr [rcx+40h]
0x140011fff  mov     [rbp+var_18], ax
0x140012003  mov     [rbp+var_14], 0
0x14001200a  mov     rax, [rcx+38h]
0x14001200e  mov     [rbp+var_10], rax
0x140012012  mov     rax, [rcx+80h]
0x140012019  mov     [rbp+var_8], rax
0x14001201d  mov     [rbp+arg_0], 0
0x140012025  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14001202c  test    rdi, rdi
0x14001202f  jnz     short loc_140012075
0x140012031  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140012038  test    rax, rax
0x14001203b  jnz     short loc_140012056
0x14001203d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140012044  call    cs:__imp_GetModuleHandleW
0x14001204a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140012051  test    rax, rax
0x140012054  jz      short loc_140012069
0x140012056  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14001205d  mov     rcx, rax; hModule
0x140012060  call    cs:__imp_GetProcAddress
0x140012066  mov     rdi, rax
0x140012069  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140012070  test    rdi, rdi
0x140012073  jz      short loc_140012088
0x140012075  lea     r8, [rbp+arg_0]
0x140012079  lea     rdx, [rbp+var_30]
0x14001207d  xor     ecx, ecx
0x14001207f  mov     rax, rdi
0x140012082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012087  nop
0x140012088  mov     eax, dword ptr [rbp+arg_0]
0x14001208b  mov     [rbx+10h], eax
0x14001208e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140012092  sub     ecx, 1
0x140012095  jz      short loc_1400120AD
0x140012097  sub     ecx, 1
0x14001209a  jz      short loc_1400120A7
0x14001209c  cmp     ecx, 1
0x14001209f  jnz     short loc_1400120B1
0x1400120a1  or      dword ptr [rbx+4], 4
0x1400120a5  jmp     short loc_1400120B1
0x1400120a7  or      dword ptr [rbx+4], 2
0x1400120ab  jmp     short loc_1400120B1
0x1400120ad  or      dword ptr [rbx+4], 1
0x1400120b1  mov     rbx, [rsp+50h+arg_8]
0x1400120b6  mov     rdi, [rsp+50h+arg_10]
0x1400120bb  add     rsp, 50h
0x1400120bf  pop     rbp
0x1400120c0  retn
```
