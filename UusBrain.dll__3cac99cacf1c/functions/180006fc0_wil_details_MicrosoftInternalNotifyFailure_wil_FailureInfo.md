# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180006fc0`
- end: `0x1800070e8`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006fc0`
- `0x1800427d0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007075`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007075`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007059`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007059`

## string_xrefs

- `0x180007052`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  char v7; // [rsp+30h] [rbp-30h]
  char v8; // [rsp+31h] [rbp-2Fh]
  __int16 v9; // [rsp+32h] [rbp-2Eh]
  int v10; // [rsp+34h] [rbp-2Ch]
  __int16 v11; // [rsp+38h] [rbp-28h]
  __int16 v12; // [rsp+3Ah] [rbp-26h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF

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
  ProcAddress = 0;
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
0x180006fc0  mov     [rsp-8+arg_8], rbx
0x180006fc5  mov     [rsp-8+arg_10], rsi
0x180006fca  mov     [rsp-8+arg_18], rdi
0x180006fcf  push    rbp
0x180006fd0  mov     rbp, rsp
0x180006fd3  sub     rsp, 60h
0x180006fd7  mov     rax, cs:__security_cookie
0x180006fde  xor     rax, rsp
0x180006fe1  mov     [rbp+var_8], rax
0x180006fe5  mov     rbx, rcx
0x180006fe8  xor     esi, esi
0x180006fea  mov     [rbp+var_3C], esi
0x180006fed  mov     [rbp+var_2F], sil
0x180006ff1  mov     [rbp+var_2C], esi
0x180006ff4  mov     [rbp+var_26], si
0x180006ff8  mov     eax, [rcx+8]
0x180006ffb  mov     [rbp+var_40], eax
0x180006ffe  mov     rax, [rcx+18h]
0x180007002  mov     [rbp+var_38], rax
0x180007006  mov     al, [rcx]
0x180007008  mov     [rbp+var_30], al
0x18000700b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007012  mov     [rbp+var_2E], ax
0x180007016  movzx   eax, word ptr [rcx+40h]
0x18000701a  mov     [rbp+var_28], ax
0x18000701e  mov     [rbp+var_24], esi
0x180007021  mov     rax, [rcx+38h]
0x180007025  mov     [rbp+var_20], rax
0x180007029  mov     rax, [rcx+80h]
0x180007030  mov     [rbp+var_18], rax
0x180007034  mov     [rbp+var_10], rsi
0x180007038  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000703f  test    rdi, rdi
0x180007042  jnz     short loc_18000708A
0x180007044  mov     edi, esi
0x180007046  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000704d  test    rax, rax
0x180007050  jnz     short loc_18000706B
0x180007052  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007059  call    cs:__imp_GetModuleHandleW
0x18000705f  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007066  test    rax, rax
0x180007069  jz      short loc_18000707E
0x18000706b  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007072  mov     rcx, rax; hModule
0x180007075  call    cs:__imp_GetProcAddress
0x18000707b  mov     rdi, rax
0x18000707e  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007085  test    rdi, rdi
0x180007088  jz      short loc_18000709D
0x18000708a  lea     r8, [rbp+var_10]
0x18000708e  lea     rdx, [rbp+var_40]
0x180007092  xor     ecx, ecx
0x180007094  mov     rax, rdi
0x180007097  call    _guard_dispatch_icall
0x18000709c  nop
0x18000709d  mov     eax, dword ptr [rbp+var_10]
0x1800070a0  mov     [rbx+10h], eax
0x1800070a3  movzx   ecx, byte ptr [rbp+var_10+4]
0x1800070a7  sub     ecx, 1
0x1800070aa  jz      short loc_1800070C2
0x1800070ac  sub     ecx, 1
0x1800070af  jz      short loc_1800070BC
0x1800070b1  cmp     ecx, 1
0x1800070b4  jnz     short loc_1800070C6
0x1800070b6  or      dword ptr [rbx+4], 4
0x1800070ba  jmp     short loc_1800070C6
0x1800070bc  or      dword ptr [rbx+4], 2
0x1800070c0  jmp     short loc_1800070C6
0x1800070c2  or      dword ptr [rbx+4], 1
0x1800070c6  mov     rcx, [rbp+var_8]
0x1800070ca  xor     rcx, rsp; StackCookie
0x1800070cd  call    __security_check_cookie
0x1800070d2  lea     r11, [rsp+60h+var_s0]
0x1800070d7  mov     rbx, [r11+18h]
0x1800070db  mov     rsi, [r11+20h]
0x1800070df  mov     rdi, [r11+28h]
0x1800070e3  mov     rsp, r11
0x1800070e6  pop     rbp
0x1800070e7  retn
```
