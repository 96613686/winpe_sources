# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007a20`
- end: `0x180007b48`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `296`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a20`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007ab9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ad5`

## string_xrefs

- `0x180007ab2`: `kernelbase.dll`

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
0x180007a20  mov     [rsp-8+arg_8], rbx
0x180007a25  mov     [rsp-8+arg_10], rsi
0x180007a2a  mov     [rsp-8+arg_18], rdi
0x180007a2f  push    rbp
0x180007a30  mov     rbp, rsp
0x180007a33  sub     rsp, 60h
0x180007a37  mov     rax, cs:__security_cookie
0x180007a3e  xor     rax, rsp
0x180007a41  mov     [rbp+var_8], rax
0x180007a45  mov     rbx, rcx
0x180007a48  xor     esi, esi
0x180007a4a  mov     [rbp+var_3C], esi
0x180007a4d  mov     [rbp+var_2F], sil
0x180007a51  mov     [rbp+var_2C], esi
0x180007a54  mov     [rbp+var_26], si
0x180007a58  mov     eax, [rcx+8]
0x180007a5b  mov     [rbp+var_40], eax
0x180007a5e  mov     rax, [rcx+18h]
0x180007a62  mov     [rbp+var_38], rax
0x180007a66  mov     al, [rcx]
0x180007a68  mov     [rbp+var_30], al
0x180007a6b  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007a72  mov     [rbp+var_2E], ax
0x180007a76  movzx   eax, word ptr [rcx+40h]
0x180007a7a  mov     [rbp+var_28], ax
0x180007a7e  mov     [rbp+var_24], esi
0x180007a81  mov     rax, [rcx+38h]
0x180007a85  mov     [rbp+var_20], rax
0x180007a89  mov     rax, [rcx+80h]
0x180007a90  mov     [rbp+var_18], rax
0x180007a94  mov     [rbp+var_10], rsi
0x180007a98  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180007a9f  test    rdi, rdi
0x180007aa2  jnz     short loc_180007AEA
0x180007aa4  mov     edi, esi
0x180007aa6  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007aad  test    rax, rax
0x180007ab0  jnz     short loc_180007ACB
0x180007ab2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180007ab9  call    cs:__imp_GetModuleHandleW
0x180007abf  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180007ac6  test    rax, rax
0x180007ac9  jz      short loc_180007ADE
0x180007acb  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x180007ad2  mov     rcx, rax; hModule
0x180007ad5  call    cs:__imp_GetProcAddress
0x180007adb  mov     rdi, rax
0x180007ade  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180007ae5  test    rdi, rdi
0x180007ae8  jz      short loc_180007AFD
0x180007aea  lea     r8, [rbp+var_10]
0x180007aee  lea     rdx, [rbp+var_40]
0x180007af2  xor     ecx, ecx
0x180007af4  mov     rax, rdi
0x180007af7  call    _guard_dispatch_icall
0x180007afc  nop
0x180007afd  mov     eax, dword ptr [rbp+var_10]
0x180007b00  mov     [rbx+10h], eax
0x180007b03  movzx   ecx, byte ptr [rbp+var_10+4]
0x180007b07  sub     ecx, 1
0x180007b0a  jz      short loc_180007B22
0x180007b0c  sub     ecx, 1
0x180007b0f  jz      short loc_180007B1C
0x180007b11  cmp     ecx, 1
0x180007b14  jnz     short loc_180007B26
0x180007b16  or      dword ptr [rbx+4], 4
0x180007b1a  jmp     short loc_180007B26
0x180007b1c  or      dword ptr [rbx+4], 2
0x180007b20  jmp     short loc_180007B26
0x180007b22  or      dword ptr [rbx+4], 1
0x180007b26  mov     rcx, [rbp+var_8]
0x180007b2a  xor     rcx, rsp; StackCookie
0x180007b2d  call    __security_check_cookie
0x180007b32  lea     r11, [rsp+60h+var_s0]
0x180007b37  mov     rbx, [r11+18h]
0x180007b3b  mov     rsi, [r11+20h]
0x180007b3f  mov     rdi, [r11+28h]
0x180007b43  mov     rsp, r11
0x180007b46  pop     rbp
0x180007b47  retn
```
