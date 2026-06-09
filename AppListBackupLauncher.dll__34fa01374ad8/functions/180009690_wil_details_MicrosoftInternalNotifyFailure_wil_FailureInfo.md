# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x180009690`
- end: `0x1800097a1`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `273`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009690`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009740`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009740`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009724`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009724`

## string_xrefs

- `0x18000971d`: `kernelbase.dll`

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
0x180009690  mov     [rsp-8+arg_8], rbx
0x180009695  mov     [rsp-8+arg_10], rdi
0x18000969a  push    rbp
0x18000969b  mov     rbp, rsp
0x18000969e  sub     rsp, 50h
0x1800096a2  mov     rbx, rcx
0x1800096a5  mov     [rbp+var_2C], 0
0x1800096ac  mov     [rbp+var_1F], 0
0x1800096b0  mov     [rbp+var_1C], 0
0x1800096b7  xor     eax, eax
0x1800096b9  mov     [rbp+var_16], ax
0x1800096bd  mov     eax, [rcx+8]
0x1800096c0  mov     [rbp+var_30], eax
0x1800096c3  mov     rax, [rcx+18h]
0x1800096c7  mov     [rbp+var_28], rax
0x1800096cb  mov     al, [rcx]
0x1800096cd  mov     [rbp+var_20], al
0x1800096d0  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x1800096d7  mov     [rbp+var_1E], ax
0x1800096db  movzx   eax, word ptr [rcx+40h]
0x1800096df  mov     [rbp+var_18], ax
0x1800096e3  mov     [rbp+var_14], 0
0x1800096ea  mov     rax, [rcx+38h]
0x1800096ee  mov     [rbp+var_10], rax
0x1800096f2  mov     rax, [rcx+80h]
0x1800096f9  mov     [rbp+var_8], rax
0x1800096fd  mov     [rbp+arg_0], 0
0x180009705  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x18000970c  test    rdi, rdi
0x18000970f  jnz     short loc_180009755
0x180009711  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009718  test    rax, rax
0x18000971b  jnz     short loc_180009736
0x18000971d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180009724  call    cs:__imp_GetModuleHandleW
0x18000972a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x180009731  test    rax, rax
0x180009734  jz      short loc_180009749
0x180009736  lea     rdx, aWilfailurenoti; "WilFailureNotifyWatchers"
0x18000973d  mov     rcx, rax; hModule
0x180009740  call    cs:__imp_GetProcAddress
0x180009746  mov     rdi, rax
0x180009749  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x180009750  test    rdi, rdi
0x180009753  jz      short loc_180009768
0x180009755  lea     r8, [rbp+arg_0]
0x180009759  lea     rdx, [rbp+var_30]
0x18000975d  xor     ecx, ecx
0x18000975f  mov     rax, rdi
0x180009762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009767  nop
0x180009768  mov     eax, dword ptr [rbp+arg_0]
0x18000976b  mov     [rbx+10h], eax
0x18000976e  movzx   ecx, byte ptr [rbp+arg_0+4]
0x180009772  sub     ecx, 1
0x180009775  jz      short loc_18000978D
0x180009777  sub     ecx, 1
0x18000977a  jz      short loc_180009787
0x18000977c  cmp     ecx, 1
0x18000977f  jnz     short loc_180009791
0x180009781  or      dword ptr [rbx+4], 4
0x180009785  jmp     short loc_180009791
0x180009787  or      dword ptr [rbx+4], 2
0x18000978b  jmp     short loc_180009791
0x18000978d  or      dword ptr [rbx+4], 1
0x180009791  mov     rbx, [rsp+50h+arg_8]
0x180009796  mov     rdi, [rsp+50h+arg_10]
0x18000979b  add     rsp, 50h
0x18000979f  pop     rbp
0x1800097a0  retn
```
