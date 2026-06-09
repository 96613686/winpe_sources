# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x1400048f0`
- end: `0x140004a00`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400048f0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400049a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400049a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004984`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004984`

## string_xrefs

- `0x14000497d`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::MicrosoftInternalNotifyFailure(wil::details *this, struct wil::FailureInfo *a2)
{
  FARPROC ProcAddress; // rdi
  HMODULE ModuleHandleW; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD v8[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  char v10; // [rsp+30h] [rbp-20h]
  char v11; // [rsp+31h] [rbp-1Fh]
  __int16 v12; // [rsp+32h] [rbp-1Eh]
  int v13; // [rsp+34h] [rbp-1Ch]
  __int16 v14; // [rsp+38h] [rbp-18h]
  __int16 v15; // [rsp+3Ah] [rbp-16h]
  int v16; // [rsp+3Ch] [rbp-14h]
  __int64 v17; // [rsp+40h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp-8h]
  __int64 v19; // [rsp+60h] [rbp+10h] BYREF

  ProcAddress = (FARPROC)`wil::details::WilFailureNotifyWatchers'::`2'::s_pfnFailureNotifyWatchers;
  v15 = 0;
  v8[0] = *((_DWORD *)this + 2);
  v9 = *((_QWORD *)this + 3);
  v10 = *(_BYTE *)this;
  v12 = wil::g_moduleFailureReportFlags;
  v14 = *((_WORD *)this + 32);
  v17 = *((_QWORD *)this + 7);
  v18 = *((_QWORD *)this + 16);
  v8[1] = 0;
  v11 = 0;
  v13 = 0;
  v16 = 0;
  v19 = 0;
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
    ((void (__fastcall *)(_QWORD, _DWORD *, __int64 *))ProcAddress)(0, v8, &v19);
  v5 = BYTE4(v19);
  *((_DWORD *)this + 4) = v19;
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
        *((_DWORD *)this + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)this + 1) |= 2u;
    }
  }
  else
  {
    *((_DWORD *)this + 1) |= 1u;
  }
}

```

## disassembly

```asm
0x1400048f0  mov     [rsp-8+arg_8], rbx
0x1400048f5  mov     [rsp-8+arg_10], rdi
0x1400048fa  push    rbp
0x1400048fb  mov     rbp, rsp
0x1400048fe  sub     rsp, 50h
0x140004902  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140004909  xor     eax, eax
0x14000490b  mov     [rbp+var_16], ax
0x14000490f  mov     rbx, rcx
0x140004912  mov     eax, [rcx+8]
0x140004915  mov     [rbp+var_30], eax
0x140004918  mov     rax, [rcx+18h]
0x14000491c  mov     [rbp+var_28], rax
0x140004920  mov     al, [rcx]
0x140004922  mov     [rbp+var_20], al
0x140004925  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x14000492c  mov     [rbp+var_1E], ax
0x140004930  movzx   eax, word ptr [rcx+40h]
0x140004934  mov     [rbp+var_18], ax
0x140004938  mov     rax, [rcx+38h]
0x14000493c  mov     [rbp+var_10], rax
0x140004940  mov     rax, [rcx+80h]
0x140004947  mov     [rbp+var_8], rax
0x14000494b  mov     [rbp+var_2C], 0
0x140004952  mov     [rbp+var_1F], 0
0x140004956  mov     [rbp+var_1C], 0
0x14000495d  mov     [rbp+var_14], 0
0x140004964  mov     [rbp+arg_0], 0
0x14000496c  test    rdi, rdi
0x14000496f  jnz     short loc_1400049B5
0x140004971  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004978  test    rax, rax
0x14000497b  jnz     short loc_140004996
0x14000497d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140004984  call    cs:__imp_GetModuleHandleW
0x14000498a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004991  test    rax, rax
0x140004994  jz      short loc_1400049A9
0x140004996  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000499d  mov     rcx, rax; hModule
0x1400049a0  call    cs:__imp_GetProcAddress
0x1400049a6  mov     rdi, rax
0x1400049a9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1400049b0  test    rdi, rdi
0x1400049b3  jz      short loc_1400049C7
0x1400049b5  lea     r8, [rbp+arg_0]
0x1400049b9  xor     ecx, ecx
0x1400049bb  lea     rdx, [rbp+var_30]
0x1400049bf  mov     rax, rdi
0x1400049c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049c7  movzx   ecx, byte ptr [rbp+arg_0+4]
0x1400049cb  mov     eax, dword ptr [rbp+arg_0]
0x1400049ce  mov     [rbx+10h], eax
0x1400049d1  sub     ecx, 1
0x1400049d4  jz      short loc_1400049EC
0x1400049d6  sub     ecx, 1
0x1400049d9  jz      short loc_1400049E6
0x1400049db  cmp     ecx, 1
0x1400049de  jnz     short loc_1400049F0
0x1400049e0  or      dword ptr [rbx+4], 4
0x1400049e4  jmp     short loc_1400049F0
0x1400049e6  or      dword ptr [rbx+4], 2
0x1400049ea  jmp     short loc_1400049F0
0x1400049ec  or      dword ptr [rbx+4], 1
0x1400049f0  mov     rbx, [rsp+50h+arg_8]
0x1400049f5  mov     rdi, [rsp+50h+arg_10]
0x1400049fa  add     rsp, 50h
0x1400049fe  pop     rbp
0x1400049ff  retn
```
