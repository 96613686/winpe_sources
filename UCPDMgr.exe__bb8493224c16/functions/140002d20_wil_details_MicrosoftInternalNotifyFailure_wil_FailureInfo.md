# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140002d20`
- end: `0x140002e48`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002d20`
- `0x14000a390`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002dd5`
- `KERNEL32!GetProcAddress` at `0x140002dd5`
- `KERNEL32!GetModuleHandleW` at `0x140002db9`
- `KERNEL32!GetModuleHandleW` at `0x140002db9`

## string_xrefs

- `0x140002db2`: `kernelbase.dll`

## pseudocode

```c
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
0x140002d20  mov     [rsp-8+arg_8], rbx
0x140002d25  mov     [rsp-8+arg_10], rsi
0x140002d2a  mov     [rsp-8+arg_18], rdi
0x140002d2f  push    rbp
0x140002d30  mov     rbp, rsp
0x140002d33  sub     rsp, 60h
0x140002d37  mov     rax, cs:__security_cookie
0x140002d3e  xor     rax, rsp
0x140002d41  mov     [rbp+var_8], rax
0x140002d45  mov     rbx, rcx
0x140002d48  xor     esi, esi
0x140002d4a  mov     [rbp+var_3C], esi
0x140002d4d  mov     [rbp+var_2F], sil
0x140002d51  mov     [rbp+var_2C], esi
0x140002d54  mov     [rbp+var_26], si
0x140002d58  mov     eax, [rcx+8]
0x140002d5b  mov     [rbp+var_40], eax
0x140002d5e  mov     rax, [rcx+18h]
0x140002d62  mov     [rbp+var_38], rax
0x140002d66  mov     al, [rcx]
0x140002d68  mov     [rbp+var_30], al
0x140002d6b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140002d72  mov     [rbp+var_2E], ax
0x140002d76  movzx   eax, word ptr [rcx+40h]
0x140002d7a  mov     [rbp+var_28], ax
0x140002d7e  mov     [rbp+var_24], esi
0x140002d81  mov     rax, [rcx+38h]
0x140002d85  mov     [rbp+var_20], rax
0x140002d89  mov     rax, [rcx+80h]
0x140002d90  mov     [rbp+var_18], rax
0x140002d94  mov     [rbp+var_10], rsi
0x140002d98  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140002d9f  test    rdi, rdi
0x140002da2  jnz     short loc_140002DEA
0x140002da4  mov     edi, esi
0x140002da6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140002dad  test    rax, rax
0x140002db0  jnz     short loc_140002DCB
0x140002db2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140002db9  call    cs:__imp_GetModuleHandleW
0x140002dbf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140002dc6  test    rax, rax
0x140002dc9  jz      short loc_140002DDE
0x140002dcb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140002dd2  mov     rcx, rax; hModule
0x140002dd5  call    cs:__imp_GetProcAddress
0x140002ddb  mov     rdi, rax
0x140002dde  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140002de5  test    rdi, rdi
0x140002de8  jz      short loc_140002DFD
0x140002dea  lea     r8, [rbp+var_10]
0x140002dee  lea     rdx, [rbp+var_40]
0x140002df2  xor     ecx, ecx
0x140002df4  mov     rax, rdi
0x140002df7  call    _guard_dispatch_icall
0x140002dfc  nop
0x140002dfd  mov     eax, dword ptr [rbp+var_10]
0x140002e00  mov     [rbx+10h], eax
0x140002e03  movzx   ecx, byte ptr [rbp+var_10+4]
0x140002e07  sub     ecx, 1
0x140002e0a  jz      short loc_140002E22
0x140002e0c  sub     ecx, 1
0x140002e0f  jz      short loc_140002E1C
0x140002e11  cmp     ecx, 1
0x140002e14  jnz     short loc_140002E26
0x140002e16  or      dword ptr [rbx+4], 4
0x140002e1a  jmp     short loc_140002E26
0x140002e1c  or      dword ptr [rbx+4], 2
0x140002e20  jmp     short loc_140002E26
0x140002e22  or      dword ptr [rbx+4], 1
0x140002e26  mov     rcx, [rbp+var_8]
0x140002e2a  xor     rcx, rsp; StackCookie
0x140002e2d  call    __security_check_cookie
0x140002e32  lea     r11, [rsp+60h+var_s0]
0x140002e37  mov     rbx, [r11+18h]
0x140002e3b  mov     rsi, [r11+20h]
0x140002e3f  mov     rdi, [r11+28h]
0x140002e43  mov     rsp, r11
0x140002e46  pop     rbp
0x140002e47  retn
```
