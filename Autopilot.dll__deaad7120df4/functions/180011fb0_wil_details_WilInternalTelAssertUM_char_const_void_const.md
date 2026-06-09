# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180011fb0`
- end: `0x180012062`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011fb0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001201c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001201c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012039`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012039`

## string_xrefs

- `0x180012015`: `ntdll.dll`

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
0x180011fb0  push    rbp
0x180011fb2  mov     rbp, rsp
0x180011fb5  sub     rsp, 60h
0x180011fb9  xorps   xmm0, xmm0
0x180011fbc  xor     eax, eax
0x180011fbe  movups  [rbp+var_40], xmm0
0x180011fc2  movups  [rbp+var_30], xmm0
0x180011fc6  movups  [rbp+var_20], xmm0
0x180011fca  mov     [rbp+var_10], rax
0x180011fce  mov     dword ptr [rbp+var_40], 0Bh
0x180011fd5  lea     rax, __ImageBase
0x180011fdc  mov     qword ptr [rbp+var_40+8], rax
0x180011fe0  mov     qword ptr [rbp+var_30], rdx
0x180011fe4  mov     byte ptr [rbp+var_30+8], 0
0x180011fe8  mov     qword ptr [rbp+var_20], 0
0x180011ff0  or      eax, 0FFFFFFFFh
0x180011ff3  mov     dword ptr [rbp+var_20+8], eax
0x180011ff6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180011ff9  mov     byte ptr [rbp+var_10], 1
0x180011ffd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180012004  test    rax, rax
0x180012007  jnz     short loc_180012051
0x180012009  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012010  test    rax, rax
0x180012013  jnz     short loc_18001202F
0x180012015  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001201c  call    cs:__imp_GetModuleHandleW
0x180012023  nop     dword ptr [rax+rax+00h]
0x180012028  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001202f  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180012036  mov     rcx, rax; hModule
0x180012039  call    cs:__imp_GetProcAddress
0x180012040  nop     dword ptr [rax+rax+00h]
0x180012045  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18001204c  test    rax, rax
0x18001204f  jz      short loc_18001205B
0x180012051  lea     rcx, [rbp+var_40]
0x180012055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001205a  nop
0x18001205b  add     rsp, 60h
0x18001205f  pop     rbp
0x180012060  retn
```
