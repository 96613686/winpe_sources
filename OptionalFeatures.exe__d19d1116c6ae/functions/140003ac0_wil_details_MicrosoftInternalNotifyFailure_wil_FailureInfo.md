# wil::details::MicrosoftInternalNotifyFailure(wil::FailureInfo *)

- ea: `0x140003ac0`
- end: `0x140003bd0`
- name: `?MicrosoftInternalNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@@Z`
- size: `272`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003ac0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140003b70`
- `KERNEL32!GetProcAddress` at `0x140003b70`
- `KERNEL32!GetModuleHandleW` at `0x140003b54`
- `KERNEL32!GetModuleHandleW` at `0x140003b54`

## string_xrefs

- `0x140003b4d`: `kernelbase.dll`

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
0x140003ac0  mov     [rsp-8+arg_8], rbx
0x140003ac5  mov     [rsp-8+arg_10], rdi
0x140003aca  push    rbp
0x140003acb  mov     rbp, rsp
0x140003ace  sub     rsp, 50h
0x140003ad2  mov     rdi, cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA
0x140003ad9  xor     eax, eax
0x140003adb  mov     [rbp+var_16], ax
0x140003adf  mov     rbx, rcx
0x140003ae2  mov     eax, [rcx+8]
0x140003ae5  mov     [rbp+var_30], eax
0x140003ae8  mov     rax, [rcx+18h]
0x140003aec  mov     [rbp+var_28], rax
0x140003af0  mov     al, [rcx]
0x140003af2  mov     [rbp+var_20], al
0x140003af5  movzx   eax, cs:?g_moduleFailureReportFlags@wil@@3W4WilFailureReportFlags@@A; WilFailureReportFlags wil::g_moduleFailureReportFlags
0x140003afc  mov     [rbp+var_1E], ax
0x140003b00  movzx   eax, word ptr [rcx+40h]
0x140003b04  mov     [rbp+var_18], ax
0x140003b08  mov     rax, [rcx+38h]
0x140003b0c  mov     [rbp+var_10], rax
0x140003b10  mov     rax, [rcx+80h]
0x140003b17  mov     [rbp+var_8], rax
0x140003b1b  mov     [rbp+var_2C], 0
0x140003b22  mov     [rbp+var_1F], 0
0x140003b26  mov     [rbp+var_1C], 0
0x140003b2d  mov     [rbp+var_14], 0
0x140003b34  mov     [rbp+arg_0], 0
0x140003b3c  test    rdi, rdi
0x140003b3f  jnz     short loc_140003B85
0x140003b41  mov     rax, cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140003b48  test    rax, rax
0x140003b4b  jnz     short loc_140003B66
0x140003b4d  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140003b54  call    cs:__imp_GetModuleHandleW
0x140003b5a  mov     cs:?wil_details_kernelbaseModuleHandle@?1??wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z@4PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * `wil_details_GetKernelBaseProcAddress(char const *)'::`2'::wil_details_kernelbaseModuleHandle
0x140003b61  test    rax, rax
0x140003b64  jz      short loc_140003B79
0x140003b66  lea     rdx, ProcName; "WilFailureNotifyWatchers"
0x140003b6d  mov     rcx, rax; hModule
0x140003b70  call    cs:__imp_GetProcAddress
0x140003b76  mov     rdi, rax
0x140003b79  mov     cs:?s_pfnFailureNotifyWatchers@?1??WilFailureNotifyWatchers@details@wil@@YAXIPEBUWilFailureReport@@PEAUWilFailureReportInformation@@@Z@4P6AXI01@_EEA, rdi
0x140003b80  test    rdi, rdi
0x140003b83  jz      short loc_140003B97
0x140003b85  lea     r8, [rbp+arg_0]
0x140003b89  xor     ecx, ecx
0x140003b8b  lea     rdx, [rbp+var_30]
0x140003b8f  mov     rax, rdi
0x140003b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b97  movzx   ecx, byte ptr [rbp+arg_0+4]
0x140003b9b  mov     eax, dword ptr [rbp+arg_0]
0x140003b9e  mov     [rbx+10h], eax
0x140003ba1  sub     ecx, 1
0x140003ba4  jz      short loc_140003BBC
0x140003ba6  sub     ecx, 1
0x140003ba9  jz      short loc_140003BB6
0x140003bab  cmp     ecx, 1
0x140003bae  jnz     short loc_140003BC0
0x140003bb0  or      dword ptr [rbx+4], 4
0x140003bb4  jmp     short loc_140003BC0
0x140003bb6  or      dword ptr [rbx+4], 2
0x140003bba  jmp     short loc_140003BC0
0x140003bbc  or      dword ptr [rbx+4], 1
0x140003bc0  mov     rbx, [rsp+50h+arg_8]
0x140003bc5  mov     rdi, [rsp+50h+arg_10]
0x140003bca  add     rsp, 50h
0x140003bce  pop     rbp
0x140003bcf  retn
```
