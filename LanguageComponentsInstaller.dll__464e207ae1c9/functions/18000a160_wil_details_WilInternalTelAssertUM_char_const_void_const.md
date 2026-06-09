# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000a160`
- end: `0x18000a21f`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `191`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003520`
- `0x18000a160`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a1f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1da`

## string_xrefs

- `0x18000a1d3`: `ntdll.dll`

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
0x18000a160  push    rbp
0x18000a162  mov     rbp, rsp
0x18000a165  sub     rsp, 60h
0x18000a169  mov     rax, cs:__security_cookie
0x18000a170  xor     rax, rsp
0x18000a173  mov     [rbp+var_8], rax
0x18000a177  xorps   xmm0, xmm0
0x18000a17a  xor     eax, eax
0x18000a17c  movups  [rbp+var_40], xmm0
0x18000a180  movups  [rbp+var_30], xmm0
0x18000a184  movups  [rbp+var_20], xmm0
0x18000a188  mov     [rbp+var_10], rax
0x18000a18c  mov     dword ptr [rbp+var_40], 0Bh
0x18000a193  lea     rax, __ImageBase
0x18000a19a  mov     qword ptr [rbp+var_40+8], rax
0x18000a19e  mov     qword ptr [rbp+var_30], rdx
0x18000a1a2  mov     byte ptr [rbp+var_30+8], 0
0x18000a1a6  mov     qword ptr [rbp+var_20], 0
0x18000a1ae  or      eax, 0FFFFFFFFh
0x18000a1b1  mov     dword ptr [rbp+var_20+8], eax
0x18000a1b4  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000a1b7  mov     byte ptr [rbp+var_10], 1
0x18000a1bb  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000a1c2  test    rax, rax
0x18000a1c5  jnz     short loc_18000A203
0x18000a1c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1ce  test    rax, rax
0x18000a1d1  jnz     short loc_18000A1E7
0x18000a1d3  lea     rcx, ModuleName; "ntdll.dll"
0x18000a1da  call    cs:__imp_GetModuleHandleW
0x18000a1e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1e7  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000a1ee  mov     rcx, rax; hModule
0x18000a1f1  call    cs:__imp_GetProcAddress
0x18000a1f7  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000a1fe  test    rax, rax
0x18000a201  jz      short loc_18000A20D
0x18000a203  lea     rcx, [rbp+var_40]
0x18000a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20c  nop
0x18000a20d  mov     rcx, [rbp+var_8]
0x18000a211  xor     rcx, rsp; StackCookie
0x18000a214  call    __security_check_cookie
0x18000a219  add     rsp, 60h
0x18000a21d  pop     rbp
0x18000a21e  retn
```
