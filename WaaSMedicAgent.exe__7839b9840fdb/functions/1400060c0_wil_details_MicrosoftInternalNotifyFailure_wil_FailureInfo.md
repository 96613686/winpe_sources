# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1400060c0`
- end: `0x1400061dc`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `284`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400060c0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006179`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006179`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000615d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000615d`

## string_xrefs

- `0x140006156`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  _DWORD v5[2]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v6; // [rsp+30h] [rbp-30h]
  char v7; // [rsp+38h] [rbp-28h]
  char v8; // [rsp+39h] [rbp-27h]
  __int16 v9; // [rsp+3Ah] [rbp-26h]
  int v10; // [rsp+3Ch] [rbp-24h]
  __int16 v11; // [rsp+40h] [rbp-20h]
  __int16 v12; // [rsp+42h] [rbp-1Eh]
  int v13; // [rsp+44h] [rbp-1Ch]
  __int64 v14; // [rsp+48h] [rbp-18h]
  __int64 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+70h] [rbp+10h] BYREF

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
0x1400060c0  mov     rax, rsp
0x1400060c3  push    rbp
0x1400060c4  mov     rbp, rsp
0x1400060c7  sub     rsp, 60h
0x1400060cb  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x1400060d3  mov     [rax+10h], rbx
0x1400060d7  mov     [rax+18h], rdi
0x1400060db  mov     rbx, rcx
0x1400060de  mov     [rbp+var_34], 0
0x1400060e5  mov     [rbp+var_27], 0
0x1400060e9  mov     [rbp+var_24], 0
0x1400060f0  xor     eax, eax
0x1400060f2  mov     [rbp+var_1E], ax
0x1400060f6  mov     eax, [rcx+8]
0x1400060f9  mov     [rbp+var_38], eax
0x1400060fc  mov     rax, [rcx+18h]
0x140006100  mov     [rbp+var_30], rax
0x140006104  mov     al, [rcx]
0x140006106  mov     [rbp+var_28], al
0x140006109  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140006110  mov     [rbp+var_26], ax
0x140006114  movzx   eax, word ptr [rcx+40h]
0x140006118  mov     [rbp+var_20], ax
0x14000611c  mov     [rbp+var_1C], 0
0x140006123  mov     rax, [rcx+38h]
0x140006127  mov     [rbp+var_18], rax
0x14000612b  mov     rax, [rcx+80h]
0x140006132  mov     [rbp+var_10], rax
0x140006136  mov     [rbp+arg_0], 0
0x14000613e  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140006145  test    rdi, rdi
0x140006148  jnz     short loc_14000618E
0x14000614a  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140006151  test    rax, rax
0x140006154  jnz     short loc_14000616F
0x140006156  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000615d  call    cs:__imp_GetModuleHandleW
0x140006163  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000616a  test    rax, rax
0x14000616d  jz      short loc_140006182
0x14000616f  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x140006176  mov     rcx, rax; hModule
0x140006179  call    cs:__imp_GetProcAddress
0x14000617f  mov     rdi, rax
0x140006182  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140006189  test    rdi, rdi
0x14000618c  jz      short loc_1400061A1
0x14000618e  lea     r8, [rbp+arg_0]
0x140006192  lea     rdx, [rbp+var_38]
0x140006196  xor     ecx, ecx
0x140006198  mov     rax, rdi
0x14000619b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061a0  nop
0x1400061a1  mov     eax, dword ptr [rbp+arg_0]
0x1400061a4  mov     [rbx+10h], eax
0x1400061a7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1400061ab  sub     ecx, 1
0x1400061ae  jz      short loc_1400061C6
0x1400061b0  sub     ecx, 1
0x1400061b3  jz      short loc_1400061C0
0x1400061b5  cmp     ecx, 1
0x1400061b8  jnz     short loc_1400061CA
0x1400061ba  or      dword ptr [rbx+4], 4
0x1400061be  jmp     short loc_1400061CA
0x1400061c0  or      dword ptr [rbx+4], 2
0x1400061c4  jmp     short loc_1400061CA
0x1400061c6  or      dword ptr [rbx+4], 1
0x1400061ca  lea     r11, [rsp+60h+var_s0]
0x1400061cf  mov     rbx, [r11+18h]
0x1400061d3  mov     rdi, [r11+20h]
0x1400061d7  mov     rsp, r11
0x1400061da  pop     rbp
0x1400061db  retn
```
