# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1400043f0`
- end: `0x140004501`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400043f0`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004484`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004484`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400044a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400044a0`

## string_xrefs

- `0x14000447d`: `kernelbase.dll`

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
0x1400043f0  mov     [rsp-8+arg_8], rbx
0x1400043f5  mov     [rsp-8+arg_10], rdi
0x1400043fa  push    rbp
0x1400043fb  mov     rbp, rsp
0x1400043fe  sub     rsp, 50h
0x140004402  mov     rbx, rcx
0x140004405  mov     [rbp+var_2C], 0
0x14000440c  mov     [rbp+var_1F], 0
0x140004410  mov     [rbp+var_1C], 0
0x140004417  xor     eax, eax
0x140004419  mov     [rbp+var_16], ax
0x14000441d  mov     eax, [rcx+8]
0x140004420  mov     [rbp+var_30], eax
0x140004423  mov     rax, [rcx+18h]
0x140004427  mov     [rbp+var_28], rax
0x14000442b  mov     al, [rcx]
0x14000442d  mov     [rbp+var_20], al
0x140004430  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140004437  mov     [rbp+var_1E], ax
0x14000443b  movzx   eax, word ptr [rcx+40h]
0x14000443f  mov     [rbp+var_18], ax
0x140004443  mov     [rbp+var_14], 0
0x14000444a  mov     rax, [rcx+38h]
0x14000444e  mov     [rbp+var_10], rax
0x140004452  mov     rax, [rcx+80h]
0x140004459  mov     [rbp+var_8], rax
0x14000445d  mov     [rbp+arg_0], 0
0x140004465  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x14000446c  test    rdi, rdi
0x14000446f  jnz     short loc_1400044B5
0x140004471  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004478  test    rax, rax
0x14000447b  jnz     short loc_140004496
0x14000447d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140004484  call    cs:__imp_GetModuleHandleW
0x14000448a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004491  test    rax, rax
0x140004494  jz      short loc_1400044A9
0x140004496  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000449d  mov     rcx, rax; hModule
0x1400044a0  call    cs:__imp_GetProcAddress
0x1400044a6  mov     rdi, rax
0x1400044a9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400044b0  test    rdi, rdi
0x1400044b3  jz      short loc_1400044C8
0x1400044b5  lea     r8, [rbp+arg_0]
0x1400044b9  lea     rdx, [rbp+var_30]
0x1400044bd  xor     ecx, ecx
0x1400044bf  mov     rax, rdi
0x1400044c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044c7  nop
0x1400044c8  mov     eax, dword ptr [rbp+arg_0]
0x1400044cb  mov     [rbx+10h], eax
0x1400044ce  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1400044d2  sub     ecx, 1
0x1400044d5  jz      short loc_1400044ED
0x1400044d7  sub     ecx, 1
0x1400044da  jz      short loc_1400044E7
0x1400044dc  cmp     ecx, 1
0x1400044df  jnz     short loc_1400044F1
0x1400044e1  or      dword ptr [rbx+4], 4
0x1400044e5  jmp     short loc_1400044F1
0x1400044e7  or      dword ptr [rbx+4], 2
0x1400044eb  jmp     short loc_1400044F1
0x1400044ed  or      dword ptr [rbx+4], 1
0x1400044f1  mov     rbx, [rsp+50h+arg_8]
0x1400044f6  mov     rdi, [rsp+50h+arg_10]
0x1400044fb  add     rsp, 50h
0x1400044ff  pop     rbp
0x140004500  retn
```
