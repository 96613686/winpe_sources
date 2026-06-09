# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000a5a0`
- end: `0x18000a645`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a60c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a60c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a623`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a623`

## string_xrefs

- `0x18000a605`: `ntdll.dll`

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
  v5[1] = 0x180000000uLL;
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
0x18000a5a0  push    rbp
0x18000a5a2  mov     rbp, rsp
0x18000a5a5  sub     rsp, 60h
0x18000a5a9  xorps   xmm0, xmm0
0x18000a5ac  xor     eax, eax
0x18000a5ae  movups  [rbp+var_40], xmm0
0x18000a5b2  movups  [rbp+var_30], xmm0
0x18000a5b6  movups  [rbp+var_20], xmm0
0x18000a5ba  mov     [rbp+var_10], rax
0x18000a5be  mov     dword ptr [rbp+var_40], 0Bh
0x18000a5c5  lea     rax, cs:180000000h
0x18000a5cc  mov     qword ptr [rbp+var_40+8], rax
0x18000a5d0  mov     qword ptr [rbp+var_30], rdx
0x18000a5d4  mov     byte ptr [rbp+var_30+8], 0
0x18000a5d8  mov     qword ptr [rbp+var_20], 0
0x18000a5e0  or      eax, 0FFFFFFFFh
0x18000a5e3  mov     dword ptr [rbp+var_20+8], eax
0x18000a5e6  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000a5e9  mov     byte ptr [rbp+var_10], 1
0x18000a5ed  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000a5f4  test    rax, rax
0x18000a5f7  jnz     short loc_18000A635
0x18000a5f9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a600  test    rax, rax
0x18000a603  jnz     short loc_18000A619
0x18000a605  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a60c  call    cs:__imp_GetModuleHandleW
0x18000a612  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a619  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000a620  mov     rcx, rax; hModule
0x18000a623  call    cs:__imp_GetProcAddress
0x18000a629  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000a630  test    rax, rax
0x18000a633  jz      short loc_18000A63F
0x18000a635  lea     rcx, [rbp+var_40]
0x18000a639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a63e  nop
0x18000a63f  add     rsp, 60h
0x18000a643  pop     rbp
0x18000a644  retn
```
