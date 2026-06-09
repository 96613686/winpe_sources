# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000a7c0`
- end: `0x18000a8f6`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `310`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a7c0`
- `0x1800119f0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a887`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a887`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a86b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a86b`

## string_xrefs

- `0x18000a864`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v6; // [rsp+30h] [rbp-40h]
  char v7; // [rsp+38h] [rbp-38h]
  char v8; // [rsp+39h] [rbp-37h]
  __int16 v9; // [rsp+3Ah] [rbp-36h]
  int v10; // [rsp+3Ch] [rbp-34h]
  __int16 v11; // [rsp+40h] [rbp-30h]
  __int16 v12; // [rsp+42h] [rbp-2Eh]
  int v13; // [rsp+44h] [rbp-2Ch]
  __int64 v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int64 v16; // [rsp+58h] [rbp-18h] BYREF

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
0x18000a7c0  mov     rax, rsp
0x18000a7c3  push    rbp
0x18000a7c4  mov     rbp, rsp
0x18000a7c7  sub     rsp, 70h
0x18000a7cb  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x18000a7d3  mov     [rax+10h], rbx
0x18000a7d7  mov     [rax+18h], rdi
0x18000a7db  mov     rax, cs:__security_cookie
0x18000a7e2  xor     rax, rsp
0x18000a7e5  mov     [rbp+var_10], rax
0x18000a7e9  mov     rbx, rcx
0x18000a7ec  mov     [rbp+var_44], 0
0x18000a7f3  mov     [rbp+var_37], 0
0x18000a7f7  mov     [rbp+var_34], 0
0x18000a7fe  xor     eax, eax
0x18000a800  mov     [rbp+var_2E], ax
0x18000a804  mov     eax, [rcx+8]
0x18000a807  mov     [rbp+var_48], eax
0x18000a80a  mov     rax, [rcx+18h]
0x18000a80e  mov     [rbp+var_40], rax
0x18000a812  mov     al, [rcx]
0x18000a814  mov     [rbp+var_38], al
0x18000a817  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000a81e  mov     [rbp+var_36], ax
0x18000a822  movzx   eax, word ptr [rcx+40h]
0x18000a826  mov     [rbp+var_30], ax
0x18000a82a  mov     [rbp+var_2C], 0
0x18000a831  mov     rax, [rcx+38h]
0x18000a835  mov     [rbp+var_28], rax
0x18000a839  mov     rax, [rcx+80h]
0x18000a840  mov     [rbp+var_20], rax
0x18000a844  mov     [rbp+var_18], 0
0x18000a84c  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000a853  test    rdi, rdi
0x18000a856  jnz     short loc_18000A89C
0x18000a858  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a85f  test    rax, rax
0x18000a862  jnz     short loc_18000A87D
0x18000a864  lea     rcx, ModuleName; "kernelbase.dll"
0x18000a86b  call    cs:__imp_GetModuleHandleW
0x18000a871  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000a878  test    rax, rax
0x18000a87b  jz      short loc_18000A890
0x18000a87d  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000a884  mov     rcx, rax; hModule
0x18000a887  call    cs:__imp_GetProcAddress
0x18000a88d  mov     rdi, rax
0x18000a890  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000a897  test    rdi, rdi
0x18000a89a  jz      short loc_18000A8AF
0x18000a89c  lea     r8, [rbp+var_18]
0x18000a8a0  lea     rdx, [rbp+var_48]
0x18000a8a4  xor     ecx, ecx
0x18000a8a6  mov     rax, rdi
0x18000a8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ae  nop
0x18000a8af  mov     eax, dword ptr [rbp+var_18]
0x18000a8b2  mov     [rbx+10h], eax
0x18000a8b5  movzx   ecx, byte ptr [rbp+var_18+4]
0x18000a8b9  sub     ecx, 1
0x18000a8bc  jz      short loc_18000A8D4
0x18000a8be  sub     ecx, 1
0x18000a8c1  jz      short loc_18000A8CE
0x18000a8c3  cmp     ecx, 1
0x18000a8c6  jnz     short loc_18000A8D8
0x18000a8c8  or      dword ptr [rbx+4], 4
0x18000a8cc  jmp     short loc_18000A8D8
0x18000a8ce  or      dword ptr [rbx+4], 2
0x18000a8d2  jmp     short loc_18000A8D8
0x18000a8d4  or      dword ptr [rbx+4], 1
0x18000a8d8  mov     rcx, [rbp+var_10]
0x18000a8dc  xor     rcx, rsp; StackCookie
0x18000a8df  call    __security_check_cookie
0x18000a8e4  lea     r11, [rsp+70h+var_s0]
0x18000a8e9  mov     rbx, [r11+18h]
0x18000a8ed  mov     rdi, [r11+20h]
0x18000a8f1  mov     rsp, r11
0x18000a8f4  pop     rbp
0x18000a8f5  retn
```
