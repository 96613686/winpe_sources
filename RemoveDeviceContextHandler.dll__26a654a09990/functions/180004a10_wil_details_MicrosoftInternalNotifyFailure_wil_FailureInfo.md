# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180004a10`
- end: `0x180004b20`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004a10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ac0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ac0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004aa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004aa4`

## string_xrefs

- `0x180004a9d`: `kernelbase.dll`

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
0x180004a10  mov     [rsp-8+arg_8], rbx
0x180004a15  mov     [rsp-8+arg_10], rdi
0x180004a1a  push    rbp
0x180004a1b  mov     rbp, rsp
0x180004a1e  sub     rsp, 50h
0x180004a22  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180004a29  xor     eax, eax
0x180004a2b  mov     [rbp+var_16], ax
0x180004a2f  mov     rbx, rcx
0x180004a32  mov     eax, [rcx+8]
0x180004a35  mov     [rbp+var_30], eax
0x180004a38  mov     rax, [rcx+18h]
0x180004a3c  mov     [rbp+var_28], rax
0x180004a40  mov     al, [rcx]
0x180004a42  mov     [rbp+var_20], al
0x180004a45  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180004a4c  mov     [rbp+var_1E], ax
0x180004a50  movzx   eax, word ptr [rcx+40h]
0x180004a54  mov     [rbp+var_18], ax
0x180004a58  mov     rax, [rcx+38h]
0x180004a5c  mov     [rbp+var_10], rax
0x180004a60  mov     rax, [rcx+80h]
0x180004a67  mov     [rbp+var_8], rax
0x180004a6b  mov     [rbp+var_2C], 0
0x180004a72  mov     [rbp+var_1F], 0
0x180004a76  mov     [rbp+var_1C], 0
0x180004a7d  mov     [rbp+var_14], 0
0x180004a84  mov     [rbp+arg_0], 0
0x180004a8c  test    rdi, rdi
0x180004a8f  jnz     short loc_180004AD5
0x180004a91  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004a98  test    rax, rax
0x180004a9b  jnz     short loc_180004AB6
0x180004a9d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180004aa4  call    cs:__imp_GetModuleHandleW
0x180004aaa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180004ab1  test    rax, rax
0x180004ab4  jz      short loc_180004AC9
0x180004ab6  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x180004abd  mov     rcx, rax; hModule
0x180004ac0  call    cs:__imp_GetProcAddress
0x180004ac6  mov     rdi, rax
0x180004ac9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180004ad0  test    rdi, rdi
0x180004ad3  jz      short loc_180004AE7
0x180004ad5  lea     r8, [rbp+arg_0]
0x180004ad9  xor     ecx, ecx
0x180004adb  lea     rdx, [rbp+var_30]
0x180004adf  mov     rax, rdi
0x180004ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180004aeb  mov     eax, dword ptr [rbp+arg_0]
0x180004aee  mov     [rbx+10h], eax
0x180004af1  sub     ecx, 1
0x180004af4  jz      short loc_180004B0C
0x180004af6  sub     ecx, 1
0x180004af9  jz      short loc_180004B06
0x180004afb  cmp     ecx, 1
0x180004afe  jnz     short loc_180004B10
0x180004b00  or      dword ptr [rbx+4], 4
0x180004b04  jmp     short loc_180004B10
0x180004b06  or      dword ptr [rbx+4], 2
0x180004b0a  jmp     short loc_180004B10
0x180004b0c  or      dword ptr [rbx+4], 1
0x180004b10  mov     rbx, [rsp+50h+arg_8]
0x180004b15  mov     rdi, [rsp+50h+arg_10]
0x180004b1a  add     rsp, 50h
0x180004b1e  pop     rbp
0x180004b1f  retn
```
