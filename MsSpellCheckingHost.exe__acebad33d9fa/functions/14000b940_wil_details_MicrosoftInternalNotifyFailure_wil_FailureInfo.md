# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x14000b940`
- end: `0x14000ba51`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b940`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b9d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b9d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b9f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b9f0`

## string_xrefs

- `0x14000b9cd`: `kernelbase.dll`

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
0x14000b940  mov     [rsp-8+arg_8], rbx
0x14000b945  mov     [rsp-8+arg_10], rdi
0x14000b94a  push    rbp
0x14000b94b  mov     rbp, rsp
0x14000b94e  sub     rsp, 50h
0x14000b952  mov     rbx, rcx
0x14000b955  mov     [rbp+var_2C], 0
0x14000b95c  mov     [rbp+var_1F], 0
0x14000b960  mov     [rbp+var_1C], 0
0x14000b967  xor     eax, eax
0x14000b969  mov     [rbp+var_16], ax
0x14000b96d  mov     eax, [rcx+8]
0x14000b970  mov     [rbp+var_30], eax
0x14000b973  mov     rax, [rcx+18h]
0x14000b977  mov     [rbp+var_28], rax
0x14000b97b  mov     al, [rcx]
0x14000b97d  mov     [rbp+var_20], al
0x14000b980  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000b987  mov     [rbp+var_1E], ax
0x14000b98b  movzx   eax, word ptr [rcx+40h]
0x14000b98f  mov     [rbp+var_18], ax
0x14000b993  mov     [rbp+var_14], 0
0x14000b99a  mov     rax, [rcx+38h]
0x14000b99e  mov     [rbp+var_10], rax
0x14000b9a2  mov     rax, [rcx+80h]
0x14000b9a9  mov     [rbp+var_8], rax
0x14000b9ad  mov     [rbp+arg_0], 0
0x14000b9b5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000b9bc  test    rdi, rdi
0x14000b9bf  jnz     short loc_14000BA05
0x14000b9c1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000b9c8  test    rax, rax
0x14000b9cb  jnz     short loc_14000B9E6
0x14000b9cd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x14000b9d4  call    cs:__imp_GetModuleHandleW
0x14000b9da  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x14000b9e1  test    rax, rax
0x14000b9e4  jz      short loc_14000B9F9
0x14000b9e6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000b9ed  mov     rcx, rax; hModule
0x14000b9f0  call    cs:__imp_GetProcAddress
0x14000b9f6  mov     rdi, rax
0x14000b9f9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x14000ba00  test    rdi, rdi
0x14000ba03  jz      short loc_14000BA18
0x14000ba05  lea     r8, [rbp+arg_0]
0x14000ba09  lea     rdx, [rbp+var_30]
0x14000ba0d  xor     ecx, ecx
0x14000ba0f  mov     rax, rdi
0x14000ba12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba17  nop
0x14000ba18  mov     eax, dword ptr [rbp+arg_0]
0x14000ba1b  mov     [rbx+10h], eax
0x14000ba1e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x14000ba22  sub     ecx, 1
0x14000ba25  jz      short loc_14000BA3D
0x14000ba27  sub     ecx, 1
0x14000ba2a  jz      short loc_14000BA37
0x14000ba2c  cmp     ecx, 1
0x14000ba2f  jnz     short loc_14000BA41
0x14000ba31  or      dword ptr [rbx+4], 4
0x14000ba35  jmp     short loc_14000BA41
0x14000ba37  or      dword ptr [rbx+4], 2
0x14000ba3b  jmp     short loc_14000BA41
0x14000ba3d  or      dword ptr [rbx+4], 1
0x14000ba41  mov     rbx, [rsp+50h+arg_8]
0x14000ba46  mov     rdi, [rsp+50h+arg_10]
0x14000ba4b  add     rsp, 50h
0x14000ba4f  pop     rbp
0x14000ba50  retn
```
