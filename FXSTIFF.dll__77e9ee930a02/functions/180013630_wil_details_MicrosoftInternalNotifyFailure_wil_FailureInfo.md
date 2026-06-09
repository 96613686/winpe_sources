# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180013630`
- end: `0x18001374e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013630`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800136c4`
- `KERNEL32!GetModuleHandleW` at `0x1800136c4`
- `KERNEL32!GetProcAddress` at `0x1800136e6`
- `KERNEL32!GetProcAddress` at `0x1800136e6`

## string_xrefs

- `0x1800136bd`: `kernelbase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180013630  mov     [rsp-8+arg_8], rbx
0x180013635  mov     [rsp-8+arg_10], rdi
0x18001363a  push    rbp
0x18001363b  mov     rbp, rsp
0x18001363e  sub     rsp, 50h
0x180013642  mov     rbx, rcx
0x180013645  mov     [rbp+var_2C], 0
0x18001364c  mov     [rbp+var_1F], 0
0x180013650  mov     [rbp+var_1C], 0
0x180013657  xor     eax, eax
0x180013659  mov     [rbp+var_16], ax
0x18001365d  mov     eax, [rcx+8]
0x180013660  mov     [rbp+var_30], eax
0x180013663  mov     rax, [rcx+18h]
0x180013667  mov     [rbp+var_28], rax
0x18001366b  mov     al, [rcx]
0x18001366d  mov     [rbp+var_20], al
0x180013670  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x180013677  mov     [rbp+var_1E], ax
0x18001367b  movzx   eax, word ptr [rcx+40h]
0x18001367f  mov     [rbp+var_18], ax
0x180013683  mov     [rbp+var_14], 0
0x18001368a  mov     rax, [rcx+38h]
0x18001368e  mov     [rbp+var_10], rax
0x180013692  mov     rax, [rcx+80h]
0x180013699  mov     [rbp+var_8], rax
0x18001369d  mov     [rbp+arg_0], 0
0x1800136a5  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x1800136ac  test    rdi, rdi
0x1800136af  jnz     short loc_180013701
0x1800136b1  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800136b8  test    rax, rax
0x1800136bb  jnz     short loc_1800136DC
0x1800136bd  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800136c4  call    cs:__imp_GetModuleHandleW
0x1800136cb  nop     dword ptr [rax+rax+00h]
0x1800136d0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x1800136d7  test    rax, rax
0x1800136da  jz      short loc_1800136F5
0x1800136dc  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x1800136e3  mov     rcx, rax; hModule
0x1800136e6  call    cs:__imp_GetProcAddress
0x1800136ed  nop     dword ptr [rax+rax+00h]
0x1800136f2  mov     rdi, rax
0x1800136f5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x1800136fc  test    rdi, rdi
0x1800136ff  jz      short loc_180013714
0x180013701  lea     r8, [rbp+arg_0]
0x180013705  lea     rdx, [rbp+var_30]
0x180013709  xor     ecx, ecx
0x18001370b  mov     rax, rdi
0x18001370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013713  nop
0x180013714  mov     eax, dword ptr [rbp+arg_0]
0x180013717  mov     [rbx+10h], eax
0x18001371a  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18001371e  sub     ecx, 1
0x180013721  jz      short loc_180013739
0x180013723  sub     ecx, 1
0x180013726  jz      short loc_180013733
0x180013728  cmp     ecx, 1
0x18001372b  jnz     short loc_18001373D
0x18001372d  or      dword ptr [rbx+4], 4
0x180013731  jmp     short loc_18001373D
0x180013733  or      dword ptr [rbx+4], 2
0x180013737  jmp     short loc_18001373D
0x180013739  or      dword ptr [rbx+4], 1
0x18001373d  mov     rbx, [rsp+50h+arg_8]
0x180013742  mov     rdi, [rsp+50h+arg_10]
0x180013747  add     rsp, 50h
0x18001374b  pop     rbp
0x18001374c  retn
```
