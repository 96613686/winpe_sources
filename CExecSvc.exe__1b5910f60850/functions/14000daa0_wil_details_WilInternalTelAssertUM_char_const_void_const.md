# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x14000daa0`
- end: `0x14000db5f`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `191`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002310`
- `0x14000daa0`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000db31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000db31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000db1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000db1a`

## string_xrefs

- `0x14000db13`: `ntdll.dll`

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
0x14000daa0  push    rbp
0x14000daa2  mov     rbp, rsp
0x14000daa5  sub     rsp, 60h
0x14000daa9  mov     rax, cs:__security_cookie
0x14000dab0  xor     rax, rsp
0x14000dab3  mov     [rbp+var_8], rax
0x14000dab7  xorps   xmm0, xmm0
0x14000daba  xor     eax, eax
0x14000dabc  movups  [rbp+var_40], xmm0
0x14000dac0  movups  [rbp+var_30], xmm0
0x14000dac4  movups  [rbp+var_20], xmm0
0x14000dac8  mov     [rbp+var_10], rax
0x14000dacc  mov     dword ptr [rbp+var_40], 0Bh
0x14000dad3  lea     rax, __ImageBase
0x14000dada  mov     qword ptr [rbp+var_40+8], rax
0x14000dade  mov     qword ptr [rbp+var_30], rdx
0x14000dae2  mov     byte ptr [rbp+var_30+8], 0
0x14000dae6  mov     qword ptr [rbp+var_20], 0
0x14000daee  or      eax, 0FFFFFFFFh
0x14000daf1  mov     dword ptr [rbp+var_20+8], eax
0x14000daf4  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000daf7  mov     byte ptr [rbp+var_10], 1
0x14000dafb  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000db02  test    rax, rax
0x14000db05  jnz     short loc_14000DB43
0x14000db07  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000db0e  test    rax, rax
0x14000db11  jnz     short loc_14000DB27
0x14000db13  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000db1a  call    cs:__imp_GetModuleHandleW
0x14000db20  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000db27  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000db2e  mov     rcx, rax; hModule
0x14000db31  call    cs:__imp_GetProcAddress
0x14000db37  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000db3e  test    rax, rax
0x14000db41  jz      short loc_14000DB4D
0x14000db43  lea     rcx, [rbp+var_40]
0x14000db47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db4c  nop
0x14000db4d  mov     rcx, [rbp+var_8]
0x14000db51  xor     rcx, rsp; StackCookie
0x14000db54  call    __security_check_cookie
0x14000db59  add     rsp, 60h
0x14000db5d  pop     rbp
0x14000db5e  retn
```
