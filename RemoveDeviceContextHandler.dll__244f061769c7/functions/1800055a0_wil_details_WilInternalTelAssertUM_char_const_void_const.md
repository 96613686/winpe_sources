# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x1800055a0`
- end: `0x180005644`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `164`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800055a0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005623`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005623`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000560c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000560c`

## string_xrefs

- `0x180005605`: `ntdll.dll`

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
  v5[1] = &_ImageBase;
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
0x1800055a0  push    rbp
0x1800055a2  mov     rbp, rsp
0x1800055a5  sub     rsp, 60h
0x1800055a9  xor     eax, eax
0x1800055ab  xorps   xmm0, xmm0
0x1800055ae  mov     [rbp+var_10], rax
0x1800055b2  lea     rax, __ImageBase
0x1800055b9  movups  [rbp+var_20], xmm0
0x1800055bd  mov     qword ptr [rbp+var_20], 0
0x1800055c5  movups  [rbp+var_40], xmm0
0x1800055c9  mov     qword ptr [rbp+var_40+8], rax
0x1800055cd  or      eax, 0FFFFFFFFh
0x1800055d0  movups  [rbp+var_30], xmm0
0x1800055d4  mov     dword ptr [rbp+var_20+8], eax
0x1800055d7  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800055da  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800055e1  mov     dword ptr [rbp+var_40], 0Bh
0x1800055e8  mov     qword ptr [rbp+var_30], rdx
0x1800055ec  mov     byte ptr [rbp+var_30+8], 0
0x1800055f0  mov     byte ptr [rbp+var_10], 1
0x1800055f4  test    rax, rax
0x1800055f7  jnz     short loc_180005635
0x1800055f9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005600  test    rax, rax
0x180005603  jnz     short loc_180005619
0x180005605  lea     rcx, ModuleName; "ntdll.dll"
0x18000560c  call    cs:__imp_GetModuleHandleW
0x180005612  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005619  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180005620  mov     rcx, rax; hModule
0x180005623  call    cs:__imp_GetProcAddress
0x180005629  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180005630  test    rax, rax
0x180005633  jz      short loc_18000563E
0x180005635  lea     rcx, [rbp+var_40]
0x180005639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000563e  add     rsp, 60h
0x180005642  pop     rbp
0x180005643  retn
```
