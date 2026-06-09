# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140007570`
- end: `0x140007681`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007570`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007604`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007604`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007620`

## string_xrefs

- `0x1400075fd`: `kernelbase.dll`

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
0x140007570  mov     [rsp-8+arg_8], rbx
0x140007575  mov     [rsp-8+arg_10], rdi
0x14000757a  push    rbp
0x14000757b  mov     rbp, rsp
0x14000757e  sub     rsp, 50h
0x140007582  mov     rbx, rcx
0x140007585  mov     [rbp+var_2C], 0
0x14000758c  mov     [rbp+var_1F], 0
0x140007590  mov     [rbp+var_1C], 0
0x140007597  xor     eax, eax
0x140007599  mov     [rbp+var_16], ax
0x14000759d  mov     eax, [rcx+8]
0x1400075a0  mov     [rbp+var_30], eax
0x1400075a3  mov     rax, [rcx+18h]
0x1400075a7  mov     [rbp+var_28], rax
0x1400075ab  mov     al, [rcx]
0x1400075ad  mov     [rbp+var_20], al
0x1400075b0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400075b7  mov     [rbp+var_1E], ax
0x1400075bb  movzx   eax, word ptr [rcx+40h]
0x1400075bf  mov     [rbp+var_18], ax
0x1400075c3  mov     [rbp+var_14], 0
0x1400075ca  mov     rax, [rcx+38h]
0x1400075ce  mov     [rbp+var_10], rax
0x1400075d2  mov     rax, [rcx+80h]
0x1400075d9  mov     [rbp+var_8], rax
0x1400075dd  mov     [rbp+arg_0], 0
0x1400075e5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400075ec  test    rdi, rdi
0x1400075ef  jnz     short loc_140007635
0x1400075f1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400075f8  test    rax, rax
0x1400075fb  jnz     short loc_140007616
0x1400075fd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140007604  call    cs:__imp_GetModuleHandleW
0x14000760a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140007611  test    rax, rax
0x140007614  jz      short loc_140007629
0x140007616  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x14000761d  mov     rcx, rax; hModule
0x140007620  call    cs:__imp_GetProcAddress
0x140007626  mov     rdi, rax
0x140007629  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140007630  test    rdi, rdi
0x140007633  jz      short loc_140007648
0x140007635  lea     r8, [rbp+arg_0]
0x140007639  lea     rdx, [rbp+var_30]
0x14000763d  xor     ecx, ecx
0x14000763f  mov     rax, rdi
0x140007642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007647  nop
0x140007648  mov     eax, dword ptr [rbp+arg_0]
0x14000764b  mov     [rbx+10h], eax
0x14000764e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140007652  sub     ecx, 1
0x140007655  jz      short loc_14000766D
0x140007657  sub     ecx, 1
0x14000765a  jz      short loc_140007667
0x14000765c  cmp     ecx, 1
0x14000765f  jnz     short loc_140007671
0x140007661  or      dword ptr [rbx+4], 4
0x140007665  jmp     short loc_140007671
0x140007667  or      dword ptr [rbx+4], 2
0x14000766b  jmp     short loc_140007671
0x14000766d  or      dword ptr [rbx+4], 1
0x140007671  mov     rbx, [rsp+50h+arg_8]
0x140007676  mov     rdi, [rsp+50h+arg_10]
0x14000767b  add     rsp, 50h
0x14000767f  pop     rbp
0x140007680  retn
```
