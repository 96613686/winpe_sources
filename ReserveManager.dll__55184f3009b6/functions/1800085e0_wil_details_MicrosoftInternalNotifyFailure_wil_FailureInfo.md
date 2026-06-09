# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1800085e0`
- end: `0x180008716`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `310`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003870`
- `0x1800085e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000868b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000868b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800086a7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800086a7`

## string_xrefs

- `0x180008684`: `kernelbase.dll`

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
0x1800085e0  mov     rax, rsp
0x1800085e3  push    rbp
0x1800085e4  mov     rbp, rsp
0x1800085e7  sub     rsp, 70h
0x1800085eb  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x1800085f3  mov     [rax+10h], rbx
0x1800085f7  mov     [rax+18h], rdi
0x1800085fb  mov     rax, cs:__security_cookie
0x180008602  xor     rax, rsp
0x180008605  mov     [rbp+var_10], rax
0x180008609  mov     rbx, rcx
0x18000860c  mov     [rbp+var_44], 0
0x180008613  mov     [rbp+var_37], 0
0x180008617  mov     [rbp+var_34], 0
0x18000861e  xor     eax, eax
0x180008620  mov     [rbp+var_2E], ax
0x180008624  mov     eax, [rcx+8]
0x180008627  mov     [rbp+var_48], eax
0x18000862a  mov     rax, [rcx+18h]
0x18000862e  mov     [rbp+var_40], rax
0x180008632  mov     al, [rcx]
0x180008634  mov     [rbp+var_38], al
0x180008637  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000863e  mov     [rbp+var_36], ax
0x180008642  movzx   eax, word ptr [rcx+40h]
0x180008646  mov     [rbp+var_30], ax
0x18000864a  mov     [rbp+var_2C], 0
0x180008651  mov     rax, [rcx+38h]
0x180008655  mov     [rbp+var_28], rax
0x180008659  mov     rax, [rcx+80h]
0x180008660  mov     [rbp+var_20], rax
0x180008664  mov     [rbp+var_18], 0
0x18000866c  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x180008673  test    rdi, rdi
0x180008676  jnz     short loc_1800086BC
0x180008678  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000867f  test    rax, rax
0x180008682  jnz     short loc_18000869D
0x180008684  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000868b  call    cs:__imp_GetModuleHandleW
0x180008691  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180008698  test    rax, rax
0x18000869b  jz      short loc_1800086B0
0x18000869d  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800086a4  mov     rcx, rax; hModule
0x1800086a7  call    cs:__imp_GetProcAddress
0x1800086ad  mov     rdi, rax
0x1800086b0  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800086b7  test    rdi, rdi
0x1800086ba  jz      short loc_1800086CF
0x1800086bc  lea     r8, [rbp+var_18]
0x1800086c0  lea     rdx, [rbp+var_48]
0x1800086c4  xor     ecx, ecx
0x1800086c6  mov     rax, rdi
0x1800086c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ce  nop
0x1800086cf  mov     eax, dword ptr [rbp+var_18]
0x1800086d2  mov     [rbx+10h], eax
0x1800086d5  movzx   ecx, byte ptr [rbp+var_18+4]
0x1800086d9  sub     ecx, 1
0x1800086dc  jz      short loc_1800086F4
0x1800086de  sub     ecx, 1
0x1800086e1  jz      short loc_1800086EE
0x1800086e3  cmp     ecx, 1
0x1800086e6  jnz     short loc_1800086F8
0x1800086e8  or      dword ptr [rbx+4], 4
0x1800086ec  jmp     short loc_1800086F8
0x1800086ee  or      dword ptr [rbx+4], 2
0x1800086f2  jmp     short loc_1800086F8
0x1800086f4  or      dword ptr [rbx+4], 1
0x1800086f8  mov     rcx, [rbp+var_10]
0x1800086fc  xor     rcx, rsp; StackCookie
0x1800086ff  call    __security_check_cookie
0x180008704  lea     r11, [rsp+70h+var_s0]
0x180008709  mov     rbx, [r11+18h]
0x18000870d  mov     rdi, [r11+20h]
0x180008711  mov     rsp, r11
0x180008714  pop     rbp
0x180008715  retn
```
