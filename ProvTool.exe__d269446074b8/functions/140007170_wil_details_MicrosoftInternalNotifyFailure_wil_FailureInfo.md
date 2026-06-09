# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140007170`
- end: `0x140007281`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007170`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007204`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007204`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007220`

## string_xrefs

- `0x1400071fd`: `kernelbase.dll`

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
0x140007170  mov     [rsp-8+arg_8], rbx
0x140007175  mov     [rsp-8+arg_10], rdi
0x14000717a  push    rbp
0x14000717b  mov     rbp, rsp
0x14000717e  sub     rsp, 50h
0x140007182  mov     rbx, rcx
0x140007185  mov     [rbp+var_2C], 0
0x14000718c  mov     [rbp+var_1F], 0
0x140007190  mov     [rbp+var_1C], 0
0x140007197  xor     eax, eax
0x140007199  mov     [rbp+var_16], ax
0x14000719d  mov     eax, [rcx+8]
0x1400071a0  mov     [rbp+var_30], eax
0x1400071a3  mov     rax, [rcx+18h]
0x1400071a7  mov     [rbp+var_28], rax
0x1400071ab  mov     al, [rcx]
0x1400071ad  mov     [rbp+var_20], al
0x1400071b0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400071b7  mov     [rbp+var_1E], ax
0x1400071bb  movzx   eax, word ptr [rcx+40h]
0x1400071bf  mov     [rbp+var_18], ax
0x1400071c3  mov     [rbp+var_14], 0
0x1400071ca  mov     rax, [rcx+38h]
0x1400071ce  mov     [rbp+var_10], rax
0x1400071d2  mov     rax, [rcx+80h]
0x1400071d9  mov     [rbp+var_8], rax
0x1400071dd  mov     [rbp+arg_0], 0
0x1400071e5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400071ec  test    rdi, rdi
0x1400071ef  jnz     short loc_140007235
0x1400071f1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400071f8  test    rax, rax
0x1400071fb  jnz     short loc_140007216
0x1400071fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140007204  call    cs:__imp_GetModuleHandleW
0x14000720a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007211  test    rax, rax
0x140007214  jz      short loc_140007229
0x140007216  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000721d  mov     rcx, rax; hModule
0x140007220  call    cs:__imp_GetProcAddress
0x140007226  mov     rdi, rax
0x140007229  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140007230  test    rdi, rdi
0x140007233  jz      short loc_140007248
0x140007235  lea     r8, [rbp+arg_0]
0x140007239  lea     rdx, [rbp+var_30]
0x14000723d  xor     ecx, ecx
0x14000723f  mov     rax, rdi
0x140007242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007247  nop
0x140007248  mov     eax, dword ptr [rbp+arg_0]
0x14000724b  mov     [rbx+10h], eax
0x14000724e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140007252  sub     ecx, 1
0x140007255  jz      short loc_14000726D
0x140007257  sub     ecx, 1
0x14000725a  jz      short loc_140007267
0x14000725c  cmp     ecx, 1
0x14000725f  jnz     short loc_140007271
0x140007261  or      dword ptr [rbx+4], 4
0x140007265  jmp     short loc_140007271
0x140007267  or      dword ptr [rbx+4], 2
0x14000726b  jmp     short loc_140007271
0x14000726d  or      dword ptr [rbx+4], 1
0x140007271  mov     rbx, [rsp+50h+arg_8]
0x140007276  mov     rdi, [rsp+50h+arg_10]
0x14000727b  add     rsp, 50h
0x14000727f  pop     rbp
0x140007280  retn
```
