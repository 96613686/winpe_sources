# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180007310`
- end: `0x1800073b4`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `164`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007310`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007393`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007393`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000737c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000737c`

## string_xrefs

- `0x180007375`: `ntdll.dll`

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
  v7 = 0;
  v5[1] = 0x180000000uLL;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  v5[0] = 11;
  v6 = (unsigned __int64)a2;
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
0x180007310  push    rbp
0x180007312  mov     rbp, rsp
0x180007315  sub     rsp, 60h
0x180007319  xor     eax, eax
0x18000731b  xorps   xmm0, xmm0
0x18000731e  mov     [rbp+var_10], rax
0x180007322  lea     rax, cs:180000000h
0x180007329  movups  [rbp+var_20], xmm0
0x18000732d  mov     qword ptr [rbp+var_20], 0
0x180007335  movups  [rbp+var_40], xmm0
0x180007339  mov     qword ptr [rbp+var_40+8], rax
0x18000733d  or      eax, 0FFFFFFFFh
0x180007340  movups  [rbp+var_30], xmm0
0x180007344  mov     dword ptr [rbp+var_20+8], eax
0x180007347  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000734a  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007351  mov     dword ptr [rbp+var_40], 0Bh
0x180007358  mov     qword ptr [rbp+var_30], rdx
0x18000735c  mov     byte ptr [rbp+var_30+8], 0
0x180007360  mov     byte ptr [rbp+var_10], 1
0x180007364  test    rax, rax
0x180007367  jnz     short loc_1800073A5
0x180007369  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007370  test    rax, rax
0x180007373  jnz     short loc_180007389
0x180007375  lea     rcx, ModuleName; "ntdll.dll"
0x18000737c  call    cs:__imp_GetModuleHandleW
0x180007382  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007389  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180007390  mov     rcx, rax; hModule
0x180007393  call    cs:__imp_GetProcAddress
0x180007399  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800073a0  test    rax, rax
0x1800073a3  jz      short loc_1800073AE
0x1800073a5  lea     rcx, [rbp+var_40]
0x1800073a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ae  add     rsp, 60h
0x1800073b2  pop     rbp
0x1800073b3  retn
```
