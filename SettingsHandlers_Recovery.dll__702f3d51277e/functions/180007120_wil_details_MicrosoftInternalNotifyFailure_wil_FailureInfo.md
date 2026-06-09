# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180007120`
- end: `0x180007231`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007120`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071b4`

## string_xrefs

- `0x1800071ad`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007120  mov     [rsp-8+arg_8], rbx
0x180007125  mov     [rsp-8+arg_10], rdi
0x18000712a  push    rbp
0x18000712b  mov     rbp, rsp
0x18000712e  sub     rsp, 50h
0x180007132  mov     rbx, rcx
0x180007135  mov     [rbp+var_2C], 0
0x18000713c  mov     [rbp+var_1F], 0
0x180007140  mov     [rbp+var_1C], 0
0x180007147  xor     eax, eax
0x180007149  mov     [rbp+var_16], ax
0x18000714d  mov     eax, [rcx+8]
0x180007150  mov     [rbp+var_30], eax
0x180007153  mov     rax, [rcx+18h]
0x180007157  mov     [rbp+var_28], rax
0x18000715b  mov     al, [rcx]
0x18000715d  mov     [rbp+var_20], al
0x180007160  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180007167  mov     [rbp+var_1E], ax
0x18000716b  movzx   eax, word ptr [rcx+40h]
0x18000716f  mov     [rbp+var_18], ax
0x180007173  mov     [rbp+var_14], 0
0x18000717a  mov     rax, [rcx+38h]
0x18000717e  mov     [rbp+var_10], rax
0x180007182  mov     rax, [rcx+80h]
0x180007189  mov     [rbp+var_8], rax
0x18000718d  mov     [rbp+arg_0], 0
0x180007195  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000719c  test    rdi, rdi
0x18000719f  jnz     short loc_1800071E5
0x1800071a1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800071a8  test    rax, rax
0x1800071ab  jnz     short loc_1800071C6
0x1800071ad  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800071b4  call    cs:__imp_GetModuleHandleW
0x1800071ba  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800071c1  test    rax, rax
0x1800071c4  jz      short loc_1800071D9
0x1800071c6  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800071cd  mov     rcx, rax; hModule
0x1800071d0  call    cs:__imp_GetProcAddress
0x1800071d6  mov     rdi, rax
0x1800071d9  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800071e0  test    rdi, rdi
0x1800071e3  jz      short loc_1800071F8
0x1800071e5  lea     r8, [rbp+arg_0]
0x1800071e9  lea     rdx, [rbp+var_30]
0x1800071ed  xor     ecx, ecx
0x1800071ef  mov     rax, rdi
0x1800071f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071f7  nop
0x1800071f8  mov     eax, dword ptr [rbp+arg_0]
0x1800071fb  mov     [rbx+10h], eax
0x1800071fe  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180007202  sub     ecx, 1
0x180007205  jz      short loc_18000721D
0x180007207  sub     ecx, 1
0x18000720a  jz      short loc_180007217
0x18000720c  cmp     ecx, 1
0x18000720f  jnz     short loc_180007221
0x180007211  or      dword ptr [rbx+4], 4
0x180007215  jmp     short loc_180007221
0x180007217  or      dword ptr [rbx+4], 2
0x18000721b  jmp     short loc_180007221
0x18000721d  or      dword ptr [rbx+4], 1
0x180007221  mov     rbx, [rsp+50h+arg_8]
0x180007226  mov     rdi, [rsp+50h+arg_10]
0x18000722b  add     rsp, 50h
0x18000722f  pop     rbp
0x180007230  retn
```
