# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180003000`
- end: `0x180003111`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003000`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003094`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003094`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030b0`

## string_xrefs

- `0x18000308d`: `kernelbase.dll`

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
0x180003000  mov     [rsp-8+arg_8], rbx
0x180003005  mov     [rsp-8+arg_10], rdi
0x18000300a  push    rbp
0x18000300b  mov     rbp, rsp
0x18000300e  sub     rsp, 50h
0x180003012  mov     rbx, rcx
0x180003015  mov     [rbp+var_2C], 0
0x18000301c  mov     [rbp+var_1F], 0
0x180003020  mov     [rbp+var_1C], 0
0x180003027  xor     eax, eax
0x180003029  mov     [rbp+var_16], ax
0x18000302d  mov     eax, [rcx+8]
0x180003030  mov     [rbp+var_30], eax
0x180003033  mov     rax, [rcx+18h]
0x180003037  mov     [rbp+var_28], rax
0x18000303b  mov     al, [rcx]
0x18000303d  mov     [rbp+var_20], al
0x180003040  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180003047  mov     [rbp+var_1E], ax
0x18000304b  movzx   eax, word ptr [rcx+40h]
0x18000304f  mov     [rbp+var_18], ax
0x180003053  mov     [rbp+var_14], 0
0x18000305a  mov     rax, [rcx+38h]
0x18000305e  mov     [rbp+var_10], rax
0x180003062  mov     rax, [rcx+80h]
0x180003069  mov     [rbp+var_8], rax
0x18000306d  mov     [rbp+arg_0], 0
0x180003075  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000307c  test    rdi, rdi
0x18000307f  jnz     short loc_1800030C5
0x180003081  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180003088  test    rax, rax
0x18000308b  jnz     short loc_1800030A6
0x18000308d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180003094  call    cs:__imp_GetModuleHandleW
0x18000309a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800030a1  test    rax, rax
0x1800030a4  jz      short loc_1800030B9
0x1800030a6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800030ad  mov     rcx, rax; hModule
0x1800030b0  call    cs:__imp_GetProcAddress
0x1800030b6  mov     rdi, rax
0x1800030b9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800030c0  test    rdi, rdi
0x1800030c3  jz      short loc_1800030D8
0x1800030c5  lea     r8, [rbp+arg_0]
0x1800030c9  lea     rdx, [rbp+var_30]
0x1800030cd  xor     ecx, ecx
0x1800030cf  mov     rax, rdi
0x1800030d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d7  nop
0x1800030d8  mov     eax, dword ptr [rbp+arg_0]
0x1800030db  mov     [rbx+10h], eax
0x1800030de  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800030e2  sub     ecx, 1
0x1800030e5  jz      short loc_1800030FD
0x1800030e7  sub     ecx, 1
0x1800030ea  jz      short loc_1800030F7
0x1800030ec  cmp     ecx, 1
0x1800030ef  jnz     short loc_180003101
0x1800030f1  or      dword ptr [rbx+4], 4
0x1800030f5  jmp     short loc_180003101
0x1800030f7  or      dword ptr [rbx+4], 2
0x1800030fb  jmp     short loc_180003101
0x1800030fd  or      dword ptr [rbx+4], 1
0x180003101  mov     rbx, [rsp+50h+arg_8]
0x180003106  mov     rdi, [rsp+50h+arg_10]
0x18000310b  add     rsp, 50h
0x18000310f  pop     rbp
0x180003110  retn
```
