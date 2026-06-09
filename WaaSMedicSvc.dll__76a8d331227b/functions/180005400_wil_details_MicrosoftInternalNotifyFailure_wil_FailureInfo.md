# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180005400`
- end: `0x180005511`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005400`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005494`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005494`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054b0`

## string_xrefs

- `0x18000548d`: `kernelbase.dll`

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
0x180005400  mov     [rsp-8+arg_8], rbx
0x180005405  mov     [rsp-8+arg_10], rdi
0x18000540a  push    rbp
0x18000540b  mov     rbp, rsp
0x18000540e  sub     rsp, 50h
0x180005412  mov     rbx, rcx
0x180005415  mov     [rbp+var_2C], 0
0x18000541c  mov     [rbp+var_1F], 0
0x180005420  mov     [rbp+var_1C], 0
0x180005427  xor     eax, eax
0x180005429  mov     [rbp+var_16], ax
0x18000542d  mov     eax, [rcx+8]
0x180005430  mov     [rbp+var_30], eax
0x180005433  mov     rax, [rcx+18h]
0x180005437  mov     [rbp+var_28], rax
0x18000543b  mov     al, [rcx]
0x18000543d  mov     [rbp+var_20], al
0x180005440  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180005447  mov     [rbp+var_1E], ax
0x18000544b  movzx   eax, word ptr [rcx+40h]
0x18000544f  mov     [rbp+var_18], ax
0x180005453  mov     [rbp+var_14], 0
0x18000545a  mov     rax, [rcx+38h]
0x18000545e  mov     [rbp+var_10], rax
0x180005462  mov     rax, [rcx+80h]
0x180005469  mov     [rbp+var_8], rax
0x18000546d  mov     [rbp+arg_0], 0
0x180005475  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000547c  test    rdi, rdi
0x18000547f  jnz     short loc_1800054C5
0x180005481  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180005488  test    rax, rax
0x18000548b  jnz     short loc_1800054A6
0x18000548d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180005494  call    cs:__imp_GetModuleHandleW
0x18000549a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800054a1  test    rax, rax
0x1800054a4  jz      short loc_1800054B9
0x1800054a6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800054ad  mov     rcx, rax; hModule
0x1800054b0  call    cs:__imp_GetProcAddress
0x1800054b6  mov     rdi, rax
0x1800054b9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800054c0  test    rdi, rdi
0x1800054c3  jz      short loc_1800054D8
0x1800054c5  lea     r8, [rbp+arg_0]
0x1800054c9  lea     rdx, [rbp+var_30]
0x1800054cd  xor     ecx, ecx
0x1800054cf  mov     rax, rdi
0x1800054d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d7  nop
0x1800054d8  mov     eax, dword ptr [rbp+arg_0]
0x1800054db  mov     [rbx+10h], eax
0x1800054de  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1800054e2  sub     ecx, 1
0x1800054e5  jz      short loc_1800054FD
0x1800054e7  sub     ecx, 1
0x1800054ea  jz      short loc_1800054F7
0x1800054ec  cmp     ecx, 1
0x1800054ef  jnz     short loc_180005501
0x1800054f1  or      dword ptr [rbx+4], 4
0x1800054f5  jmp     short loc_180005501
0x1800054f7  or      dword ptr [rbx+4], 2
0x1800054fb  jmp     short loc_180005501
0x1800054fd  or      dword ptr [rbx+4], 1
0x180005501  mov     rbx, [rsp+50h+arg_8]
0x180005506  mov     rdi, [rsp+50h+arg_10]
0x18000550b  add     rsp, 50h
0x18000550f  pop     rbp
0x180005510  retn
```
