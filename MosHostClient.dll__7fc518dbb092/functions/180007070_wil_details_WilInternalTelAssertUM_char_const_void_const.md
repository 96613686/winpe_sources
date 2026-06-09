# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180007070`
- end: `0x180007115`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007070`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800070f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070dc`

## string_xrefs

- `0x1800070d5`: `ntdll.dll`

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
0x180007070  push    rbp
0x180007072  mov     rbp, rsp
0x180007075  sub     rsp, 60h
0x180007079  xorps   xmm0, xmm0
0x18000707c  xor     eax, eax
0x18000707e  movups  [rbp+var_40], xmm0
0x180007082  movups  [rbp+var_30], xmm0
0x180007086  movups  [rbp+var_20], xmm0
0x18000708a  mov     [rbp+var_10], rax
0x18000708e  mov     dword ptr [rbp+var_40], 0Bh
0x180007095  lea     rax, __ImageBase
0x18000709c  mov     qword ptr [rbp+var_40+8], rax
0x1800070a0  mov     qword ptr [rbp+var_30], rdx
0x1800070a4  mov     byte ptr [rbp+var_30+8], 0
0x1800070a8  mov     qword ptr [rbp+var_20], 0
0x1800070b0  or      eax, 0FFFFFFFFh
0x1800070b3  mov     dword ptr [rbp+var_20+8], eax
0x1800070b6  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800070b9  mov     byte ptr [rbp+var_10], 1
0x1800070bd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800070c4  test    rax, rax
0x1800070c7  jnz     short loc_180007105
0x1800070c9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070d0  test    rax, rax
0x1800070d3  jnz     short loc_1800070E9
0x1800070d5  lea     rcx, ModuleName; "ntdll.dll"
0x1800070dc  call    cs:__imp_GetModuleHandleW
0x1800070e2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070e9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800070f0  mov     rcx, rax; hModule
0x1800070f3  call    cs:__imp_GetProcAddress
0x1800070f9  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007100  test    rax, rax
0x180007103  jz      short loc_18000710F
0x180007105  lea     rcx, [rbp+var_40]
0x180007109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000710e  nop
0x18000710f  add     rsp, 60h
0x180007113  pop     rbp
0x180007114  retn
```
