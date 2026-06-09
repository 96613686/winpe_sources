# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x140009310`
- end: `0x1400093b5`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009310`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000937c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000937c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009393`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009393`

## string_xrefs

- `0x140009375`: `ntdll.dll`

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
  v5[1] = 0x140000000uLL;
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
0x140009310  push    rbp
0x140009312  mov     rbp, rsp
0x140009315  sub     rsp, 60h
0x140009319  xorps   xmm0, xmm0
0x14000931c  xor     eax, eax
0x14000931e  movups  [rbp+var_40], xmm0
0x140009322  movups  [rbp+var_30], xmm0
0x140009326  movups  [rbp+var_20], xmm0
0x14000932a  mov     [rbp+var_10], rax
0x14000932e  mov     dword ptr [rbp+var_40], 0Bh
0x140009335  lea     rax, cs:140000000h
0x14000933c  mov     qword ptr [rbp+var_40+8], rax
0x140009340  mov     qword ptr [rbp+var_30], rdx
0x140009344  mov     byte ptr [rbp+var_30+8], 0
0x140009348  mov     qword ptr [rbp+var_20], 0
0x140009350  or      eax, 0FFFFFFFFh
0x140009353  mov     dword ptr [rbp+var_20+8], eax
0x140009356  mov     dword ptr [rbp+var_20+0Ch], eax
0x140009359  mov     byte ptr [rbp+var_10], 1
0x14000935d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x140009364  test    rax, rax
0x140009367  jnz     short loc_1400093A5
0x140009369  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009370  test    rax, rax
0x140009373  jnz     short loc_140009389
0x140009375  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000937c  call    cs:__imp_GetModuleHandleW
0x140009382  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009389  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140009390  mov     rcx, rax; hModule
0x140009393  call    cs:__imp_GetProcAddress
0x140009399  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1400093a0  test    rax, rax
0x1400093a3  jz      short loc_1400093AF
0x1400093a5  lea     rcx, [rbp+var_40]
0x1400093a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093ae  nop
0x1400093af  add     rsp, 60h
0x1400093b3  pop     rbp
0x1400093b4  retn
```
