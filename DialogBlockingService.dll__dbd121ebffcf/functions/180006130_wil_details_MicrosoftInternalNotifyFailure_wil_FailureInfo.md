# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006130`
- end: `0x180006241`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006130`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061c4`

## string_xrefs

- `0x1800061bd`: `kernelbase.dll`

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
0x180006130  mov     [rsp-8+arg_8], rbx
0x180006135  mov     [rsp-8+arg_10], rdi
0x18000613a  push    rbp
0x18000613b  mov     rbp, rsp
0x18000613e  sub     rsp, 50h
0x180006142  mov     rbx, rcx
0x180006145  mov     [rbp+var_2C], 0
0x18000614c  mov     [rbp+var_1F], 0
0x180006150  mov     [rbp+var_1C], 0
0x180006157  xor     eax, eax
0x180006159  mov     [rbp+var_16], ax
0x18000615d  mov     eax, [rcx+8]
0x180006160  mov     [rbp+var_30], eax
0x180006163  mov     rax, [rcx+18h]
0x180006167  mov     [rbp+var_28], rax
0x18000616b  mov     al, [rcx]
0x18000616d  mov     [rbp+var_20], al
0x180006170  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180006177  mov     [rbp+var_1E], ax
0x18000617b  movzx   eax, word ptr [rcx+40h]
0x18000617f  mov     [rbp+var_18], ax
0x180006183  mov     [rbp+var_14], 0
0x18000618a  mov     rax, [rcx+38h]
0x18000618e  mov     [rbp+var_10], rax
0x180006192  mov     rax, [rcx+80h]
0x180006199  mov     [rbp+var_8], rax
0x18000619d  mov     [rbp+arg_0], 0
0x1800061a5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800061ac  test    rdi, rdi
0x1800061af  jnz     short loc_1800061F5
0x1800061b1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800061b8  test    rax, rax
0x1800061bb  jnz     short loc_1800061D6
0x1800061bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800061c4  call    cs:__imp_GetModuleHandleW
0x1800061ca  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800061d1  test    rax, rax
0x1800061d4  jz      short loc_1800061E9
0x1800061d6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x1800061dd  mov     rcx, rax; hModule
0x1800061e0  call    cs:__imp_GetProcAddress
0x1800061e6  mov     rdi, rax
0x1800061e9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800061f0  test    rdi, rdi
0x1800061f3  jz      short loc_180006208
0x1800061f5  lea     r8, [rbp+arg_0]
0x1800061f9  lea     rdx, [rbp+var_30]
0x1800061fd  xor     ecx, ecx
0x1800061ff  mov     rax, rdi
0x180006202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006207  nop
0x180006208  mov     eax, dword ptr [rbp+arg_0]
0x18000620b  mov     [rbx+10h], eax
0x18000620e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180006212  sub     ecx, 1
0x180006215  jz      short loc_18000622D
0x180006217  sub     ecx, 1
0x18000621a  jz      short loc_180006227
0x18000621c  cmp     ecx, 1
0x18000621f  jnz     short loc_180006231
0x180006221  or      dword ptr [rbx+4], 4
0x180006225  jmp     short loc_180006231
0x180006227  or      dword ptr [rbx+4], 2
0x18000622b  jmp     short loc_180006231
0x18000622d  or      dword ptr [rbx+4], 1
0x180006231  mov     rbx, [rsp+50h+arg_8]
0x180006236  mov     rdi, [rsp+50h+arg_10]
0x18000623b  add     rsp, 50h
0x18000623f  pop     rbp
0x180006240  retn
```
