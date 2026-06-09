# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18002f9b0`
- end: `0x18002fa55`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002f9b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fa33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fa1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fa1c`

## string_xrefs

- `0x18002fa15`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18002f9b0  push    rbp
0x18002f9b2  mov     rbp, rsp
0x18002f9b5  sub     rsp, 60h
0x18002f9b9  xorps   xmm0, xmm0
0x18002f9bc  xor     eax, eax
0x18002f9be  movups  [rbp+var_40], xmm0
0x18002f9c2  movups  [rbp+var_30], xmm0
0x18002f9c6  movups  [rbp+var_20], xmm0
0x18002f9ca  mov     [rbp+var_10], rax
0x18002f9ce  mov     dword ptr [rbp+var_40], 0Bh
0x18002f9d5  lea     rax, cs:180000000h
0x18002f9dc  mov     qword ptr [rbp+var_40+8], rax
0x18002f9e0  mov     qword ptr [rbp+var_30], rdx
0x18002f9e4  mov     byte ptr [rbp+var_30+8], 0
0x18002f9e8  mov     qword ptr [rbp+var_20], 0
0x18002f9f0  or      eax, 0FFFFFFFFh
0x18002f9f3  mov     dword ptr [rbp+var_20+8], eax
0x18002f9f6  mov     dword ptr [rbp+var_20+0Ch], eax
0x18002f9f9  mov     byte ptr [rbp+var_10], 1
0x18002f9fd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18002fa04  test    rax, rax
0x18002fa07  jnz     short loc_18002FA45
0x18002fa09  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fa10  test    rax, rax
0x18002fa13  jnz     short loc_18002FA29
0x18002fa15  lea     rcx, ModuleName; "ntdll.dll"
0x18002fa1c  call    cs:__imp_GetModuleHandleW
0x18002fa22  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002fa29  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18002fa30  mov     rcx, rax; hModule
0x18002fa33  call    cs:__imp_GetProcAddress
0x18002fa39  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18002fa40  test    rax, rax
0x18002fa43  jz      short loc_18002FA4F
0x18002fa45  lea     rcx, [rbp+var_40]
0x18002fa49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa4e  nop
0x18002fa4f  add     rsp, 60h
0x18002fa53  pop     rbp
0x18002fa54  retn
```
