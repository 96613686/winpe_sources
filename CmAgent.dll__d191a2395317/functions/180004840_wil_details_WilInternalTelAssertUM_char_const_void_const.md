# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180004840`
- end: `0x1800048f2`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004840`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800048ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800048c9`

## string_xrefs

- `0x1800048a5`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-20h]
  __int64 v8; // [rsp+48h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 1;
  v5[0] = 11;
  v5[1] = &_ImageBase;
  v6 = (unsigned __int64)a2;
  v7 = 0;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "MicrosoftTelemetryAssertTriggeredUM");
  `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(_QWORD *, const char *, const void *))ProcAddress)(v5, a2, a3);
}

```

## disassembly

```asm
0x180004840  push    rbp
0x180004842  mov     rbp, rsp
0x180004845  sub     rsp, 60h
0x180004849  xorps   xmm0, xmm0
0x18000484c  xor     eax, eax
0x18000484e  movups  [rbp+var_40], xmm0
0x180004852  movups  [rbp+var_30], xmm0
0x180004856  movups  [rbp+var_20], xmm0
0x18000485a  mov     [rbp+var_10], rax
0x18000485e  mov     dword ptr [rbp+var_40], 0Bh
0x180004865  lea     rax, __ImageBase
0x18000486c  mov     qword ptr [rbp+var_40+8], rax
0x180004870  mov     qword ptr [rbp+var_30], rdx
0x180004874  mov     byte ptr [rbp+var_30+8], 0
0x180004878  mov     qword ptr [rbp+var_20], 0
0x180004880  or      eax, 0FFFFFFFFh
0x180004883  mov     dword ptr [rbp+var_20+8], eax
0x180004886  mov     dword ptr [rbp+var_20+0Ch], eax
0x180004889  mov     byte ptr [rbp+var_10], 1
0x18000488d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180004894  test    rax, rax
0x180004897  jnz     short loc_1800048E1
0x180004899  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800048a0  test    rax, rax
0x1800048a3  jnz     short loc_1800048BF
0x1800048a5  lea     rcx, ModuleName; "ntdll.dll"
0x1800048ac  call    cs:__imp_GetModuleHandleW
0x1800048b3  nop     dword ptr [rax+rax+00h]
0x1800048b8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800048bf  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800048c6  mov     rcx, rax; hModule
0x1800048c9  call    cs:__imp_GetProcAddress
0x1800048d0  nop     dword ptr [rax+rax+00h]
0x1800048d5  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800048dc  test    rax, rax
0x1800048df  jz      short loc_1800048EB
0x1800048e1  lea     rcx, [rbp+var_40]
0x1800048e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ea  nop
0x1800048eb  add     rsp, 60h
0x1800048ef  pop     rbp
0x1800048f0  retn
```
