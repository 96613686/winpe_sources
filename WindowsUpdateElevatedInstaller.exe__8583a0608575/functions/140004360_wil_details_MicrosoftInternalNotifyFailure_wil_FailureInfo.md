# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140004360`
- end: `0x140004471`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004360`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140004410`
- `KERNEL32!GetProcAddress` at `0x140004410`
- `KERNEL32!GetModuleHandleW` at `0x1400043f4`
- `KERNEL32!GetModuleHandleW` at `0x1400043f4`

## string_xrefs

- `0x1400043ed`: `kernelbase.dll`

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
0x140004360  mov     [rsp-8+arg_8], rbx
0x140004365  mov     [rsp-8+arg_10], rdi
0x14000436a  push    rbp
0x14000436b  mov     rbp, rsp
0x14000436e  sub     rsp, 50h
0x140004372  mov     rbx, rcx
0x140004375  mov     [rbp+var_2C], 0
0x14000437c  mov     [rbp+var_1F], 0
0x140004380  mov     [rbp+var_1C], 0
0x140004387  xor     eax, eax
0x140004389  mov     [rbp+var_16], ax
0x14000438d  mov     eax, [rcx+8]
0x140004390  mov     [rbp+var_30], eax
0x140004393  mov     rax, [rcx+18h]
0x140004397  mov     [rbp+var_28], rax
0x14000439b  mov     al, [rcx]
0x14000439d  mov     [rbp+var_20], al
0x1400043a0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1400043a7  mov     [rbp+var_1E], ax
0x1400043ab  movzx   eax, word ptr [rcx+40h]
0x1400043af  mov     [rbp+var_18], ax
0x1400043b3  mov     [rbp+var_14], 0
0x1400043ba  mov     rax, [rcx+38h]
0x1400043be  mov     [rbp+var_10], rax
0x1400043c2  mov     rax, [rcx+80h]
0x1400043c9  mov     [rbp+var_8], rax
0x1400043cd  mov     [rbp+arg_0], 0
0x1400043d5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1400043dc  test    rdi, rdi
0x1400043df  jnz     short loc_140004425
0x1400043e1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1400043e8  test    rax, rax
0x1400043eb  jnz     short loc_140004406
0x1400043ed  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1400043f4  call    cs:__imp_GetModuleHandleW
0x1400043fa  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140004401  test    rax, rax
0x140004404  jz      short loc_140004419
0x140004406  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x14000440d  mov     rcx, rax; hModule
0x140004410  call    cs:__imp_GetProcAddress
0x140004416  mov     rdi, rax
0x140004419  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140004420  test    rdi, rdi
0x140004423  jz      short loc_140004438
0x140004425  lea     r8, [rbp+arg_0]
0x140004429  lea     rdx, [rbp+var_30]
0x14000442d  xor     ecx, ecx
0x14000442f  mov     rax, rdi
0x140004432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004437  nop
0x140004438  mov     eax, dword ptr [rbp+arg_0]
0x14000443b  mov     [rbx+10h], eax
0x14000443e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140004442  sub     ecx, 1
0x140004445  jz      short loc_14000445D
0x140004447  sub     ecx, 1
0x14000444a  jz      short loc_140004457
0x14000444c  cmp     ecx, 1
0x14000444f  jnz     short loc_140004461
0x140004451  or      dword ptr [rbx+4], 4
0x140004455  jmp     short loc_140004461
0x140004457  or      dword ptr [rbx+4], 2
0x14000445b  jmp     short loc_140004461
0x14000445d  or      dword ptr [rbx+4], 1
0x140004461  mov     rbx, [rsp+50h+arg_8]
0x140004466  mov     rdi, [rsp+50h+arg_10]
0x14000446b  add     rsp, 50h
0x14000446f  pop     rbp
0x140004470  retn
```
