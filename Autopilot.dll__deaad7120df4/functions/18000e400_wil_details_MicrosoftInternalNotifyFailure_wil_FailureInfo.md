# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x18000e400`
- end: `0x18000e51e`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `286`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e400`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e494`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e494`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4b6`

## string_xrefs

- `0x18000e48d`: `kernelbase.dll`

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
0x18000e400  mov     [rsp-8+arg_8], rbx
0x18000e405  mov     [rsp-8+arg_10], rdi
0x18000e40a  push    rbp
0x18000e40b  mov     rbp, rsp
0x18000e40e  sub     rsp, 50h
0x18000e412  mov     rbx, rcx
0x18000e415  mov     [rbp+var_2C], 0
0x18000e41c  mov     [rbp+var_1F], 0
0x18000e420  mov     [rbp+var_1C], 0
0x18000e427  xor     eax, eax
0x18000e429  mov     [rbp+var_16], ax
0x18000e42d  mov     eax, [rcx+8]
0x18000e430  mov     [rbp+var_30], eax
0x18000e433  mov     rax, [rcx+18h]
0x18000e437  mov     [rbp+var_28], rax
0x18000e43b  mov     al, [rcx]
0x18000e43d  mov     [rbp+var_20], al
0x18000e440  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x18000e447  mov     [rbp+var_1E], ax
0x18000e44b  movzx   eax, word ptr [rcx+40h]
0x18000e44f  mov     [rbp+var_18], ax
0x18000e453  mov     [rbp+var_14], 0
0x18000e45a  mov     rax, [rcx+38h]
0x18000e45e  mov     [rbp+var_10], rax
0x18000e462  mov     rax, [rcx+80h]
0x18000e469  mov     [rbp+var_8], rax
0x18000e46d  mov     [rbp+arg_0], 0
0x18000e475  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000e47c  test    rdi, rdi
0x18000e47f  jnz     short loc_18000E4D1
0x18000e481  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e488  test    rax, rax
0x18000e48b  jnz     short loc_18000E4AC
0x18000e48d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e494  call    cs:__imp_GetModuleHandleW
0x18000e49b  nop     dword ptr [rax+rax+00h]
0x18000e4a0  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x18000e4a7  test    rax, rax
0x18000e4aa  jz      short loc_18000E4C5
0x18000e4ac  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000e4b3  mov     rcx, rax; hModule
0x18000e4b6  call    cs:__imp_GetProcAddress
0x18000e4bd  nop     dword ptr [rax+rax+00h]
0x18000e4c2  mov     rdi, rax
0x18000e4c5  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x18000e4cc  test    rdi, rdi
0x18000e4cf  jz      short loc_18000E4E4
0x18000e4d1  lea     r8, [rbp+arg_0]
0x18000e4d5  lea     rdx, [rbp+var_30]
0x18000e4d9  xor     ecx, ecx
0x18000e4db  mov     rax, rdi
0x18000e4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e3  nop
0x18000e4e4  mov     eax, dword ptr [rbp+arg_0]
0x18000e4e7  mov     [rbx+10h], eax
0x18000e4ea  movzx   ecx, byte ptr [rbp+arg_0+4]
0x18000e4ee  sub     ecx, 1
0x18000e4f1  jz      short loc_18000E509
0x18000e4f3  sub     ecx, 1
0x18000e4f6  jz      short loc_18000E503
0x18000e4f8  cmp     ecx, 1
0x18000e4fb  jnz     short loc_18000E50D
0x18000e4fd  or      dword ptr [rbx+4], 4
0x18000e501  jmp     short loc_18000E50D
0x18000e503  or      dword ptr [rbx+4], 2
0x18000e507  jmp     short loc_18000E50D
0x18000e509  or      dword ptr [rbx+4], 1
0x18000e50d  mov     rbx, [rsp+50h+arg_8]
0x18000e512  mov     rdi, [rsp+50h+arg_10]
0x18000e517  add     rsp, 50h
0x18000e51b  pop     rbp
0x18000e51c  retn
```
